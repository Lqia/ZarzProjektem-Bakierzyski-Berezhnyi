# SPRAWOZDANIE Z PROJEKTU
## **SwapCar – platforma do wymiany samochodów**

**Przedmiot:** Zarządzanie Projektem Informatycznym – Poziomy gotowości technologicznej
**Etap projektu:** Zarządzanie jakością i struktura organizacyjna projektu (Lab 10)
**Aktualny poziom gotowości technologicznej:** *TRL 6 (PGT VI)*

---

## **Spis treści**

1. **Poziom TRL 1 – koncepcja projektu**
   1.1. Opis pomysłu
   1.2. Główne funkcje aplikacji
   1.3. Działanie algorytmu dopasowywania
   1.4. Gdzie można to wykorzystać
2. **Poziom TRL 2 – rozwinięcie koncepcji i zasoby**
   2.1. Założenia drugiej fazy
   2.2. Wykorzystane zasoby
   2.3. Zrealizowany plan przygotowawczy
3. **Poziom TRL 3 – testy założeń i osobnych elementów (Badania przemysłowe)**
   3.1. Potwierdzenie założeń koncepcji (Zadanie 1 z Lab 4)
   3.2. Projekt SwapCar a 7 pryncypiów metodyki PRINCE2 (Zadanie 2 z Lab 4)
4. **Poziom TRL 4 – badania prototypu w warunkach laboratoryjnych**
   4.1. Weryfikacja koncepcji w warunkach laboratoryjnych (Zadanie 1 z Lab 5)
   4.2. Określenie ryzyk dla IV poziomu TRL i sposoby ich eliminacji (Zadanie 2 z Lab 5)
5. **Punkt Kontrolny – Jakość dokumentacji oraz plan komercjalizacji (Lab 6)**
   5.1. Uporządkowanie struktury dokumentu (Zadanie 1 z Lab 6)
   5.2. Grupa docelowa oraz model biznesowy i komercjalizacja produktu (Zadanie 2 z Lab 6)
6. **Poziom TRL 5 – weryfikacja koncepcji w środowisku zbliżonym do rzeczywistego (Lab 7)**
   6.1. Integracja komponentów za pomocą wzorca MVC oraz testy na zwiększonej próbie (Zadanie 1 z Lab 7)
7. **Analiza SWOT projektu SwapCar (Lab 8)**
   7.1. Macierz analizy SWOT (Zadanie 1 z Lab 8)
   7.2. Szczegółowa analiza czynników z oszacowaniem prawdopodobieństwa procentowego (Zadanie 2 z Lab 8)
8. **Poziom TRL 6 – demonstracja prototypu w warunkach zbliżonych do rzeczywistego (Lab 9)**
   8.1. Zaawansowane testy serwerowe oraz badania użyteczności prototypu (Zadanie 1 z Lab 9)
   8.2. Ryzyka technologiczne dla VI poziomu TRL i sposoby ich eliminacji (Zadanie 2 z Lab 9)
9. **Zarządzanie jakością i struktura organizacyjna projektu (Lab 10)**
   9.1. Metryka produktu z mierzalnymi parametrami jakościowymi (Zadanie 1 z Lab 10)
   9.2. Diagram struktury organizacyjnej i zarządczej projektu (Zadanie 2 z Lab 10)
   9.3. Charakterystyka unikalnych ról w zespole projektowym (Zadanie 3 z Lab 10)
10. **Podsumowanie**

---

## 1. Poziom TRL 1 – koncepcja projektu

### 1.1. Opis pomysłu

**SwapCar** to aplikacja umożliwiająca *bezpośrednią wymianę samochodów* między użytkownikami. Działanie aplikacji przypomina aplikacje randkowe (np. Tinder): użytkownicy przesuwają karty samochodów w lewo lub w prawo, aby odrzucić ofertę lub wyrazić zainteresowanie.

W odróżnieniu od zwykłych portali ogłoszeniowych, które skupiają się na sprzedaży, w **SwapCar** chodzi o *wymianę aut sztuka za sztukę lub z dopłatą*, jeśli samochody mają różną wartość.

Użytkownicy dodają ogłoszenia swoich aut, wpisują ich parametry i zaznaczają, jakiego samochodu szukają. Gdy obie strony polubią swoje auta, aplikacja tworzy *parę (match)*, co pozwala im porozmawiać na czacie i dogadać szczegóły wymiany.

### 1.2. Główne funkcje aplikacji

**Tworzenie ogłoszenia samochodu:**
Użytkownik dodaje swoje auto poprzez prosty formularz, wpisując:
* **Markę i model**,
* **Rocznik**,
* **Rodzaj paliwa** (*benzyna, diesel, LPG, elektryk, hybryda*),
* **Typ nadwozia i kolor**,
* **Pojemność i moc silnika**,
* **Przebieg**,
* **Rodzaj napędu** (*FWD, RWD, AWD*),
* **Położenie kierownicy** (*lewa/prawa*),
* **Stan techniczny** (*uszkodzony/nieuszkodzony*),
* **Orientacyjną cenę i zdjęcia samochodu**.

**Określanie preferencji:**
Na starcie użytkownik zaznacza, czego szuka (np. *czarny sedan w benzynie po 2015 roku do 30 000 zł*). Określa też, czy interesuje go **wymiana bezgotówkowa**, czy jest gotów dopłacić (i ile maksymalnie), albo czy sam oczekuje dopłaty od drugiej osoby.

**Przeglądanie ofert i dopasowania (matche):**
Oferty są wyświetlane jako karty ze zdjęciem, podstawowymi danymi i ceną:
* **Przesunięcie w prawo** – *podoba mi się (chcę się wymienić)*.
* **Przesunięcie w lewo** – *odrzucam*.

Gdy dwóch użytkowników polubi swoje samochody nawzajem, tworzy się **dopasowanie (match)** i odblokowuje się czat, na którym mogą się dogadać.

**Ustalanie dopłaty:**
Aplikacja pozwala na wymianę aut o różnej wartości. Przykładowo: *Auto A jest warte 25 000 zł, a Auto B 30 000 zł*. Właściciel Auta A oferuje swoje auto plus **5 000 zł dopłaty**. System bierze te widełki pod uwagę przy podsyłaniu ofert.

### 1.3. Działanie algorytmu dopasowywania

Algorytm bierze pod uwagę trzy rzeczy:
1. **Preferencje początkowe** – to, co użytkownik zaznaczył w filtrach na starcie oraz ile może dopłacić.
2. **Zachowanie w aplikacji** – jakie auta użytkownik najczęściej przesuwa w prawo, a jakie odrzuca (np. jeśli ciągle odrzuca diesle, aplikacja zaczyna pokazywać więcej benzyniaków).
3. **Zgodność w dwie strony** – nie wystarczy, że użytkownikowi A podoba się auto B. Algorytm sprawdza, czy auto A ma szansę spodobać się użytkownikowi B i czy zgadzają się ich *oczekiwania finansowe*.

### 1.4. Gdzie można to wykorzystać

1. **Wymiana aut między zwykłymi kierowcami** (*osoby prywatne*).
2. **Wymiana aut między komisami samochodowymi** (*segment B2B*).
3. **Podpowiadanie pasujących ofert** na podstawie wyborów użytkownika.
4. **Pomoc w wycenie aut** i sugerowaniu kwoty dopłaty.
5. **Sprawdzanie historii pojazdów** po numerze *VIN*.

---

## 2. Poziom TRL 2 – rozwinięcie koncepcji i zasoby

### 2.1. Założenia drugiej fazy

Pierwsza wersja **SwapCar** została zaprojektowana jako *strona internetowa (aplikacja webowa)*, którą w kolejnych krokach rozwiniemy o wersję mobilną na telefony.

### 2.2. Wykorzystane zasoby

**Sprzęt i infrastruktura:**
* 3 komputery/laptopy,
* stabilne łącze internetowe,
* *serwer testowy (chmura)*,
* telefon do sprawdzania, jak strona wyświetla się na małym ekranie.

**Programy i narzędzia:**
* **Visual Studio Code** do pisania kodu,
* **GitHub** do trzymania kodu i wspólnej pracy w grupie.

**Dane i organizacja:**
* przykładowe dane o samochodach i ich cenach (*sztuczna baza do testów*),
* darmowe zdjęcia aut z internetu, które można legalnie wykorzystać,
* przykładowe konta użytkowników z różnymi wymaganiami,
* **podział zadań** (osoba od wyglądu strony, osoba od logiki i bazy danych oraz osoba od testów).

### 2.3. Zrealizowany plan przygotowawczy

1. Rozrysowaliśmy wygląd aplikacji.
2. Zaplanowaliśmy bazę danych.
3. Opracowaliśmy założenia *algorytmu dopasowywania ofert*.
4. Przygotowaliśmy środowisko pod pierwszą wersję strony.
5. Zgromadziliśmy przykładowe dane o autach do testów.

