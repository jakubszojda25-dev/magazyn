# Magazyn SAFETY – wgranie na Firebase

Adres po wgraniu: **https://safetymagazynszojda.web.app**

## 1. Konta użytkowników (robisz raz, w przeglądarce)

1. Wejdź na https://console.firebase.google.com → projekt **Magazyn**.
2. **Authentication → Users → Add user**.
3. Wpisz e-mail pracownika i **hasło tymczasowe**.
4. Wyślij pracownikowi e-mailem adres strony i to hasło.

Przy pierwszym logowaniu aplikacja wymusi ustawienie własnego hasła (min. 8 znaków).
Dopiero potem pracownik zobaczy magazyn.

- Samodzielna rejestracja jest wyłączona, więc nikt obcy nie założy sobie konta.
- Zapomniane hasło: na ekranie logowania jest „Nie pamiętam hasła” (link przychodzi na e-mail).
- Chcesz, żeby ktoś znów musiał zmienić hasło (np. po resecie w konsoli)?
  Firestore → Data → kolekcja `userState` → usuń dokument tej osoby.

## 2. Wgranie strony (robisz raz, potem przy każdej zmianie)

Potrzebny jest Node.js (https://nodejs.org, wersja LTS).

1. Rozpakuj ten folder, np. do `Dokumenty\magazyn-firebase`.
2. Otwórz terminal (Windows: PowerShell) w tym folderze.
3. Zaloguj się do Firebase (otworzy się przeglądarka):

   ```
   npx firebase-tools login
   ```

4. Wgraj stronę i reguły bazy:

   ```
   npx firebase-tools deploy
   ```

Po chwili strona działa pod adresem **https://safetymagazynszojda.web.app**, na telefonie i na komputerze.

## Co jest w folderze

- `public/index.html` – cała aplikacja.
- `firestore.rules` – reguły bazy: dostęp tylko dla zalogowanych.
- `firebase.json`, `.firebaserc` – ustawienia projektu `magazyn-f870c` i hostingu `safetymagazynszojda`.

## Telefon jak aplikacja

Otwórz adres w telefonie → menu przeglądarki → „Dodaj do ekranu głównego”.
