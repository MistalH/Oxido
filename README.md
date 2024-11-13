
# Witajcie Rekruterzy OXIDO! 👋

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
W miejscu `openai.api_key = '####'` należy wprowadzić swój klucz API, aby umożliwić działanie aplikacji. Aby zwiększyć bezpieczeństwo:

---

## Jak uruchomić?

### 1. Sklonuj repozytorium
Uruchom w terminalu:
```bash
git clone <url_repozytorium>