---

## 3. Poziom TRL 3 – testy założeń i osobnych elementów (Badania przemysłowe)

### 3.1. Potwierdzenie założeń koncepcji (Zadanie 1 z Lab 4)

Na trzecim poziomie **TRL** sprawdziliśmy w praktyce, czy nasz pomysł ma sens i przetestowaliśmy osobno najważniejsze kawałki (*moduły*) naszego systemu, zanim połączyliśmy je w jedną całość.

W ramach tego etapu zrealizowaliśmy i przetestowaliśmy następujące elementy:

* **Moduł dodawania i sprawdzania ogłoszeń** – odpowiada za przyjmowanie danych o samochodach z formularza. Na tym etapie położyliśmy nacisk na to, żeby użytkownicy nie mogli wpisać głupot (np. ujemnego przebiegu, rocznika z przyszłości albo pustej ceny). Moduł został wyposażony w *mechanizm sprawdzający kompletność danych* przed zapisaniem ich do bazy. W ramach testów wrzuciliśmy do niego paczkę przykładowych, częściowo błędnych ogłoszeń – moduł poprawnie wyłapał wszystkie błędy i nie przepuścił niekompletnych ofert.
* **Moduł liczenia dopłat** – kawałek kodu, który porównuje ceny dwóch samochodów i sprawdza, czy użytkownicy są w stanie się dogadać finansowo. Zadaniem modułu jest policzenie różnicy w cenie między autem A i autem B oraz sprawdzenie, czy ta różnica mieści się w kwocie, którą jedna ze stron zadeklarowała jako *maksymalną dopłatę*. W testach laboratoryjnych opracowaliśmy system walidacji i sprawdziliśmy go na przykładowych parach aut. Określiliśmy w procentach **współczynnik zgodności** i potwierdziliśmy, że moduł poprawnie łączy oferty z różnymi widełkami cenowymi, odrzucając auta, na które użytkowników nie stać.
* **Moduł dopasowywania ofert (Silnik Matchingowy)** – najważniejszy element, który odpowiada za podsyłanie kart z samochodami w *czasie rzeczywistym*. W tym module zweryfikowaliśmy, jak szybko system potrafi przejrzeć bazę ogłoszeń i wybrać te, które pasują do filtrów użytkownika. Zbadaliśmy przy tym **obciążenie procesora (CPU)** i **zużycie pamięci RAM** na naszym serwerze testowym podczas symulacji, w której wielu użytkowników naraz szybko przesuwało karty w lewo i w prawo. Zastosowaliśmy tu pewną tolerancję – założyliśmy, że *płynność ładowania kart* i zgodność głównych parametrów (cena, paliwo, rocznik) ma pierwszeństwo przed mniej ważnymi detalami (np. kolor). Badania pozwoliły nam znaleźć optymalny balans między trafnością podpowiedzi a szybkością działania serwera.

Na tym etapie określiliśmy również prosty sposób liczenia punktów dopasowania (*model matematyczny oparty na wagach*), który pozwolił na **wielowątkowe wykonywanie obliczeń**. Każda zgodna cecha auta (np. pasujący rocznik czy marka) dodaje punkty, dzięki czemu system szybko układa listę aut od najbardziej do najmniej pasujących.

### 3.2. Projekt SwapCar a 7 pryncypiów metodyki PRINCE2 (Zadanie 2 z Lab 4)

Aby w projekcie nie zrobił się bałagan, organizację naszej pracy oparliśmy o **7 zasad (pryncypiów) z metodyki PRINCE2**. Trzymaliśmy się ich wszystkich, bo pominięcie chociaż jednej oznacza, że nie pracujemy już zgodnie z *PRINCE2*:

1. **Ciągła zasadność biznesowa** – cały czas weryfikowaliśmy, czy robienie tej aplikacji ma sens. Przeprowadzone na 3 poziomie TRL testy poszczególnych modułów udowodniły nam, że nasz algorytm faktycznie działa i pozwala szybciej znaleźć auto na wymianę niż zwykłe filtry na portalach typu Otomoto czy OLX. Dzięki temu na bieżąco kontrolowaliśmy ryzyko (np. ryzyko zbyt wolnego działania algorytmu przy dużej bazie aut) i wiedzieliśmy, że jest ono na *akceptowalnym poziomie*.
2. **Zdefiniowane role i odpowiedzialności** – najpierw ustaliliśmy, jakie role są nam potrzebne w zespole, a dopiero potem przypisaliśmy do nich konkretne osoby z naszej grupy. Wyznaczyliśmy **Kierownika Projektu** (pilnuje terminów i sprawozdań) oraz **role techniczne** (osoba od wyglądu strony, osoba od bazy i algorytmu, osoba od testów). Rolę **Komitetu Sterującego** (który ocenia naszą pracę i decyduje o zaliczeniu etapu) pełnił prowadzący zajęcia. Trzymaliśmy się zasady, że członkowie zespołu mogą łączyć kilka zadań programistycznych, ale Kierownik Projektu nie zasiada w Komitecie Sterującym.
3. **Koncentracja na produktach** – nie skupialiśmy się na samym „pisaniu kodu”, tylko na konkretnych rzeczach (*produktach*), które dostarczyliśmy na koniec etapu, i ich jakości. Na tym etapie naszymi gotowymi produktami były trzy przetestowane osobno moduły (sprawdzania ogłoszeń, liczenia dopłat i dopasowywania kart) oraz sprawozdanie. Całą drogę do gotowej aplikacji podzieliliśmy na mniejsze kroki prowadzące do wykonania tych produktów.
4. **Korzystanie z doświadczeń** – mimo że sam pomysł wymiany aut w stylu Tindera jest dość świeży, to tworzenie stron internetowych składa się z powtarzalnych procesów. Skorzystaliśmy z doświadczeń z poprzednich zajęć i projektów na studiach oraz podpatrzyliśmy sprawdzone rozwiązania z istniejących aplikacji randkowych (*mechanizm przesuwania kart*) i portali ogłoszeniowych (*wygląd formularza z parametrami auta*). Wyciągnęliśmy też wnioski z tego, co wypracowaliśmy w sprawozdaniach dla TRL 1 i TRL 2.
5. **Zarządzanie z wykorzystaniem tolerancji** – w projekcie określiliśmy granice tolerancji (*swobody*), w których nasz Kierownik Projektu sam podejmował decyzje. Ustaliliśmy **tolerancję czasową** (terminy oddania sprawozdań i kolejnych etapów), **kosztową** (korzystaliśmy z darmowych narzędzi i własnych laptopów, więc budżet wynosił 0 zł) oraz **jakościową** (w module dopasowywania ofert założyliśmy, że płynność działania aplikacji jest ważniejsza niż idealne dopasowanie drugorzędnych cech, takich jak kolor auta).
6. **Zarządzanie etapowe** – podzieliliśmy nasz projekt na konkretne, niezbyt długie etapy, które pokrywały się z kolejnymi poziomami TRL (*TRL 1 – pomysł, TRL 2 – zasoby i plan, TRL 3 – testy pojedynczych modułów*). Po każdym etapie robiliśmy podsumowanie w formie sprawozdania i po uzyskaniu akceptacji przechodziliśmy dalej. Dzięki temu mieliśmy pełną kontrolę nad postępami prac i jakością projektu.
7. **Dostosowanie do projektu w danym środowisku** – dostosowaliśmy narzędzia i sposób zarządzania do rozmiaru naszego projektu. Jak mówi zasada: *„nie strzela się do komara z armaty”*. Zrealizowaliśmy projekt w 3-osobowej grupie, więc zamiast tworzyć setki stron zbędnej dokumentacji, dobraliśmy lekkie i wygodne narzędzia (**VS Code, GitHub**, komunikator do szybkiego kontaktu) oraz prosty podział zadań skrojony dokładnie pod nasze potrzeby.

---

## 4. Poziom TRL 4 – badania prototypu w warunkach laboratoryjnych

### 4.1. Weryfikacja koncepcji w warunkach laboratoryjnych (Zadanie 1 z Lab 5)

Na czwartym poziomie **TRL** połączyliśmy nasze wcześniejsze moduły w jeden *działający prototyp* i przebadaliśmy go w warunkach laboratoryjnych. Chcieliśmy szybko poznać wyniki na konkretnej próbce danych, żeby w razie niepowodzenia móc na czas przerwać projekt i uratować budżet. Okazało się, że po złożeniu modułów w całość nie wszystko od razu działało tak idealnie, jak zakładaliśmy, ale po wprowadzeniu poprawek badanie zakończyło się pełnym sukcesem.

W ramach realizacji IV poziomu gotowości technologicznej zrealizowaliśmy prace badawcze w następującym zakresie:

