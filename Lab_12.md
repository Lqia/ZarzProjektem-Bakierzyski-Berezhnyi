# SPRAWOZDANIE Z PROJEKTU
## **SwapCar – platforma do wymiany samochodów**
### *Symulacja projektu informatycznego realizacji platformy do wymiany samochodów SwapCar*

**Przedmiot:** Zarządzanie Projektem Informatycznym – Poziomy gotowości technologicznej
**Etap projektu:** Punkt Kontrolny – Zespół projektowy, budżet i opłacalność wdrożenia (Lab 12)
**Aktualny poziom gotowości technologicznej:** *TRL 9 (PGT IX)*

---

## **Spis treści**

1. **Zespół projektowy** *(Zadanie 1 z Lab 12 – doświadczenia członków zespołu z Lab 1)*
2. **Poziom TRL 1 – koncepcja projektu**
   2.1. Opis pomysłu
   2.2. Główne funkcje aplikacji
   2.3. Działanie algorytmu dopasowywania
   2.4. Gdzie można to wykorzystać
3. **Poziom TRL 2 – rozwinięcie koncepcji i zasoby**
   3.1. Założenia drugiej fazy
   3.2. Wykorzystane zasoby
   3.3. Zrealizowany plan przygotowawczy
4. **Poziom TRL 3 – testy założeń i osobnych elementów (Badania przemysłowe)**
   4.1. Potwierdzenie założeń koncepcji (Zadanie 1 z Lab 4)
   4.2. Projekt SwapCar a 7 pryncypiów metodyki PRINCE2 (Zadanie 2 z Lab 4)
5. **Poziom TRL 4 – badania prototypu w warunkach laboratoryjnych**
   5.1. Weryfikacja koncepcji w warunkach laboratoryjnych (Zadanie 1 z Lab 5)
   5.2. Określenie ryzyk dla IV poziomu TRL i sposoby ich eliminacji (Zadanie 2 z Lab 5)
6. **Punkt Kontrolny – Jakość dokumentacji oraz plan komercjalizacji (Lab 6)**
   6.1. Uporządkowanie struktury dokumentu (Zadanie 1 z Lab 6)
   6.2. Grupa docelowa oraz model biznesowy i komercjalizacja produktu (Zadanie 2 z Lab 6)
7. **Poziom TRL 5 – weryfikacja koncepcji w środowisku zbliżonym do rzeczywistego (Lab 7)**
   7.1. Integracja komponentów za pomocą wzorca MVC oraz testy na zwiększonej próbie (Zadanie 1 z Lab 7)
8. **Analiza SWOT projektu SwapCar (Lab 8)**
   8.1. Macierz analizy SWOT (Zadanie 1 z Lab 8)
   8.2. Szczegółowa analiza czynników z oszacowaniem prawdopodobieństwa procentowego (Zadanie 2 z Lab 8)
9. **Poziom TRL 6 – demonstracja prototypu w warunkach zbliżonych do rzeczywistego (Lab 9)**
   9.1. Zaawansowane testy serwerowe oraz badania użyteczności prototypu (Zadanie 1 z Lab 9)
   9.2. Ryzyka technologiczne dla VI poziomu TRL i sposoby ich eliminacji (Zadanie 2 z Lab 9)
10. **Zarządzanie jakością i struktura organizacyjna projektu (Lab 10)**
    10.1. Metryka produktu z mierzalnymi parametrami jakościowymi (Zadanie 1 z Lab 10)
    10.2. Diagram struktury organizacyjnej i zarządczej projektu (Zadanie 2 z Lab 10)
    10.3. Charakterystyka unikalnych ról w zespole projektowym (Zadanie 3 z Lab 10)
11. **Prace rozwojowe – poziomy TRL 7, TRL 8 i TRL 9 (Lab 11)**
    11.1. Poziom TRL 7 – demonstracja prototypu w warunkach operacyjnych (Zadanie 1 z Lab 11)
    11.2. Poziom TRL 8 – zakończenie badań i demonstracja ostatecznej formy technologii (Zadanie 2 z Lab 11)
    11.3. Poziom TRL 9 – gotowość na komercjalizację (Zadanie 3 z Lab 11)
12. **Punkt Kontrolny – Budżet projektu i opłacalność wdrożenia / Cash Flow (Lab 12)**
    12.1. Założenia finansowe i horyzont symulacji (24 miesiące)
    12.2. Filar I – Koszty jednorazowe (inwestycja początkowa)
    12.3. Filar II – Koszty stałe (miesięczne)
    12.4. Filar III – Przychody ze sprzedaży licencji B2B i usług B2C
    12.5. Analiza Cash Flow (24 miesiące), próg rentowności i zwrot inwestycji
13. **Podsumowanie**

---

## 1. Zespół projektowy

Projekt **SwapCar** realizowany jest przez 3-osobowy zespół studentów informatyki łączących kompetencje z zakresu projektowania interfejsów webowych i mobilnych, programowania logiki serwerowej i baz danych oraz zapewnienia jakości i zarządzania projektem. Poniżej zestawiono doświadczenia członków zespołu (opracowane na podstawie **Lab 1**):

* **[Imię i Nazwisko – Członek Zespołu 1] – Kierownik Projektu / Frontend & UI Developer:**
  * *Doświadczenie i kompetencje:* Doświadczenie w projektowaniu responsywnych aplikacji webowych (HTML5, CSS3, Tailwind CSS, JavaScript/React) oraz makiet UX/UI w środowisku Visual Studio Code. Praktyczna znajomość pracy z systemem kontroli wersji GitHub oraz podstaw zarządzania harmonogramem i dokumentacją projektową według zasad PRINCE2. W projekcie **SwapCar** odpowiada za warstwę widoku (*View*), płynność mechanizmu przesuwania kart (*swipe*), spójność dokumentacji oraz pilnowanie terminów etapów TRL.
* **[Imię i Nazwisko – Członek Zespołu 2] – Architekt Backendu, Baz Danych i Algorytmu Matchingowego:**
  * *Doświadczenie i kompetencje:* Praktyczne doświadczenie w programowaniu aplikacji serwerowych, projektowaniu relacyjnych i dokumentowych baz danych oraz budowie interfejsów REST API. Zainteresowania i wcześniejsze projekty akademickie obejmują optymalizację algorytmów wyszukiwania, przetwarzanie wielowątkowe oraz kompresję danych. W projekcie **SwapCar** odpowiada za centralny **Kontroler MVC**, formaty **`*.scd`/`*.scm`**, **Moduł liczenia dopłat** oraz **Silnik Matchingowy**.
* **[Imię i Nazwisko – Członek Zespołu 3] – Inżynier QA, Testów oraz Analizy Biznesowej:**
  * *Doświadczenie i kompetencje:* Doświadczenie w tworzeniu scenariuszy testowych, debugowaniu kodu, testach integracyjnych i wydajnościowych oraz walidacji formularzy i bezpieczeństwa danych. Praktyczna znajomość analizy rynkowej, modelowania procesów biznesowych i przygotowywania kalkulacji finansowych w arkuszach kalkulacyjnych. W projekcie **SwapCar** odpowiada za **Moduł sprawdzania ogłoszeń**, testy laboratoryjne i obciążeniowe (TRL 4–6), organizację badań *usability* oraz opracowanie modelu komercjalizacji i budżetu.

