Weiterleitung von https://o.lws20.de/#<Pfad> auf obsidian://open für den Vault „Second Brain“. Der Pfad steht im Fragment und erreicht keinen Server.

```mermaid
sequenceDiagram
    autonumber
    participant T as 📱 Telegram
    participant B as 🌐 Browser
    participant G as GitHub Pages<br/>o.lws20.de
    participant O as 🗂️ Obsidian
    Note over T: Telegram macht nur http(s)-Links klickbar
    T->>B: Tipp auf https://o.lws20.de/#30_Projekte/…
    B->>G: GET / (ohne #-Teil)
    G-->>B: index.html mit JavaScript
    B->>O: obsidian://open?vault=Second%20Brain&file=30_Projekte/…
    Note over G: Der Pfad hinter # verlässt das Gerät nie
```

Erzeugt werden die Links von `brain/links.py` im Repo [second-brain](https://github.com/adubdubdub/second-brain).
