# Workout Tracker

Personal workout tracker with categories, cycles, sessions, history and weekly reflections.

## Stack
- Plain HTML/JS — no build step needed
- Supabase for database and authentication
- Supabase project: `hebuaabantmnfdxxkaif`

## Features
- Workout categories with weekly goals and progress tracking
- HIIT cycle support — tracks which cycle and session is next automatically
- Workout subgroups for organising sessions within a category
- Favorite workouts and affirmations
- Workout history with notes and equipment logging
- Weekly reflections journal
- Admin panel — manage categories, subgroups and workouts via `?admin=true` URL param
- Login protected — requires email/password authentication

## Tables
| Table | Description |
|---|---|
| `workout_categories` | Top level categories with weekly goals |
| `workout_cycles` | Cycles within categories (e.g. HIIT cycles) |
| `workout_subgroups` | Subgroups within categories for organisation |
| `workouts` | Individual workout sessions |
| `workout_history` | Log of completed workouts |
| `workout_favorites` | Saved favourite workouts |
| `affirmation_favorites` | Saved favourite affirmations |
| `weekly_reflections` | Weekly reflection journal entries |

## Deploy
Edit `index.html` directly, push to GitHub — GitHub Pages serves it automatically. No build step required.

## Auth
Single user via Supabase email/password auth. RLS enabled on all tables — only authenticated sessions can read or write data.

## Admin Panel
Access the admin panel by adding `?admin=true` to the URL:
```
https://yourusername.github.io/workout_tracker/?admin=true
```

## Notes
- History older than 3 months is automatically cleaned up on load
- Affirmations are hardcoded in the HTML — edit the `affirmations` array to customise them
- Session persists across page refreshes via Supabase localStorage
