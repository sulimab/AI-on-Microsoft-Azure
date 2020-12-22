To repozytorium zawiera bota stworzonego prze Bot Framework Composer. 


## Projekt - Bot dla Wykładowcy

Bot pozwala w pewnym stopniu zautomatyzować kontakt z wykładowcą w zakresie organizacji konsultacji oraz współpracy przy pracy dyplomowej. Pisany był z myślą o wydziale elektrycznym, mimo iż na tym wydziale większość zawartych w bocie funkcjonalności można zrealizować korzystając z systemu ISOD. Projekt ten realizuje tylko częśc konwersacyjną, nie zawiera w sobie integracji z systemem ISOD.

### Przypadki użycia

Użytkownik korzystając z bota może zrealizować poniższe przypadki użycia
1. Uzyskać informację o aktualnie realizowanych przedmiotach przez prowadzącego, który udostepnia takowego Bota - aktualnie sugestia, aby sprawdzić te informacje w systemie ISOD.
1. Uzyskać informację o egzaminach realizowanych z przedmiotów prowadzonych przez danego prowadzącego - aktualnie sugestia, aby sprawdzić te informacje w systemie ISOD.
1. Uzyskać informację o tym gdzie umówić się na konsultacje - informacja o tym, że funkcjonalnośc tę ralizuje system ISOD.
1. Uzyskać informacje o pracy dyplomowej 
	* Pierwszy przypadek skierowany do użykownika, który jest aktualnym dyplomantem danego prowadzącego, w takim przypadku kierowany jest na konsultacje
	* Kolejny przypadek to sytuacja gdy użytkownik, nie jest aktualnie dyplomantem, ale chciałyby nim zostać i ma już pomysł na własny temat pracy, w takim przypadku bot prosi o krótki opis, tytuł oraz dane studenta i przygotowuje dla niego treśc maila do wysłania do prowadzącego.
	* Ostatni przypadek to sytuacja gdy użytkownik nie jest aktualnym dyplomantem, chciałby nim zostać, ale nie posiada włąsnego tematu. W takim przypadku może zobaczyć dotychczas obronione prace oraz proponowane w celu inspiracji i wybrania własnego tematu. Może także przejść do konsultacji. 



### Architektura

Bot składa się z głownego dialogu, nazwanego WykladowcaBot oraz 7 innych dialogów, które zostaną omówione w dalszej części tego dokumentu.

# WykladowcaBot
WykladowcaBot to główny dialog bota. Wewnątrz odbywa się przywitanie, oraz pobranie od użytkonika informacji o imieniu, a następnie przekazanie kontroli do dialogu start_dialog, w którym użytkownikowi przedstawiane są możliwości. Oprócz głownego Triggera Greeting znajduje się w nim jeszcze 8 innych: 
* praca_dyplomowa - trigger kieruje do dialogu praca_dyplomowa_dialog
* konsultacje - trigger kieruje do dialogu konsultacje_dialog
* obronione_tematy - trigger kieruje do dialogu obronione_tematy_dialog
* lista - trigger kieruje do dialogu lista_tematow_dialog
* propozycja_tematu - trigger kieruje do dialogu nowa_praca_dyplomowa_zapytanie_dialog
* STOP - trigger służy do wyłączenia wszystkich
* zajecia - trigger zwraca informacje o zajęciach które prowadzi wykładowca
* egzaminy - trigger informuje, gdzie można znaleźć informacje o zaliczeniach i egzaminach

# konsultacje_dialog
Dialog w którym zawarta jest informacja o tym, że umawianie na konsultacje realizowane jest przez system ISOD. 

# lista_tematow_dialog
Dialog w którym uzupełniana jest (aktualnie sztucznie) lista dostępnych tematów prac dyplomowych, która następnie jest zwracana użytkownikowi korzystając z pętli for-each. Po wyświetleniu listy pojawia się możliwość zobaczenia już obronionych tematów (obronione_tematy_dialog), a także przejścia do dialogu konsultacji (konsultacje_dialog) oraz ustalania tematu pracy (nowa_praca_dyplomowa_zapytanie_dialog).

# nowa_praca_dyplomowa_brak_tematu_dialog
Dialog, który wyświetla się osobom, które nie są aktualnymi dyplomantami oraz nie mają swojeog własnego pomysłu na temat. Pozwala przejść do listy dostepnych tematów (lista_tematow_dialog) lub obronionych prac (obronione_tematy_dialog), aby zainspirować studenta do znalezienia własnego tematu.

# nowa_praca_dyplomowa_zapytanie_dialog
Dialog wyświetla się studentowi, który ma pomysł na swój własny temat. Użytkownik jest proszony o tytuł i krótki opis pracy, a także numer indeksu. Na tej podstawie przygotowywana jest treść maila, którą student musi samodzielnie wysłać prowadzącemu.

# obronione_tematy_dialog
Dialog wyświetlający listę obronionych tematów prac, skierowany do osób nie będących aktualnymi dyplomantami. Aktualnie lista tematów uzupełniana jest sztucznie wewnątrz dialogu. Po wyświetleniu listy pojawia się możliwość zobaczenia proponowanych tematów (lista_tematow_dialog), a także przejścia do dialogu konsultacji (konsultacje_dialog) oraz ustalania tematu pracy (nowa_praca_dyplomowa_zapytanie_dialog).

# praca_dyplomowa_dialog
Dialog uruchamiany przez zapytanie "PRACA DYPLOMOWA", który korzystając z funkcji switch sprawdza, do którego dialogu powinien przekierować użytkownika, zainteresowanego tematem pracy dyplomowej. 

# start_dialog
Dialog startowy prezentujący 4 podstawowe tematy, czyli "PRACA DYPLOMOWA", "KONSULTACJE", "EGZAMINY" oraz "ZAJĘCIA"
