# SwapCar – platforma do wymiany samochodów

**Poziom gotowości technologicznej: TRL 1 (PGT I)**

## 1. Opis koncepcji technologicznej

Celem projektu jest opracowanie koncepcji platformy umożliwiającej bezpośrednią wymianę samochodów pomiędzy użytkownikami. Aplikacja będzie działała na zasadzie popularnych aplikacji randkowych, w których użytkownicy przeglądają profile i wyrażają zainteresowanie poprzez przesuwanie kart w lewo lub w prawo.

W odróżnieniu od tradycyjnych portali ogłoszeniowych, które koncentrują się przede wszystkim na sprzedaży pojazdów, SwapCar będzie skupiał się na bezpośredniej wymianie samochodów, z możliwością ustalenia dopłaty finansowej pomiędzy właścicielami.

Użytkownik będzie mógł dodać ogłoszenie swojego samochodu, określić jego parametry oraz wskazać, jakiego pojazdu poszukuje. Następnie aplikacja będzie prezentowała dopasowane oferty. Jeśli dwie osoby wyrażą zainteresowanie swoimi samochodami, system utworzy dopasowanie (match) i umożliwi im rozpoczęcie rozmowy w celu ustalenia szczegółów wymiany.

## 2. Główne funkcjonalności koncepcji

### 2.1. Tworzenie ogłoszenia samochodu

Użytkownik będzie mógł dodać swój samochód, uzupełniając formularz zawierający następujące informacje:

- Marka.
- Model.
- Rocznik.
- Rodzaj paliwa: benzyna, diesel, LPG, samochód elektryczny lub hybrydowy.
- Typ nadwozia.
- Kolor.
- Pojemność silnika.
- Moc silnika.
- Przebieg.
- Rodzaj napędu: FWD, RWD lub AWD.
- Umiejscowienie kierownicy: lewa lub prawa.
- Stan techniczny: uszkodzony lub nieuszkodzony.
- Orientacyjna cena pojazdu.
- Zdjęcia samochodu.

Dzięki temu użytkownicy będą mogli dokładnie określić parametry oferowanego pojazdu, co ułatwi późniejsze dopasowywanie ogłoszeń.

### 2.2. Określanie preferencji użytkownika

Podczas rozpoczęcia korzystania z aplikacji użytkownik będzie mógł określić, jakiego samochodu poszukuje. Będzie mógł wskazać między innymi preferowaną markę, model, rocznik, kolor, rodzaj paliwa, typ nadwozia, moc silnika oraz przedział cenowy.

Przykładowo użytkownik może szukać czarnego sedana z silnikiem benzynowym, wyprodukowanego po 2015 roku, o wartości do 30 000 zł.

Dodatkowo użytkownik będzie mógł określić, czy interesuje go wymiana bez dopłaty, wymiana z dopłatą z jego strony, czy też wymiana, w której oczekuje dopłaty od drugiego właściciela. Będzie mógł również określić maksymalną akceptowaną różnicę cenową.

### 2.3. Przeglądanie ofert

Aplikacja będzie prezentowała samochody w formie kart zawierających zdjęcia, podstawowe parametry oraz cenę orientacyjną.

Obsługa będzie opierała się na prostym mechanizmie przesuwania kart:

- Przesunięcie w prawo oznacza zainteresowanie samochodem.
- Przesunięcie w lewo oznacza odrzucenie oferty.

Na podstawie preferencji użytkownika oraz jego wcześniejszych decyzji system będzie mógł dostosowywać kolejność prezentowanych ogłoszeń, aby wyświetlać przede wszystkim te, które mają największą szansę spełnić jego oczekiwania.

### 2.4. Dopasowanie użytkowników i komunikacja

Jeżeli dwóch użytkowników wyrazi zainteresowanie swoimi samochodami, system utworzy wzajemne dopasowanie, czyli match.

Po utworzeniu dopasowania użytkownicy uzyskają możliwość rozpoczęcia rozmowy. Będą mogli wymieniać się dodatkowymi informacjami o pojazdach, zadawać pytania, negocjować warunki oraz ustalać szczegóły przekazania samochodów.

### 2.5. Ustalanie dopłaty finansowej

Jedną z istotnych funkcjonalności będzie możliwość wymiany samochodów o różnej wartości.

Przykład:

- Samochód A ma wartość orientacyjną 25 000 zł.
- Samochód B ma wartość orientacyjną 30 000 zł.
- Właściciel samochodu A oferuje swój pojazd i dopłatę w wysokości 5 000 zł.

Dzięki temu użytkownicy nie będą musieli szukać wyłącznie samochodów o zbliżonej wartości. System będzie uwzględniał różnicę cenową podczas dopasowywania ofert.

