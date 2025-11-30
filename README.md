# 🏏 IPL Auction Game

_A fun side-project combining cricket passion + coding skills_

---

## 👋 Introduction

I’m a cricket enthusiast who loves hosting IPL-style auction games with my friends.
To make the experience more exciting (and less manual), I built this **interactive IPL Auction Game** using **FastAPI**, **HTML/CSS/JS**, and an **Excel backend** to fully simulate an auction environment.

This app lets you:

- Conduct a complete IPL-style auction
- Add Sold and Unsold players
- Move players between teams
- Track purse remaining & slot counts
- Visually switch between team tabs
- Maintain “Playing XI” & “Impact Sub” sections
- Auto-sort sheets and refresh instantly
- Use team-wise dynamic background images

This project merges my **love for cricket** with my **coding skills**, turning friendly auctions into a polished and fun experience.

---

# 📂 Project Structure

```
project/
│
├── auction_app.py           # Main FastAPI application
├── /templates               # HTML templates
│     └── auction_summary_page.html
│
├── /static
│     └── images/            # Team and arena background images
│
├── /data
│     ├── Auction_Sheet.xlsx  # Excel file containing all team sheets
│     └── teams_data.json     # Initial team purse/slots metadata
│
└── requirements.txt
```

---

# 🔧 Installation & Environment Setup

Follow these steps to set up the app locally from GitHub.

---

## 1️⃣ Clone the Repository

```bash
git clone <your-repository-url>
cd <repo-folder-name>
```

---

## 2️⃣ Create a Virtual Environment

### Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

### macOS / Linux:

```bash
python3 -m venv venv
source venv/bin/activate
```

---

## 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 4️⃣ Restore Game Data (IMPORTANT)

Inside the `/data` folder of the repo, you will find:

- `Auction_Sheet.xlsx`
- `teams_data.json`

These files contain the **entire state of the auction**.

### You MUST download and replace these files in your local project when you:

✔️ start a fresh auction
✔️ reset all team data
✔️ want to replay with friends

Place them here:

```
/data/Auction_Sheet.xlsx
/data/teams_data.json
```

These files are the **heart of the system**.

---

# ▶️ Running the Application

Since we've renamed the app to `auction_app.py`, use:

### Development mode (auto-reload):

```bash
uvicorn auction_app:app --reload
```

### Production-style:

```bash
uvicorn auction_app:app --host 0.0.0.0 --port 8000
```

Then open:

```
http://127.0.0.1:8000/auction-summary-page
```

---

# 🧠 What This Application Does

## ✔️ 1. Real-Time IPL Auction Simulation

Add players as **Sold** or **Unsold**. Data is instantly written to Excel sheets and auto-sorted.

## ✔️ 2. Dynamic Backgrounds for Every Team

Each team tab displays its own theme image using:

- `cover` mode for team tabs
- `contain` mode for the Arena page

With blur effects for a clean UI.

## ✔️ 3. Move Players Between Sheets

The **Remove Player** feature:

- pops up a modal
- asks for base price
- removes the player from the team sheet
- re-adds them to **Unsold**
- auto-refreshes both sheets

## ✔️ 4. Tables With Stylish UI

Every team tab displays:

- The main squad table
- A right-side layout (2 sections)

  - **Playing XI (12 rows)**
  - **Impact Sub (2 rows)**

(Business logic for editing these rows will be added later.)

## ✔️ 5. Excel-Driven Backend

`Auction_Sheet.xlsx` contains:

- 10 Team Sheets
- Unsold Sheet
- Auto-managed sorting
- Persistent auction progress

Everything is centralized and easy to reset.

---

# 📘 Tech Stack

- **FastAPI** — Backend API
- **Uvicorn** — Application server
- **Jinja2 Templates** — HTML rendering
- **Vanilla JavaScript** — Dynamic updates
- **Excel (openpyxl)** — Data storage
- **Custom CSS (Glassmorphism)** — UI styling

---

# 🏁 Resetting the Auction

Whenever you want to play with friends again:

1. Go to `/data` folder
2. Replace **Auction_Sheet.xlsx** with the fresh one from Git
3. Replace **teams_data.json**
4. Restart the server

Your auction restarts from a clean slate.

---

# 🙌 Final Note

This project is built with passion — for cricket, for coding, and for the fun of hosting IPL auctions with friends.
Feel free to fork, modify, extend, or break it in your own way.

If you want:

- Dockerfile
- Prettier UI
- Auto-save snapshots
- Export final squads
- Live leaderboard

Just tell me — I’ll add them ❤️🏏
