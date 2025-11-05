# Domain Hunter Pro

Czy wciąż używasz Excela do zarządzania celami?

Czy wciąż męczysz się ze zbieraniem informacji o swoich celach?

Czy podczas testów wciąż kopiujesz i wklejasz te same dane?

Wypróbuj **Domain Hunter Pro**! To narzędzie oferuje wygodne zarządzanie celami, automatyczne zbieranie informacji, bezproblemową integrację z Burp Suite oraz współpracę z zewnętrznymi narzędziami bezpieczeństwa.

Jest to narzędzie stworzone, aby zwiększyć wydajność pracy specjalistów ds. bezpieczeństwa, etycznych hakerów (SRC white hats) i inżynierów testów bezpieczeństwa!

## Autorzy i Współtwórcy

*   **bit4woo**
*   **mmmark** (wiele kluczowych pomysłów pochodzi z jego cennego doświadczenia praktycznego!)

## Szybki Start

### Pobieranie i Instalacja

Pobierz plik `.jar` z sekcji [Releases](https://github.com/bit4woo/domain_hunter_pro/releases).

Ponieważ program jest wtyczką do Burp Suite, musi być używany razem z nim.

1.  Otwórz Burp Suite.
2.  Przejdź do zakładki `Extender` -> `Extensions`.
3.  Kliknij `Add` i wybierz pobrany plik `.jar`.

Po instalacji interfejs wtyczki pojawi się jako nowa zakładka.

### Tworzenie Pliku Projektu (Baza SQLite)

Możesz stworzyć nowy projekt lub otworzyć istniejący plik projektu (z rozszerzeniem `.db`).

### Zarządzanie Domenami Głównymi

Domeny główne są kluczowym elementem zarządzania celami. Wszystkie powiązane z nimi subdomeny, domeny podobne, adresy e-mail czy nazwy pakietów Javy są grupowane na podstawie domeny głównej. Na przykład, weźmy `baidu.com`.

Po dodaniu domeny głównej, przeglądaj stronę za pomocą przeglądarki skonfigurowanej z Burp Proxy, aby zbierać ruch sieciowy. Następnie, używając funkcji wyszukiwania wtyczki, możesz wyodrębnić wszystkie powiązane domeny z przechwyconego ruchu.

### Pobieranie Tytułów Stron (Titles)

W zakładce `Titles` możesz automatycznie, wielowątkowo odwiedzić znalezione domeny, aby pobrać tytuły ich stron głównych, adresy IP i inne informacje.

### Zarządzanie Celami

Menu kontekstowe (prawy przycisk myszy) umożliwia integrację z przeglądarką i innymi funkcjami Burp Suite, takimi jak `Repeater` czy `Intruder`.

## Samodzielna Kompilacja

Aby skorzystać z najnowszych funkcji, możesz samodzielnie skompilować projekt.

**Wymagania:**
*   JDK 1.8 (lub nowszy)
*   Apache Maven

**Kroki:**
1.  Sklonuj repozytorium: `git clone https://github.com/bit4woo/domain_hunter_pro`
2.  Przejdź do katalogu projektu: `cd domain_hunter_pro`
3.  Uruchom kompilację: `mvn package`

Skompilowany plik `.jar` znajdzie się w katalogu `target`.

*Uwaga: W zależności od konfiguracji Maven, może być konieczne dodanie tokenu dostępowego GitHub do pliku `settings.xml`, zgodnie z instrukcjami w oryginalnym `README.md`.*

---

## Analiza Projektu (Wykonana przez AI)

### Opis Funkcjonalności

**Domain Hunter Pro** to zaawansowane rozszerzenie do **Burp Suite**, które automatyzuje i upraszcza proces zbierania informacji oraz zarządzania celami w testach penetracyjnych.

#### Główne Moduły

1.  **Zakładka `Domains` (Domeny):**
    *   **Automatyczne zbieranie danych:** Pasywnie analizuje ruch z Burp Proxy, wyodrębniając subdomeny, powiązane domeny, adresy e-mail i inne.
    *   **Wykrywanie Zone Transfer:** Aktywnie skanuje serwery DNS w poszukiwaniu podatności umożliwiającej wyciek subdomen.
    *   **Zarządzanie zakresem:** Umożliwia definiowanie celów jako domen, adresów IP lub całych podsieci.
    *   **Czarna lista:** Pozwala na wykluczenie nieistotnych zasobów z analizy.

2.  **Zakładka `Titles` (Tytuły):**
    *   **Pobieranie informacji o stronach:** Wielowątkowo odpytuje znalezione domeny, aby pobrać tytuły stron, adresy IP oraz informacje o dostawcach CDN.
    *   **Zarządzanie postępem:** Umożliwia sortowanie, filtrowanie (także za pomocą dorków), dodawanie notatek i oznaczanie statusu (np. "sprawdzone").
    *   **Integracja z Burp Suite:** Ułatwia przesyłanie żądań do innych narzędzi, jak Repeater czy Intruder.

3.  **Zakładka `Tools` (Narzędzia):**
    *   Zestaw prostych narzędzi pomocniczych, m.in. do konwersji danych, ekstrakcji wartości z JSON, dekodowania HTML/Unicode oraz operacji na adresach IP.

### Wymagania Środowiskowe

*   **Oprogramowanie:**
    *   **Burp Suite:** Wersja Professional lub Community.
    *   **JDK 1.8 (lub nowszy):** Wymagany do samodzielnej kompilacji projektu.
    *   **Apache Maven:** Wymagany do samodzielnej kompilacji.
*   **Sprzęt:**
    *   **RAM:** Minimum 8 GB (zalecane 16 GB).
    *   **CPU:** Nowoczesny, wielordzeniowy procesor.
    *   **Dysk:** Kilkaset MB wolnego miejsca na pliki projektu.

### Integracja z Zewnętrznymi API i Szacunkowe Koszty

Rozszerzenie może integrować się z zewnętrznymi serwisami w celu zaawansowanego wyszukiwania informacji. Większość z nich działa w modelu **freemium**, oferując darmowy, ale ograniczony plan.

| Serwis               | Darmowy Plan (Limity)                                | Szacunkowy Koszt Planu Płatnego                |
| -------------------- | ---------------------------------------------------- | ---------------------------------------------- |
| **Fofa**             | Tak, z ograniczeniami                                | Od ok. **$25 / miesiąc**                       |
| **FullHunt**         | Tak, 10 zapytań / miesiąc                            | Od **$29 / miesiąc**                           |
| **Hunter (qianxin)** | Tak, bardzo hojny (do 10 000 wyników / miesiąc)      | Od ok. **$8 / miesiąc**                        |
| **Hunter.io**        | Tak, 50 zapytań / miesiąc                            | Od **$49 / miesiąc**                           |
| **Shodan**           | Bardzo ograniczony                                   | **$49 (jednorazowo)** za członkostwo           |
| **ZoomEye**          | Tak, z ograniczeniami                                | Model oparty na punktach (np. $249 za 10 000)  |
| **Quake (360)**      | Prawdopodobnie tak                                   | Brak publicznego cennika                       |

*Uwaga: Korzystanie z tych integracji jest **opcjonalne**. Podstawowa funkcjonalność narzędzia nie wymaga żadnych kluczy API ani dodatkowych opłat.*

### Analiza Bezpieczeństwa

Kod źródłowy projektu został przeanalizowany pod kątem obecności złośliwego oprogramowania. Analiza obejmowała wyszukiwanie potencjalnie niebezpiecznych słów kluczowych oraz funkcji mogących wykonywać kod systemowy (np. `Runtime.exec`).

**Wynik:** W kodzie **nie znaleziono żadnych dowodów na obecność złośliwego oprogramowania, backdoorów ani innych zagrożeń bezpieczeństwa.** Projekt można uznać za bezpieczny w użyciu.
