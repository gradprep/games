# MIM Prep Arena — entrance exam practice games

Upload ALL these web files to your GitHub repo (keep them together in one folder).

## Files
- index.html          — sign in / create account (lands on games.html)
- games.html          — arcade hub: pick a game
- game.html           — Formula Sprint (20 mixed Q, live ranked leaderboard)
- topic-sprint.html   — Topic Sprint: pick 1 of 9 topics, race your best
- match.html          — Formula Match: duel (Computer / Pass & Play / Online code)
- rapid-fire.html     — Rapid Fire: 60-second high-yield blitz across all topics
- math-trainer.html   — MIM Quant Trainer: 12-game study+test course (standalone, no login)
- coach.html          — Coach Dashboard: monitor candidate progress (instructor)
- leaderboard.html    — global + class boards
- sprint-auth.js      — auth layer. Has PLACEHOLDER Firebase config — see below.
- sprint-game.js      — game logic + scoring + live rooms
- invites.js          — challenge/invite layer (opponent picker)
- questions.js        — the 20 Formula Sprint questions
- math-games.js       — 9 topic games incl. Geometry (Topic Sprint / Match / Rapid Fire)
- database.rules.json — security rules (paste into Firebase; do NOT upload to web)

## Firebase setup (this deploy needs its OWN Firebase project — separate from any other instance of this app)
1. Create a new Firebase project → add a Web App → copy the config object it gives you.
2. Open sprint-auth.js and replace the placeholder values (apiKey, authDomain,
   databaseURL, projectId, storageBucket, messagingSenderId, appId) with your project's.
3. Realtime Database → Rules → paste database.rules.json → Publish.
   (Re-paste and Publish again if you already deployed an earlier version — this
   copy adds an "activity" node the Coach Dashboard's Program Impact report needs.)
4. Authentication → Sign-in method → enable Email/Password.
5. After deploying: Authentication → Settings → Authorized domains → add your
   hosting domain (e.g. your github.io domain).

## Coach dashboard
- Open coach.html (link is in the games hub top bar).
- "By class code": type the class/cohort code you gave candidates → see each
  candidate's tier, best score, games played, and last-active (7-day inactivity flagged).
  Export CSV.
- "All members": same view across everyone. No extra setup — reads the live boards.
- "Program impact" panel: sessions-per-day chart (14 days), week-over-week session
  trend, how many candidates are actively practicing, and % who improved their best
  score — builds up automatically as candidates play. "Copy summary for department"
  puts a plain-text report on the clipboard to paste into an email/update.

## Opponent picker (Formula Match → Online → Pick opponent)
- Shows your class members (or all members), with a green dot for who's online.
- Click Challenge → they get an "X challenged you" banner on the games hub / match page
  (Accept joins the same deck). You can still share a Room code the old way.

## Deploy
GitHub repo → Settings → Pages → deploy from main / root.
Open your Pages URL → Create account → play.

## The four games (ALL feed the leaderboard — best score counts)
- Formula Sprint — 20 mixed problems, streak ×3, hint costs 40, live leaderboard.
- Topic Sprint — choose 1 of 9 topics incl. Geometry & Solids. Personal best per topic.
- Formula Match — ask/answer duel: Computer, Pass & Play, or Online by room code.
- Rapid Fire — 60-second high-yield blitz across every topic, streak up to ×3.

Content note: questions draw on GMAT/GRE-style quantitative reasoning, since that's
the closest published question format to MIM entrance-exam quant sections.
