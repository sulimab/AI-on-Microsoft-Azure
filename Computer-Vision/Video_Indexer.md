# Video Indexer

### Przedstawienie serwisu
Video Indexer to usługa pozwalająca na analizę nagrań (obrazu i dźwieku). Serwis pozwala na wyodrębnienie ogólnych właściwości i zawartości nagrania w podobny sposób w jaki Computer Vision przedstawiało informacje o obrazie. Informacje które możemy w ten sposób pobrać z nagrania obejmują m. in. osoby mówiące, emocje, słowa kluczowe itp.

### Zastosowanie
Jako, że wzrok jest dla ludzi jednym z głównych narzadów poznawczych, tak i serwis opierający się na "widzeniu" i rozumieniu tego co widzi ma szerokie zastosowanie, np.: 
 * Klasyfikacja nagrań w celu łatwiejszego ich wyszukiwania i sugerowania podobnych
 * Ułatwiony odbiór dla osób niepełnosprawnych 
 * Możliwość wyznaczania istotnych fragmentów, co może być ułatwieniem zarówno dla twórcy w trakcie montazu jak i dla oglądającego

### Główne funkcjonalności
Analiza nagrań wykonywana przez serwis Video Indexer jest dość szeroka i można ją podzielić na kilka funkcjonalności wideo i audio takich jak: 
##### Funkcjonalności wideo
Najważniejsze funkcjonalności z zakresu wideo obejmują:
###### Face detection 
Rozpoznawanie twarzy i oznaczanie ich na wide
###### Celebrity identification 
Serwis jest w stanie rozpoznać ponad milion celebrytów z całego 
###### Thumbnail extraction for faces  
Pozwala a generowanie miniaturek twarzy wyciągając z kadrów zdjęcia w których twarz wygląda najlepiej
###### Visual text recognition (OCR)
Funkcjonalnośc pozwalająca wychwytywać w nagraniu wideo zapisany tekst i go odczytywać
###### Visual content moderation
Pozwala wykrywać treści nieodpowiednie
###### Labels identification
Pozwala nadać etykiety zgodnie z tym co się dzieje i znajduje w nagraniu
###### Scene segmentation
Pozwala podzielić nagranie na sceny
###### Shot detection
Pozwala zidentyfikować miejsca cięć
###### Black frame detection
Pozwala zidentyfikować "czarne plansze"
###### Keyframe extraction
Funkcjonalność pozwalająca znaleźć zdjęcie które dobrze oddaje pojedyncze ujęcie
###### Rolling credits
Pozwala zidentyfikować początek i koniec napisów końcowych
###### Animated characters detection
Pozwala zidentyfikować animowane postaci
###### Editorial shot type detection
Serwis oznacza ujęcia w zależności od ich typu

##### Funkcjonalności audio
Najważniejsze funkcjonalności z zakresu audio obejmują:
###### Audio transcription
Realizuje transkrypcję z nagrania
###### Automatic language detection
Pozwala wykryć jaki język jest głównie używany w nagraniu
###### Multi-language speech identification and transcription
Kombinacja dwóch powyższych funkcjonalności
###### Closed captioning
Tworzy napisy do nagrania w trzech formatach: VTT, TTML, SRT.
###### Noise reduction
"Odzszumia" nagranie, czyli wycina dżwięki tła z nagrań rozmów.
###### Speaker enumeration
Pozwala na "rozpoznawanie" mówców. Dopuszczalne jest maksymalnie 16 w jednym nagraniu.
###### Speaker statistics
Generuje statystyki dla mówcy.
###### Textual content moderation
Identyfikuje nieodpowiednie słownictwo w transkrypcji
###### Audio effects
Rozpoznaje efekty w nagraniu
###### Emotion detection
Pozwala rozpoznawać emocje mówców na podstawie tego co zostało powiedziane i jakim tonem
###### Translation
Pozwala na tłumaczenie transkrypcji.

### Sposób użycia Azure Video Indexer 
W celu użycia serwisu, należy go dodać jako zasób w Azure. Z samego serwisu możemy nastepnie korzystać na 3 sposoby: przez portal, korzystając z REST API, lub wykorzystując gotowy widżet, który osadzamy w naszej aplikacji.

### Koszty Azure Video Indexer 
Koszty najważniejszych komponentów znajdują się poniżej. Jednak ze względu na złożoność tego serwisu cennik jest bardziej rozbudowany i w celu jego pełnego zrozumienia zachęcam do zapoznania się z dokumentacją pod adresem https://azure.microsoft.com/pl-pl/pricing/details/media-services/ 
 * Analiza
	* Analiza wideo na żywo w usłudze IoT Edge - Cena za strumień wideo - €0,029/dzień
	* Indeksator wideo 
		* Konto bezpłatnej wersji próbnej - do 10 godzin bezpłatnego indeksowania u użytkowników witryn internetowych, do 40 godzin bezpłatnego indeksowania u użytkowników interfejsów API
		* konto płatne - Analiza wideo €0,127, Analiza audio €0,034 Funkcja Analiza dźwięku w warstwie Podstawowa €0,01690 (Cena za minutę sygnału wejściowego)
	* Redactor
		* S1 - rozdzielczość wyjściowa 640 x 480 i mniej
			* Pierwsze 50,000 min/miesiąc - €0,033 za minutę zawartości (€1,923/godz.)
			* Kolejne 950 000 min (50K–1M min)/miesiąc - €0,031 za minutę zawartości (€1,807/godz.)
			* Powyżej 1 000 000 min/miesiąc - €0,027 za minutę zawartości (€1,574/godz.) 
		* S2 - rozdzielczość wyjściowa 641 x 481 do 1280 x 720
			* Pierwsze 50,000 min/miesiąc - €0,065 za minutę zawartości (€3,846/godz.)
			* Kolejne 950 000 min (50K–1M min)/miesiąc - €0,061 za minutę zawartości (€3,608/godz.)
			* Powyżej 1 000 000 min/miesiąc - €0,052 za minutę zawartości (€3,087/godz.)
		* S3 - rozdzielczość wyjściowa 1281 x 721 do 1920 x 1200
			* Pierwsze 50,000 min/miesiąc - €0,129 za minutę zawartości (€7,691/godz.) 
			* Kolejne 950 000 min (50K–1M min)/miesiąc - €0,120 za minutę zawartości (€7,160/godz.) 
			* Powyżej 1 000 000 min/miesiąc - €0,104 za minutę zawartości (€6,224/godz.) 
 * Kodowanie
	* Kodowanie wideo na żądanie (VoD)
		* wersja standardowa - €0,013 za minutę danych wyjściowych
		* wersja premium - €0,030 za minutę danych wyjściowych
 * Wideo na żywo
	* Analiza wideo na żywo w usłudze IoT Edge - Cena za strumień wideo - €0,029/dzień
	* Wydarzenia na żywo 
		* Przekazywanie - rozdzielczość do 4K 60fps, bez opcji Kodowania w różnych szybkościach transmisji bitów - ~€0,0140/minutę (€0,835/godz.)
		* Live Encoding w wersji Standardowa - rozdzielczość do 720p 30fps, dostępne Kodowanie w różnych szybkościach transmisji bitów - ~€0,0335/minutę (€2,008/godz.) 
		* Live Encoding w wersji Premium - rozdzielczość do 1080p 30fps, dostępne Kodowanie w różnych szybkościach transmisji bitów - ~€0,0429/minutę (€2,574/godz.)
	* Transkrypcja na żywo - ~€0,0197/minutę (€1,181/godz.) 