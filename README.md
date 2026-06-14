# 📚 CampusLedger — Student, Attendance & Marks Management System

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![No Dependencies](https://img.shields.io/badge/Dependencies-Zero-34408A?style=for-the-badge)
![Deploy Ready](https://img.shields.io/badge/Deploy-Ready-2F8F5B?style=for-the-badge)

> A fully client-side academic administration tool — manage a student directory, mark daily attendance with a "stamp register," and enter subject-wise exam marks with automatic percentage & grade computation. Zero backend. Zero dependencies. One HTML file.

---

## 🖥️ Live Preview

```
Open index.html in any modern browser — works instantly, no setup required.
```

---

## ✨ Features

### 🏠 Dashboard
- **Real-time KPIs** — Total Students, Present/Late/Absent Today, with live percentages
- **Section-wise Attendance Bars** — average attendance % per class (CSE-4A / 4B / 4C)
- **Recent Activity Feed** — latest attendance entries with status icons
- **At-Risk Students Table** — auto-flags students with attendance below 75%
- **Top Performers Leaderboard** — top 5 students ranked by marks percentage with grade badges

### 👨‍🎓 Student Directory
- Full **CRUD** — add, edit, delete student records via modal form
- Fields: name, roll number, class/section, gender, email, phone, date of joining
- **Live search** by name or roll number, plus class filter
- Inline attendance percentage bar per student

### 📅 Attendance Management
- **Stamp-based register** — ✓ Present, ⏱ Late, ✕ Absent (click again to clear)
- **"Mark All Present"** shortcut for the whole section
- Live running summary: present / late / absent / unmarked counts
- Select any class + date to view or edit a past register
- All data persisted to `localStorage` — survives page refresh

### 📝 Marks Management
- **6 subject-wise marks entry** for 4th Semester CSE (100 marks each, 600 total):
  - Engineering Mathematics-III (MATH301)
  - Data Structures & Algorithms (CS301)
  - Digital Electronics (CS302)
  - Object Oriented Programming (CS303)
  - Operating Systems (CS304)
  - Database Management Systems (CS305)
- **Live calculation** — Total, Percentage, and Grade update instantly as marks are typed
- Inputs auto-clamp to 0–100 per subject
- **Live class summary** — section average % and grade-wise headcount (A/B/C/D/F)
- Built-in **grading scale reference** panel

### 📊 Reports
- **Attendance Register** — per-student present/late/absent counts and overall %, filterable by section
- **Academic Performance** — per-student total marks, percentage, and grade, filterable by section
- **Student Calendar Heatmap** — monthly view colour-coded by daily attendance status

### 💾 Data Persistence
- All data saved to **localStorage** — survives page refresh with no backend
- Auto-seeds **21 students** (3 sections × 7) with **21 days of attendance** and **full marks for 6 subjects** on first visit

---

## 🎓 Grading Scale (Percentage-Based)

| Percentage Range | Grade | Remark |
|-------------------|:-----:|--------|
| 85% – 100%       | **A** | Outstanding |
| 70% – 84.99%     | **B** | Very Good |
| 55% – 69.99%     | **C** | Good |
| 40% – 54.99%     | **D** | Pass |
| Below 40%        | **F** | Fail / Needs Improvement |

---

## 📁 Project Structure

```
campusledger/
└── index.html        ← Entire app (HTML + CSS + JS in one file)
```

That's it. No `node_modules`, no `package.json`, no build step.

---

## 🚀 Getting Started

### Run Locally

```bash
# Clone the repository
git clone https://github.com/your-username/campusledger.git

# Navigate into the folder
cd campusledger

# Open in browser (any of the below)
open index.html                        # macOS
start index.html                       # Windows
xdg-open index.html                    # Linux
```

Or simply **double-click** `index.html` in your file explorer.

### Optional — serve with a local server

```bash
# Python (built-in)
python -m http.server 8000

# Node.js (npx, no install needed)
npx serve .
```

Then visit `http://localhost:8000`.

---

## ☁️ Deployment

Since CampusLedger is a static single-file app, it deploys in seconds on any static hosting platform.

### Netlify (Drag & Drop)
1. Go to [netlify.com](https://netlify.com) → **Add new site**
2. Drag and drop the `index.html` file (or the project folder)
3. Done — live URL generated instantly ✅

### GitHub Pages
1. Push this repository to GitHub
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Your app is live at `https://your-username.github.io/campusledger/`

### Vercel
```bash
npx vercel
```
Vercel auto-detects it as a static site — zero configuration needed.

### Cloudflare Pages
1. Connect your GitHub repository in the Cloudflare dashboard
2. Leave build settings blank (static site)
3. Deploy ✅

---

## 🧮 How Calculations Work

| Metric | Formula |
|--------|---------|
| Attendance % | `((Days Present + 0.5 × Days Late) ÷ Total Recorded Days) × 100` |
| At-Risk Flag | Attendance % < 75% |
| Section Average | Mean Attendance % across all students in a class |
| Marks Total | Sum of marks obtained across all subjects entered |
| Marks Percentage | `(Total Marks ÷ (Subjects Entered × 100)) × 100` |
| Letter Grade | Derived from Percentage (see Grading Scale above) |
| Class Marks Average | Mean Percentage across all students in a section |

---

## 🎨 Tech Stack

| Technology | Usage |
|-----------|-------|
| **HTML5** | Semantic structure, native `date`, `email`, `tel`, `number` inputs |
| **CSS3** | Custom properties, Grid & Flexbox, keyframe animations, calendar heatmap, custom scrollable tables |
| **JavaScript ES6+** | Single-page navigation, DOM manipulation, Array.reduce/filter/sort, Date API, localStorage, template literals |
| **Web Storage API** | `localStorage` for students, attendance, and marks persistence |
| **Google Fonts** | Lora (headings/ledger feel) + Inter (UI) + IBM Plex Mono (roll numbers, dates, marks) |

---

## 📸 App Sections

```
┌──────────────────────────────────────────────────────────────────┐
│ CampusLedger          Dashboard · Students · Attendance · Marks   │
│                        · Reports                                  │
├──────────────────────────────────────────────────────────────────┤
│  Total Students   Present Today   Late Today   Absent Today       │
│       21               16             3             2             │
├──────────────────────────────┬─────────────────────────────────  │
│  Section-wise Attendance      │  Recent Activity                  │
│  CSE-4A ████████░░ 82%        │  ✓ Aarav Sharma marked present    │
│  CSE-4B ███████░░░ 76%        │  ✕ Diya Verma marked absent       │
│  CSE-4C ████████░░ 80%        │  ⏱ Kabir Singh marked late        │
├──────────────────────────────┴─────────────────────────────────  │
│  At-Risk Students (< 75%)        │  Top Performers                │
│  Diya Verma   CSE-4B   71%       │  #1 Aadhya Mehta  B  73.17%    │
├───────────────────────────────────────────────────────────────── │
│  📝 MARKS PAGE — CSE-4A                                            │
│  Student      MATH301 CS301 CS302 CS303 CS304 CS305  Total  %  Grade│
│  Aarav Sharma   78    85    64    91    73    80     471  78.5  B  │
└──────────────────────────────────────────────────────────────────┘
```

---

## 🧪 Demo Data

On first launch, the app auto-loads:

- **21 students** across 3 sections (CSE-4A, CSE-4B, CSE-4C), 7 per section
- **21 days** of attendance history (weekdays only) with a realistic ~78% present / 12% late / 10% absent distribution
- **Marks for all 6 subjects** per student (35–98 range)

To start fresh: delete a student via the directory, or clear browser localStorage for this page.

---

## 🗺️ Future Roadmap

- [ ] Multi-user roles (Admin / Faculty / Student) with role-based access
- [ ] Backend & database (MySQL / PostgreSQL) for multi-device sync
- [ ] Subject-wise attendance (per period, not just daily)
- [ ] Multiple exams per semester (Internal-1, Internal-2, Semester End) with weighted grades
- [ ] Email/SMS alerts for low attendance or low grades
- [ ] CSV / PDF export of registers and mark sheets
- [ ] Bulk import via CSV
- [ ] GPA/CGPA computation with credit weighting
- [ ] Biometric/QR-based attendance capture

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👨‍💻 Author

Built as a **B.Tech CSE 4th Semester Web Development Project**.

> *"From paper registers to pixels — attendance and academics, simplified."*

---

<div align="center">
  Made with HTML, CSS & JavaScript &nbsp;·&nbsp; No frameworks. No excuses.
</div>
# CampusLedger