*(Uwaga edytorska: w powyższych polach `[Imię i Nazwisko]` należy wstawić dokładne dane osobowe oraz ewentualne indywidualne detale z oryginalnego pliku z Lab 1).*

---

## 2. Poziom TRL 1 – koncepcja projektu

### 2.1. Opis pomysłu

**SwapCar** to aplikacja umożliwiająca *bezpośrednią wymianę samochodów* między użytkownikami. Działanie aplikacji przypomina aplikacje randkowe (np. Tinder): użytkownicy przesuwają karty samochodów w lewo lub w prawo, aby odrzucić ofertę lub wyrazić zainteresowanie.

W odróżnieniu od zwykłych portali ogłoszeniowych, które skupiają się na sprzedaży, w **SwapCar** chodzi o *wymianę aut sztuka za sztukę lub z dopłatą*, jeśli samochody mają różną wartość.

Użytkownicy dodają ogłoszenia swoich aut, wpisują ich parametry i zaznaczają, jakiego samochodu szukają. Gdy obie strony polubią swoje auta, aplikacja tworzy *parę (match)*, co pozwala im porozmawiać na czacie i dogadać szczegóły wymiany.

### 2.2. Główne funkcje aplikacji

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

### 2.3. Działanie algorytmu dopasowywania

Algorytm bierze pod uwagę trzy rzeczy:
1. **Preferencje początkowe** – to, co użytkownik zaznaczył w filtrach na starcie oraz ile może dopłacić.
2. **Zachowanie w aplikacji** – jakie auta użytkownik najczęściej przesuwa w prawo, a jakie odrzuca (np. jeśli ciągle odrzuca diesle, aplikacja zaczyna pokazywać więcej benzyniaków).
3. **Zgodność w dwie strony** – nie wystarczy, że użytkownikowi A podoba się auto B. Algorytm sprawdza, czy auto A ma szansę spodobać się użytkownikowi B i czy zgadzają się ich *oczekiwania finansowe*.

### 2.4. Gdzie można to wykorzystać

1. **Wymiana aut między zwykłymi kierowcami** (*osoby prywatne*).
2. **Wymiana aut między komisami samochodowymi** (*segment B2B*).
3. **Podpowiadanie pasujących ofert** na podstawie wyborów użytkownika.
4. **Pomoc w wycenie aut** i sugerowaniu kwoty dopłaty.
5. **Sprawdzanie historii pojazdów** po numerze *VIN*.

---

## 3. Poziom TRL 2 – rozwinięcie koncepcji i zasoby

### 3.1. Założenia drugiej fazy

Pierwsza wersja **SwapCar** została zaprojektowana jako *strona internetowa (aplikacja webowa)*, którą w kolejnych krokach rozwiniemy o wersję mobilną na telefony.

### 3.2. Wykorzystane zasoby

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

### 3.3. Zrealizowany plan przygotowawczy

1. Rozrysowaliśmy wygląd aplikacji.
2. Zaplanowaliśmy bazę danych.
3. Opracowaliśmy założenia *algorytmu dopasowywania ofert*.
4. Przygotowaliśmy środowisko pod pierwszą wersję strony.
5. Zgromadziliśmy przykładowe dane o autach do testów.

---

## 4. Poziom TRL 3 – testy założeń i osobnych elementów (Badania przemysłowe)

### 4.1. Potwierdzenie założeń koncepcji (Zadanie 1 z Lab 4)

Na trzecim poziomie **TRL** sprawdziliśmy w praktyce, czy nasz pomysł ma sens i przetestowaliśmy osobno najważniejsze kawałki (*moduły*) naszego systemu, zanim połączyliśmy je w jedną całość.

W ramach tego etapu zrealizowaliśmy i przetestowaliśmy następujące elementy:

* **Moduł dodawania i sprawdzania ogłoszeń** – odpowiada za przyjmowanie danych o samochodach z formularza. Na tym etapie położyliśmy nacisk na to, żeby użytkownicy nie mogli wpisać głupot (np. ujemnego przebiegu, rocznika z przyszłości albo pustej ceny). Moduł został wyposażony w *mechanizm sprawdzający kompletność danych* przed zapisaniem ich do bazy. W ramach testów wrzuciliśmy do niego paczkę przykładowych, częściowo błędnych ogłoszeń – moduł poprawnie wyłapał wszystkie błędy i nie przepuścił niekompletnych ofert.
* **Moduł liczenia dopłat** – kawałek kodu, który porównuje ceny dwóch samochodów i sprawdza, czy użytkownicy są w stanie się dogadać finansowo. Zadaniem modułu jest policzenie różnicy w cenie między autem A i autem B oraz sprawdzenie, czy ta różnica mieści się w kwocie, którą jedna ze stron zadeklarowała jako *maksymalną dopłatę*. W testach laboratoryjnych opracowaliśmy system walidacji i sprawdziliśmy go na przykładowych parach aut. Określiliśmy w procentach **współczynnik zgodności** i potwierdziliśmy, że moduł poprawnie łączy oferty z różnymi widełkami cenowymi, odrzucając auta, na które użytkowników nie stać.
* **Moduł dopasowywania ofert (Silnik Matchingowy)** – najważniejszy element, który odpowiada za podsyłanie kart z samochodami w *czasie rzeczywistym*. W tym module zweryfikowaliśmy, jak szybko system potrafi przejrzeć bazę ogłoszeń i wybrać te, które pasują do filtrów użytkownika. Zbadaliśmy przy tym **obciążenie procesora (CPU)** i **zużycie pamięci RAM** na naszym serwerze testowym podczas symulacji, w której wielu użytkowników naraz szybko przesuwało karty w lewo i w prawo. Zastosowaliśmy tu pewną tolerancję – założyliśmy, że *płynność ładowania kart* i zgodność głównych parametrów (cena, paliwo, rocznik) ma pierwszeństwo przed mniej ważnymi detalami (np. kolor). Badania pozwoliły nam znaleźć optymalny balans między trafnością podpowiedzi a szybkością działania serwera.

Na tym etapie określiliśmy również prosty sposób liczenia punktów dopasowania (*model matematyczny oparty na wagach*), który pozwolił na **wielowątkowe wykonywanie obliczeń**. Każda zgodna cecha auta (np. pasujący rocznik czy marka) dodaje punkty, dzięki czemu system szybko układa listę aut od najbardziej do najmniej pasujących.

### 4.2. Projekt SwapCar a 7 pryncypiów metodyki PRINCE2 (Zadanie 2 z Lab 4)

Aby w projekcie nie zrobił się bałagan, organizację naszej pracy oparliśmy o **7 zasad (pryncypiów) z metodyki PRINCE2**. Trzymaliśmy się ich wszystkich, bo pominięcie chociaż jednej oznacza, że nie pracujemy już zgodnie z *PRINCE2*:

