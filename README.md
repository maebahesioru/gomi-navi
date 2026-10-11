# ごみの日ナビ — Gomi Navi 🗓️

**Never miss garbage day again.**
*もう、ごみの日を逃さない。*

A tiny offline app that tracks your neighborhood's garbage collection schedule and reminds you the evening before. Built for **WarriorHacks 2.0** (theme: solve an issue in your community).

## The problem

In Japan, garbage collection follows complex local rules: 燃えるごみ on Mondays and Thursdays, プラスチック on Wednesdays, 燃やせないごみ only on the 1st and 3rd Tuesday, hazardous waste once a month… Miss your slot and the bag sits in the kitchen for another week — or you chase the truck down the street at 8am. It's one of the most universal small frustrations of community life.

Gomi Navi turns your area's rules into a simple dashboard:

## Features

- 🗓️ **Next collection at a glance** — what, when, and a countdown ("Today!" / "Tomorrow" / "in 3 days")
- ✅ **Weekday toggles** — tap the days each category is collected (Mon–Sat)
- 📅 **Monthly patterns** — "1st & 3rd Tuesday only" chips for non-burnable waste
- 🔔 **Evening-before reminders** — browser notifications the day before collection
- 💾 **Everything saved locally** — no accounts, no server, works offline (localStorage)
- 🇯🇵🇬🇧 Japanese-first UI with English labels

## Default schedule (fully editable)

| Category | Days |
|---|---|
| 燃えるごみ (Burnable) | Mon & Thu |
| プラスチック (Plastics) | Wed |
| 紙・布 (Paper & Cloth) | 2nd & 4th Tue |
| 燃やせないごみ (Non-burnable) | 1st & 3rd Tue |
| 有害ごみ・電池 (Hazardous) | 1st Fri |

Presets match common Japanese municipal patterns — adjust to your own town with two taps.

## Run it

Open `index.html` in a browser, or:

```bash
python3 -m http.server 3965
```

## How it works

Single HTML file, no dependencies. The schedule is a small data model (`{category, weekdays[], months[]}`); "next collection" is computed by scanning the next 31 days. Reminders use the Web Notifications API while the app is open.

## Files

- `index.html` — the whole app