* **Moduł dodawania i sprawdzania ogłoszeń** – przygotowaliśmy *zestaw kontrolny 100 ogłoszeń* samochodów zawierających dane tekstowe oraz zdjęcia w formatach: `jpg`, `png` i `webp`. Określiliśmy, że pliki z samymi danymi tekstowymi ogłoszenia zapisywane przez nasz system mają wewnętrzny format z rozszerzeniem: **`*.scd` (SwapCar Data)**. Określiliśmy też, że paczki ogłoszeń zawierające skompresowane zdjęcia samochodów mają rozszerzenie: **`*.scm` (SwapCar Media)**. Wykonaliśmy 100 serii testów wczytywania i walidacji na zestawie kontrolnym. Algorytm wykazał pewne odchylenie w niektórych seriach testów (zdjęcia o dużej rozdzielczości powodowały przycięcia i opóźnienia przy zapisie do bazy). Ustaliliśmy, że na wynik ma wpływ sposób przydzielania pamięci podręcznej i obciążenie wątków procesora przy jednoczesnym zmniejszaniu zdjęć. Wprowadziliśmy poprawkę do algorytmu (*automatyczne zmniejszanie zdjęć przed zapisem*) i ponownie wykonaliśmy 100 serii testów. Wyniki w całej serii były porównywalne, a odchylenia zostały zminimalizowane.
* **Moduł liczenia dopłat** – przygotowaliśmy *zestaw kontrolny 100 wygenerowanych plików ofert* w formacie **`*.scd`** (same dane o cenach i widełkach budżetowych użytkowników, bez multimediów). Wykonaliśmy po 100 serii testów parowania cenowego dla zestawu kontrolnego plików. Algorytm wykazał pewne odchylenie w niektórych seriach testów. Ustaliliśmy, że na wynik ma wpływ zaokrąglanie kwot przez procesor oraz błędne traktowanie ofert, w których użytkownik wpisał dopłatę równą 0 zł. Wprowadziliśmy poprawkę do algorytmu liczącego i ponownie wykonaliśmy 100 serii testów. Wyniki w całej serii były porównywalne, a odchylenia zostały zminimalizowane.
* **Moduł dopasowywania ofert (Silnik Matchingowy)** – przygotowaliśmy *zestaw kontrolny 100 pełnych ofert samochodów* zapisanych w formacie **`*.scm`** (dane razem ze zdjęciami). Wykonaliśmy po 100 serii testów szybkiego przeglądania i przesuwania kart (*swipe*) dla zestawu kontrolnego. Podczas każdego testu rejestrowaliśmy **czas odpowiedzi serwera** oraz płynność wyświetlania kart z obrazkami w przeglądarce. Algorytm wykazał pewne odchylenie w niektórych seriach testów – przy bardzo szybkim przesuwaniu kart pojawiały się opóźnienia w ładowaniu kolejnych propozycji. Ustaliliśmy, że na wynik ma wpływ taktowanie procesora pod dużym obciążeniem oraz brak wcześniejszego wczytywania kart w tle. Wprowadziliśmy poprawkę do algorytmu (*buforowanie 5 kolejnych kart w pamięci z wyprzedzeniem*) i ponownie wykonaliśmy 100 serii testów. Wyniki w całej serii były porównywalne, a odchylenia zostały zminimalizowane.

### 4.2. Określenie ryzyk dla IV poziomu TRL i sposoby ich eliminacji (Zadanie 2 z Lab 5)

Podczas badania prototypu określiliśmy **główne ryzyka**, które mogłyby popsuć działanie połączonych modułów. Do każdego ryzyka przypisaliśmy w procentach *szansę jego wystąpienia* (żeby wiedzieć, co naprawiać w pierwszej kolejności) oraz sposób rozwiązania problemu:

1. **Ryzyko (prawdopodobieństwo: $65\%$):** Brak poprawnej komunikacji pomiędzy modułami (np. moduł dopasowywania ofert nie pobierał na czas wyliczonych kwot z modułu dopłat).
   * **Rozwiązanie:** Zastosowaliśmy zaprogramowane *testy automatyczne* sprawdzające przepływ informacji oraz uporządkowaliśmy kod według wzorca architektonicznego **MVC – Model-View-Controller** (*Model-Widok-Kontroler*).
2. **Ryzyko (prawdopodobieństwo: $50\%$):** Niekompatybilność przesyłanych danych pomiędzy modułami (np. formularz wysyłał cenę auta jako zwykły tekst ze spacjami, a moduł liczenia dopłat oczekiwał czystej liczby, przez co prototyp wyrzucał błąd).
   * **Rozwiązanie:** Dokonaliśmy dokładnego *debugowania kodu* oraz zastosowaliśmy metodę eliminacji wszystkich błędów i nieścisłości związanych z przesyłaniem danych „krok po kroku” (ujednoliciliśmy format przesyłanych danych do standardu **JSON**).
3. **Ryzyko (prawdopodobieństwo: $35\%$):** Algorytm dopasowujący i ładujący zdjęcia mógł działać inaczej (z inną szybkością) na różnych jednostkach CPU oraz różnych przeglądarkach internetowych użytkowników.
   * **Rozwiązanie:** Rozszerzyliśmy testy w badaniu o inne rodzaje jednostek CPU (przetestowaliśmy prototyp na wszystkich 3 laptopach w zespole oraz na telefonie) i na kilku popularnych przeglądarkach (*Chrome, Firefox, Edge*).
4. **Ryzyko (prawdopodobieństwo: $20\%$):** Przeciążenie pamięci RAM serwera przy jednoczesnym przesyłaniu wielu zdjęć samochodów w formacie `*.scm`.
   * **Rozwiązanie:** Wprowadziliśmy *twardy limit rozmiaru* dodawanych zdjęć (maksymalnie do **2 MB** na zdjęcie) oraz automatyczną kompresję plików po stronie serwera.

---

## 5. Punkt Kontrolny – Jakość dokumentacji oraz plan komercjalizacji (Lab 6)

### 5.1. Uporządkowanie struktury dokumentu (Zadanie 1 z Lab 6)

W ramach punktu kontrolnego uporządkowaliśmy nasze dotychczasowe sprawozdanie i dostosowaliśmy je do wymogów formalnych. Zadbaliśmy o to, aby dokumentacja projektu **SwapCar** dobrze świadczyła o naszym zespole:
* Przygotowaliśmy przejrzystą i czytelną **stronę okładkową (tytułową)**, na której nie umieściliśmy numeru strony.
* Utworzyliśmy pełny **spis treści** odzwierciedlający strukturę rekurencyjnego sprawozdania.
* Dodaliśmy czytelne **nagłówki i podtytuły** dla wszystkich poziomów TRL oraz poszczególnych zadań.
* W całym tekście **pogrubiliśmy** oraz oznaczyliśmy *kursywą* najważniejsze pojęcia, nazwy modułów i parametry techniczne.
* Sprawdziliśmy poprawność ortograficzną i gramatyczną tekstu oraz sformatowaliśmy akapity (zastosowaliśmy *justowanie tekstu*, *wcięcia akapitowe* oraz ujednolicony rozmiar czcionki **11 pkt**).
* Na koniec wykonaliśmy ponowny przegląd dokumentu od pierwszego punktu (zgodnie z *TIP 8*), aby upewnić się, że żaden element formatowania nie został pominięty.

### 5.2. Grupa docelowa oraz model biznesowy i komercjalizacja produktu (Zadanie 2 z Lab 6)

Na tym etapie określiliśmy również, dla kogo dokładnie stworzyliśmy platformę **SwapCar**, jak zaplanowaliśmy na niej zarabiać oraz jak oszacowaliśmy wielkość rynku w Polsce.

**Grupa docelowa:**
Naszą technologię podzieliliśmy na dwie główne grupy odbiorców:
1. **Klienci indywidualni (segment B2C)** – w skład tej grupy wchodzą prywatni właściciele samochodów i aktywni kierowcy w wieku **18–45 lat**, którzy średnio lub dobrze radzą sobie z obsługą smartfona i komputera. Są to osoby, które chcą szybko zmienić samochód na inny (np. mniejszy do miasta, większy dla rodziny lub po prostu nowszy model za dopłatą), bez konieczności wielotygodniowego czekania na kupca z gotówką na tradycyjnych portalach. Oszacowaliśmy, że w **ok. $80\%$ są to mężczyźni**, w tym fani motoryzacji, którzy lubią często zmieniać auta. Do tej grupy skierowaliśmy podstawową aplikację wymiany w formule *swipe* (przesuwania kart).
2. **Klienci biznesowi i instytucjonalni (segment B2B)** – do tej grupy zaliczyliśmy **komisy samochodowe**, niezależnych handlarzy aut używanych oraz mniejsze salony prowadzące rozliczenia aut w programach „zostaw stare auto w rozliczeniu”. Dla komisów największym problemem są tzw. *„leżaki placowe”*, czyli samochody, które stoją na placu przez wiele miesięcy i zamrażają gotówkę. Do tego segmentu skierowaliśmy hurtowy moduł wymiany międzykomisowej oraz zautomatyzowany system dopasowań cenowych.

