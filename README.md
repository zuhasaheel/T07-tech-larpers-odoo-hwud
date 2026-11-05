# 🎓 Student Gig Marketplace — BuildOdoo 2026

> 🥈 **2nd Place — BuildOdoo 2026**, a 48-hour hackathon hosted by HW Tech Club × Odoo
> **Track 3: Open Innovation** · Team **Tech Larpers**

A student freelance marketplace built as a custom **Odoo 19** module. Students can post small gigs (tutoring, design work, errands and more) and apply to gigs posted by others, with AI helping to organize the marketplace and match the right people to the right work.

---

## 💡 The Problem

University students often need quick help with tasks like tutoring, design or small errands, and many other students would like to earn some money doing them. Right now, this happens in scattered group chats and word of mouth: gigs get lost, pricing is guesswork, and it's hard to tell which applicant is the best fit.

## ✨ Our Solution

A single platform inside Odoo where students can:

- **Post gigs** with a description, budget and deadline
- **Browse and apply** to gigs posted by other students
- **Manage applications** and track each gig from start to finish

AI improves the experience at every step:

| AI Feature | What it does |
|---|---|
| 🏷️ **Auto-categorization** | Reads the gig description and fills in the right category automatically |
| 💰 **Budget suggestion** | Suggests a fair budget based on what the gig involves |
| 🎯 **Match scoring** | Scores how well each applicant fits a gig, so posters can spot strong candidates quickly |

## 🚀 Features

- **Gig management:** create gigs with a title, description, category, budget, deadline and status
- **Kanban board:** gigs grouped by status, plus a list view with search and filters
- **Status workflow:** Open → In Progress → Completed (or Cancelled), shown in a status bar on each gig
- **Applications:** students apply with a message, and every application has a status (Pending / Accepted / Rejected)
- **Access control:**
  - Only a gig's poster can accept or reject applications to that gig
  - Applicants can't approve their own applications
- **Automation:** accepting an application automatically moves the gig to *In Progress*

## 🔄 How It Works

1. A student posts a gig and describes what they need.
2. AI fills in the category and suggests a fair budget.
3. Other students apply with a short message.
4. AI scores each applicant's match to the gig.
5. The poster reviews the applicants and accepts the best fit.
6. The gig moves to *In Progress* and later to *Completed*.

## 🗂️ Data Model

**`gig.posting`**

| Field | Description |
|---|---|
| `name` | Gig title |
| `description` | What the gig involves |
| `poster_id` | The student who posted it (→ `res.partner`) |
| `category` | Gig category (AI-suggested) |
| `budget` | Gig budget (AI-suggested) |
| `deadline` | Due date |
| `state` | Open / In Progress / Completed / Cancelled |
| `application_ids` | Applications received (→ `gig.application`) |

**`gig.application`**

| Field | Description |
|---|---|
| `gig_id` | The gig applied to (→ `gig.posting`) |
| `applicant_id` | The student applying (→ `res.partner`) |
| `message` | Application message |
| `status` | Pending / Accepted / Rejected |
| `match_score` | AI-generated fit score |

## 🛠️ Tech Stack

- **Odoo 19** (custom module)
- **Python** for models, business logic and AI integration
- **XML** for views, menus and actions
- **PostgreSQL**
- **[AI provider/API used]**
- **Git & GitHub** for team collaboration

## ⚙️ Installation

**Prerequisites:** a local Odoo 19 setup with PostgreSQL.

1. Clone the repository:
   ```bash
   git clone https://github.com/NadaK110/T07-tech-larpers-odoo-hwud.git
   ```
2. Add the repository folder to the `addons_path` in your Odoo config.
3. Set up your AI API key: [describe how the key is configured].
4. Restart the Odoo server.
5. In Odoo, enable developer mode, go to **Apps → Update Apps List**, search for **Gig Marketplace** and click **Activate**.

> **Note:** the `estate` and `estate_accounts` folders are reference modules from the Odoo intro workshop and are not part of this project.

## 👥 Team — Tech Larpers

- Nada
- Zuha Saheel
- Irina Koroleva
- Shayaan Kazi
- Madiha Ejaz

## 🙏 Acknowledgements

Thank you to **HW Tech Club** and **Odoo** for organizing BuildOdoo 2026, and to our mentors and judges for their support and feedback.