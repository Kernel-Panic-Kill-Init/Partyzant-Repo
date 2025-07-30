✍️ Mój styl nauki
Nie klikam bez zrozumienia – każda akcja to lekcja

Payloady notuję i taguję, żeby je potem zrecyklować

Staram się zrozumieć logikę aplikacji, nie tylko "co działa"

🧠 Dziennik progresu
Data	Czas	Progres
2025-07-30	~5h	33/172 tasków wpadło (część pewnie sama)
+ 500ka na /profile

🧠 Cytat dnia
"Czasem jak coś jebnie, to właśnie o to chodziło." – gen. Italia

juice-shop/
├── gobuster_dir.txt
├── nikto_scan.txt
├── nmap_full_scan.txt
├── subfinder_output.txt
└── SecLists/
---




---

## 📓 Key Findings & Notes

| Tool      | Found(Znalezisko) / Comment(Komentarz)                             |
|-----------|----------------------------------------------------|
| `nmap`    | Port 3000 open – Node.js service (Express?)        |
| `gobuster`| 🔥 `/login` `/rest/products` `/score-board` found  |
| `nikto`   | XSS headers missing, HTTP methods enabled          |
| `subfinder`| No subdomains (as expected – local)               |
| ⚠️ Error  | Port `36789` → `400 Bad Request` (need to check what it is)  |

🧠 **Wnioski:**
- Interfejs RESTowy aktywny pod `/rest/`
- Możliwe exploity na `score-board` lub `feedback`
- Część wyzwań aktywuje się pasywnie (np. błąd 500 z `/profile`)

---

## 🧪 Next Steps

- [ ] Zmapować `/rest` API – sprawdzić metody, parametry, dane
- [ ] Testować injection w formularzach (`login`, `feedback`)
- [ ] Analiza JWT w `Application > LocalStorage`
- [ ] Sprawdzić logikę `/score-board` (czy da się oszukać wynik)

---

## 🖼️ Screenshots
<--!
Trzymaj screeny w `screenshots/` i wrzucaj linki np. tak:

- ![500 error](./screenshots/error_500_profile.png)
- ![Gobuster result](./screenshots/gobuster_login.png)
-->
---

## 🔗 Ref & Tools

- 🛠️ [PayloadAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings)
- 🍹 [Juice Shop GitHub](https://github.com/juice-shop/juice-shop)
- 🧠 [Juice Shop Wiki / Hints](https://pwning.owasp-juice.shop/)

---

> 🧠 *“Czasem recon mówi więcej niż exploity. Ale dopiero jedno z drugim daje punkty.”* – Tryb Partyzancki