1. **Ciągła zasadność biznesowa** – cały czas weryfikowaliśmy, czy robienie tej aplikacji ma sens. Przeprowadzone na 3 poziomie TRL testy poszczególnych modułów udowodniły nam, że nasz algorytm faktycznie działa i pozwala szybciej znaleźć auto na wymianę niż zwykłe filtry na portalach typu Otomoto czy OLX. Dzięki temu na bieżąco kontrolowaliśmy ryzyko (np. ryzyko zbyt wolnego działania algorytmu przy dużej bazie aut) i wiedzieliśmy, że jest ono na *akceptowalnym poziomie*.
2. **Zdefiniowane role i odpowiedzialności** – najpierw ustaliliśmy, jakie role są nam potrzebne w zespole, a dopiero potem przypisaliśmy do nich konkretne osoby z naszej grupy. Wyznaczyliśmy **Kierownika Projektu** (pilnuje terminów i sprawozdań) oraz **role techniczne** (osoba od wyglądu strony, osoba od bazy i algorytmu, osoba od testów). Rolę **Komitetu Sterującego** (który ocenia naszą pracę i decyduje o zaliczeniu etapu) pełnił prowadzący zajęcia. Trzymaliśmy się zasady, że członkowie zespołu mogą łączyć kilka zadań programistycznych, ale Kierownik Projektu nie zasiada w Komitecie Sterującym.
3. **Koncentracja na produktach** – nie skupialiśmy się na samym „pisaniu kodu”, tylko na konkretnych rzeczach (*produktach*), które dostarczyliśmy na koniec etapu, i ich jakości. Na tym etapie naszymi gotowymi produktami były trzy przetestowane osobno moduły (sprawdzania ogłoszeń, liczenia dopłat i dopasowywania kart) oraz sprawozdanie. Całą drogę do gotowej aplikacji podzieliliśmy na mniejsze kroki prowadzące do wykonania tych produktów.
4. **Korzystanie z doświadczeń** – mimo że sam pomysł wymiany aut w stylu Tindera jest dość świeży, to tworzenie stron internetowych składa się z powtarzalnych procesów. Skorzystaliśmy z doświadczeń z poprzednich zajęć i projektów na studiach oraz podpatrzyliśmy sprawdzone rozwiązania z istniejących aplikacji randkowych (*mechanizm przesuwania kart*) i portali ogłoszeniowych (*wygląd formularza z parametrami auta*). Wyciągnęliśmy też wnioski z tego, co wypracowaliśmy w sprawozdaniach dla TRL 1 i TRL 2.
5. **Zarządzanie z wykorzystaniem tolerancji** – w projekcie określiliśmy granice tolerancji (*swobody*), w których nasz Kierownik Projektu sam podejmował decyzje. Ustaliliśmy **tolerancję czasową** (terminy oddania sprawozdań i kolejnych etapów), **kosztową** (korzystaliśmy z darmowych narzędzi i własnych laptopów, więc budżet wynosił 0 zł) oraz **jakościową** (w module dopasowywania ofert założyliśmy, że płynność działania aplikacji jest ważniejsza niż idealne dopasowanie drugorzędnych cech, takich jak kolor auta).
6. **Zarządzanie etapowe** – podzieliliśmy nasz projekt na konkretne, niezbyt długie etapy, które pokrywały się z kolejnymi poziomami TRL (*TRL 1 – pomysł, TRL 2 – zasoby i plan, TRL 3 – testy pojedynczych modułów*). Po każdym etapie robiliśmy podsumowanie w formie sprawozdania i po uzyskaniu akceptacji przechodziliśmy dalej. Dzięki temu mieliśmy pełną kontrolę nad postępami prac i jakością projektu.
7. **Dostosowanie do projektu w danym środowisku** – dostosowaliśmy narzędzia i sposób zarządzania do rozmiaru naszego projektu. Jak mówi zasada: *„nie strzela się do komara z armaty”*. Zrealizowaliśmy projekt w 3-osobowej grupie, więc zamiast tworzyć setki stron zbędnej dokumentacji, dobraliśmy lekkie i wygodne narzędzia (**VS Code, GitHub**, komunikator do szybkiego kontaktu) oraz prosty podział zadań skrojony dokładnie pod nasze potrzeby.

---

## 5. Poziom TRL 4 – badania prototypu w warunkach laboratoryjnych

### 5.1. Weryfikacja koncepcji w warunkach laboratoryjnych (Zadanie 1 z Lab 5)

Na czwartym poziomie **TRL** połączyliśmy nasze wcześniejsze moduły w jeden *działający prototyp* i przebadaliśmy go w warunkach laboratoryjnych. Chcieliśmy szybko poznać wyniki na konkretnej próbce danych, żeby w razie niepowodzenia móc na czas przerwać projekt i uratować budżet. Okazało się, że po złożeniu modułów w całość nie wszystko od razu działało tak idealnie, jak zakładaliśmy, ale po wprowadzeniu poprawek badanie zakończyło się pełnym sukcesem.

W ramach realizacji IV poziomu gotowości technologicznej zrealizowaliśmy prace badawcze w następującym zakresie:

* **Moduł dodawania i sprawdzania ogłoszeń** – przygotowaliśmy *zestaw kontrolny 100 ogłoszeń* samochodów zawierających dane tekstowe oraz zdjęcia w formatach: `jpg`, `png` i `webp`. Określiliśmy, że pliki z samymi danymi tekstowymi ogłoszenia zapisywane przez nasz system mają wewnętrzny format z rozszerzeniem: **`*.scd` (SwapCar Data)**. Określiliśmy też, że paczki ogłoszeń zawierające skompresowane zdjęcia samochodów mają rozszerzenie: **`*.scm` (SwapCar Media)**. Wykonaliśmy 100 serii testów wczytywania i walidacji na zestawie kontrolnym. Algorytm wykazał pewne odchylenie w niektórych seriach testów (zdjęcia o dużej rozdzielczości powodowały przycięcia i opóźnienia przy zapisie do bazy). Ustaliliśmy, że na wynik ma wpływ sposób przydzielania pamięci podręcznej i obciążenie wątków procesora przy jednoczesnym zmniejszaniu zdjęć. Wprowadziliśmy poprawkę do algorytmu (*automatyczne zmniejszanie zdjęć przed zapisem*) i ponownie wykonaliśmy 100 serii testów. Wyniki w całej serii były porównywalne, a odchylenia zostały zminimalizowane.
* **Moduł liczenia dopłat** – przygotowaliśmy *zestaw kontrolny 100 wygenerowanych plików ofert* w formacie **`*.scd`** (same dane o cenach i widełkach budżetowych użytkowników, bez multimediów). Wykonaliśmy po 100 serii testów parowania cenowego dla zestawu kontrolnego plików. Algorytm wykazał pewne odchylenie w niektórych seriach testów. Ustaliliśmy, że na wynik ma wpływ zaokrąglanie kwot przez procesor oraz błędne traktowanie ofert, w których użytkownik wpisał dopłatę równą 0 zł. Wprowadziliśmy poprawkę do algorytmu liczącego i ponownie wykonaliśmy 100 serii testów. Wyniki w całej serii były porównywalne, a odchylenia zostały zminimalizowane.
* **Moduł dopasowywania ofert (Silnik Matchingowy)** – przygotowaliśmy *zestaw kontrolny 100 pełnych ofert samochodów* zapisanych w formacie **`*.scm`** (dane razem ze zdjęciami). Wykonaliśmy po 100 serii testów szybkiego przeglądania i przesuwania kart (*swipe*) dla zestawu kontrolnego. Podczas każdego testu rejestrowaliśmy **czas odpowiedzi serwera** oraz płynność wyświetlania kart z obrazkami w przeglądarce. Algorytm wykazał pewne odchylenie w niektórych seriach testów – przy bardzo szybkim przesuwaniu kart pojawiały się opóźnienia w ładowaniu kolejnych propozycji. Ustaliliśmy, że na wynik ma wpływ taktowanie procesora pod dużym obciążeniem oraz brak wcześniejszego wczytywania kart w tle. Wprowadziliśmy poprawkę do algorytmu (*buforowanie 5 kolejnych kart w pamięci z wyprzedzeniem*) i ponownie wykonaliśmy 100 serii testów. Wyniki w całej serii były porównywalne, a odchylenia zostały zminimalizowane.

