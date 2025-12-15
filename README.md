# SnippetVault

**SnippetVault** to aplikacja typu "Baza Wiedzy" dla programistów. Pozwala przechowywać, organizować i szybko wyszukiwać fragmenty kodu (snippety), konfiguracje i komendy, które często wypadają z pamięci.

Projekt stworzony w architekturze mikroserwisowej przy użyciu **Docker Compose**.

## 🚀 Technologie (Tech Stack)

* **Frontend:** React.js (Create React App) + Syntax Highlighting
* **Backend:** Node.js + Express
* **Baza danych:** MongoDB
* **Konteneryzacja:** Docker + Docker Compose

## 🌟 Główne Funkcjonalności

1.  **Dodawanie Snippetów:** Edytor z wyborem języka (JS, Python, CSS, SQL, etc.) i kolorowaniem składni.
2.  **Tagowanie:** System tagów (np. `#docker`, `#react`) umożliwiający grupowanie wiedzy.
3.  **Smart Search:** Błyskawiczne filtrowanie snippetów po tytule lub tagach.
4.  **Kopiowanie (Clipboard):** Kopiowanie kodu do schowka jednym kliknięciem.
5.  **Ulubione ⭐:** Możliwość przypinania najważniejszych notatek na górę listy.

## 📂 Struktura Projektu

Projekt jest zorganizowany jako monorepo obsługiwane przez Dockera:

```text
SnippetVault/
├── api/                # Backend (Node.js + Express)
├── client/             # Frontend (React)
├── mongo-data/         # Trwałe dane bazy (Docker Volume)
└── docker-compose.yml  # Orkiestracja kontenerów
