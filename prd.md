# Dokument wymagań produktu (PRD) - HealthyMeal

## 1. Przegląd produktu
HealthyMeal to aplikacja skierowana do osób szukających przepisów kulinarnych idealnie dopasowanych do ich indywidualnych wymagań żywieniowych. Aplikacja wykorzystuje model LLM do modyfikowania przepisów w oparciu o preferencje użytkownika oraz umożliwia ich zapisywanie i przeglądanie. W wersji MVP system obejmuje podstawowe funkcje takie jak: rejestracja, logowanie, zarządzanie przepisami oraz prosty mechanizm wyszukiwania przepisu.

## 2. Problem użytkownika
Użytkownicy mają trudności w znalezieniu przepisów, które odpowiadałyby ich specyficznym wymaganiom dietetycznym. Standardowe przepisy dostępne w sieci nie uwzględniają indywidualnych preferencji, co powoduje, że dostosowanie przepisu do własnych potrzeb jest czasochłonne i problematyczne.

## 3. Wymagania funkcjonalne
- Rejestracja użytkownika z wykorzystaniem adresu email i hasła.
- Logowanie i uwierzytelnianie użytkownika zapewniające dostęp do własnych danych.
- Funkcjonalność zapisywania, odczytywania, przeglądania oraz usuwania przepisów w formie tekstowej.
- Strona profilu użytkownika umożliwiająca zapisanie preferencji żywieniowych.
- Mechanizm wyszukiwania przepisu oparty na zapytaniach tekstowych, integrujący model LLM do generowania przepisu.
- Walidacja inputu użytkownika, w tym limit do 1000 znaków z kontrolką umożliwiającą decyzję o przekroczeniu tego limitu.
- Interaktywne przetwarzanie wyniku wyszukiwania, umożliwiające akceptację przepisu lub ponowne wyszukiwanie w przypadku odrzucenia.

## 4. Granice produktu
- Rejestracja odbywa się wyłącznie przy użyciu prawidłowego adresu email i hasła; brak zaawansowanych metod uwierzytelniania, takich jak dwuskładnikowa weryfikacja.
- Przepisy są przechowywane jedynie w formie tekstowej; brak importu przepisów z URL oraz obsługi multimediów (np. obrazów czy filmów).
- Brak funkcjonalności społecznościowych, takich jak udostępnianie przepisów, komentowanie lub ocena przepisów przez innych użytkowników.
- Rozbudowany profil użytkownika (np. szczegółowe dane odżywcze, plan treningowy) nie jest częścią MVP.
- Zaawansowane mechanizmy analizy i interpretacji wyjścia LLM pozostają poza zakresem MVP.

## 5. Historyjki użytkowników

- ID: US-001  
  Tytuł: Rejestracja konta użytkownika  
  Opis: Użytkownik rejestruje się podając swój adres email oraz hasło, co umożliwia mu utworzenie konta w systemie i dostęp do swoich danych.  
  Kryteria akceptacji:
  - Formularz rejestracyjny przyjmuje prawidłowy adres email i hasło.
  - System tworzy unikalne konto użytkownika po poprawnej walidacji danych.
  - Użytkownik otrzymuje potwierdzenie utworzenia konta.

- ID: US-002  
  Tytuł: Logowanie do systemu  
  Opis: Użytkownik loguje się do systemu używając swojego adresu email oraz hasła, co zapewnia dostęp do prywatnych przepisów zapisanych w jego koncie.  
  Kryteria akceptacji:
  - System akceptuje logowanie tylko przy użyciu poprawnych danych.
  - Użytkownik ma dostęp wyłącznie do swoich zapisanych przepisów.
  - W przypadku błędnych danych użytkownik otrzymuje odpowiednią informację.

- ID: US-003  
  Tytuł: Dodawanie przepisu  
  Opis: Użytkownik ma możliwość dodania nowego przepisu w formie tekstowej, który zostaje zapisany w systemie powiązanym z jego kontem.  
  Kryteria akceptacji:
  - Formularz wprowadzania przepisu umożliwia wprowadzenie tekstu do 1000 znaków (z opcją potwierdzenia przekroczenia limitu).
  - Przepis zostaje zapisany i pojawia się na liście przepisów użytkownika.

- ID: US-004  
  Tytuł: Przeglądanie zapisanych przepisów  
  Opis: Użytkownik może przeglądać listę wszystkich zapisanych przepisów, a także uzyskać szczegółowe informacje o wybranym przepisie. Przepisy są prezentowane w formie wyboldowanego nagłówka (zwięzłego podsumowania dania) oraz szczegółowego opisu (który można zwinąć lub rozwinąć). Występuje też paginacja
  Kryteria akceptacji:
  - Lista przepisów wyświetla wszystkie dane przypisane do danego konta użytkownika.
  - Użytkownik może kliknąć wybrany przepis, aby zobaczyć jego pełną treść.

- ID: US-005  
  Tytuł: Usuwanie przepisu  
  Opis: Użytkownik ma możliwość usunięcia przepisu, który nie jest już potrzebny, poprzez prostą akcję w interfejsie.  
  Kryteria akceptacji:
  - System umożliwia usunięcie przepisu po potwierdzeniu użytkownika.
  - Po usunięciu, przepis nie pojawia się na liście zapisanych pozycji.

- ID: US-006  
  Tytuł: Wyszukiwanie przepisu  
  Opis: Użytkownik wpisuje zapytanie tekstowe, które jest wysyłane do modelu LLM i na jego podstawie generowany jest przepis. Po kliknięciu przycisku "Szukaj", użytkownik otrzymuje wygenerowany przepis.  
  Kryteria akceptacji:
  - System waliduje długość wejścia (limit do 1000 znaków z opcją potwierdzenia przekroczenia).
  - Po wysłaniu zapytania, użytkownik otrzymuje wynikowy przepis generowany przez LLM.
  - Interfejs umożliwia akceptację przepisu lub ponowne wyszukiwanie w przypadku odrzucenia.

- ID: US-007  
  Tytuł: Ponowne wyszukiwanie przepisu  
  Opis: Po otrzymaniu przepisu, użytkownik może zdecydować o jego odrzuceniu, co skutkuje wysłaniem nowego zapytania do systemu w celu wygenerowania alternatywnego przepisu.  
  Kryteria akceptacji:
  - Opcja "Ponów" umożliwia odrzucenie przepis i generowanie nowego wyniku.
  - System wyświetla nowy przepis po ponownym wysłaniu zapytania.

- ID: US-008  
  Tytuł: Ustawienia preferencji żywieniowych  
  Opis: Użytkownik może ustawić swoje preferencje żywieniowe w profilu, co wpływa na wyniki wyszukiwania przepisu.  
  Kryteria akceptacji:
  - Strona profilu umożliwia wprowadzenie i zapisanie preferencji żywieniowych.
  - Zapisane preferencje są wykorzystywane przez system przy generowaniu przepisu na podstawie zdefiniowanych kryteriów.

## 6. Metryki sukcesu
- 90% użytkowników wypełnia sekcję preferencji żywieniowych w swoim profilu.
- 75% użytkowników generuje jeden lub więcej przepisów w tygodniu.