### 5.2. Określenie ryzyk dla IV poziomu TRL i sposoby ich eliminacji (Zadanie 2 z Lab 5)

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

## 6. Punkt Kontrolny – Jakość dokumentacji oraz plan komercjalizacji (Lab 6)

### 6.1. Uporządkowanie struktury dokumentu (Zadanie 1 z Lab 6)

W ramach punktu kontrolnego uporządkowaliśmy nasze dotychczasowe sprawozdanie i dostosowaliśmy je do wymogów formalnych. Zadbaliśmy o to, aby dokumentacja projektu **SwapCar** dobrze świadczyła o naszym zespole:
* Przygotowaliśmy przejrzystą i czytelną **stronę okładkową (tytułową)**, na której nie umieściliśmy numeru strony.
* Utworzyliśmy pełny **spis treści** odzwierciedlający strukturę rekurencyjnego sprawozdania.
* Dodaliśmy czytelne **nagłówki i podtytuły** dla wszystkich poziomów TRL oraz poszczególnych zadań.
* W całym tekście **pogrubiliśmy** oraz oznaczyliśmy *kursywą* najważniejsze pojęcia, nazwy modułów i parametry techniczne.
* Sprawdziliśmy poprawność ortograficzną i gramatyczną tekstu oraz sformatowaliśmy akapity (zastosowaliśmy *justowanie tekstu*, *wcięcia akapitowe* oraz ujednolicony rozmiar czcionki **11 pkt**).
* Na koniec wykonaliśmy ponowny przegląd dokumentu od pierwszego punktu (zgodnie z *TIP 8*), aby upewnić się, że żaden element formatowania nie został pominięty.

### 6.2. Grupa docelowa oraz model biznesowy i komercjalizacja produktu (Zadanie 2 z Lab 6)

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

## 7. Poziom TRL 5 – weryfikacja koncepcji w środowisku zbliżonym do rzeczywistego (Lab 7)

### 7.1. Integracja komponentów za pomocą wzorca MVC oraz testy na zwiększonej próbie (Zadanie 1 z Lab 7)

Na piątym poziomie **TRL** (w ramach *badań przemysłowych*) przeszliśmy z prostych testów laboratoryjnych do weryfikacji naszego systemu w **środowisku zbliżonym do rzeczywistego (symulowanym)**. Na tym etapie nasza aplikacja **SwapCar** stała się już działającym programem z interfejsem webowym oraz panelem konsolowym do wydawania komend tekstowych i podglądu logów serwera.

Aby zbliżyć warunki badawcze do rzeczywistych (zgodnie z *TIP 2*), **dziesięciokrotnie zwiększyliśmy liczbę danych testowych** – z wcześniejszych 100 plików na poziomie TRL 4 do pełnej bazy **1000 plików ogłoszeń**. W celu trwałego połączenia wszystkich wcześniej zaprogramowanych komponentów zastosowaliśmy wzorzec architektoniczny **MVC (ang. *Model-View-Controller*, pol. *Model-Widok-Kontroler*)**, który uporządkował strukturę naszej aplikacji. W tym celu zaprogramowaliśmy dodatkowy, centralny moduł **Kontrolera**. Jego zadaniem stała się koordynacja pracy całego systemu **SwapCar** poprzez przyjmowanie danych od użytkowników, reagowanie na ich akcje (np. przesunięcia kart), zarządzanie aktualizacją modelu bazy danych oraz odświeżaniem widoków w przeglądarce.

W ramach tego etapu przeprowadziliśmy szczegółowe prace techniczne i weryfikacyjne dla poszczególnych podsystemów (z zachowaniem różnic w ich działaniu zgodnie z *TIP 1*):

* **Kontroler (główny moduł koordynujący MVC)** – został zaprogramowany w celu spięcia i koordynowania pracy pozostałych trzech modułów systemu. Sprawdziliśmy stabilność Kontrolera poprzez jego wielokrotne uruchamianie i restartowanie pod obciążeniem, zdefiniowaliśmy wtyczki (endpointy API) dla podmodułów oraz zweryfikowaliśmy odporność na dane celowo „uszkodzone” (błędne typy danych w polu `cena_auta`, uszkodzone nagłówki **`*.scm`**, puste obiekty JSON), eliminując wykryte błędy walidacji.
* **Moduł dodawania i sprawdzania ogłoszeń (kompresja i zapis danych)** – po integracji z Kontrolerem przeprowadziliśmy testy na bazie **1000 plików ogłoszeniowych** (`*.scd` oraz `*.scm`), eliminując błędy ucinania długich opisów i gubienia zdjęć poprzez powiększenie bufora i synchronizację wątków zapisu.
* **Moduł liczenia dopłat (przetwarzanie danych niemultimedialnych)** – po integracji przetestowaliśmy moduł na bazie **1000 plików `*.scd`**, usuwając przeciążenia przy porównywaniu „każdy z każdym” za pomocą wstępnej filtracji cenowej po stronie Kontrolera.
* **Moduł dopasowywania ofert – Silnik Matchingowy (odczyt strumieniowy danych multimedialnych)** – zweryfikowaliśmy dekompresję i strumieniowanie **1000 plików `*.scm`** w czasie rzeczywistym, usuwając przycięcia i opóźnienia poprzez kolejkowanie żądań w Kontrolerze oraz asynchroniczne doczytywanie zdjęć w tle.

---

## 8. Analiza SWOT projektu SwapCar (Lab 8)

### 8.1. Macierz analizy SWOT (Zadanie 1 z Lab 8)