**Szacowana wielkość rynku (liczba klientów):**
Analizując polski rynek wtórny, ustaliliśmy, że co roku w Polsce dochodzi do około **2–2,5 miliona transakcji** sprzedaży i zamiany samochodów używanych. Przyjęliśmy, że:
* W **segmencie prywatnym (B2C)** grupa osób otwartych na bezpośrednią wymianę auta (zamiast klasycznej sprzedaży) wynosi około **150 000 – 250 000 użytkowników rocznie**. Założyliśmy, że w pierwszym roku po wdrożeniu z naszej platformy skorzysta realnie około **20 000 – 50 000 aktywnych użytkowników**.
* W **segmencie komisów (B2B)** w Polsce działa około **10 000 – 12 000 aktywnych punktów handlu autami używanymi**. Naszym docelowym rynkiem w pierwszych dwóch latach stało się pozyskanie około **500 – 1 000 komisów** regularnie wymieniających się autami za pomocą **SwapCar**.

**Model biznesowy (sprzedażowy) i komercjalizacja:**
Wykorzystując wnioski z historii komercjalizacji programów takich jak płatny *WinZip* (gdzie praktycznie żaden prywatny użytkownik nie kupuje wersji Premium, jeśli podstawowa funkcja jest darmowa, ale za to darmowy program buduje ogromną **rozpoznawalność marki**), oparliśmy nasz model biznesowy na dwóch filarach:

1. **Filar I – Użytkownicy prywatni (Model Freemium budujący zasięg i markę):**
   Podstawowe korzystanie z **SwapCar** (założenie konta, dodanie **1 ogłoszenia samochodu**, przeglądanie kart i czatowanie po uzyskaniu *matcha*) udostępniliśmy **całkowicie za darmo**. Zrobiliśmy to celowo – tak jak w przypadku popularnych kompresorów plików, darmowy dostęp miał przyciągnąć tłumy użytkowników, zapełnić bazę ogłoszeniami i zbudować silną, rozpoznawalną markę wśród kierowców.
   Dla bardziej wymagających użytkowników prywatnych wprowadziliśmy dobrowolną opcję **SwapCar Premium** oraz mikropłatności:
   * **Konto Premium (29 zł / miesiąc)** – pozwala na dodanie do 3 aut jednocześnie, daje nielimitowaną liczbę przesunięć kart dziennie, możliwość *cofnięcia przypadkowo odrzuconej oferty* oraz podgląd, kto już polubił nasze auto (zanim sami natrafimy na jego kartę).
   * **Podbicie oferty „SuperSwap” (9,99 zł jednorazowo)** – wyróżnienie karty samochodu, dzięki któremu nasze auto wyświetla się jako pierwsze u innych kierowców z wybranego województwa przez 48 godzin.
   * **Raport historii VIN w aplikacji** – prowizja od sprzedaży raportu historii pojazdu z zewnętrznej bazy danych przed finalizacją wymiany.

2. **Filar II – Segment instytucjonalny / Komisy samochodowe (Umowy licencyjne i abonament B2B):**
   Główny ciężar zarabiania pieniędzy przenieśliśmy na firmy (komisy), które zarabiają na obrocie autami i chętnie płacą za narzędzia przyspieszające rotację towaru na placu. W tym segmencie opracowaliśmy **model licencyjny (abonament miesięczny lub roczny)**:
   * **Pakiet Start (Darmowy okres próbny)** – pozwala komisowi na wrzucenie do **3 samochodów** i przetestowanie silnika dopasowań w ograniczonym limicie, aby przekonać się o skuteczności narzędzia.
   * **Licencja Komis Standard (249 zł / miesiąc lub 2 490 zł / rok)** – pozwala na utrzymywanie do **30 aktywnych ofert aut**, automatyczne parowanie z ofertami prywatnymi (z wyliczeniem gotowej kwoty dopłaty dla klienta) oraz oznaczenie profilu odznaką *„Zweryfikowany Komis”*.
   * **Licencja Komis PRO / Sieć (599 zł / miesiąc lub 5 990 zł / rok)** – brak limitu ogłoszeń, dostęp do zamkniętej *giełdy wymian międzykomisowych (B2B)*, automatyczny eksport i import ogłoszeń w naszych formatach **`*.scd`** oraz **`*.scm`** bezpośrednio z systemów komisowych oraz priorytetowe wsparcie techniczne.

Dzięki takiemu podejściu uniknęliśmy błędu polegającego na zmuszaniu zwykłych kierowców do płacenia za sam dostęp do aplikacji – prywatni użytkownicy robią nam darmową reklamę i ruch na stronie, a stały zysk zapewniają licencje dla komisów oraz drobne mikropłatności za promowanie ogłoszeń.

---

## 6. Poziom TRL 5 – weryfikacja koncepcji w środowisku zbliżonym do rzeczywistego (Lab 7)

### 6.1. Integracja komponentów za pomocą wzorca MVC oraz testy na zwiększonej próbie (Zadanie 1 z Lab 7)

Na piątym poziomie **TRL** (w ramach *badań przemysłowych*) przeszliśmy z prostych testów laboratoryjnych do weryfikacji naszego systemu w **środowisku zbliżonym do rzeczywistego (symulowanym)**. Na tym etapie nasza aplikacja **SwapCar** stała się już działającym programem z interfejsem webowym oraz panelem konsolowym do wydawania komend tekstowych i podglądu logów serwera.

Aby zbliżyć warunki badawcze do rzeczywistych (zgodnie z *TIP 2*), **dziesięciokrotnie zwiększyliśmy liczbę danych testowych** – z wcześniejszych 100 plików na poziomie TRL 4 do pełnej bazy **1000 plików ogłoszeń**. W celu trwałego połączenia wszystkich wcześniej zaprogramowanych komponentów zastosowaliśmy wzorzec architektoniczny **MVC (ang. *Model-View-Controller*, pol. *Model-Widok-Kontroler*)**, który uporządkował strukturę naszej aplikacji. W tym celu zaprogramowaliśmy dodatkowy, centralny moduł **Kontrolera**. Jego zadaniem stała się koordynacja pracy całego systemu **SwapCar** poprzez przyjmowanie danych od użytkowników, reagowanie na ich akcje (np. przesunięcia kart), zarządzanie aktualizacją modelu bazy danych oraz odświeżaniem widoków w przeglądarce.

W ramach tego etapu przeprowadziliśmy szczegółowe prace techniczne i weryfikacyjne dla poszczególnych podsystemów (z zachowaniem różnic w ich działaniu zgodnie z *TIP 1*):

* **Kontroler (główny moduł koordynujący MVC)** – został zaprogramowany w celu spięcia i koordynowania pracy pozostałych trzech modułów systemu. W opisanym etapie sprawdziliśmy działanie samego Kontrolera i przeprowadziliśmy testy jego stabilności poprzez jego wielokrotne włączanie, wyłączanie oraz restartowanie pod obciążeniem. Błędy powodujące zawieszanie się i destabilizację pracy Kontrolera (np. nieobsłużone wyjątki przy zerwaniu połączenia z bazą) były przez nas korygowane w kodzie do momentu, aż wykonaliśmy pełny cykl uruchomieniowy bez ani jednego błędu. Pozwoliło to zweryfikować, że Kontroler prawidłowo odbiera żądania od użytkownika, dokonuje ich podstawowej identyfikacji i bezbłędnie przesyła je do wybranych modułów. W Kontrolerze zdefiniowaliśmy dedykowane **wtyczki (endpointy API)** do wszystkich trzech zaprogramowanych wcześniej modułów oraz podstawową weryfikację danych (i ich typów), jakie mają wyjść do danego modułu. Przetestowaliśmy także działanie mechanizmu rozpoznawania danych dla poszczególnych wtyczek. W tym celu poddaliśmy Kontroler testom na danych kontrolnych oraz sprawdziliśmy jego reakcję na dane celowo **„uszkodzone”** (np. zmieniony typ danych: wysłanie ciągu znaków tekstowych zamiast liczby w polu `cena_auta`, uszkodzony nagłówek pliku **`*.scm`** lub pusty obiekt JSON). Za pierwszym razem Kontroler przepuścił część błędnych danych, co powodowało zatrzymanie pracy podrzędnych modułów. Dokonaliśmy analizy logów, która ustaliła przyczynę błędu (brak rygorystycznej walidacji typów na wejściu), po czym wprowadziliśmy zmiany programistyczne w obszarze warunków weryfikujących zgodność danych. Pomyślny test prawidłowego działania Kontrolera (tj. uzyskanie natychmiastowego zwrotu informacji o błędach w danych i zablokowanie uszkodzonego pliku przed dalszym procesowaniem) pozwolił nam na jego pełną integrację z pozostałymi modułami.

