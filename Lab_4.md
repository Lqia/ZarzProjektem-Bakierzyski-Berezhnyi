# Sprawozdanie z projektu SwapCar – platforma do wymiany samochodów

**Aktualny poziom gotowości technologicznej: TRL 3 (PGT III)**

## 1. Poziom TRL 1 – koncepcja projektu

### 1.1. Opis pomysłu

SwapCar to aplikacja umożliwiająca wymianę samochodów bezpośrednio między użytkownikami. Działanie aplikacji przypomina aplikacje randkowe (np. Tinder): użytkownicy przesuwają karty samochodów w lewo lub w prawo, aby odrzucić ofertę lub wyrazić zainteresowanie.

W odróżnieniu od zwykłych portali ogłoszeniowych, które skupiają się na sprzedaży, w SwapCar chodzi o wymianę aut sztuka za sztukę lub z dopłatą, jeśli samochody mają różną wartość.

Użytkownicy mogą dodawać ogłoszenia swoich aut, wpisywać ich parametry i zaznaczać, jakiego samochodu szukają. Gdy obie strony polubią swoje auta, aplikacja tworzy parę (match), co pozwala im porozmawiać na czacie i dogadać szczegóły wymiany.

### 1.2. Główne funkcje aplikacji

**Tworzenie ogłoszenia samochodu:**
Użytkownik dodaje swoje auto poprzez prosty formularz, wpisując:

* Markę i model,
* Rocznik,
* Rodzaj paliwa (benzyna, diesel, LPG, elektryk, hybryda),
* Typ nadwozia i kolor,
* Pojemność i moc silnika,
* Przebieg,
* Rodzaj napędu (FWD, RWD, AWD),
* Położenie kierownicy (lewa/prawa),
* Stan techniczny (uszkodzony/nieuszkodzony),
* Orientacyjną cenę i zdjęcia samochodu.

**Określanie preferencji:**
Na starcie użytkownik zaznacza, czego szuka (np. czarny sedan w benzynie po 2015 roku do 30 000 zł). Określa też, czy interesuje go wymiana bezgotówkowa, czy jest gotów dopłacić (i ile maksymalnie), albo czy sam oczekuje dopłaty od drugiej osoby.

**Przeglądanie ofert i dopasowania (matche):**
Oferty są wyświetlane jako karty ze zdjęciem, podstawowymi danymi i ceną:

* Przesunięcie w prawo – podoba mi się (chcę się wymienić).
* Przesunięcie w lewo – odrzucam.

Gdy dwóch użytkowników polubi swoje samochody nawzajem, tworzy się dopasowanie (match) i odblokowuje się czat, na którym mogą się dogadać.

**Ustalanie dopłaty:**
Aplikacja pozwala na wymianę aut o różnej wartości. Przykładowo: Auto A jest warte 25 000 zł, a Auto B 30 000 zł. Właściciel Auta A oferuje swoje auto plus 5 000 zł dopłaty. System bierze te widełki pod uwagę przy podsyłaniu ofert.

### 1.3. Działanie algorytmu dopasowywania

Algorytm bierze pod uwagę trzy rzeczy:

1. **Preferencje początkowe** – to, co użytkownik zaznaczył w filtrach na starcie oraz ile może dopłacić.
2. **Zachowanie w aplikacji** – jakie auta użytkownik najczęściej przesuwa w prawo, a jakie odrzuca (np. jeśli ciągle odrzuca diesle, aplikacja zaczyna pokazywać więcej benzyniaków).
3. **Zgodność w dwie strony** – nie wystarczy, że użytkownikowi A podoba się auto B. Algorytm sprawdza, czy auto A ma szansę spodobać się użytkownikowi B i czy zgadzają się ich oczekiwania finansowe.

### 1.4. Gdzie można to wykorzystać

1. Wymiana aut między zwykłymi kierowcami (osoby prywatne).
2. Wymiana aut między komisami samochodowymi.
3. Podpowiadanie pasujących ofert na podstawie wyborów użytkownika.
4. Pomoc w wycenie aut i sugerowaniu kwoty dopłaty.
5. Sprawdzanie historii pojazdów po numerze VIN.

## 2. Poziom TRL 2 – rozwinięcie koncepcji i zasoby

### 2.1. Założenia drugiej fazy

Pierwsza wersja SwapCar została zaprojektowana jako strona internetowa (aplikacja webowa), którą w kolejnych krokach można rozwinąć o wersję mobilną na telefony.

### 2.2. Wykorzystane zasoby

**Sprzęt i infrastruktura:**

* 3 komputery/laptopy,
* stabilne łącze internetowe,
* serwer testowy (chmura),
* telefon do sprawdzania, jak strona wyświetla się na małym ekranie.

