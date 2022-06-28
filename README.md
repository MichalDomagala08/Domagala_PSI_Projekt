# Domagala_PSI_Projekt

## Opis projektu 
Projekt na podstawy sztucznej inteligencji - klasyfikacja Komponentów Niezależnych, otrzymanych z sygnałów elektrycznych z EEG na pochodzące z Mózgu i Artefakty

W przypadku danych Elektrofizjologicznych, a szczegolnie danych mózgowych, ICA służy do wydzielenia pewnych źródeł aktywności mózgowej, która składa się na obserwowany przez nas przy pomocy EEG, mocno zagmatwany i zaszumiony sygnał. Możemy dzięki temu z czasowego sygnału EEG, uzyskać komponenty, gdzie wieksza katywność będzie widoczna na pewnych konkretnie ułożonych w przestrzeni elektrodach - tym samym, mozna wnioskować o źródle tego konkretnego komponentu:

Mixing Matrix, w przypadku neurofizjologi będzie więc obrazowało,Jaka wartość będzie rejestrowana na każdej z elektrod, dajac nam określonę źródło aktywności.

![EEGdecomposition](https://user-images.githubusercontent.com/56306081/176242429-eba64114-8e2a-421d-abfa-e198a5958553.png)


Natomiast ICA nie będzie klasyfikowało jedynie źródła mózgowe - ponieważ liczy się tutaj tylko sygnał Elektrofizjologiczny! Oznacza to, że ruchy oczu, mięśni, bicie serca, a nawet otaczające badanego urządzenia elektryczne również mogą pojawić się jako niezależne komponenty! --> trzeba w takim razie móc je skutecznie odfiltrowywać.

Istnieją pewne konkretne metody by wykonywać tą operację automatycznie, jednak szczególnie w badaniach, gdzie wymagana jest duża ilość komponentów - dalsze analizy ICA bedą dawały komponenty niezbyt wyraźne i mało konkretne: odróżnienie tego typu komponentów, dokonuje się więc najczęściej manualnie - co jest neizwykle żmudne i czasochłonne. Prócz tego, odróżnienie komponentów mózgowych od artefaktów jest Ekstremalnie trudne i wymaga wprawy - szacuje się, że nawet doświadczony ekspert może osiągnąć skuteczność maksymalnie 90%

Dlatego właśnie w tym projekcie chciałbym zeksplorować, czy możliwe jest zautomatyzowanie procesu przez zastosowanie modeli uczenia maszynowego zarówno dla danych korelacyjnych jak i danych topograficznych i czy da się to wykorzystać w praktyce?
'

zbiór danych który jest tutaj rozważany pochodzi ze zbiorów Instytutu Psychologii. Zawiera on podział na testwoe i treningowe zbiory zawierające obrazki, zalabelowane jako rozkład topograficzny aktywności elektrofizjologicznej dla sygnałów pochodzących z mózgu, oraz tych które z mózgu nie pochodzą.

Mamy tez zbiory testowe i treningowe z danych korelacyjnych, które kojarzą, dany komponent wydzielony przez Analizę ICA, z  z amplitudą, częstotliwością, fazą itp. sygnału z elektrod referencyjnych - to znaczy umieszczonych na Mastoidach (uszy) oraz w okół oczu (EOG) lub serca (EKG) - Korelacje te, będą informowały o występowaniu artefaktów.


## Zawartość Repozytorium:
+ **Data** - zawiera dane, testowe, treningowe, obrazkowe jak i korelacyjne
+ **ICA_classification** - notebook z właściwym rozwiazaniem
+ **Models** - zawiera zachowane w toku analizy model ANN - swoisty backup najlepszych rozwiazan
