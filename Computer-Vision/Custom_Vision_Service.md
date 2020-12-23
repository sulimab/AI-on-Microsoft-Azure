# Custom Vision Service

### Przedstawienie serwisu
Custom Vision to usługa podobna do Computer Vision, ale skierowana do specyficznych zastosowań, które wymagają własnego modelu. Korzystając z Custom Vision możemy stworzyc wałsny model na podstawie zdjęć i dostarczonych tagów i korzystać z niego do detekcji lub klasyfikacji.

### Zastosowanie
Custom Vision znajdzie zastosowanie wszędzie tam gdzie potrzebujemy Computer Vision, i potrzebujemy detekcji lub klasyfikacji, ale nasze wykorzystanie jest mocno specyficzne i wychodzi po za ramy ogólnego opisu jaki znajdziemy w Computer Vision. Przykłądem takich zastosowań może być np.: 
 * Znajdowanie na lini produkcyjnej ziemniaków, które nie spełniają normy
 * Znajdowanie zmian nowotworowych 
 * Rozpoznawanie hieroglifów

### Główne funkcjonalności
Custom Vision wykorzystuje przygotowany pod konkretne zastosowanie model i dopuszcza dwa tryby działania:
###### Image classification
Klasyfikacja pozwala na przydzielenie do obrazu jednej lub więcej etykiet na podstawie modelu.

###### Object detection
Detekcja również pozwala na przydzielenie etykiet, ale dodatkowo wskazje koordynaty obiektu, któremu przydziela daną etykietę

### Sposób użycia Azure Custom Vision
W celu użycia serwisu, należy go dodać jako zasób w Azure. Następnie należy przejśc na stronę https://www.customvision.ai/ i stworzyć projekt w którym wybieramy typ projektu (klasyfikacja lub detekcja obiektu). Po stworzeniu projektu możemy przejśc do trenowania modelu dostarczając mu zdjęcia i odpowiednio je tagując. Wymagane jest także przetrenowanie detektora lub klasyfikatora. 
Oprócz portalu możliwe jest tez skorzystanie z SDK jeżeli ręcznie piszemy aplikację która ma korzystać z Custom Vision.

### Koszty Azure Custom Vision 
Serwis występuje w dwóch wariantach:
 * Darmowy - dopuszczalny limit 2 TPS
	* maksymalnie 2 projekty
	* maksymalnie 1 godzina treningu miesięcznie
	* Magazyn obrazów - limit 5000 obrazów treningowych na projekt
	* 10 000 prognoz miesięcznie
 * Standard - dopuszczalny limit 10 
	* maksymalnie 100 projekty
	* trening - €16,866 za godzinę obliczeniową
	* Magazyn obrazów (maks. 6 MB każdy) - €0,591 za następującą liczbę obrazów: 1 000 
	* Transakcje przekazywania i przewidywania - €1,687 za 1000 transakcji 