| Czynniki | **Pozytywne** | **Negatywne** |
| :--- | :--- | :--- |
| **Wewnętrzne** | **S – Mocne strony (*Strengths*)**<br>1. Nowoczesny interfejs *swipe* i intuicyjna obsługa<br>2. Dwustronny algorytm dopasowań z modułem dopłat<br>3. Lekka architektura MVC i autorskie formaty `*.scd`/`*.scm`<br>4. Dwufilarowy model biznesowy (*Freemium* B2C + licencje B2B) | **W – Słabe strony (*Weaknesses*)**<br>1. Niewielki, 3-osobowy zespół programistyczny i ograniczony czas<br>2. Brak początkowego kapitału na masową kampanię reklamową<br>3. Zależność wydajności od obciążenia serwera przy paczkach `*.scm`<br>4. Konieczność rozbudowy aplikacji webowej o natywne funkcje mobilne |
| **Zewnętrzne** | **O – Szanse (*Opportunities*)**<br>1. Duży rynek aut używanych w Polsce ($2$–$2{,}5\text{ mln}$ transakcji/rok)<br>2. Zainteresowanie komisów B2B upłynnianiem tzw. „leżaków placowych”<br>3. Pozyskanie dofinansowania (np. grant EU / inwestor zalążkowy)<br>4. Integracja z zewnętrznymi bazami historii pojazdów (API VIN) | **T – Zagrożenia (*Threats*)**<br>1. Silna dominacja tradycyjnych portali ogłoszeniowych (Otomoto, OLX)<br>2. Efekt „pustego placu” (niska liczba ofert na starcie w małych miastach)<br>3. Próby dodawania fałszywych ogłoszeń i zaniżania/zawyżania wycen aut<br>4. Zmiany prawne i podatkowe (np. PCC przy zamianie pojazdów) |

### 8.2. Szczegółowa analiza czynników z oszacowaniem prawdopodobieństwa procentowego (Zadanie 2 z Lab 8)

* **Mocne strony (S):**
  1. Nowoczesny interfejs *swipe* i intuicyjna obsługa ($95\%$) – sprawdzona ergonomia znana z aplikacji mobilnych.
  2. Dwustronny algorytm dopasowań z modułem liczenia dopłat ($90\%$) – przewaga nad zwykłymi portalami ogłoszeniowymi.
  3. Lekka architektura MVC i formaty `*.scd`/`*.scm` ($88\%$) – szybkie strumieniowanie kart przy niskim zużyciu zasobów.
  4. Dwufilarowy model biznesowy B2C/B2B ($85\%$) – darmowy ruch użytkowników indywidualnych wspierający sprzedaż licencji komisom.
* **Słabe strony (W):**
  1. Niewielki, 3-osobowy zespół początkowy ($80\%$) – rozwiązane przez plan rozbudowy do 14-osobowej struktury po pozyskaniu finansowania.
  2. Brak kapitału początkowego na masowy marketing ($75\%$) – niwelowane przez wirusowy model aplikacji i bezpośrednią sprzedaż do komisów.
  3. Wrażliwość serwera na skoki ruchu przy plikach `*.scm` ($30\%$) – ograniczone limitem $2\text{ MB}$ i testami obciążeniowymi na TRL 6.
  4. Konieczność dopracowania wersji mobilnej ($40\%$) – rozwiązane przez pełną obsługę Android/iOS w ramach TRL 6–7.
* **Szanse (O):**
  1. Chłonny rynek wtórny w Polsce i rotacja aut w komisach ($80\%$) – silny popyt na pakiety *Komis Standard* i *Komis PRO*.
  2. Integracja z bazami historii pojazdów po numerze VIN ($70\%$) – dodatkowe źródło przychodu prowizyjnego i wzrost zaufania.
  3. Pozyskanie grantu UE lub inwestora zalążkowego ($35\%$) – wzrost wiarygodności dzięki dokumentacji TRL 1–9 i analizie Cash Flow.
  4. Ekspansja na rynki Europy Środkowo-Wschodniej ($25\%$) – skalowalność modelu po ustabilizowaniu pozycji w Polsce.
* **Zagrożenia (T):**
  1. Silna pozycja tradycyjnych portali Otomoto/OLX ($60\%$) – obrona przez specjalizację w obustronnych wymianach z dopłatą.
  2. Efekt „pustego placu” na starcie ($45\%$) – eliminacja poprzez wczesny onboarding komisów darmowym *Pakietem Start*.
  3. Nierzetelne ogłoszenia i zawyżane wyceny ($50\%$) – ograniczone walidacją parametrów, raportami VIN i weryfikacją komisów.
  4. Zmiany przepisów podatkowych PCC ($10\%$) – stały monitoring prawny i informator podatkowy w aplikacji.

---

## 9. Poziom TRL 6 – demonstracja prototypu w warunkach zbliżonych do rzeczywistego (Lab 9)

### 9.1. Zaawansowane testy serwerowe oraz badania użyteczności prototypu (Zadanie 1 z Lab 9)

Na szóstym poziomie **TRL** zademonstrowaliśmy zintegrowany model platformy **SwapCar** (web + mobile Android/iOS) w warunkach w stopniu zaawansowanym odzwierciedlających środowisko rzeczywiste:

1. **Testy serwerowe:** 10-dniowe, nieprzerwane próby obciążeniowe symulujące **$50\,000$ jednoczesnych użytkowników** z ciągłym monitoringiem co 15 minut. Potwierdziliśmy wysoką jakość danych po dekompresji paczek **`*.scm`** oraz brak dywergencji wydajnościowej.
2. **Testy użytkowe (*usability testing*):** ponowna weryfikacja jakości algorytmu na **$30\,000$ plików** ogłoszeń (skuteczność powyżej $99{,}8\%$) oraz testy na **$200$ niezależnych użytkownikach** ($160$ B2C + $40$ B2B) realizujących scenariusze krok po kroku. Zebrano informację zwrotną, m.in. sugestię dodania mobilnego suwaka kwoty dopłaty (wdrażaną na TRL 7).

**Efekt końcowy:** Uzyskanie przetestowanej wersji aplikacji webowej i mobilnej działającej stabilnie w warunkach odwzorowujących rzeczywiste obciążenie rynkowe.

### 9.2. Ryzyka technologiczne dla VI poziomu TRL i sposoby ich eliminacji (Zadanie 2 z Lab 9)

1. **Ryzyko:** Trudności z wiernym odwzorowaniem nierównomiernego obciążenia szczytowego w testach serwerowych dla dekompresji strumieniowej **`*.scm`**.
   * **Rozwiązanie:** Zastosowanie zewnętrznych narzędzi obciążeniowych (*Apache JMeter*, *k6*) oraz autorskich skryptów symulujących losowe godziny szczytu (18:00–22:00).
2. **Ryzyko:** Różnice w obsłudze gestów *swipe* i formatu `webp` na starszych systemach mobilnych.
   * **Rozwiązanie:** Uniwersalna obsługa *Touch/Pointer Events*, alternatywne przyciski akcji oraz automatyczny fallback obrazów do `jpg`.

---

## 10. Zarządzanie jakością i struktura organizacyjna projektu (Lab 10)

### 10.1. Metryka produktu z mierzalnymi parametrami jakościowymi (Zadanie 1 z Lab 10)

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

### 10.2. Diagram struktury organizacyjnej i zarządczej projektu (Zadanie 2 z Lab 10)