* **Moduł dodawania i sprawdzania ogłoszeń (kompresja i zapis danych)** – dokonaliśmy pełnej integracji tego modułu z Kontrolerem. Przetestowaliśmy działanie samego modułu oraz jego pracę w relacji z Kontrolerem. Testu dokonaliśmy na zwiększonej, próbnej bazie **1000 plików ogłoszeniowych** (zarówno tekstowych jak i ze zdjęciami) w zakresie prawidłowej walidacji parametrów auta, kompresji zdjęć i zapisu gotowych paczek do naszych formatów **`*.scd`** oraz **`*.scm`**. Analizie podlegała także **kompletność zapisanych i skompresowanych danych** (sprawdzaliśmy, czy podczas masowego dodawania 1000 ofert przez Kontroler nie giną opisy samochodów, parametry silnika lub pojedyncze zdjęcia). W pierwszych próbach wykryliśmy błędy polegające na ucinaniu długich opisów aut oraz gubieniu co kilkudziesięciu zdjęć przy szybkim przesyłaniu danych z Kontrolera. Wyeliminowaliśmy te błędy poprzez poprawki programistyczne (zwiększenie bufora odbiorczego we wtyczce modułu oraz synchronizację wątków zapisu) i wykonaliśmy kolejne testy na tych samych 1000 plikach, aż do uzyskania w $100\%$ poprawnego skomunikowania się z modułem Kontrolera i bezbłędnego odczytu otrzymanych z niego poleceń.

* **Moduł liczenia dopłat (przetwarzanie danych niemultimedialnych)** – dokonaliśmy integracji modułu z Kontrolerem oraz przetestowaliśmy działanie samego modułu i jego współpracę w relacji z Kontrolerem. Testu dokonaliśmy na próbnej bazie **1000 plików niemultimedialnych** zapisanych w formacie **`*.scd`** (zawierających wyłącznie ustrukturyzowane dane liczbowe i tekstowe: ceny pojazdów, roczniki oraz zadeklarowane widełki dopłat użytkowników), w zakresie prawidłowego odczytu danych i wyliczania różnic cenowych. Zweryfikowaliśmy jakość komunikacji danych i kompatybilność z pozostałymi współpracującymi modułami systemu (sprawdziliśmy, czy wyliczona dopłata trafia z powrotem przez Kontroler do widoku karty samochodu). Przeprowadziliśmy procedurę sprawdzającą dokładność wyliczanych informacji finansowych na plikach testowych. W trakcie testów na bazie 1000 plików wystąpiły błędy spowodowane przeciążeniem Kontrolera i modułu liczenia dopłat przy jednoczesnym porównywaniu ofert w układzie „każdy z każdym” (czas oczekiwania na wyliczenie dopłaty przekraczał 4 sekundy). Usunęliśmy te błędy poprzez analizę wyników i dokonanie korekty programistycznej w kodzie (wprowadziliśmy wstępne odrzucanie ofert skrajnie odległych cenowo jeszcze na poziomie zapytania z Kontrolera). Następnie ponownie wykonaliśmy test na tych samych **1000 plikach `*.scd`**, uzyskując stabilną i natychmiastową odpowiedź systemu.

* **Moduł dopasowywania ofert – Silnik Matchingowy (odczyt strumieniowy danych multimedialnych)** – dokonaliśmy integracji modułu z Kontrolerem oraz przetestowaliśmy działanie samego silnika, jak i jego zachowanie w relacji z Kontrolerem. Testu dokonaliśmy na próbnej bazie **1000 plików multimedialnych** w formacie **`*.scm`** (pełne karty samochodów wraz ze skompresowanymi galeriami zdjęć), w zakresie prawidłowej dekompresji paczek i strumieniowego podsyłania kolejnych kart aut w **czasie rzeczywistym** podczas przesuwania ich w lewo i w prawo (*swipe*). Zweryfikowaliśmy jakość odczytu danych w postaci **jakości wyświetlanego obrazu (zdjęć pojazdów w formatach `jpg`, `png`, `webp`)** oraz płynności animacji interfejsu. Sprawdziliśmy także jakość komunikacji danych i kompatybilność z pozostałymi współpracującymi modułami systemu (jednoczesne pobieranie danych o dopłacie z modułu finansowego oraz statusu weryfikacji z modułu ogłoszeń). W pierwszych seriach testowych na 1000 plikach pojawiły się błędy spowodowane przeciążeniem Kontrolera i modułu dopasowywania przy strumieniowym odczycie zdjęć przez wielu symulowanych użytkowników naraz (występowały rozmycia obrazów, opóźnienia w doładowywaniu zdjęć oraz chwilowe przycięcia widoku). Usunęliśmy je poprzez analizę wyników obciążenia i dokonanie korekty programistycznej w kodzie (zoptymalizowaliśmy kolejkowanie żądań w Kontrolerze oraz wprowadziliśmy asynchroniczne doczytywanie zdjęć w tle). Następnie ponownie wykonaliśmy test na tych samych **1000 plikach `*.scm`**, który potwierdził pełną stabilność i płynność działania połączonego systemu.

---

## 7. Analiza SWOT projektu SwapCar (Lab 8)

### 7.1. Macierz analizy SWOT (Zadanie 1 z Lab 8)

W celu uporządkowania informacji strategicznych dotyczących platformy **SwapCar** oraz oceny jej pozycji przed przejściem do zaawansowanych testów w warunkach zbliżonych do rzeczywistych (TRL 6), przeprowadziliśmy **analizę SWOT**. Informacje podzieliliśmy na cztery klasyczne grupy (czynniki wewnętrzne i zewnętrzne oraz pozytywne i negatywne), przypisując po 4 kluczowe elementy do każdej kategorii (łącznie 16 elementów):

| Czynniki | **Pozytywne** | **Negatywne** |
| :--- | :--- | :--- |
| **Wewnętrzne** | **S – Mocne strony (*Strengths*)**<br>1. Nowoczesny interfejs *swipe* i intuicyjna obsługa<br>2. Dwustronny algorytm dopasowań z modułem dopłat<br>3. Lekka architektura MVC i autorskie formaty `*.scd`/`*.scm`<br>4. Dwufilarowy model biznesowy (*Freemium* B2C + licencje B2B) | **W – Słabe strony (*Weaknesses*)**<br>1. Niewielki, 3-osobowy zespół programistyczny i ograniczony czas<br>2. Brak początkowego kapitału na masową kampanię reklamową<br>3. Zależność wydajności od obciążenia serwera przy paczkach `*.scm`<br>4. Konieczność rozbudowy aplikacji webowej o natywne funkcje mobilne |
| **Zewnętrzne** | **O – Szanse (*Opportunities*)**<br>1. Duży rynek aut używanych w Polsce ($2$–$2{,}5\text{ mln}$ transakcji/rok)<br>2. Zainteresowanie komisów B2B upłynnianiem tzw. „leżaków placowych”<br>3. Pozyskanie dofinansowania (np. grant EU / inwestor zalążkowy)<br>4. Integracja z zewnętrznymi bazami historii pojazdów (API VIN) | **T – Zagrożenia (*Threats*)**<br>1. Silna dominacja tradycyjnych portali ogłoszeniowych (Otomoto, OLX)<br>2. Efekt „pustego placu” (niska liczba ofert na starcie w małych miastach)<br>3. Próby dodawania fałszywych ogłoszeń i zaniżania/zawyżania wycen aut<br>4. Zmiany prawne i podatkowe (np. PCC przy zamianie pojazdów) |

### 7.2. Szczegółowa analiza czynników z oszacowaniem prawdopodobieństwa procentowego (Zadanie 2 z Lab 8)

Do każdego elementu zidentyfikowanego w macierzy SWOT przypisaliśmy **oszacowane prawdopodobieństwo procentowe** jego wystąpienia, posiadania lub realizacji, wraz z komentarzem strategicznym określającym sposób wykorzystania szans i minimalizacji zagrożeń:

#### **S – Mocne strony (*Strengths*)**

1. **Nowoczesny interfejs *swipe* i intuicyjna obsługa (prawdopodobieństwo osiągnięcia/posiadania: $95\%$):**
   * *Komentarz:* Mechanizm przesuwania kart jest już zaimplementowany w prototypie webowym i jest doskonale znany użytkownikom z aplikacji randkowych. Wysokie prawdopodobieństwo oznacza, że ten atut jest niemal w pełni dopracowany i nie wymaga gruntownej przebudowy koncepcji.
