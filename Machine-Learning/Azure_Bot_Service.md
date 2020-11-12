# Azure Bot Service

### Przedstawienie serwisu

Azure Bot Service to usługa pozwalająca na budowanie, publikowanie i zarządzanie botami na platformie Azure. W łatwy sposób pozwala na integrację z innymi usługami z grupy Azure Cognitive Services, dzięki czemu jest idealnym wyborem przy tworzeniu interfejsu komunikacji z użytkownikiem z wykorzystaniem języka naturalnego.

### Zastosowanie
Boty mogą być zintegrowane z różnymi kanałami komunikacji, a przez to mogą być wykorzystywane wielu sytacjach. Poniżej kilka typowych i nietypowych przykłądów: 
 * Systemy zgłaszania kolizji do ubezpieczyciela
 * Pomoc dla klienta w wyborze produktu (np. pralki lub jogurtu)
 * Bot przekierowujący problem do odpowiedniego działu  
	* opcjonalnie bot może zawsze przekierowywać problemy do działów innych niż IT
 * Centrala telefoniczna tworząca pętle mjącą na celu zniechęcenie klienta chcącego złożyć skargę
 * Bot przeprowadzający wstępny wywiad zgłoszenia gwarancyjnego sugerujący winę użytkownika

### How to
Boty można stworzyć na kilka sposobów, m. in. korzystając z pomocy QnA Maker lub Bot Framework Composer.

#### QnA Maker
QnA Maker pozwala na udostepnianie baz wiedzy z wykorzystaniem komunikacji w języku naturalnym. Jest dobrym rozwiązaniem kiedy posiadamy rozległą bazę wiedzy, ale przeszukiwanie jej może być problematyczne. Komunikacja w języku naturalnym pozwala na zidentyfikowanie problemu i udzielenie odpowiedzi zgodnie z bazą wiedzy. 

##### Baza wiedzy
Jak widać korzystając z usługi QnA Maker baza wiedzy jest jej centralnym elementem. Zawiera ona pary pytań i odpowiedzi. Co ważne bazy nie musimy tworzyc od nowa, jeżeli istnieje już FAQ będące bazą wiedzy możemy je zaimportować. Oczywście możemy później edytować pary, dodawać nowe oraz wzbogacać bazę o alternatywne formy pytań. Baza jest nastepnie uczona, tak aby pytania podobne, ale nie identyczne, również byly rozpoznawane i przypisywane do odpowiedniego pytania. 

##### Zastosowanie
Kiedy warto korzystać z QnA Maker? Jeżeli:
 * Istotne jest wykorzystanie istniejącej bazy wiedzy
 * Problemy które ma rozwiązywać bot, łatwo da się przedstawić w sposób pytanie odpowiedź (z jedną odpowiedzią na konkretne pytanie)

##### Cennik QnA Maker
QnA Maker posiada dwa warianty:
 * Bezpłatny - dopuszczając 3 TPS (Transactions Per Second), Każdy dokument o rozmiarze do 1 MB, do 100 transakcji na minutę, do 50 000 transakcji na miesiąc, 3 dokumenty miesięcznie za darmo
 * Standard - dopuszczając 3 TPS, Do 100 transakcji na minutę, €8,433 za nielimitowaną liczbę dokumentów
 
#### Bot Framework Composer

Bot Framework Composer to narzędzie desktopowe pozwalająca tworzyć zaawansowane boty korzystająć z graficznego interfejsu bez koniecznośći pisania kodu. Dzięki integracji LUIS (
Language Understanding) z botem stworzonym w ten sposób porozumiewać możemy się korzystając z języka naturalnego. Możliwe jest także wykorzystanie w ramach tego narzędzia usługi QnA Maker jezeli chcemy skorzystać z bazy wiedzy.


##### Zastosowanie
Bot stworzony korzystając z Bot Framework Composer jest idealnym rozwiązaniem jeżeli:
 * Potrzebujemy prostego interfejsu graficznego do sworzenia w pełni funkcjconalnego bota
 * Tworzony bot będzie integrowany z usługami Azure App Service lub Azure Functions
 * Bot będzie posługiwał się wieloma językami
 
##### Cennik Bot Framework Composer
Samo narzędzie jest bezpłatne.

### Cennik Azure Bot Service
Azure Bot Service dospępny jest w dwóch wariantach:
 * Darmowy - nielimitowana liczba wiadomośi w kanałach standardowych (serwisy mające publicznie dostępny klucz BotAPI, takie jak Facebook oraz Slack), 10 000 wiadomości na miesiąc w kanałach premium (serwisy inne niż standardowe takie jak serwisy prywatne)
 * S1 - nielimitowana liczba wiadomośi w kanałach standardowych, €0,422 za każde 1000 wiadomości w kanałach premium