**Programy i narzędzia:**

* Visual Studio Code do pisania kodu,
* GitHub do trzymania kodu i wspólnej pracy w grupie.

**Dane i organizacja:**

* przykładowe dane o samochodach i ich cenach (sztuczna baza do testów),
* darmowe zdjęcia aut z internetu, które można legalnie wykorzystać,
* przykładowe konta użytkowników z różnymi wymaganiami,
* podział zadań (osoba od wyglądu strony, osoba od logiki i bazy danych oraz osoba od testów).

### 2.3. Zrealizowany plan przygotowawczy

1. Rozrysowano wygląd aplikacji.
2. Zaplanowano bazę danych.
3. Opracowano założenia algorytmu dopasowywania ofert.
4. Przygotowano środowisko pod pierwszą wersję strony.
5. Zgromadzono przykładowe dane o autach do testów.

## 3. Poziom TRL 3 – testy założeń i osobnych elementów (Badania przemysłowe)

### 3.1. Potwierdzenie założeń koncepcji (Zadanie 1)

Na trzecim poziomie TRL sprawdziliśmy w praktyce, czy nasz pomysł ma sens i przetestowaliśmy osobno najważniejsze kawałki (moduły) naszego systemu, zanim połączyliśmy je w jedną całość.

W ramach tego etapu zostały zrealizowane i przetestowane następujące elementy:

* **Moduł dodawania i sprawdzania ogłoszeń** – odpowiada za przyjmowanie danych o samochodach z formularza. Na tym etapie położyliśmy nacisk na to, żeby użytkownicy nie mogli wpisać głupot (np. ujemnego przebiegu, rocznika z przyszłości albo pustej ceny). Moduł został wyposażony w mechanizm sprawdzający kompletność danych przed zapisaniem ich do bazy. W ramach testów wrzuciliśmy do niego paczkę przykładowych, częściowo błędnych ogłoszeń – moduł poprawnie wyłapał wszystkie błędy i nie przepuścił niekompletnych ofert.

* **Moduł liczenia dopłat** – kawałek kodu, który porównuje ceny dwóch samochodów i sprawdza, czy użytkownicy są w stanie się dogadać finansowo. Zadaniem modułu jest policzenie różnicy w cenie między autem A i autem B oraz sprawdzenie, czy ta różnica mieści się w kwocie, którą jedna ze stron zadeklarowała jako maksymalną dopłatę. W testach laboratoryjnych opracowaliśmy system walidacji i sprawdziliśmy go na przykładowych parach aut. Określiliśmy w procentach współczynnik zgodności i potwierdziliśmy, że moduł poprawnie łączy oferty z różnymi widełkami cenowymi, odrzucając auta, na które użytkowników nie stać.

* **Moduł dopasowywania ofert (Silnik Matchingowy)** – najważniejszy element, który odpowiada za podsyłanie kart z samochodami w czasie rzeczywistym. W tym module zweryfikowaliśmy, jak szybko system potrafi przejrzeć bazę ogłoszeń i wybrać te, które pasują do filtrów użytkownika. Zbadaliśmy przy tym obciążenie procesora (CPU) i zużycie pamięci RAM na naszym serwerze testowym podczas symulacji, w której wielu użytkowników naraz szybko przesuwało karty w lewo i w prawo. Zastosowaliśmy tu pewną tolerancję – założyliśmy, że płynność ładowania kart i zgodność głównych parametrów (cena, paliwo, rocznik) ma pierwszeństwo przed mniej ważnymi detalami (np. kolor). Badania pozwoliły nam znaleźć optymalny balans między trafnością podpowiedzi a szybkością działania serwera.

Na tym etapie został również określony prosty sposób liczenia punktów dopasowania (model matematyczny oparty na wagach), który pozwolił na wielowątkowe wykonywanie obliczeń. Każda zgodna cecha auta (np. pasujący rocznik czy marka) dodaje punkty, dzięki czemu system szybko układa listę aut od najbardziej do najmniej pasujących.

### 3.2. Projekt SwapCar a 7 pryncypiów metodyki PRINCE2 (Zadanie 2)

Aby w projekcie nie zrobił się bałagan, organizację naszej pracy oparliśmy o 7 zasad (pryncypiów) z metodyki PRINCE2. Trzymamy się ich wszystkich, bo pominięcie chociaż jednej oznacza, że nie pracujemy już zgodnie z PRINCE2:

