# Azure Cognitive Language Services

### Przedstawienie serwisu

Azure Cognitive Language Services to usługi służące do analizy tekstu i przetwarzania mowy naturalnej, w tym takich zadań jak: określanie "nastroju" rozmówcy, wykrywanie przekleństw i moderacja wypowiedzi, klasyfikowanie wiadomości itd. 

### Zastosowanie
Wykorzystanie możliwośći "rozumienia" mowy naturalnej ma szerokie zastosowanie, np.: 
 * W chatbotach
 * Na forach i stronach internetowych do moderacji postów i komentarzy
 * W publicznych repozytoriach/zbiorach dokumentów w celu wyszukiwania wrażliwych danych 
 * Na stronach typu instagram do weryfikacji zdjęc
 

### Azure Content Moderator
Azure Content Moderator to usługa pozwalająca na moderowanie treści, które są potencjalnie obraźliwe lub niepożądane z innego powodu. W skład serwisu wchodzi komponent służący do automatycznej moderacji, wspierany przez sztuczną inteligencję, który skanuje tekst, zdjęcia, nagrania. Oprócz tego dostępne jest także środowisko przeznaczone dla ludzkich moderatorów. 

#### Zastosowanie Azure Content Moderator
 * Serwisy przeznaczone dla nieletnich, w których nie powinny się pojawiać treści przeznaczone dla dorosłych
 * Aplikacje umożliwiające wyświetlanie opini o produkcie naszej firmy, w tym przypadku istotne może być odfiltrowanie nieprzychy;lnych komentarzy
 * Wszelkiej maści czaty
 * Repozytoria dokumentów, w których nie powinny się pojawić poufne dane
 
#### Sposób użycia Azure Content Moderator
W celu użycia serwisu, należy go dodać jako zasób w Azure. KOmunikacja odbywa się z wykorzystaniem API. Wysyłając zapytanie z treścią, która wymaga moderacji, w odpowiedzi uzyskujemy JSON z informacją zwrotną.

#### Cennik Azure Content Moderator
Serwis występuje w dwóch wariantach:
 * Darmowy - dopuszczalny limit 1 TPS (Transactions Per Second), dostępne jest 5000 moderacji oraz 5000 recenzji w miesiącu
 * Standard - dopuszczalny limit 10 TPS, koszty zależą od liczy recenzji/moderacji i kształtują się następująco:
	* 0-1 Mln transakcji	- €0.844 za każdy 1 tys. transakcji
	* 1-5 Mln transakcji	- €0.633 za każdy 1 tys. transakcji
	* 5-10 Mln transakcji	- €0.506 za każdy 1 tys. transakcji
	* 10+ Mln transakcji	- €0.338 za każdy 1 tys. transakcji
	
### Language Understanding Intelligent Service (LUIS)
Language Understanding Intelligent Service to serwis który służy do analizy naturalnego języka w celu ekstrakcji istotnych informacji z punktu widzenia aplikacji. Dane możemy podzielic w tym kontekście na 3 kategorie: Wypowiedź - będącą tym co użykownik przekazał, Zamiar - czyli to co użytkownik chciałby, aby stało się po wypowiedzi oraz encje - które są obiektami "wyciągniętymi" z wypowiedzi takimi jak nazwa towaru, liczebność itd. 

#### Zastosowanie Language Understanding Intelligent Service
 * Chatboty
 * Systemy rezerwacji
 * NPC w grach MMO
 
#### Sposób użycia Language Understanding Intelligent Service
W celu użycia serwisu, należy go dodać jako zasób w Azure. Następnie należy określić zbiór encji oraz intencji, a także dostarczyć przykładowe wypowiedzi, w których oznaczymy wymienione elementy. Następnie trenujemy nasz model i publikujemy nasz serwis

#### Cennik Language Understanding Intelligent Service
Serwis występuje w dwóch wariantach:
 * Darmowy - dopuszczalny limit 5 TPS (Transactions Per Second), dostępne jest 10000 żądań tekstowych oraz 1 mln stworzonych transakcji
 * Standard - dopuszczalny limit 50 TPS, €1.265 za 1000 żądań tekstowych, €4.639 za 1000 żądań wymawianych
 
### Text Analytics API
Serwis TextAnalytics API pozwala na odczytanie dodatkowych informacji z tekstu, takich jak język w jakim został napisany, wyszukac najwazniejsze zdania, a także odczytać "nastawienie" piszącego

#### Zastosowanie Text Analytics API
 * Chatboty - w których istotny jest poziom zadowolenia klienta
 * System recenzji - pozwalający wybierać jak najlepsze opinie lub przeciwnie, jak najgorsze, aby mógł je przejrzeć ludzki konsultant
 
#### Sposób użycia Text Analytics API
W celu użycia serwisu, należy go dodać jako zasób w Azure. Po dodaniu go możemy wysyłać na jego API zapytania zawierające tekst, o którym chcielibyśmy sie więcej dowiedzieć. Odpowiedź zwracana jest w formacie JSON.

#### Cennik Text Analytics API
Serwis występuje w siedmiu wariantach:
 * Darmowy - dostępne jest 5000 transakcji w miesiącu
 * Standard - koszty zależą od liczy transakcji i kształtują się następująco:
	* 0-0.5 Mln transakcji		- €1.687 za każdy 1 tys. transakcji
	* 0.5-2.5 Mln transakcji	- €0.844 za każdy 1 tys. transakcji
	* 2.5-10 Mln transakcji		- €0.422 za każdy 1 tys. transakcji
	* 10+ Mln transakcji		- €0.211 za każdy 1 tys. transakcji