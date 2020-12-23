# Computer Vision

### Przedstawienie serwisu
Computer Vision to usługa pozwalająca na analizę obrazu. Serwis jest w stanie pozyskiwać z niego istotne dla danego procesu informacje, takie jak co znajduje sie na obrazie, analiza ruchu obiektów na nagraniu, odczytywanie napisów znajdujących się w polu widzenia, opis obrazu za pomocą tagów, klasyfikacja obrazów jako nieodpowiednie dla dzieci itp.

### Zastosowanie
Jako, że wzrok jest dla ludzi jednym z głównych narzadów poznawczych, tak i serwis opierający się na "widzeniu" i rozumieniu tego co widzi ma szerokie zastosowanie, np.: 
 * Na stronach internetowych ze zdjęciami na sprzedaż/do wykorzystania w celu ich analizy i ułatwienia wyszukiwania
 * W wyszukiwarkach zdjęć podobnych do podanego
 * Na bramkach na autostradzie w celu odczytania tablic rejestracyjnych 
 * Do zarządzania ilością osób które przebywają w sklepie, aby spełniać normy sanitarne
 * Do wstepnego rozpoznawania osób wchodzących do baru - analiza wieku
 * Przy automatycznych kioskach w McDonald do sprawdzania czy pokazywać menu dla dzieci czy dla dorosłych

### Główne funkcjonalności
Analiza obrazów wykonywana przez serwis Computer Vision jest dość szeroka i można ją podzielić na kilka funkcjonalności takich jak: 
###### Optical Character Recognition (OCR) 
Odczytywanie napisów (drukowanych lub odręcznych) zawartych w obrazie
###### Object detection
Wykrywanie, rozpoznawanie i lokalizwoanie w przestrzeni obiektów. Są one zaznaczane na obrazie prostokątami i nazwane. 
###### Brand detection
Serwis potrafi zidentyfikować popularne marki. Funkcjonalność ta może być przydatna kiedy nie chcemy być posądzeni o promowanie jakiejś marki i przed wypuszczeniem obrazu chcemy odpowiednio zasłonić loga.
###### Content tags
Funkcjonalność przydziela tagi obrazowi co pozwala dowiedzieć się jakie obiekty znajdują się na obrazie.
###### Image categorization
Funkcjonalność podobna do tagów, z tą różnicą iż kategorii jest tylko 86 i są hierarchiczne.
###### Image descriptions
Serwis dodaje krótki opis w języku naturalnym. Może być pomocne dla osób z problemami wzrokowymi.
###### Face detection
Funkcjonalność pozwalająca na wykrywanie twarzy i szacowanie płci i wieku osoby.
###### Image type detection
Pozwala na sprawdzenie czy obraz jest typu clipart lub line-drawing
###### Domain-specific content
Oprócz ogólnej analizy możemy też sami wyszkolić model, aby rozpoznawał specyficzne obiekty lub osoby
###### Color scheme detection
Wykrywanie schematu barw. Może być użyteczne kiedy potrzebujemy utrzymać spójność graficzną w jakims materiale i poszukujemy materiałów o podobnych właściwościach kolorystycznych do pozostałych obrazów.
###### Smart-cropped thumbnails
Serwis umożliwia inteligentne generowanie miniaturek zdjęcia, tak aby jego główna zawartość nie była przycięta.
###### Adult content detection
Umożliwia wykrywanie treści przeznaczonych dla dorosłych.

### Sposób użycia Azure Computer Vision
W celu użycia serwisu, należy go dodać jako zasób w Azure. Następnie korzystając z klucza który znajdziemy w ustawieniach naszego serwisu, możemy kmunikować się z naszym serwisem korzystająć z REST API.

### Koszty Azure Computer Vision 
Serwis występuje w dwóch wariantach:
 * Darmowy - dopuszczalny limit 20 transakcji na minutę
	* limit 5000 transakcji miesięcznie
 * S1 - dopuszczalny limit 10 TPS
	* Funkcje Tag, Face GetThumbnail, Colour, ImageType, GetAreaOfInterest: 
		* 0–1 mln transakcji — €0,844 za 1000 transakcji
		* 1–5 mln transakcji — €0,675 za 1000 transakcji
		* 5–10 mln transakcji — €0,549 za 1000 transakcji
		* 10–100 mln transakcji — €0,549 za 1000 transakcji
		* Ponad 100 mln transakcji — €0,549 za 1000 transakcji  
	* Funkcje OCR, Adult, Celebrity, Landmark, Detect objects, Detect Brand:
		* 0-1 mln transakcji — €1.265 za 1,000 transakcji
		* 1M-5 mln transakcji — €0.844 za 1,000 transakcji
		* 5M-10 mln transakcji — €0.549 za 1,000 transakcji
		* 10M-100 mln transakcji — €0.549 za 1,000 transakcji
		* Ponad 100 mln transakcji — €0.549 za 1,000 transakcji 
	* Funkcje Describe, Read:
		* €2,109 za 1000 transakcji 
	*  Spatial analysis :
		* Bezpłatnie w okresie zapoznawczym 