2. **Dwustronny algorytm dopasowań z modułem liczenia dopłat (prawdopodobieństwo osiągnięcia/posiadania: $90\%$):**
   * *Komentarz:* W przeciwieństwie do zwykłych wyszukiwarek, nasz system kojarzy oferty obustronnie i automatycznie uwzględnia widełki dopłat finansowych. Testy na próbie 1000 ofert potwierdziły wysoką skuteczność i dokładność tego rozwiązania.
3. **Lekka architektura MVC i autorskie formaty paczek `*.scd` oraz `*.scm` (prawdopodobieństwo osiągnięcia/posiadania: $88\%$):**
   * *Komentarz:* Rozdzielenie danych tekstowych (`*.scd`) od skompresowanych multimediów (`*.scm`) oraz spięcie modułów centralnym Kontrolerem pozwala na szybkie strumieniowanie ofert przy niskim zużyciu zasobów serwera.
4. **Dwufilarowy model biznesowy łączący darmowy ruch B2C z płatnymi licencjami B2B (prawdopodobieństwo osiągnięcia/posiadania: $85\%$):**
   * *Komentarz:* Darmowy dostęp dla kierowców prywatnych gwarantuje szybki przyrost bazy ogłoszeń, podczas gdy abonamenty dla komisów zapewniają stabilne źródło przychodów bez zniechęcania użytkowników indywidualnych.

#### **W – Słabe strony (*Weaknesses*)**

1. **Niewielki, 3-osobowy zespół i ograniczone moce przerobowe (prawdopodobieństwo wystąpienia: $80\%$):**
   * *Komentarz:* Na etapie akademickim i wczesnego rozwoju zespół liczy 3 osoby łączące wiele ról. Aby przejść do pełnej komercjalizacji, konieczne będzie zaplanowanie docelowej struktury organizacyjnej (minimum 12–14 specjalistów) po pozyskaniu finansowania.
2. **Brak własnego kapitału na ogólnopolską kampanię marketingową (prawdopodobieństwo wystąpienia: $75\%$):**
   * *Komentarz:* Budżet początkowy wynosi $0\text{ zł}$ (praca na własnym sprzęcie). Słabość tę niwelujemy poprzez wirusowy charakter aplikacji (*matchowanie* w mediach społecznościowych) oraz bezpośredni kontakt z komisami samochodowymi.
3. **Wrażliwość serwera na jednoczesne przesyłanie wielu dużych plików multimedialnych `*.scm` (prawdopodobieństwo wystąpienia: $30\%$):**
   * *Komentarz:* Choć wprowadziliśmy limit $2\text{ MB}$ na zdjęcie i asynchroniczne buforowanie, przy nagłym skoku liczby użytkowników mogą wystąpić opóźnienia. Wymaga to zaawansowanych testów obciążeniowych na poziomie TRL 6.
4. **Konieczność dopracowania pełnej responsywności i wersji mobilnej (prawdopodobieństwo wystąpienia: $40\%$):**
   * *Komentarz:* Prototyp powstał jako aplikacja webowa. Ponieważ docelowa grupa B2C korzysta głównie ze smartfonów, przed wdrożeniem konieczne jest przetestowanie wersji mobilnej na różnych systemach operacyjnych (Android, iOS).

#### **O – Szanse (*Opportunities*)**

1. **Chłonny rynek wtórny w Polsce oraz potrzeba szybkiej rotacji aut w komisach B2B (prawdopodobieństwo wystąpienia: $80\%$):**
   * *Komentarz:* Wysokie ceny aut nowych sprawiają, że kierowcy i komisy aktywnie szukają alternatywnych form wymiany pojazdów bez zamrażania gotówki. Jest to bardzo wysoka szansa rynkowa, którą wykorzystujemy poprzez dedykowany pakiet *Komis PRO*.
2. **Integracja z zewnętrznymi bazami historii pojazdów po numerze VIN (prawdopodobieństwo wystąpienia: $70\%$):**
   * *Komentarz:* Udostępnienie płatnych raportów VIN bezpośrednio na karcie pojazdu podniesie wiarygodność ofert i wygeneruje dodatkowy strumień prowizji dla platformy.
3. **Pozyskanie zewnętrznego finansowania z funduszy UE lub funduszu VC dla projektów technologicznych (prawdopodobieństwo wystąpienia: $35\%$):**
   * *Komentarz:* Prowadzenie dokumentacji zgodnie ze skalą TRL zwiększa naszą wiarygodność wobec inwestorów. Aby podnieść tę szansę z $35\%$ do ponad $60\%$, musimy pomyślnie przejść testy na poziomie TRL 6 i przygotować kompletną dokumentację jakościową.
4. **Ekspansja platformy na rynki sąsiednie Europy Środkowo-Wschodniej (prawdopodobieństwo wystąpienia: $25\%$):**
   * *Komentarz:* Model wymiany samochodów można łatwo przenieść np. na rynek czeski czy słowacki po ustabilizowaniu pozycji w Polsce.

#### **T – Zagrożenia (*Threats*)**

1. **Silna pozycja rynkowa tradycyjnych portali ogłoszeniowych takich jak Otomoto czy OLX (prawdopodobieństwo wystąpienia: $60\%$):**
   * *Komentarz:* Duży gracz mógłby skopiować funkcję wymiany aut. Naszą obroną jest wysoka specjalizacja (algorytm obustronnych dopłat i giełda międzykomisowa) oraz szybkość wdrożenia jako pierwsi na rynku.
2. **Efekt „pustego placu” – zbyt mała liczba ofert w danym regionie na początku działalności (prawdopodobieństwo wystąpienia: $45\%$):**
   * *Komentarz:* Jeśli użytkownik po instalacji nie zobaczy lokalnych aut, może zrezygnować. Threat ten eliminujemy poprzez wcześniejsze pozyskanie komisów (darmowy *Pakiet Start*), które natychmiast zapełnią bazę setkami sprawdzonych pojazdów.
3. **Dodawanie nierzetelnych ogłoszeń lub celowe zawyżanie wartości auta przez użytkowników (prawdopodobieństwo wystąpienia: $50\%$):**
   * *Komentarz:* Zagrożenie to ograniczymy poprzez moduł walidacji parametrów, weryfikację numeru VIN, oznaczanie *„Zweryfikowanych Komisów”* oraz system ocen po kontakcie na czacie.
4. **Zmiany przepisów podatkowych dotyczących umów zamiany pojazdów i podatku PCC (prawdopodobieństwo wystąpienia: $10\%$):**
   * *Komentarz:* Ryzyko stosunkowo niskie, jednak wymaga stałego monitoringu prawnego i dodania w aplikacji prostego kalkulatora informacyjnego dotyczącego formalności przy zamianie aut.

---

## 8. Poziom TRL 6 – demonstracja prototypu w warunkach zbliżonych do rzeczywistego (Lab 9)

### 8.1. Zaawansowane testy serwerowe oraz badania użyteczności prototypu (Zadanie 1 z Lab 9)

Na szóstym poziomie **TRL** (ostatnim etapie *badań przemysłowych*) rozbudowaliśmy nasz zintegrowany w architekturze **MVC** prototyp platformy **SwapCar** do postaci w pełni funkcjonalnego modelu systemu (obejmującego aplikację webową oraz responsywną wersję mobilną dla systemów Android i iOS), który w zaawansowanym stopniu odzwierciedla docelowe warunki rynkowe.

Aplikacja osiągnęła pełną integrację wszystkich modułów (centralnego **Kontrolera**, **Modułu dodawania i sprawdzania ogłoszeń**, **Modułu liczenia dopłat** oraz **Silnika Matchingowego** wraz z czatem po uzyskaniu *matcha*) i została poddana kompleksowym badaniom pod kątem:
* obciążenia generowanego na serwerach (wielowątkowe przetwarzanie zapytań, kompresja i strumieniowa dekompresja paczek **`*.scd`** oraz **`*.scm`**),
* jakości zwracanych wyników dopasowań i poprawności obliczeń finansowych,
* stabilności działania na urządzeniach stacjonarnych i mobilnych pod kątem różnych wersji systemów operacyjnych i przeglądarek,
* intuicyjności obsługi w ramach badań użyteczności (*usability testing*).

Zgodnie z założeniami etapu testy podzieliliśmy na dwie główne grupy:

