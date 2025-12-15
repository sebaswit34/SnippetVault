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

##Struktura plików:
SnippetVault/
├── docker-compose.yml          # PLIK GŁÓWNY: Definiuje usługi (api, client, mongo)
├── .gitignore                  # Ważne: ignoruj node_modules i folder z danymi bazy
├── README.md
│
├── api/                        # === BACKEND (Node.js/Express) ===
│   ├── Dockerfile              # Instrukcja budowania obrazu API
│   ├── .dockerignore           # Czego nie kopiować do kontenera (np. node_modules)
│   ├── package.json
│   ├── nodemon.json            # (Opcjonalnie) Config do restartowania serwera przy zmianach
│   └── src/
│       ├── index.js            # Punkt startowy serwera, połączenie z DB
│       ├── models/
│       │   └── Snippet.js      # Schemat Mongoose (struktura danych snippetu)
│       └── routes/
│           └── snippets.js     # Endpointy: GET /, POST /, DELETE /:id
│
├── client/                     # === FRONTEND (React) ===
│   ├── Dockerfile              # Instrukcja budowania obrazu Reacta
│   ├── .dockerignore
│   ├── package.json
│   ├── public/
│   │   └── index.html
│   └── src/
│       ├── index.js
│       ├── App.js              # Główny layout aplikacji
│       ├── App.css             # Style globalne
│       ├── api.js              # Instancja axios/fetch skonfigurowana pod API
│       └── components/         # Komponenty UI
│           ├── SnippetForm.jsx # Formularz dodawania (pola: kod, język, tagi)
│           ├── SnippetList.jsx # Kontener wyświetlający listę
│           ├── SnippetCard.jsx # Pojedynczy kafelek (tu będzie kolorowanie składni)
│           └── SearchBar.jsx   # Input do filtrowania
│
└── mongo-data/                 # === BAZA DANYCH (Volume) ===
    # Ten folder utworzy się sam po uruchomieniu Dockera.
    # Tutaj MongoDB fizycznie zapisuje pliki na Twoim dysku.
    # Pamiętaj, aby dodać go do .gitignore!
