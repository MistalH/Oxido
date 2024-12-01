
# Witajcie Rekruterzy OXIDO! 👋

## Spis treści
1. [Opis Projektu](#opis-projektu)
2. [Jak działa aplikacja?](#jak-działa-aplikacja)
3. [Koszt przetwarzania promptów](#koszt-przetwarzania-promptów)
4. [Dlaczego należy wpisać swój klucz API?](#dlaczego-należy-wpisać-swoj-klucz-api)
5. [Jak uruchomić?](#jak-uruchomić)
6. [Przykład wygenerowanego HTML](#przykład-wygenerowanego-html)
7. [Zadanie dodatkowe: Szablon HTML i Podgląd Artykułu](#zadanie-dodatkowe-szablon-html-i-podgląd-artykułu)
8. [Uwagi końcowe](#uwagi-końcowe)

## Opis Projektu

W Zadaniu wykorzystuje OpenAI API do przekształcania tekstu z pliku do strukturalnego kodu HTML. 
Projekt posiada odczyt danych z pliku tekstowego z funkcjonalnością generowania treści przy użyciu modelu GPT-4.

---

## Jak działa aplikacja?

1. **Odczyt artykułu z pliku tekstowego**:
   - Aplikacja odczytuje treść artykułu z pliku `artykul.txt`.

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
   - Wygenerowany kod HTML jest zapisywany do pliku `artykul.html` w folderze projektu.
   - Plik HTML jest gotowy do użycia, np. w przeglądarce internetowej lub jako część strony internetowej.

5. **Efekt końcowy**:
   - Otrzymany kod HTML jest sformatowany w sposób przejrzysty i profesjonalny.
   - Miejsca na grafiki są oznaczone tagami `<img>` z atrybutami `src` i `alt`, a pod grafikami znajdują się podpisy (`<figcaption>`).

### Koszt przetwarzania promptów
- Do obliczenia liczby tokenów wykorzystano narzędzie: [OpenAI Tokenizer](https://platform.openai.com/tokenizer).
- Koszt jednego prompta dla wersji GPT-4 wynosi około **10 centów**.
---

## Dlaczego należy wpisać swój klucz API?
W miejscu `openai.api_key = '####'` należy wprowadzić swój klucz API, aby umożliwić działanie aplikacji.

---

## Jak uruchomić?

### 1. Sklonuj repozytorium
Uruchom w terminalu:
```bash
git clone <url_repozytorium>

```
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

### 2. Plik `podglad.html`
Jest to kompletny podgląd artykułu z pełną treścią. Zawiera:
- Wyróżniony wstęp z ikonami dla kluczowych trendów technologicznych.
- Przyciski "Więcej informacji" i "Przejdź do kontaktu".
- Tabela z przykładami technologii.

---

## Ograniczenia aplikacji
- Aplikacja **nie generuje pełnych dokumentów HTML** – kod zawiera jedynie zawartość przeznaczoną do umieszczenia między `<body>` i `</body>`.
- **Nie obsługiwane są style CSS ani skrypty JavaScript.**
- Wymaga **poprawnego pliku wejściowego w formacie tekstowym** (np. `artykul.txt`).
- Wymaga **aktywnego połączenia z internetem** do korzystania z API OpenAI.