1. **Ciągła zasadność biznesowa** – cały czas weryfikujemy, czy robienie tej aplikacji ma sens. Przeprowadzone na 3 poziomie TRL testy poszczególnych modułów udowodniły nam, że nasz algorytm faktycznie działa i pozwala szybciej znaleźć auto na wymianę niż zwykłe filtry na portalach typu Otomoto czy OLX. Dzięki temu na bieżąco kontrolujemy ryzyko (np. ryzyko zbyt wolnego działania algorytmu przy dużej bazie aut) i wiemy, że jest ono na akceptowalnym poziomie.

2. **Zdefiniowane role i odpowiedzialności** – najpierw ustaliliśmy, jakie role są nam potrzebne w zespole, a dopiero potem przypisaliśmy do nich konkretne osoby z naszej grupy. Wyznaczyliśmy Kierownika Projektu (pilnuje terminów i sprawozdań) oraz role techniczne (osoba od wyglądu strony, osoba od bazy i algorytmu, osoba od testów). Rolę Komitetu Sterującego (który ocenia naszą pracę i decyduje o zaliczeniu etapu) pełni prowadzący zajęcia. Trzymamy się zasady, że członkowie zespołu mogą łączyć kilka zadań programistycznych, ale Kierownik Projektu nie zasiada w Komitecie Sterującym.

3. **Koncentracja na produktach** – nie skupiamy się na samym „pisaniu kodu”, tylko na konkretnych rzeczach (produktach), które dostarczyliśmy na koniec etapu, i ich jakości. Na obecnym etapie naszymi gotowymi produktami są trzy przetestowane osobno moduły (sprawdzania ogłoszeń, liczenia dopłat i dopasowywania kart) oraz niniejsze sprawozdanie. Całą drogę do gotowej aplikacji podzieliliśmy na mniejsze kroki prowadzące do wykonania tych produktów.

4. **Korzystanie z doświadczeń** – mimo że sam pomysł wymiany aut w stylu Tindera jest dość świeży, to tworzenie stron internetowych składa się z powtarzalnych procesów. Skorzystaliśmy z doświadczeń z poprzednich zajęć i projektów na studiach oraz podpatrzyliśmy sprawdzone rozwiązania z istniejących aplikacji randkowych (mechanizm przesuwania kart) i portali ogłoszeniowych (wygląd formularza z parametrami auta). Wyciągnęliśmy też wnioski z tego, co wypracowaliśmy w sprawozdaniach dla TRL 1 i TRL 2.

5. **Zarządzanie z wykorzystaniem tolerancji** – w projekcie określiliśmy granice tolerancji (swobody), w których nasz Kierownik Projektu sam podejmuje decyzje. Ustaliliśmy tolerancję czasową (terminy oddania sprawozdań i kolejnych etapów), kosztową (korzystamy z darmowych narzędzi i własnych laptopów, więc budżet wynosi 0 zł) oraz jakościową (w module dopasowywania ofert założyliśmy, że płynność działania aplikacji jest ważniejsza niż idealne dopasowanie drugorzędnych cech, takich jak kolor auta).

6. **Zarządzanie etapowe** – podzieliliśmy nasz projekt na konkretne, niezbyt długie etapy, które pokrywają się z kolejnymi poziomami TRL (TRL 1 – pomysł, TRL 2 – zasoby i plan, TRL 3 – testy pojedynczych modułów). Po każdym etapie robimy podsumowanie w formie sprawozdania i po uzyskaniu akceptacji przechodzimy dalej. Dzięki temu mamy pełną kontrolę nad postępami prac i jakością projektu.

7. **Dostosowanie do projektu w danym środowisku** – dostosowaliśmy narzędzia i sposób zarządzania do rozmiaru naszego projektu. Jak mówi zasada: „nie strzela się do komara z armaty”. Zrealizowaliśmy projekt w 3-osobowej grupie, więc zamiast tworzyć setki stron zbędnej dokumentacji, dobraliśmy lekkie i wygodne narzędzia (VS Code, GitHub, komunikator do szybkiego kontaktu) oraz prosty podział zadań skrojony dokładnie pod nasze potrzeby.

## 4. Podsumowanie

Na poziomie **TRL 1** opracowaliśmy koncepcję aplikacji SwapCar, określiliśmy jakie dane o autach są potrzebne i jak działa system dopasowań oraz dopłat. Na poziomie **TRL 2** ustaliliśmy architekturę aplikacji internetowej, przygotowaliśmy potrzebny sprzęt, programy i dane testowe.

Na obecnym poziomie **TRL 3** zrealizowaliśmy i przetestowaliśmy trzy główne moduły systemu (walidację ogłoszeń, liczenie dopłat oraz silnik dopasowań), sprawdziliśmy ich wydajność pod kątem obciążenia procesora i pamięci RAM, opracowaliśmy punktowy model dopasowań oraz zorganizowaliśmy pracę zgodnie z 7 zasadami metodyki PRINCE2.