1. **Testy serwerowe (obciążeniowe i długotrwałe):**
   * Polegały na symulowaniu maksymalnego obciążenia dla jednoczesnej obsługi **$50\,000$ aktywnych użytkowników** platformy **SwapCar** wykonujących w czasie rzeczywistym operacje przeglądania i przesuwania kart (*swipe*), dekompresji strumieniowej paczek multimedialnych **`*.scm`**, przeliczania dopłat finansowych **`*.scd`** oraz wysyłania wiadomości na czacie.
   * Testy trwały nieprzerwanie przez **10 dni** bez jakichkolwiek przerw technicznych w celu realizacji pełnych prób obciążeniowych.
   * Przez cały okres 10 dni system podlegał nieustannemu monitoringowi telemetrycznemu (obciążenie CPU, zajętość pamięci RAM, przepustowość łącza, czasy odpowiedzi endpointów Kontrolera), a wyniki kontrolne były automatycznie zapisywane w równych interwałach czasowych (co 15 minut).
   * W trakcie testów serwerowych zweryfikowaliśmy i potwierdziliśmy, że:
     * dane i zdjęcia w systemie bazowym po kompresji i strumieniowej dekompresji paczek **`*.scm`** zachowują odpowiednią jakość wizualną i pełną spójność parametrów technicznych pojazdów,
     * wydajność całego systemu utrzymuje się na przewidywanym, wysokim poziomie przez pełne 10 dni i nie występuje zjawisko *dywergencji wydajnościowej* (stopniowego zwalniania serwera lub wycieków pamięci przy długotrwałej pracy).

2. **Testy użytkowe (*usability testing* oraz weryfikacja jakości danych):**
   * Pierwsza część badań polegała na ponownej, masowej weryfikacji jakości algorytmu na próbce **$30\,000$ plików** ogłoszeń samochodowych (zarówno danych tekstowych **`*.scd`**, jak i pełnych pakietów ze zdjęciami **`*.scm`**) poddanych procesowi walidacji, kompresji, indeksowania w silniku matchingowym, a następnie dekompresji i prezentacji na kartach ofert. Badanie potwierdziło, że jakość danych oraz trafność obustronnych dopasowań utrzymuje się na stabilnym, zakładanym poziomie powyżej $99{,}8\%$ bez utraty pakietów.
   * Druga część polegała na przeprowadzeniu **testów na rzeczywistych użytkownikach**, ponieważ badania *usability* dostarczają bezpośredniej wiedzy o tym, jak zachowują się prawdziwi odbiorcy niebiorący udziału w tworzeniu oprogramowania. Do badania zaangażowaliśmy grupę **$200$ niezależnych testerów** nieznających wcześniej aplikacji **SwapCar** ($160$ kierowców prywatnych z segmentu B2C oraz $40$ przedstawicieli komisów samochodowych z segmentu B2B).
   * Uczestnicy otrzymali zestawy danych kontrolnych (parametry pojazdów i zdjęcia testowe) oraz instrukcje krok po kroku obejmujące: instalację/uruchomienie aplikacji na komputerze lub smartfonie, rejestrację konta, dodanie ogłoszenia auta, określenie preferencji oraz budżetu dopłaty, przeglądanie kart w formule *swipe*, nawiązanie dopasowania (*match*) oraz przeprowadzenie negocjacji na czacie.
   * Podczas badania zebraliśmy szczegółową informację zwrotną (*feedback*) dotyczącą zrozumienia interfejsu oraz ergonomii formularzy. Użytkownicy pozytywnie ocenili czytelność mechanizmu dopłat i płynność przesuwania kart, zgłaszając jedynie drobne uwagi ergonomiczne (np. potrzebę dodania suwaka do szybszego ustawiania kwoty maksymalnej dopłaty na ekranach smartfonów), które zakwalifikowaliśmy do korekt programistycznych na kolejnym, VII poziomie gotowości technologicznej.

**Efekt końcowy VI poziomu TRL:**
W efekcie końcowym VI poziomu gotowości technologicznej uzyskaliśmy **w pełni zintegrowaną i przetestowaną wersję aplikacji SwapCar (zarówno webową, jak i mobilną)** działającą w warunkach odwzorowujących rzeczywiste obciążenie rynkowe. Potwierdziliśmy wysoką stabilność infrastruktury serwerowej oraz zrozumiałość działania interfejsu dla docelowych użytkowników B2C i B2B, przygotowując listę drobnych korekt programistycznych do wdrożenia na poziomie TRL 7.

### 8.2. Ryzyka technologiczne dla VI poziomu TRL i sposoby ich eliminacji (Zadanie 2 z Lab 9)

Podczas realizacji zaawansowanych badań na poziomie TRL 6 zidentyfikowaliśmy kluczowe ryzyka technologiczne oraz wdrożyliśmy skuteczne mechanizmy ich eliminacji:

1. **Ryzyko technologiczne 1:** Trudności z wiernym odwzorowaniem rzeczywistego, nierównomiernego obciążenia szczytowego w testach serwerowych dla strumieniowej dekompresji paczek **`*.scm`** oraz jednoczesnego przeliczania dopłat przez $50\,000$ użytkowników (ryzyko, że syntetyczny ruch testowy będzie zbyt jednorodny i nie wykryje wąskich gardeł w wieczornych godzinach szczytu).
   * **Rozwiązanie:** Wykorzystaliśmy specjalistyczne zewnętrzne narzędzia do testów obciążeniowych (*Apache JMeter* oraz *k6*) połączone z autorskimi skryptami symulującymi losowe zachowania użytkowników (zmienna częstotliwość przesuwania kart *swipe*, nagłe skoki zapytań w godzinach 18:00–22:00 oraz jednoczesne wgrywanie zdjęć przez komisy).
2. **Ryzyko technologiczne 2:** Różnice w obsłudze gestów dotykowych (*swipe* w lewo/prawo) oraz renderowaniu skompresowanych zdjęć `webp` na starszych wersjach systemów mobilnych (Android/iOS) podczas testów prowadzonych przez grupę 200 niezależnych użytkowników.
   * **Rozwiązanie:** Wprowadziliśmy w warstwie widoku (View) uniwersalną obsługę zdarzeń dotykowych (*Touch Events* oraz *Pointer Events*) wraz z alternatywnymi przyciskami akcji (*„Odrzuć”* / *„Wymień się”*) oraz mechanizmem automatycznego przełączania formatu obrazu na `jpg` w przypadku starszych przeglądarek mobilnych.

---

## 9. Zarządzanie jakością i struktura organizacyjna projektu (Lab 10)

### 9.1. Metryka produktu z mierzalnymi parametrami jakościowymi (Zadanie 1 z Lab 10)

Aby obiektywnie kontrolować jakość platformy **SwapCar**, weryfikować osiągnięcie kamieni milowych w punktach kontrolnych oraz mieć jednoznaczny punkt odniesienia podczas testów wdrożeniowych, opracowaliśmy **metrykę produktu** zawierającą konkretne, mierzalne parametry techniczne i wydajnościowe:

| Parametr jakościowy | Metryka produktu: Platforma wymiany samochodów SwapCar |
| :--- | :--- |
| **Wydajność kompresji i zapisu ogłoszeń (`*.scm`)** | $45\text{ MB/s}$ |
| **Wydajność strumieniowej dekompresji kart (`*.scm`)** | $60\text{ MB/s}$ |
| **Czas odpowiedzi Silnika Matchingowego (załadowanie kolejnej karty)** | $\le 120\text{ ms}$ |
| **Czas wyliczenia dopłat finansowych dla próby $1000$ ofert (`*.scd`)** | $\le 50\text{ ms}$ |
| **Maksymalny rozmiar pojedynczego zdjęcia po kompresji** | $\le 2\text{ MB}$ |
| **Maksymalny rozmiar aplikacji mobilnej / klienta PWA** | $28\text{ MB}$ |
| **Maksymalna liczba jednoczesnych użytkowników bez degradacji usług** | $50\,000\text{ użytkowników}$ |
| **Gwarantowana dostępność systemu (SLA)** | $99{,}5\%$ |
| **Obsługiwane systemy operacyjne i środowiska** | Windows, Linux, macOS, Android, iOS (Chrome, Firefox, Edge, Safari) |

### 9.2. Diagram struktury organizacyjnej i zarządczej projektu (Zadanie 2 z Lab 10)

Na potrzeby przejścia projektu **SwapCar** z fazy badawczej do pełnej realizacji i komercjalizacji rynkowej dobraliśmy **strukturę sztabowo-liniową** organizacji projektu. Model ten łączy wyraźne, jednoosobowe kierownictwo liniowe nad zespołami technicznymi (co zapewnia szybkość podejmowania decyzji programistycznych i jasną odpowiedzialność za moduły) ze wsparciem wyspecjalizowanych komórek sztabowych (doradzających w zakresie jakości, prawa/RODO oraz rozwoju biznesowego B2B/B2C).

Docelowa organizacja projektowo-zarządcza liczy **14 osób** (spełniając wymóg minimum 12 osób):