Podane wartości będą miały charakter orientacyjny, a ostateczne warunki wymiany będą ustalane bezpośrednio przez zainteresowane osoby.

## 3. Koncepcja algorytmu dopasowywania ofert

Jednym z najważniejszych elementów projektu będzie algorytm odpowiedzialny za dopasowywanie samochodów do preferencji użytkowników.

Algorytm będzie uwzględniał dwa główne rodzaje danych.

### 3.1. Preferencje początkowe

Pierwszym źródłem informacji będą preferencje podane przez użytkownika podczas rozpoczęcia korzystania z aplikacji. Obejmą one między innymi:

- Preferowaną markę i model.
- Rodzaj paliwa.
- Typ nadwozia.
- Kolor.
- Rocznik.
- Moc silnika.
- Przedział cenowy.
- Akceptowaną różnicę cenową przy wymianie.

### 3.2. Analiza zachowania użytkownika

Drugim źródłem informacji będą działania użytkownika podczas przeglądania ofert. System będzie analizował, które samochody zostały zaakceptowane, a które odrzucone.

Na tej podstawie algorytm będzie mógł stopniowo rozpoznawać preferencje użytkownika i dostosowywać prezentowane propozycje. Przykładowo, jeżeli użytkownik często akceptuje sedany z silnikami benzynowymi, a odrzuca samochody z silnikami Diesla, system będzie mógł zwiększać priorytet ofert spełniających te preferencje.

W przyszłości możliwe będzie również zastosowanie bardziej zaawansowanych metod uczenia maszynowego.

### 3.3. Wzajemna zgodność ofert

Algorytm będzie mógł również analizować, czy wymiana jest korzystna z punktu widzenia obu stron.

Nie wystarczy bowiem, że użytkownik A zainteresuje się samochodem użytkownika B. Ważne jest również, czy użytkownik B będzie zainteresowany samochodem A oraz czy obie strony zaakceptują warunki finansowe.

W tym celu system będzie mógł obliczać wynik dopasowania na podstawie zgodności parametrów pojazdów, preferencji użytkowników oraz różnicy cenowej.

## 4. Potencjalne zastosowania technologii

Opracowana koncepcja może znaleźć zastosowanie w kilku obszarach:

1. **Wymiana samochodów pomiędzy osobami prywatnymi** – podstawowe zastosowanie platformy, umożliwiające bezpośrednie wyszukiwanie osób zainteresowanych wymianą pojazdów.
2. **Wymiana pojazdów pomiędzy komisami samochodowymi** – możliwość wykorzystania platformy przez przedsiębiorstwa zajmujące się handlem samochodami.
3. **Inteligentne rekomendacje** – personalizowanie prezentowanych ofert na podstawie preferencji i zachowania użytkowników.
4. **Analiza wartości pojazdów** – rozwinięcie systemu o mechanizmy szacowania wartości samochodów i sugerowania różnic cenowych.
5. **Weryfikacja ofert** – w przyszłości możliwość wykorzystania zewnętrznych baz danych do sprawdzania historii pojazdów i ograniczania liczby nieuczciwych ogłoszeń.

## 5. Uzasadnienie poziomu gotowości technologicznej TRL 1

Projekt znajduje się na pierwszym poziomie gotowości technologicznej TRL 1, ponieważ jego obecny etap obejmuje sformułowanie koncepcji rozwiązania, określenie jego podstawowych funkcjonalności oraz wskazanie potencjalnych zastosowań.

Na tym etapie nie zakłada się jeszcze istnienia gotowej aplikacji ani sprawdzonego algorytmu dopasowującego oferty. Nie przeprowadzono również testów potwierdzających skuteczność proponowanego rozwiązania.

Dalszy rozwój projektu mógłby obejmować opracowanie szczegółowej specyfikacji, zaprojektowanie architektury systemu, przygotowanie prototypu oraz przeprowadzenie testów weryfikujących poprawność działania algorytmu.

## 6. Podsumowanie

SwapCar to koncepcja platformy umożliwiającej wymianę samochodów pomiędzy użytkownikami, wykorzystującej mechanizm wzajemnego dopasowywania ofert, personalizację rekomendacji oraz możliwość ustalania dopłat finansowych.

Głównym założeniem projektu jest uproszczenie procesu poszukiwania odpowiedniego samochodu poprzez połączenie funkcjonalności portalu ogłoszeniowego z intuicyjnym interfejsem opartym na przesuwaniu kart.

Potencjalną przewagą rozwiązania będzie uwzględnianie nie tylko parametrów pojazdów, ale również indywidualnych preferencji użytkowników oraz warunków finansowych wymiany.

Na obecnym etapie projekt stanowi koncepcję technologiczną, która może zostać rozwinięta w kolejnych etapach prac badawczych i rozwojowych.
