# 🔐 Uprawnienia plików Linux i podstawy kluczy SSH

## 🎯 Składnia `chmod`
```bash
chmod [opcje] uprawnienia plik


---

📦 Tryb ósemkowy – Wartości i znaczenie

Wartość	Symbolicznie	Znaczenie

7	rwx	odczyt, zapis, wykonanie
6	rw-	odczyt, zapis
5	r-x	odczyt, wykonanie
4	r--	tylko odczyt
0	---	brak dostępu



---

🧑‍💻 Struktura trzech cyfr

Każda cyfra oznacza dostęp dla:

1. Właściciela


2. Grupy


3. Innych



Przykład:

chmod 754 plik
#    ^ właściciel: rwx → pełny dostęp
#     ^ grupa: r-x → odczyt i wykonanie
#      ^ inni: r-- → tylko odczyt


---

📌 Przykładowe użycia chmod

Komenda	Uprawnienia	Znaczenie	Przypadek użycia

chmod +x	dodaj x	Nadaje prawa do wykonania	Dla skryptów .sh lub binarek
chmod 600	rw-------	Tylko właściciel ma odczyt i zapis	Prywatny klucz SSH (id_ed25519)
chmod 700	rwx------	Pełny dostęp tylko dla właściciela	Folder .ssh/ lub prywatne pliki
chmod 644	rw-r--r--	Właściciel: odczyt/zapis, reszta: odczyt	Pliki konfiguracyjne, dokumenty
chmod 755	rwxr-xr-x	Właściciel: pełny, reszta: odczyt/wykonanie	Udostępniane skrypty lub programy



---

✅ Przykłady chmod

chmod 700 ~/.ssh/              # Folder z kluczami SSH
chmod 600 ~/.ssh/id_ed25519    # Prywatny klucz SSH
chmod +x backup.sh             # Umożliw wykonanie skryptu
chmod 755 my_script.sh         # Skrypt do udostępnienia


---

🔑 Dlaczego używać id_ed25519 do SSH?

id_ed25519 to klucz oparty o algorytm Ed25519 — nowoczesny, bezpieczny i szybki.

Jest to zalecany typ klucza zamiast RSA.

Użyj chmod 600 na prywatnym kluczu (id_ed25519), aby ograniczyć dostęp.

Klucz publiczny (id_ed25519.pub) można bezpiecznie udostępniać serwerom lub GitHubowi.



---

🚀 Jak dodać swój klucz SSH do GitHuba

1. Wygeneruj klucz:



ssh-keygen -t ed25519 -C "twój_email@example.com"

2. Wyświetl zawartość klucza publicznego:



cat ~/.ssh/id_ed25519.pub

3. W GitHubie:
Przejdź do Settings → SSH and GPG keys → New SSH key, wklej tam klucz.


4. Przetestuj połączenie:



ssh -T git@github.com

Jeśli działa, zobaczysz:

Hi username! You've successfully authenticated, but GitHub does not provide shell access.


---

📋 Tabela podsumowująca uprawnienia

Komenda	Uprawnienia	Opis

chmod 600	rw-------	Klucz prywatny — tylko właściciel
chmod 644	rw-r--r--	Klucz publiczny — odczyt dla wszystkich
chmod 700	rwx------	Prywatny katalog lub skrypt



---

💡 Wskazówki

Zawsze używaj chmod 600 dla prywatnych kluczy.

chmod +x sprawia, że skrypty są uruchamialne.

chmod 700 zabezpiecza prywatne foldery.

Sprawdź uprawnienia komendą:


ls -l


---

🔗 Przydatne linki

Dokumentacja SSH na GitHubie

Ed25519 – Wikipedia


---
