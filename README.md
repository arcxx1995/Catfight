# 🐱 Catfight – Custom AI Mock Battles for CAT & More

Catfight is a gamified web platform that lets users create **custom mock tests** for CAT, SSC, UPSC, and more — powered by **AI-generated questions** and **real-time battle modes** with friends.

Built with **Cursor**, **Bolt**, **Supabase**, and **shadcn/ui** — this is your ultimate prep battleground.

---

## 🧠 Key Features

### 🎯 Custom Mock Generator
- Select exam type: CAT, SSC, UPSC, etc.
- Choose question count, topics, subtopics
- Fine-tune difficulty level per question
- Auto-adjusted exam duration
- Questions generated in real-time using OpenAI (no static CSVs!)

### ⚔️ Battle Mode
- Challenge friends or random users
- Real-time matchmaking & countdown
- Auto-timed question flow
- Compare scores immediately after battle

### 📊 Performance Analytics
- Section/topic-wise breakdown (Accuracy, Speed, Score)
- Mistake log and retry system
- Visual charts of progress

### 🔁 Practice & Review
- Instantly retry incorrect questions
- Filter past mistakes by topic/difficulty
- Focused revision sessions

### 🧑‍🤝‍🧑 Social Layer
- Custom profiles with public stats
- Add & battle friends
- Global and friend leaderboards
- Match history and profile streaks

### 📆 Smart Mock Scheduling
- Weekly practice plans & streaks
- Nudges when falling behind
- Adaptive revision paths

---

## 🛠️ Tech Stack

| Layer         | Technology         |
|---------------|--------------------|
| Frontend      | React (Cursor + Bolt) |
| UI Components | shadcn/ui          |
| Backend       | Supabase (PostgreSQL + Auth) |
| Realtime      | Supabase Realtime / WebSockets |
| AI Generation | OpenAI API (via Bolt Webhooks) |
| Hosting       | Vercel / Supabase |

---

## 🧱 Database Schema Overview

```sql
users(id, email, username, avatar_url, bio, stats_json)
friends(id, user_id_1, user_id_2, status)
mocks(id, user_id, exam_type, topic, total_time, is_battle)
questions(id, mock_id, question_text, options[], answer_index, topic, difficulty)
attempts(id, user_id, mock_id, question_id, is_correct, time_taken)
battles(id, user_1, user_2, mock_id, winner_id, status)
matchmaking_queue(id, user_id, timestamp)
user_plans(id, user_id, plan_json, streak)
leaderboards(id, user_id, percentile, total_score)
```

---

## 🤖 Sample AI Prompt for Question Generation

```txt
Generate 3 multiple choice questions for CAT Quantitative Aptitude, difficulty level 3 (medium), on the topic 'Number System'. Each question must have 4 options, with one correct answer. Format the output as JSON.
```

---

## 🖼 Pages & UI Flow

| Page             | Description                                     |
|------------------|-------------------------------------------------|
| `Home`           | Quick mock, battle invite, leaderboard, streak |
| `Mock Generator` | Topic selection, difficulty sliders, config    |
| `Mock Attempt`   | Full-screen timed mode, 1 question per page    |
| `Battle Mode`    | Invite / Live matchmaking                      |
| `Results`        | Scorecard + Analytics                          |
| `Review`         | Wrong answers, retry mode                      |
| `Friends`        | Add/search, battle friends                     |
| `Profile`        | Stats, bio, history                            |
| `Settings`       | Notifications, visibility toggles              |

---

## 📦 Project Setup

```bash
# 1. Clone the repo
git clone https://github.com/your-username/catfight.git
cd catfight

# 2. Install dependencies
pnpm install

# 3. Start development
pnpm dev
```

Make sure to:
- Setup your Supabase project with the schema above
- Add environment variables (`.env.local`) for Supabase + OpenAI
- Deploy Bolt Webhook for AI question generation

---

## 🗓️ MVP Timeline

| Week | Deliverables |
|------|--------------|
| 1    | Auth, Profile, DB Schema |
| 2    | Mock Generator + GPT Hook |
| 3    | Timer UI, Attempt Logic |
| 4    | Battle Mode + Matchmaking |
| 5    | Results, Retry System |
| 6    | Leaderboard + Social Layer |
| 7    | Smart Schedule + Notifications |
| 8    | Testing & Launch 🚀 |

---

## 🤝 Contributing

Have an idea or want to build a feature? PRs are welcome!

---

## 📫 Contact

Created with love by [Arpan].  
DM on Instagram [@spacekapow) or email at `arcxx1995@gmail.com`.

---

## ⭐️ Star This Repo

If you like the project, give it a star to support future development!