Dla fazy pełnej realizacji i komercjalizacji dobrano **strukturę sztabowo-liniową** obejmującą **14 osób**:

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
```

### 10.3. Charakterystyka unikalnych ról w zespole projektowym (Zadanie 3 z Lab 10)

1. **Komitet Sterujący / Sponsor Projektu (1 os.):** Sprawuje nadzór strategiczny, akceptuje przejścia między etapami TRL oraz zatwierdza budżet i zmiany przekraczające tolerancje Kierownika Projektu. Weryfikuje ciągłą zasadność biznesową projektu.
2. **Kierownik Projektu – PM (1 os.):** Zarządza operacyjnie harmonogramem, budżetem i zadaniami zespołów. Koordynuje współpracę między komórkami sztabowymi a zespołem technicznym oraz prowadzi rejestr ryzyk.
3. **Specjalista ds. Kontroli Jakości i Zgodności Prawnej / RODO (1 os.):** Doradza w zakresie norm jakościowych, metryki produktu i ochrony danych osobowych oraz numerów VIN. Nadzoruje regulaminy B2B/B2C i bezpieczeństwo prawne usług.
4. **Analityk Biznesowy i Rozwój B2B/B2C (1 os.):** Analizuje rynek motoryzacyjny, definiuje wymagania funkcjonalne dla komisów i kierowców oraz optymalizuje cenniki abonamentowe. Wspiera działania komercjalizacyjne i raportowanie dla inwestorów.
5. **Architekt Systemu / Tech Lead (1 os.):** Odpowiada za spójność architektury MVC i interfejsów API wszystkich modułów. Prowadzi przeglądy kodu (*code review*) oraz wyznacza standardy wydajnościowe.
6. **Programista Backend (3 os.):** Implementuje centralny Kontroler, moduł walidacji ogłoszeń, moduł dopłat oraz silnik matchingowy. Optymalizuje przetwarzanie paczek **`*.scd`** i obsługę czatu w czasie rzeczywistym.
7. **Programista Frontend i Mobile (3 os.):** Tworzy interfejs webowy oraz aplikacje mobilne Android/iOS z płynną obsługą gestów *swipe*. Implementuje asynchroniczne ładowanie galerii **`*.scm`** i formularze ofert.
8. **Inżynier DevOps i Administrator Baz Danych (1 os.):** Konfiguruje infrastrukturę chmurową, automatyzację wdrożeń CI/CD oraz bazy danych. Monitoruje wydajność serwerów i gwarantuje utrzymanie dostępności SLA $99{,}5\%$.
9. **Inżynier QA / Tester Oprogramowania i Użyteczności (2 os.):** Opracowuje testy automatyczne i obciążeniowe oraz organizuje badania *usability* na użytkownikach końcowych. Dokumentuje błędy i weryfikuje poprawność poprawek przed wydaniami produkcyjnymi.

---

## 11. Prace rozwojowe – poziomy TRL 7, TRL 8 i TRL 9 (Lab 11)

### 11.1. Poziom TRL 7 – demonstracja prototypu w warunkach operacyjnych (Zadanie 1 z Lab 11)

**I. Zakres prac badawczych:**
* wprowadzenie korekt programistycznych wynikających z odchyleń i uwag ergonomicznych wykrytych na etapie VI TRL (m.in. mobilny suwak dopłat i usprawnienia czatu negocjacyjnego);
* integracja modułu raportów historii pojazdów po numerze **VIN** oraz systemu płatności i licencji;
* przeprowadzenie ostatecznego testu operacyjnego (beta-testów) aplikacji **SwapCar** na grupie **$50\,000$ użytkowników**.

**II. Zakładany efekt końcowy:**
* dokonanie demonstracji prototypu aplikacji **SwapCar** w warunkach operacyjnych poprzez ostateczny test użytkowników, potwierdzające osiągnięcie VII poziomu TRL.

### 11.2. Poziom TRL 8 – zakończenie badań i demonstracja ostatecznej formy technologii (Zadanie 2 z Lab 11)

**I. Zakres prac badawczych:**
* pomiar założonych parametrów metryki produktu aplikacji **SwapCar** względem faktycznie uzyskanych wyników w ujęciu do etapu VI i VII;
* przygotowanie końcowych raportów z pomiarów i testów akceptacyjnych;
* opracowanie dokumentacji technicznej, dokumentacji szkoleniowej dla komisów oraz uzyskanie certyfikatów jakości i zgodności z RODO.

**II. Zakładany efekt końcowy:**
* zakończenie badań i demonstracji ostatecznej formy aplikacji **SwapCar** oraz oficjalne potwierdzenie, że docelowy poziom technologii został osiągnięty i produkt nadaje się do wdrożenia.

### 11.3. Poziom TRL 9 – gotowość na komercjalizację (Zadanie 3 z Lab 11)

**I. Zakres prac badawczych:**
* przygotowanie dokumentacji projektowej w ujęciu holistycznym;
* przygotowanie dokumentów standardów jakościowych dla świadczonej usługi wymiany samochodów **SwapCar**;
* przygotowanie finalnych instrukcji użytkowania aplikacji **SwapCar** (dla segmentu B2C oraz B2B).

**II. Zakładany efekt końcowy:**
* opracowanie dokumentacji projektowej, dokumentów standardów jakościowych oraz instrukcji użytkowania aplikacji **SwapCar**;
* potwierdzenie, że technologia w warunkach rzeczywistych odniosła zamierzony efekt, w związku z czym **spółka** (SwapCar Sp. z o.o.) przechodzi do realizacji komponentu wdrożeniowego.

---

## 12. Punkt Kontrolny – Budżet projektu i opłacalność wdrożenia / Cash Flow (Lab 12)

### 12.1. Założenia finansowe i horyzont symulacji (24 miesiące)

W celu weryfikacji uzasadnienia biznesowego projektu **SwapCar** opracowano budżet oraz symulację przepływów pieniężnych (**Cash Flow**) w horyzoncie **24 miesięcy**, opartą na strukturze wzorca `budzet_sprzedaz_licencji.xlsx` (trzy filary: koszty jednorazowe, koszty stałe miesięczne, przychody oraz Cash Flow).

Przyjęto następujące założenia operacyjne, spójne z modelem komercjalizacji z **Lab 6** oraz strukturą z **Lab 10**:
* **Miesiąc 0 (Start inwestycji):** poniesienie kosztów jednorazowych uruchomienia projektu ($200\,000\text{ zł}$).
* **Miesiące 1–6 (Faza B+R, testów TRL 4–9 i wdrożenia):** ponoszenie kosztów stałych ($125\,000\text{ zł / mies.}$) przy przychodach równych $0\text{ zł}$.
* **Miesiące 7–24 (Faza komercjalizacji i skalowania sprzedaży):** stopniowy przyrost płatnych licencji dla komisów (**Komis Standard** oraz **Komis PRO**) oraz usług dobrowolnych dla kierowców indywidualnych (**Konto Premium**, podbicia **SuperSwap** oraz prowizja od **Raportów VIN**). Pod koniec 24. miesiąca platforma osiąga $665$ płacących komisów ($460$ Standard + $205$ PRO), co mieści się dokładnie w docelowym przedziale $500$–$1\,000$ komisów założonym w **Lab 6**.

---

### 12.2. Filar I – Koszty jednorazowe (inwestycja początkowa)

| Lp. | Pozycja kosztu jednorazowego | Kwota (zł) | Udział (%) |
| :---: | :--- | ---: | ---: |
| 1 | Sprzęt programistyczny i urządzenia testowe (laptopy, smartfony Android/iOS) | $48\,000$ | $24{,}0\%$ |
| 2 | Konfiguracja infrastruktury chmurowej, CI/CD oraz baz `*.scd`/`*.scm` | $18\,000$ | $9{,}0\%$ |
| 3 | Projekt graficzny UX/UI aplikacji webowej oraz mobilnej | $25\,000$ | $12{,}5\%$ |
| 4 | Integracja zewnętrznych API (płatności online, bazy historii VIN/CEPiK) | $16\,000$ | $8{,}0\%$ |
| 5 | Badania użyteczności (*usability* – 200 osób) i testy obciążeniowe (TRL 6–7) | $22\,000$ | $11{,}0\%$ |
| 6 | Obsługa prawna, rejestracja spółki, RODO, regulaminy oraz certyfikacja jakości | $26\,000$ | $13{,}0\%$ |
| 7 | Kampania marketingowa na start (*launch* B2C oraz materiały sprzedażowe B2B) | $45\,000$ | $22{,}5\%$ |
| | **SUMA KOSZTÓW JEDNORAZOWYCH** | **$200\,000$** | **$100{,}0\%$** |

---

### 12.3. Filar II – Koszty stałe (miesięczne)

| Lp. | Pozycja kosztu stałego (miesięcznego) | Kwota mies. (zł) | Suma 24 mies. (zł) |
| :---: | :--- | ---: | ---: |
| 1 | Wynagrodzenia zespołu technicznego i PM (Backend, Frontend/Mobile, DevOps, QA, Architekt) | $85\,000$ | $2\,040\,000$ |
| 2 | Komórki sztabowe (Specjalista ds. Jakości/RODO, Analityk Biznesowy B2B/B2C) | $12\,000$ | $288\,000$ |
| 3 | Serwery chmurowe, CDN dla plików `*.scm`, backup i monitoring SLA $99{,}5\%$ | $8\,000$ | $192\,000$ |
| 4 | Marketing ciągły, pozyskiwanie komisów B2B i kampanie reklamowe B2C | $15\,000$ | $360\,000$ |
| 5 | Księgowość, biuro/coworking, licencje narzędzi (GitHub, Figma) i obsługa klienta | $5\,000$ | $120\,000$ |
| | **SUMA KOSZTÓW STAŁYCH** | **$125\,000$** | **$3\,000\,000$** |

*Łączny budżet kosztowy projektu za 24 miesiące (koszty jednorazowe + 24 miesiące kosztów stałych):*
$$K_{\text{całk}} = 200\,000\text{ zł} + 24 \times 125\,000\text{ zł} = 3\,200\,000\text{ zł}$$

---

### 12.4. Filar III – Przychody ze sprzedaży licencji B2B i usług B2C

| Lp. | Strumień przychodu (zgodny z Lab 6) | Segment | Cena jedn. (zł) | Łączny wolumen (24 mies.) | Suma przychodów (zł) | Udział (%) |
| :---: | :--- | :---: | ---: | ---: | ---: | ---: |
| 1 | **Licencja Komis Standard** (abonament mies.) | B2B | $249{,}00$ | $4\,590$ szt. | $1\,142\,910$ | $34{,}5\%$ |
| 2 | **Licencja Komis PRO / Sieć** (abonament mies.) | B2B | $599{,}00$ | $1\,910$ szt. | $1\,144\,090$ | $34{,}5\%$ |
| 3 | **Konto SwapCar Premium** (abonament mies.) | B2C | $29{,}00$ | $22\,050$ szt. | $639\,450$ | $19{,}3\%$ |
| 4 | **Podbicie oferty „SuperSwap”** (48 h) | B2C | $9{,}99$ | $17\,100$ szt. | $170\,829$ | $5{,}2\%$ |
| 5 | **Raport historii VIN** (prowizja platformy) | B2C/B2B | $15{,}00$ | $14\,400$ szt. | $216\,000$ | $6{,}5\%$ |
| | **SUMA PRZYCHODÓW (24 MIESIĄCE)** | | | | **$3\,313\,279$** | **$100{,}0\%$** |

*Struktura przychodów potwierdza założenia z Lab 6: główny ciężar finansowy ($69{,}0\%$) generują umowy licencyjne z komisami samochodowymi (B2B), natomiast segment B2C ($31{,}0\%$) uzupełnia przychody i buduje zasięg marki.*

---

### 12.5. Analiza Cash Flow (24 miesiące), próg rentowności i zwrot inwestycji

Poniższa tabela przedstawia pełną symulację przepływów pieniężnych (**Cash Flow**) dla każdego miesiąca trwania projektu (`KS` – Licencja Komis Standard, `KP` – Licencja Komis PRO, `PR` – Konto Premium B2C, `SS` – SuperSwap, `VN` – Raport VIN):

| Mies. | KS ($249\text{ zł}$) | KP ($599\text{ zł}$) | PR ($29\text{ zł}$) | SS ($9{,}99\text{ zł}$) | VN ($15\text{ zł}$) | Przychody (zł) | Koszty (zł) | Bilans mies. (zł) | Cash Flow skumulowany (zł) | Status etapu |
| :---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | :--- |
| **M0** | 0 | 0 | 0 | 0 | 0 | $0$ | $200\,000$ | $-200\,000$ | $-200\,000$ | Inwestycja początkowa |
| **M1** | 0 | 0 | 0 | 0 | 0 | $0$ | $125\,000$ | $-125\,000$ | $-325\,000$ | Prace B+R (TRL 4–5) |
| **M2** | 0 | 0 | 0 | 0 | 0 | $0$ | $125\,000$ | $-125\,000$ | $-450\,000$ | Prace B+R (TRL 5) |
| **M3** | 0 | 0 | 0 | 0 | 0 | $0$ | $125\,000$ | $-125\,000$ | $-575\,000$ | Prace B+R (TRL 6) |
| **M4** | 0 | 0 | 0 | 0 | 0 | $0$ | $125\,000$ | $-125\,000$ | $-700\,000$ | Testy obciążeniowe i usability |
| **M5** | 0 | 0 | 0 | 0 | 0 | $0$ | $125\,000$ | $-125\,000$ | $-825\,000$ | Beta-testy operacyjne (TRL 7) |
| **M6** | 0 | 0 | 0 | 0 | 0 | $0$ | $125\,000$ | $-125\,000$ | $-950\,000$ | Certyfikacja i wdrożenie (TRL 8–9) |
| **M7** | 30 | 10 | 100 | 100 | 100 | $18\,859$ | $125\,000$ | $-106\,141$ | $-1\,056\,141$ | Start komercjalizacji |
| **M8** | 50 | 15 | 200 | 200 | 150 | $31\,483$ | $125\,000$ | $-93\,517$ | $-1\,149\,658$ | Pozyskiwanie pierwszych komisów |
| **M9** | 70 | 25 | 300 | 300 | 200 | $47\,102$ | $125\,000$ | $-77\,898$ | $-1\,227\,556$ | Wzrost bazy ofert |
| **M10** | 100 | 35 | 450 | 400 | 300 | $67\,411$ | $125\,000$ | $-57\,589$ | $-1\,285\,145$ | Skalowanie sprzedaży B2B |
| **M11** | 130 | 45 | 600 | 500 | 400 | $87\,720$ | $125\,000$ | $-37\,280$ | $-1\,322\,425$ | Rozbudowa sieci partnerskiej |
| **M12** | 160 | 55 | 750 | 600 | 500 | $108\,029$ | $125\,000$ | $-16\,971$ | **$-1\,339\,396$** | **Maks. luka kapitałowa** |
| **M13** | 190 | 70 | 900 | 700 | 600 | $131\,333$ | $125\,000$ | **$+6\,333$** | $-1\,333\,063$ | **PRÓG RENTOWNOŚCI (BEP)** |
| **M14** | 220 | 85 | 1 050 | 800 | 700 | $154\,637$ | $125\,000$ | $+29\,637$ | $-1\,303\,426$ | Generowanie nadwyżki |
| **M15** | 250 | 100 | 1 200 | 900 | 800 | $177\,941$ | $125\,000$ | $+52\,941$ | $-1\,250\,485$ | Spłata nakładów inwestycyjnych |
| **M16** | 280 | 115 | 1 350 | 1 000 | 900 | $201\,245$ | $125\,000$ | $+76\,245$ | $-1\,174\,240$ | Spłata nakładów inwestycyjnych |
| **M17** | 310 | 130 | 1 500 | 1 100 | 1 000 | $224\,549$ | $125\,000$ | $+99\,549$ | $-1\,074\,691$ | Spłata nakładów inwestycyjnych |
| **M18** | 340 | 145 | 1 650 | 1 200 | 1 100 | $247\,853$ | $125\,000$ | $+122\,853$ | $-951\,838$ | Spłata nakładów inwestycyjnych |
| **M19** | 360 | 155 | 1 750 | 1 300 | 1 150 | $263\,472$ | $125\,000$ | $+138\,472$ | $-813\,366$ | Dynamiczny wzrost zysku |
| **M20** | 380 | 165 | 1 850 | 1 400 | 1 200 | $279\,091$ | $125\,000$ | $+154\,091$ | $-659\,275$ | Dynamiczny wzrost zysku |
| **M21** | 400 | 175 | 1 950 | 1 500 | 1 250 | $294\,710$ | $125\,000$ | $+169\,710$ | $-489\,565$ | Dynamiczny wzrost zysku |
| **M22** | 420 | 185 | 2 050 | 1 600 | 1 300 | $310\,329$ | $125\,000$ | $+185\,329$ | $-304\,236$ | Dynamiczny wzrost zysku |
| **M23** | 440 | 195 | 2 150 | 1 700 | 1 350 | $325\,948$ | $125\,000$ | $+200\,948$ | $-103\,288$ | Zbliżenie do pełnego zwrotu |
| **M24** | 460 | 205 | 2 250 | 1 800 | 1 400 | $341\,567$ | $125\,000$ | $+216\,567$ | **$+113\,279$** | **ZWROT INWESTYCJI (ROI)** |
| **RAZEM** | **4 590** | **1 910** | **22 050** | **17 100** | **14 400** | **$3\,313\,279$** | **$3\,200\,000$** | **$+113\,279$** | **$+113\,279$** | **Projekt rentowny** |

#### **Podsumowanie kluczowych wskaźników finansowych projektu SwapCar:**

| Wskaźnik finansowy | Wartość | Interpretacja biznesowa |
| :--- | :--- | :--- |
| **Horyzont budżetu** | $24\text{ miesiące}$ | Pełny cykl od prac B+R po skalowanie sprzedaży |
| **Całkowite koszty projektu (M0–M24)** | $3\,200\,000\text{ zł}$ | $200\,000\text{ zł}$ jednorazowe + $3\,000\,000\text{ zł}$ stałe |
| **Całkowite przychody projektu (M0–M24)** | $3\,313\,279\text{ zł}$ | $69\%$ licencje B2B + $31\%$ usługi B2C |
| **Maksymalne zapotrzebowanie na kapitał** | $1\,339\,396\text{ zł}$ *(M12)* | Minimalny kapitał/grant wymagany do zachowania płynności (zalecana rezerwa: $1{,}40\text{ mln zł}$) |
| **Próg rentowności (Break-Even Point)** | **Miesiąc 13** | Miesięczne przychody ($131\,333\text{ zł}$) przewyższają koszty stałe ($125\,000\text{ zł}$), bilans $+6\,333\text{ zł}$ |
| **Moment zwrotu inwestycji (Payback)** | **Miesiąc 24** | Skumulowany Cash Flow przechodzi na plus ($+113\,279\text{ zł}$), pełny zwrot nakładów |
| **Miesięczny zysk operacyjny pod koniec M24** | $+216\,567\text{ zł / mies.}$ | Wysoka zdolność generowania gotówki (prognoza ponad $2{,}6\text{ mln zł}$ zysku w 3. roku) |

---

## 13. Podsumowanie

Niniejsze sprawozdanie stanowi kompletną, rekurencyjną dokumentację symulacji projektu informatycznego realizacji platformy do wymiany samochodów **SwapCar** – od zdefiniowania kompetencji zespołu projektowego i koncepcji (**TRL 1**), przez budowę i weryfikację modułów w architekturze **MVC** zgodnie z metodyką **PRINCE2** (**TRL 2–5**), analizę **SWOT**, zaawansowane testy serwerowe i użyteczności (**TRL 6**), określenie mierzalnej metryki jakości oraz 14-osobowej struktury sztabowo-liniowej (**Lab 10**), aż po zamknięcie prac rozwojowych i potwierdzenie gotowości do komercjalizacji (**TRL 7–9**).

Przeprowadzona w ramach **Lab 12** analiza budżetu oraz przepływów pieniężnych (**Cash Flow**) w horyzoncie **24 miesięcy** potwierdziła pełną opłacalność wdrożenia platformy **SwapCar**. Przy łącznych nakładach finansowych wynoszących $3\,200\,000\text{ zł}$ i maksymalnym zapotrzebowaniu na kapitał w 12. miesiącu na poziomie $1\,339\,396\text{ zł}$, projekt osiąga **próg rentowności już w 13. miesiącu** (pierwsza nadwyżka miesięczna $+6\,333\text{ zł}$), a **pełny zwrot zainwestowanego kapitału następuje w 24. miesiącu** (skumulowany Cash Flow $+113\,279\text{ zł}$ przy bieżącym zysku miesięcznym $+216\,567\text{ zł}$).