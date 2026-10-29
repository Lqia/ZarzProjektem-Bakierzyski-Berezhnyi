# SPRAWOZDANIE Z PROJEKTU
## **SwapCar – platforma do wymiany samochodów**

**Przedmiot:** Poziomy gotowości technologicznej
**Etap projektu:** Punkt Kontrolny – Struktura dokumentu oraz komercjalizacja i grupa docelowa (Lab 6)
**Aktualny poziom gotowości technologicznej:** *TRL 4 (PGT IV)*

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
6. **Podsumowanie**

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

1. **Ryzyko (prawdopodobieństwo: 65%):** Brak poprawnej komunikacji pomiędzy modułami (np. moduł dopasowywania ofert nie pobierał na czas wyliczonych kwot z modułu dopłat).
   * **Rozwiązanie:** Zastosowaliśmy zaprogramowane *testy automatyczne* sprawdzające przepływ informacji oraz uporządkowaliśmy kod według wzorca architektonicznego **MVC – Model-View-Controller** (*Model-Widok-Kontroler*).
2. **Ryzyko (prawdopodobieństwo: 50%):** Niekompatybilność przesyłanych danych pomiędzy modułami (np. formularz wysyłał cenę auta jako zwykły tekst ze spacjami, a moduł liczenia dopłat oczekiwał czystej liczby, przez co prototyp wyrzucał błąd).
   * **Rozwiązanie:** Dokonaliśmy dokładnego *debugowania kodu* oraz zastosowaliśmy metodę eliminacji wszystkich błędów i nieścisłości związanych z przesyłaniem danych „krok po kroku” (ujednoliciliśmy format przesyłanych danych do standardu **JSON**).
3. **Ryzyko (prawdopodobieństwo: 35%):** Algorytm dopasowujący i ładujący zdjęcia mógł działać inaczej (z inną szybkością) na różnych jednostkach CPU oraz różnych przeglądarkach internetowych użytkowników.
   * **Rozwiązanie:** Rozszerzyliśmy testy w badaniu o inne rodzaje jednostek CPU (przetestowaliśmy prototyp na wszystkich 3 laptopach w zespole oraz na telefonie) i na kilku popularnych przeglądarkach (*Chrome, Firefox, Edge*).
4. **Ryzyko (prawdopodobieństwo: 20%):** Przeciążenie pamięci RAM serwera przy jednoczesnym przesyłaniu wielu zdjęć samochodów w formacie `*.scm`.
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
1. **Klienci indywidualni (segment B2C)** – w skład tej grupy wchodzą prywatni właściciele samochodów i aktywni kierowcy w wieku **18–45 lat**, którzy średnio lub dobrze radzą sobie z obsługą smartfona i komputera. Są to osoby, które chcą szybko zmienić samochód na inny (np. mniejszy do miasta, większy dla rodziny lub po prostu nowszy model za dopłatą), bez konieczności wielotygodniowego czekania na kupca z gotówką na tradycyjnych portalach. Oszacowaliśmy, że w **ok. 80% są to mężczyźni**, w tym fani motoryzacji, którzy lubią często zmieniać auta. Do tej grupy skierowaliśmy podstawową aplikację wymiany w formule *swipe* (przesuwania kart).
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

## 6. Podsumowanie

Na poziomie **TRL 1** opracowaliśmy koncepcję aplikacji **SwapCar**, określiliśmy jakie dane o autach są potrzebne i jak działa system dopasowań oraz dopłat. Na poziomie **TRL 2** ustaliliśmy architekturę aplikacji internetowej, przygotowaliśmy potrzebny sprzęt, programy i dane testowe. Na poziomie **TRL 3** przetestowaliśmy trzy główne moduły systemu osobno, sprawdziliśmy ich wydajność i ułożyliśmy pracę według *7 zasad PRINCE2*.

Na poziomie **TRL 4** połączyliśmy moduły w działający prototyp i przebadaliśmy go w warunkach laboratoryjnych na zestawach kontrolnych po 100 plików (**`*.scd`** oraz **`*.scm`**) w 100 seriach testów. Wykryliśmy drobne odchylenia w działaniu algorytmów, wprowadziliśmy poprawki (m.in. *buforowanie kart* i *optymalizację zdjęć*), dzięki czemu zminimalizowaliśmy błędy. Określiliśmy też główne ryzyka techniczne wraz z procentowym priorytetem i wdrożyliśmy rozwiązania pozwalające na ich wyeliminowanie.

W ramach obecnego **Punktu Kontrolnego (Lab 6)** uporządkowaliśmy strukturę naszego dokumentu zgodnie z wytycznymi edytorskimi (okładka, spis treści, nagłówki i wyróżnienia tekstu) oraz opracowaliśmy pełny **plan komercjalizacji projektu**. Zdefiniowaliśmy dwie grupy docelowe (*prywatnych kierowców oraz komisy samochodowe*), oszacowaliśmy wielkość rynku w Polsce i stworzyliśmy dwufilarowy model biznesowy łączący darmowe budowanie rozpoznawalności marki (*Freemium*) z płatnymi opcjami promowania oraz abonamentami licencyjnymi dla firm.