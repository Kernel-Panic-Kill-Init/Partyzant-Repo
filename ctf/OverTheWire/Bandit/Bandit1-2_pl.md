🎯 Cel misji:

Zdobyć hasło do Bandit2, przebrnąwszy przez trolla plikowego o imieniu -, który wygląda niewinnie, ale ma więcej jadu niż sąsiadka spod 6-tki.


---

🧙 Warunki wejściowe:

Host: bandit.labs.overthewire.org

Port: 2220

Login: bandit1

Password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

Stan psychiczny: niewyspany, ale zdeterminowany



---

🧰 Zaklęcia i ciosy podstawowe:

ls -al        # pokaż wszystko, nawet rzeczy z podziemia
pwd           # powiedz mi gdzie jestem, terminalowy Gandalfie
cat <plik>    # przeczytaj plik, chyba że się zesrasz jak w tym levelu


---

🔪 Walkthrough — albo jak rzucić terminalem o ścianę, a potem się z tego śmiać:

1. Wbijasz się na serwer jak ninja przez backdoora:



ssh bandit1@bandit.labs.overthewire.org -p 2220

2. Rozglądasz się jak Scooby-Doo w opuszczonym domu:



ls -al

— i co widzisz? Plik o nazwie -... co to niby jest? Tytuł jakiegoś niemieckiego art-house filmu?

3. Próbujesz klasycznie, jak uczą w szkołach:



cat -

— i jeb, terminal zamiera. Wchodzisz w matrixa. cat czeka na dane z klawiatury. Czaisz? Ten skurwiel - to nie plik, tylko krwiożerczy stdin-owy kamuflażysta.

4. Ale jesteś chytrzejszy niż wygląda Twój RAM i atakujesz bokiem:



cat ./-

💥💥💥 DING DING DING — HEADSHOT.

5. Z pliku wycieka hasło. Kopiujesz, zapisujesz, całujesz w czoło i lecisz dalej.




---

🔑 Hasło do Bandit2:

aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG


---

🧠 Notatki spod znaku sierpa, młota i chmod 777:

1. Pliki zaczynające się od - to bashowe gremliny. Psują cat, rm, mv, bo terminal myśli, że to argumenty a nie nazwy. Troll nad trollami. Prawie jak “Wracaj do pracy, leniu.”


2. ./- to sposób na powiedzenie: Nie, kochany terminalu, to nie flagi. To rzeczywistość.


3. Alternatywa, jak chcesz się poczuć jak Dumbledore Linuksa:



cat -- -

To -- mówi: koniec opcji, od teraz wszystko to pliki. Nawet jak mają imię z kreskówki.


---

💥 Podsumowanie:

👨‍💻 Czas wykonania: 20 sekund
🧠 Czas ogarnięcia co się odpierdala: 3 minuty
🧻 Czas na regenerację po emocjonalnej traumie: bez komentarza
📓 Wniosek: Bash to zło. Ale Twoje zło.


---

✍️ Zapisano podczas robienia pierogów na kolację po pracy o 21:37 śpiewając przy tym "Barkę"

---
