# ID3a2024 — Plan Zajęć UBB

Aplikacja webowa wyświetlająca plan zajęć Uniwersytetu Bielsko-Bialskiego, aktualizowana automatycznie przez background workera. Użytkownik może przeglądać plany zajęć w czytelny, responsywny sposób oraz dodawać je do ulubionych.

![Diagram aplikacji](images/diagram.png)

---

## Stack technologiczny

| Warstwa | Technologia |
|---|---|
| Backend | Go 1.23 + Fiber v2 |
| Frontend | SvelteKit + TypeScript + Tailwind CSS |
| Build tool | Vite + Bun |

---

## Wymagania

Przed uruchomieniem upewnij się, że masz zainstalowane:

- [Go](https://go.dev/dl/) >= 1.23
- [Node.js](https://nodejs.org/) >= 18 lub [Bun](https://bun.sh/)
- `git`

---

## Uruchomienie projektu

### 1. Klonowanie repozytorium

```bash
git clone https://github.com/<twój-username>/ID3a2024.git
cd ID3a2024
```

### 2. Uruchomienie backendu (Go + Fiber)

```bash
cd backend/src/id3a2024
go mod download        # pobierz zależności
go run main.go         # uruchom serwer
```

Backend domyślnie nasłuchuje na porcie **:3000**.

### 3. Uruchomienie frontendu (SvelteKit)

W osobnym terminalu:

```bash
cd frontend
npm install            # lub: bun install
npm run dev            # lub: bun run dev
```

Frontend będzie dostępny pod adresem **http://localhost:5173**.

---

## Budowanie produkcyjne

### Backend

```bash
cd backend/src/id3a2024
go build -o id3a2024 .
./id3a2024
```

### Frontend

```bash
cd frontend
npm run build
npm run preview        # podgląd zbudowanej wersji
```

---

## Testy

### Backend

```bash
cd backend/src/id3a2024
go test -v ./...
```

### Frontend

```bash
cd frontend
npm run test
```

---

## Struktura projektu

```
ID3a2024/
├── backend/
│   └── src/id3a2024/
│       ├── main.go          # punkt wejścia serwera
│       ├── routes/          # definicje tras API
│       └── fetch/           # logika pobierania planu UBB
├── frontend/
│   ├── src/
│   │   ├── routes/          # strony SvelteKit
│   │   └── lib/             # komponenty i kontrolery
│   └── static/              # zasoby statyczne
├── images/
│   └── diagram.png          # diagram architektury
└── .github/workflows/       # CI/CD (GitHub Actions)
```

---

## Wymagania funkcjonalne

- Przeglądanie planów zajęć UBB
- Automatyczna aktualizacja planu przez background workera
- Przechowywanie danych w formacie JSON
- Dodawanie planów do ulubionych
- Nowoczesny i responsywny interfejs

---

## CI/CD

Projekt posiada skonfigurowany GitHub Actions workflow (`.github/workflows/go.yml`), który automatycznie buduje i testuje backend przy każdym pushu lub pull requeście do gałęzi `main`.

---

## Licencja

Projekt edukacyjny — Inżynieria Oprogramowania 2024.
