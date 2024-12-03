
# Witajcie Rekruterzy OXIDO! 👋

## Spis treści
1. [Opis Projektu](#opis-projektu)
2. [Jak działa aplikacja?](#jak-działa-aplikacja)
3. [Koszt przetwarzania promptów](#koszt-przetwarzania-promptów)
4. [Dlaczego należy wpisać swój klucz API?](#dlaczego-należy-wpisać-swoj-klucz-api)
5. [Jak uruchomić?](#jak-uruchomić)
6. [Przykład wygenerowanego HTML](#przykład-wygenerowanego-html)
7. [Zadanie dodatkowe: Szablon HTML i Podgląd Artykułu](#zadanie-dodatkowe-szablon-html-i-podgląd-artykułu)
   - [Stylizacja i animacje w CSS](#stylizacja-i-animacje-w-css)
   - [Podgląd HTML](#podgląd-html)
   - [Dodatkowe efekty i animacje](#dodatkowe-efekty-i-animacje)
8. [Uwagi końcowe](#uwagi-końcowe)

   
---


## Opis Projektu

W Zadaniu wykorzystuje OpenAI API do przekształcania tekstu z pliku do strukturalnego kodu HTML. 
Projekt posiada odczyt danych z pliku tekstowego z funkcjonalnością generowania treści przy użyciu modelu GPT-4.

---

# Oxido - Generowanie HTML z treści artykułów

Aplikacja służy do automatycznego generowania kodu HTML z plików tekstowych zawierających treści artykułów, z wykorzystaniem API OpenAI GPT-4.

---

## Jak działa aplikacja?

1. **Odczyt artykułu z pliku tekstowego**:
   - Aplikacja odczytuje treść artykułu z pliku `artykul.txt`.
   - Weryfikowana jest obecność i zawartość pliku, aby uniknąć błędów związanych z brakującymi lub pustymi plikami.

2. **Przygotowanie prompta**:
   - Aplikacja generuje szczegółowy prompt, który zawiera:
     - Treść artykułu.
     - Instrukcje dotyczące tworzenia kodu HTML:
       - Użycie odpowiednich tagów HTML do strukturyzacji treści.
       - Dodanie znaczników `<img>` z placeholderem `src="image_placeholder.jpg"` oraz opisami w atrybucie `alt`.
       - Wstawienie podpisów pod grafikami przy użyciu tagu `<figcaption>`.
       - Wykluczenie nagłówków `<html>`, `<head>`, czy `<body>`.

3. **Wysłanie zapytania do OpenAI**:
   - Przygotowany prompt jest wysyłany do OpenAI GPT-4 za pomocą funkcji `openai.ChatCompletion.create`.
   - Model generuje kod HTML zgodnie z podanymi wytycznymi.

4. **Odbiór i zapis wygenerowanego kodu HTML**:
   - Wygenerowany kod HTML jest zapisywany do plików `artykul_part_1.html`, `artykul_part_2.html` itd., w zależności od ilości podzielonych fragmentów tekstu.
   - Każdy plik HTML zawiera semantycznie poprawny kod, gotowy do użycia w przeglądarkach internetowych.

5. **Efekt końcowy**:
   - Otrzymany kod HTML jest sformatowany w sposób przejrzysty i profesjonalny.
   - Miejsca na grafiki są oznaczone tagami `<img>` z atrybutami `src` i `alt`, a pod grafikami znajdują się podpisy (`<figcaption>`).

---

## Koszt przetwarzania promptów
- Aplikacja generuje kod HTML za pomocą GPT-4. Do obliczenia liczby tokenów wykorzystano narzędzie: [OpenAI Tokenizer](https://platform.openai.com/tokenizer).
- Koszt jednego prompta dla wersji GPT-4 wynosi około **10 centów**, w zależności od liczby tokenów w treści artykułu.

---

## Wymagania

1. **Klucz API OpenAI**:
   - W miejscu `openai.api_key = '####'` należy wprowadzić swój klucz API, aby umożliwić działanie aplikacji.
   - Klucz powinien być przechowywany bezpiecznie, najlepiej w zmiennej środowiskowej.

2. **Zainstalowane zależności**:
   - Python 3.7+.
   - Biblioteki: `openai`, `os`, `logging`.

---

## Jak uruchomić?

1. Skopiuj repozytorium na swój komputer:
   ```bash
   git clone <URL-repozytorium>
   cd Oxido
2. Zainstaluj wymagane biblioteki:
   ```bash
   pip install -r requirements.txt
3.Wprowadź klucz API OpenAI:
   -Dodaj go jako zmienną środowiskową OPENAI_API_KEY.
4. Umieść plik tekstowy z artykułem jako artykul.txt w folderze projektu.
5.Uruchom aplikację:
     ```bash
     python Oxido.ipynb
Znajdź wygenerowane pliki HTML w folderze projektu.

## Funkcje bezpieczeństwa i niezawodności
- Obsługa błędów:
     - Aplikacja loguje błędy (np. brakujące pliki, błędne odpowiedzi API) do pliku error_log.txt.
     - W przypadku braku klucza API aplikacja przerywa działanie z czytelnym komunikatem błędu.
- Walidacja danych wejściowych:
   - Sprawdzanie obecności i zawartości pliku artykul.txt.
- Podział treści na fragmenty:
   - W celu uniknięcia przekroczenia limitu tokenów w zapytaniu do API, tekst jest automatycznie dzielony na mniejsze części.

# Zadanie Dodatkowe "Szablon HTML i Podgląd Artykułu"

## 📄 Opis Projektu
Projekt dotyczy stworzenia **szablonu HTML** i **podglądu artykułu** w pliku HTML, z uwzględnieniem odpowiedniej struktury, stylów CSS i funkcji interaktywnych w JavaScript. 

Zadanie obejmowało:
- **Plik `szablon.html`** – zawiera pustą sekcję `<body>`, gotową do wklejenia treści artykułu.
- **Plik `podglad.html`** – prezentuje pełny podgląd artykułu z tekstem, stylami oraz elementami interaktywnymi.

---

## 🔧 Wykorzystane technologie

1. **HTML5**: Struktura strony.
2. **CSS3**: Stylizacja ciemnego motywu, animacje oraz efekty hover.
3. **Bootstrap 5**: Użyty do stworzenia responsywnego navbaru i stylizacji przycisków.
4. **Font Awesome**: Dodane ikony do uatrakcyjnienia wizualnego projektu.
5. **JavaScript**: Animacje, przewijanie strony, efekty interaktywne.

---

## ⚙️ Funkcjonalności

1. **Szablon HTML (`szablon.html`)**:
   - Zawiera responsywny navbar przygotowany w Bootstrapie.
   - Pustą sekcję `<div class="container">`, która pozwala na wklejenie dowolnej treści.
   - Przygotowane style w CSS, takie jak animacje gradientowego tła czy efekty hover na przyciskach i linkach.

2. **Podgląd HTML (`podglad.html`)**:
   - Pełna wizualizacja artykułu z treścią.
   - Lista funkcji z ikonami oraz wyróżnione sekcje.
   - Tabela porównawcza z trendami technologicznymi (AI, IoT, 5G).
   - Stylizowane nagłówki i przyciski z efektami hover.

3. **Dodatkowe efekty i animacje**:
   - Gradientowe tło animowane za pomocą CSS.
   - Hover z poświatą dla przycisków i linków.
   - Efekt pojawiania się treści po załadowaniu strony (CSS `@keyframes`).
---
## 📋 Instrukcje

### 1. Plik `szablon.html`
Jest to szablon podstawowy, który zawiera wszystkie style i strukturę strony, z pustą sekcją `<body>`. Wykorzystaj ten plik, aby dodawać własne treści do artykułu. 

Główne elementy:
- **Navbar**: Gotowy, responsywny pasek nawigacyjny.
- **Sekcja body**: Pusta przestrzeń gotowa do wklejenia treści artykułu.
- **Style i animacje**: Całkowicie zintegrowane w `<head>`.

## 2. Plik `podglad.html`

Jest to kompletny podgląd artykułu w formacie HTML, który prezentuje nowoczesne podejście do prezentacji treści i technologii. Zawiera następujące elementy:

### 1. Wyróżniony wstęp
- Zastosowano przykuwające uwagę ikony (np. roboty, chmura, IoT) dla kluczowych trendów technologicznych.
- Wstęp podkreślony jest czytelną typografią i atrakcyjnym gradientowym tłem.

### 2. Interaktywne przyciski
- **"Więcej informacji"**: Wyświetla komunikat z dalszymi szczegółami artykułu.
- **"Przejdź do kontaktu"**: Nawiguje do sekcji kontaktowej.

### 3. Tabela technologii
- Prezentuje najważniejsze technologie w porównawczym formacie tabelarycznym.
- Nagłówki tabel wyróżnione kolorem, co poprawia czytelność.
- Dodano podświetlenie wierszy tabeli przy najechaniu kursorem.

### 4. Galeria zdjęć
- Użyto biblioteki **Lightbox.js** do wyświetlania zdjęć w pełnym rozmiarze po kliknięciu.
- Dynamiczne efekty hover z subtelnymi powiększeniami i filtrowaniem obrazów.

### 5. Mapa interaktywna
- Umieszczono mapę z oznaczoną siedzibą firmy Oxido w Krakowie.
- Po kliknięciu markera mapa płynnie przybliża widok, a popup wyświetla szczegóły lokalizacji.

### 6. Wykres w czasie rzeczywistym
- Zastosowano bibliotekę **Chart.js** do wizualizacji popularności technologii w dynamicznie zmieniającej się formie wykresu liniowego.

### 7. Sekcja komentarzy
- Komentarze ładowane dynamicznie z animacją.
- Każdy komentarz zawiera zdjęcie użytkownika, jego imię oraz treść.

### 8. Przełącznik motywów
- Możliwość zmiany między trybem ciemnym a jasnym z płynną animacją tła. 

---
---

## Ograniczenia aplikacji
- Aplikacja **nie generuje pełnych dokumentów HTML** – kod zawiera jedynie zawartość przeznaczoną do umieszczenia między `<body>` i `</body>`.
- **Nie obsługiwane są style CSS ani skrypty JavaScript.**
- Wymaga **poprawnego pliku wejściowego w formacie tekstowym** (np. `artykul.txt`).
- Wymaga **aktywnego połączenia z internetem** do korzystania z API OpenAI.