```text
                        +-----------------------------------+
                        |   KOMITET STERUJĄCY / SPONSOR     |
                        |  (Nadzór strategiczny - 1 os.)    |
                        +-----------------+-----------------+
                                          |
                                          v
                        +-----------------------------------+
                        |   KIEROWNIK PROJEKTU (PM)         |
                        |  (Zarządzanie operacyjne - 1 os.) |
                        +-----------------+-----------------+
                                          |
         +--------------------------------+--------------------------------+
         | (Komórki sztabowe - doradcze)                                   | (Linia zarządcza)
         v                                                                 v
+-----------------------------------+                             +-----------------------------------+
| SZTAB: SPECJALISTA DS. JAKOŚCI    |                             |   ARCHITEKT SYSTEMU / TECH LEAD   |
| I ZGODNOŚCI PRAWNEJ / RODO (1 os.)|                             |   (Lider Techniczny MVC - 1 os.)  |
+-----------------------------------+                             +-----------------+-----------------+
         |                                                                          |
         v                                    +------------------+------------------+------------------+
+-----------------------------------+         |                  |                  |                  |
| SZTAB: ANALITYK BIZNESOWY         |         v                  v                  v                  v
| I ROZWÓJ B2B/B2C (1 os.)          |  +--------------+   +--------------+   +--------------+   +--------------+
+-----------------------------------+  | ZESPÓŁ       |   | ZESPÓŁ       |   | ZESPÓŁ       |   | ZESPÓŁ QA    |
                                       | BACKEND      |   | FRONTEND     |   | DEVOPS I     |   | I TESTÓW     |
                                       | (3 os.)      |   | I MOBILE     |   | BAZ DANYCH   |   | UŻYTKOWYCH   |
                                       |              |   | (3 os.)      |   | (1 os.)      |   | (2 os.)      |
                                       +--------------+   +--------------+   +--------------+   +--------------+
                                       * Kontroler MVC    * Interfejs Web    * Chmura/Serwery   * Testy autom.
                                       * Silnik Matching  * Android / iOS    * Bazy *.scd/*.scm * Usability
                                       * Moduł Dopłat     * Gest Swipe/UI    * Monitoring SLA   * Raporty QA
```

*Zestawienie liczebności organizacji: Komitet Sterujący ($1\text{ os.}$) + Kierownik Projektu ($1\text{ os.}$) + Komórki sztabowe ($2\text{ os.}$) + Architekt Systemu ($1\text{ os.}$) + Zespół Backend ($3\text{ os.}$) + Zespół Frontend i Mobile ($3\text{ os.}$) + Zespół DevOps i Baz Danych ($1\text{ os.}$) + Zespół QA ($2\text{ os.}$) = **$14\text{ osób}$**.*

### 9.3. Charakterystyka unikalnych ról w zespole projektowym (Zadanie 3 z Lab 10)

Poniżej przedstawiono opis wszystkich **9 unikalnych ról** występujących w powyższej strukturze organizacyjnej projektu **SwapCar**:

1. **Komitet Sterujący / Sponsor Projektu (1 osoba):**
   * Pełni najwyższą funkcję nadzorczą w projekcie, zatwierdza przejście pomiędzy kolejnymi poziomami gotowości technologicznej (TRL) oraz podejmuje kluczowe decyzje finansowe i strategiczne. Monitoruje zgodność realizowanych prac z założeniami biznesowymi komercjalizacji B2C i B2B oraz akceptuje zmiany wykraczające poza ustalone granice tolerancji Kierownika Projektu.
2. **Kierownik Projektu – Project Manager (1 osoba):**
   * Odpowiada za bieżące operacyjne zarządzanie całym przedsięwzięciem, harmonogramem, budżetem oraz alokacją zadań pomiędzy zespołami. Koordynuje współpracę pomiędzy komórkami sztabowymi a zespołem technicznym, zarządza rejestrem ryzyk projektowych oraz odpowiada za terminowe przygotowanie dokumentacji sprawozdawczej.
3. **Specjalista ds. Kontroli Jakości i Zgodności Prawnej / RODO (1 osoba – komórka sztabowa):**
   * Doradza Kierownikowi Projektu w zakresie przestrzegania norm jakościowych (w tym weryfikacji metryki produktu) oraz przepisów dotyczących ochrony danych osobowych użytkowników i numerów VIN pojazdów. Nadzoruje zgodność regulaminów świadczenia usług drogą elektroniczną, polityki prywatności oraz procedur bezpieczeństwa informacji z obowiązującym prawem.
4. **Analityk Biznesowy i Specjalista ds. Komercjalizacji B2B/B2C (1 osoba – komórka sztabowa):**
   * Odpowiada za analizę potrzeb rynku motoryzacyjnego, opracowywanie wymagań funkcjonalnych dla komisów samochodowych oraz kierowców indywidualnych, a także optymalizację cenników abonamentowych i pakietów *Freemium*. Wspiera Kierownika Projektu w przygotowywaniu ofert partnerskich dla sieci komisów oraz raportów rynkowych dla inwestorów.
5. **Architekt Systemu / Tech Lead (1 osoba):**
   * Sprawuje bezpośredni nadzór techniczny nad spójnością architektury **MVC (Model-Widok-Kontroler)** całej platformy **SwapCar** oraz wyznacza standardy wytwarzania oprogramowania. Projektuje interfejsy komunikacyjne (API) pomiędzy centralnym Kontrolerem a modułami podrzędnymi, przeprowadza przeglądy kodu (*code review*) i rozwiązuje najbardziej złożone problemy wydajnościowe.
6. **Programista Backend (3 osoby – traktowane jako jedna unikalna rola):**
   * Odpowiada za implementację i optymalizację logiki serwerowej platformy, w tym centralnego **Kontrolera**, **Modułu walidacji ogłoszeń**, **Modułu liczenia dopłat** oraz **Silnika Matchingowego**. Tworzy algorytmy odpowiedzialne za przetwarzanie ustrukturyzowanych danych **`*.scd`**, wielowątkowe punktowanie dopasowań pojazdów oraz obsługę czasu rzeczywistego dla czatu użytkowników.
7. **Programista Frontend i Mobile (3 osoby – traktowane jako jedna unikalna rola):**
   * Projektuje i programuje warstwę widoku (*View*) aplikacji webowej oraz wersji mobilnej dla systemów Android i iOS, dbając o płynność animacji przesuwania kart (*swipe*) i responsywność interfejsu. Implementuje formularze dodawania ogłoszeń, kalkulatory dopłat oraz mechanizmy asynchronicznego doczytywania i wyświetlania galerii zdjęć z paczek **`*.scm`**.
8. **Inżynier DevOps i Administrator Baz Danych (1 osoba):**
   * Zarządza infrastrukturą chmurową, konfiguracją serwerów produkcyjnych i testowych oraz automatyzacją procesów wdrażania kodu (CI/CD). Odpowiada za wydajność, kopie zapasowe i integralność baz danych przechowujących pakiety **`*.scd`** oraz **`*.scm`**, a także za ciągły monitoring obciążenia i utrzymanie gwarantowanej dostępności usługi (SLA na poziomie $99{,}5\%$).
9. **Inżynier QA / Tester Oprogramowania i Użyteczności (2 osoby – traktowane jako jedna unikalna rola):**
   * Przygotowuje scenariusze testowe, programuje testy automatyczne sprawdzające poprawność komunikacji w architekturze MVC oraz przeprowadza testy obciążeniowe i wydajnościowe. Organizuje również badania użyteczności (*usability testing*) z udziałem zewnętrznych testerów, dokumentuje wykryte błędy i weryfikuje ich skuteczną eliminację przed każdym wydaniem nowej wersji aplikacji.

---

## 10. Podsumowanie

Na poziomach **TRL 1–6** rozwinęliśmy platformę **SwapCar** od wstępnej koncepcji technologicznej, poprzez budowę i testy pojedynczych modułów (TRL 3), badania prototypu w warunkach laboratoryjnych (TRL 4), opracowanie modelu biznesowego B2C/B2B (Lab 6), integrację w architekturze **MVC** na próbie 1000 plików (TRL 5) i **analizę SWOT** (Lab 8), aż po zaawansowane testy serwerowe dla $50\,000$ użytkowników oraz badania użyteczności z udziałem $200$ niezależnych testerów (TRL 6).

W ramach obecnego etapu (**Lab 10**) sformalizowaliśmy proces **zarządzania jakością** poprzez utworzenie **metryki produktu** zawierającej 9 precyzyjnych, mierzalnych parametrów (m.in. wydajność kompresji $45\text{ MB/s}$, dekompresji $60\text{ MB/s}$, czas odpowiedzi karty $\le 120\text{ ms}$ oraz SLA $99{,}5\%$). Ponadto zaprojektowaliśmy docelową, **14-osobową strukturę sztabowo-liniową** organizacji projektu wraz ze szczegółowym opisem wszystkich 9 unikalnych ról, co przygotowuje zespół do realizacji końcowych prac rozwojowych (TRL 7–9) i pełnej komercjalizacji rynkowej.