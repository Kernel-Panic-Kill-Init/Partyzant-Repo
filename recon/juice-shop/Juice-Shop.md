# 🍹 OWASP Juice Shop – Partyzant Notes (by 7-2)
> Moje notatki, rozwiązania i payloady do ćwiczeń w Juice Shop. Styl: luźny, techniczny, bez ściemy.

---

## ✅ Wyzwania ukończone

### 1. `Error: Blocked illegal activity by ::ffff:10.1.10.14`
- **Typ:** Error Handling / Security Violation
- **Opis:** Przy wejściu na `/profile` dostałem 500: `Blocked illegal activity`. Serwer wykrył podejrzaną aktywność i mnie zbanował z imienia i nazwiska (czyli IP xD).
- **Co zrobiłem:** Prawdopodobnie odpaliło się samo — mogła to być błędna akcja, payload lub manipulacja parametrem.
- **Screenshot:** ![screenshot](link lub lokalny path)
- **Ref:** `routes/userProfile.js:72:18`

---

## 🧪 Wyzwania w toku / do zrobienia

| Wyzwanie                      | Kategoria       | Status  | Notatki                            |
|------------------------------|-----------------|---------|------------------------------------|
| Admin Section Access         | Broken Access   | ❌      | Próbuję dostać się do `/admin`    |
| Score Board Spoofing         | Injection       | ⏳      | Szukam payloadów do modyfikacji   |
| Forged Feedback              | API Tampering   | ⏳      | Testuję manualnie w DevTools      |

---

## 🧨 Przydatne Payloady

```js
<script>alert('XSS')</script>
"><img src=x onerror=alert(1)>
'||1==1--      -- SQLi
{"role":"admin"}  -- JSON tampering
../../etc/passwd -- LFI

---

🛠️ Notatki techniczne
🔧 nslookup i dir doinstalowałem ręcznie:

bash
apt install dnsutils
apt install coreutils


---
🔍 DevTools:

Zakładka „Network” – śledzenie requestów

Zakładka „Application” – localStorage i JWT
---
✍️ Mój styl nauki
Nie klikam bez zrozumienia – każda akcja to lekcja

Payloady notuję i taguję, żeby je potem zrecyklować

Staram się zrozumieć logikę aplikacji, nie tylko "co działa"

---

🧠 Dziennik progresu
Data	Czas	Progres
2025-07-30	~5h	33/172 tasków wpadło (część pewnie sama)
+ 500ka na /profile

---


🧠 Cytat dnia
"Czasem jak coś jebnie, to właśnie o to chodziło." – gen. Italia

---
