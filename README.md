# CramPlan 📚⚡

**An emergency exam-prep generator built for last-minute study sessions.**

CramPlan takes a student's **subject**, **hours left** before an exam, and current **brain battery** (_Fresh_, _Tired_, or _Full Panic_) to generate a custom survival schedule, a recommended study technique, and an honest reality check.

> _Built as a 1-hour end-to-end hackathon practice sprint._

---

## run

```sh
uv run flask --app cramplan run --debug
```

## ✨ Features

- **Adaptive Study Schedules:** Automatically breaks down your remaining hours into realistic work blocks and mandatory breaks.
- **Energy-Based Study Techniques:**
  - 🔋 **Fresh:** 50-minute deep-work blocks using the _Feynman Technique_.
  - 🪫 **Tired:** 25-minute _Pomodoro_ bursts focused on active recall and flashcards.
  - 🚨 **Full Panic (or $\le 2$ hours left):** _Triage Mode_—skips note-taking and jumps straight into past exam questions.
- **Honest Reality Checks:** Keeps students focused on high-impact studying instead of passive re-reading.

---

## 🛠️ Tech Stack

- **Frontend:** HTML5, CSS3, Vanilla JavaScript (`fetch` API)
- **Backend:** Python (Flask) / Node.js (Express) _(Update this with whichever your team chooses!)_
- **Database:** None (Rule-based in-memory logic for rapid prototyping)

---

## 🔌 API Contract

The frontend communicates with the backend via a single REST endpoint.

### Request

```http
GET /plan?subject=Biology&hours=3&energy=tired
```

| Parameter | Type     | Description                                         |
| :-------- | :------- | :-------------------------------------------------- |
| `subject` | `string` | Name of the class or exam topic                     |
| `hours`   | `number` | Hours remaining until the exam                      |
| `energy`  | `string` | Current energy state (`fresh`, `tired`, or `panic`) |

### Response (`200 OK`)

```json
{
  "method": "The Blurting Method",
  "schedule": [
    "0:00 - 0:40 | Write down everything you know about Biology from memory",
    "0:40 - 0:50 | Mandatory break (no phone scrolling)",
    "0:50 - 1:30 | Check notes and drill only what you missed"
  ],
  "reality_check": "With 3 hours left and low energy, stop re-reading slides—only do active recall."
}
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/cramplan.git
cd cramplan
```

### 2. Run the Backend

_(Example using Python Flask — adjust if using Node.js)_

```bash
cd backend
pip install flask flask-cors
python app.py
```

The server will start on `http://localhost:5000`.

### 3. Run the Frontend

Open `frontend/index.html` directly in your browser, or serve it using VS Code's **Live Server** extension.

---

## 🔮 What We'd Add With 24 Hours

- **Live Study Timer:** An interactive countdown clock synced directly to each block in the generated schedule.
- **Syllabus PDF Upload:** Parse a course syllabus or study guide to automatically prioritize high-weight exam topics.
- **Shareable Study Links:** Allow study groups to generate and share a synchronized cram schedule via URL.

---

## 👥 Team

- **[Teammate 1]** – Frontend & UI
- **[Teammate 2]** – Backend & API Logic
- **[Teammate 3]** – Testing & Pitch
