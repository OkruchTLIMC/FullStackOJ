```mermaid
sequenceDiagram
    participant Browser
    participant Server

    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate Server
    Server-->>Browser: HTML document
    deactivate Server

    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate Server
    Server-->>Browser: stylesheet CSS
    deactivate Server

    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate Server
    Server-->>Browser: script JS
    deactivate Server

    Note right of Browser: Przeglądarka uruchamia skrypt JavaScript, który pobiera dane JSON

    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate Server
    Server-->>Browser: JSON
    deactivate Server

    Note right of Browser: JavaScript generuje strukturę DOM i wyświetla notatki na ekranie

    Note right of Browser: Użytkownik tworzy nową notatkę i klika Save

    Browser->>Server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate Server

    Note right of Browser: Przeglądarka wysyła dane nowej notatki
    Note right of Server: Serwer zapisuje otrzymaną notatkę w tablicy

    Server-->>Browser: HTTP 201 Created
    deactivate Server

```
