# Azure Cognitive Speech Services

### Przedstawienie serwisu

Azure Cognitive Speech Services to usługi służące do analizy i przetwarzania mowy. Pozwalają dzięki temu stworzyć bardziej natuaralny dla człowieka interfejs.

### Zastosowanie
Wykorzystanie możliwośći "rozumienia" i posługiwania się mową naturalną ma szerokie zastosowanie, np.: 
 * W chatbotach
 * W celu zwiększenia dostepności aplikacji dla osób niepełnosprawnych
 * W aplikacjach dla kierowców
 * W wirtualnych asystentach
 

### Speech service
Speech service to serwis którego funkcjonalności oscylują wokół transkrypcji na lini mowa-tekst oraz tekst-mowa oraz tłumaczeń "w locie". Dzięki zunifikowaniu tych funkcjonalności w ramach pojedynczego serwisu, dodanie go do naszej aplikacji pozwala nam na korzystanie z dobrodziejstw rozumienia mowy, otwierając tym samym nowy kanał komunikacji z użytkownikiem. Zawiera w sobie takie funkcjonalności jak: 
 * Speech to Text 
 * Text to Speech 
 * Speech translation

#### Speech to Text
Przetwarzanie mowy na tekst to funkcjonalność, która pozwala nam na bardziej naturalną komunikację z aplikacją. Jest też znacznym ułatwieniem, jeżeli projektujemy aplikację, która ma być wykorzystywana przez aplikację, która wymaga zapisywania ciągów znaków w języku naturalnym (notatki, wiadomości itd.) lub po prostu chcemy ułatwić korzystanie z naszej aplikacji osobom z niepełnosprawościami.
 
#### Text to Speech
Funkcjonalność odwrotna do opisywanej przed chwilą, czyli przetwarzanie tekstu na mowę. Ponownie może być dużym ułatwieniem dla osób z niepełnosprawnościami, ale także dla osób, które nie powinny się skupiać na czytaniu w trakcie używania aplikacji, czyli np. kierowcy.

#### Speech Translation
Funkcjonalność która pozwala tłumaczyć nam mowę na inny język. Funkcjonalność ta zawiera w sobie tłumaczenie mowy na tekst, który następnie jest tłumaczony na inny język. Narzędzie to moze być szczególnie przydatne w chatbotach w których chcemy wprowadzić obsługę wielu językach lub w terminalach informacyjnych np. na lotnisku
 
 
### Sposób użycia Azure Cognitive Speech Services
W celu użycia serwisu, należy go dodać jako zasób w Azure. Następnie korzystając z klucza który znajdziemy w ustawieniach naszego serwisu, możemy kmunikować się z naszym serwisem korzystająć z REST API.

### Azure Cognitive Speech Services
Serwis występuje w dwóch wariantach:
 * Darmowy - dopuszczalny limit 1 żądania w danym momencie
	* Speech to Text:
		* Standard - maksymalnie 5 godzin audio miesięcznie
		* Niestandardowe - maksymalnie 5 godzin audio miesięcznie, 1 bezpłatny model miesięcznie 
	* Text to Speech:
		* Standard - maksymalnie 5 mln znaków miesięcznie
		* Neuronowa - maksymalnie 0,5 mln znaków miesięcznie
		* Niestandardowe - maksymalnie 5 mln znaków miesięcznie, 1 bezpłatny model miesięcznie 
	* Speech Translation:
		* Standard - maksymalnie 5 godzin audio miesięcznie
 * Standard - dopuszczalny limit 20 równoczesnych żądań
	* Speech to Text:
		* Standard - €0,844 za każdą godzinę audio 
		* Niestandardowe - €1,181 za każdą godzinę audio, €1,0882 za model na godzinę 
	* Text to Speech:
		* Standard - €3,374 za każdy milion znaków
		* Neuronowa - €13,493 za każdy milion znaków, W przypadku długich materiałów dźwiękowych: €84,33 za każdy milion znaków
		* Niestandardowe - €5,060 za każdą godzinę audio, €0,0453 za model na godzinę 
	* Speech Translation:
		* Standard - €2,11 za każdą godzinę audio