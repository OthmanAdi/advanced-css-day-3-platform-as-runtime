 > [!TIP]
> **Lest dieses Doc komplett bevor ihr anfangt.** Es ist kürzer als es aussieht und spart euch nachher zwei Stunden Verwirrung.

---

# Hausaufgabe — Donnerstag 07.05.2026
## Issue lösen, PR stellen, mergen lassen.

| | |
|---|---|
| **Dauer heute** | 45–70 Minuten |
| **Fortsetzung** | Morgen Vormittag im Review-Block |
| **Format** | Pull-Request gegen das Class-Repo |
| **Ergebnis** | Mindestens **ein** Issue gelöst, mindestens **ein** PR eingereicht |
| **Repo** | https://github.com/OthmanAdi/advanced-css-day-3-platform-as-runtime |
| **Live** | https://othmanadi.github.io/advanced-css-day-3-platform-as-runtime/ |

---

## WAS HEUTE PASSIERT

Heute Vormittag haben wir **ein Ticket** zusammen erledigt — Issue #1, View Transitions. Eine Page-Animation, vier Pages, kein Framework. Wir haben commited mit `closes #1`, gepushed, GitHub hat die Issue geschlossen. Ihr habt gesehen wie der Loop läuft.

Heute Nachmittag macht **ihr** den gleichen Loop. Eigener Fork, eigener Branch, eigener Pull-Request gegen das Repo. Ich review eure PRs morgen früh in der Klasse — wir mergen die guten in `main`. Euer Code geht **echt** ins Production-Repo. Eure GitHub-Profile zeigen die Contributions an. Recruiter, die später durch euer GitHub stöbern, sehen einen offenen-Source-Beitrag mit Discussion und Merge.

Das ist kein Übung. Das ist Workflow.

---

## DER WORKFLOW — SECHS SCHRITTE

### Schritt 1 — Fork

Geht auf https://github.com/OthmanAdi/advanced-css-day-3-platform-as-runtime und klickt oben rechts **"Fork"**. Standardeinstellungen, "Create fork".

Ihr habt jetzt eine Kopie unter `github.com/EUER_USERNAME/advanced-css-day-3-platform-as-runtime`.

### Schritt 2 — Klonen

Im Terminal:

```bash
cd ~/Documents
git clone https://github.com/EUER_USERNAME/advanced-css-day-3-platform-as-runtime.git
cd advanced-css-day-3-platform-as-runtime
code .
```

Ersetzt `EUER_USERNAME` durch euren echten GitHub-Namen.

### Schritt 3 — Issue wählen + Branch erstellen

Sucht euch ein Issue aus der Liste unten aus (eines mindestens, gerne mehr). Der Branch-Name folgt einem Schema: `issue-NUMMER-kurze-beschreibung`. Beispiele:

```bash
git checkout -b issue-13-fix-cubic-bezier
git checkout -b issue-9-scroll-fade-hero
git checkout -b issue-14-dark-mode-toggle
```

### Schritt 4 — Code schreiben

Lokalen Server starten, im Browser arbeiten:

```bash
python -m http.server 8000
# oder auf Mac wenn python3:
python3 -m http.server 8000
# oder VSCode Live-Server-Extension
```

Browser auf `http://localhost:8000`. Page läuft. Datei editieren, speichern, `Ctrl+Shift+R` für Hard-Refresh.

### Schritt 5 — Commit + Push

```bash
git add .
git commit -m "fix: cubic-bezier missing fourth value, closes #13"
git push origin issue-13-fix-cubic-bezier
```

**Wichtig:** Commit-Message endet mit `closes #N` oder `fixes #N`. GitHub erkennt das automatisch und schließt die Issue, sobald der PR gemerged ist.

### Schritt 6 — Pull-Request stellen

Im Terminal:

```bash
gh pr create --base main --head issue-13-fix-cubic-bezier --title "Fix cubic-bezier missing fourth value" --body "Closes #13. Replaces \`cubic-bezier(0.4, 0, 0.2,)\` with \`cubic-bezier(0.4, 0, 0.2, 1)\` in transitions.css line 32. Old/new transitions now use identical Material easing."
```

Oder ohne `gh` CLI: GitHub-Web → euer Fork → "Compare & pull request" Button → Description schreiben → "Create pull request".

**Title:** kurz, was geändert wurde.
**Description:** muss mindestens enthalten:
- `Closes #ISSUE_NUMBER` (verlinkt automatisch)
- 2–4 Sätze was ihr geändert habt
- Bei visuellen Änderungen: Screenshot oder kurze Notiz "Test: navigiere zwischen Home und Pricing — Animation läuft."

---

## DIE 11 ISSUES — WÄHLT MINDESTENS EINS

| # | Titel | Tags | Schwierigkeit |
|---|-------|------|---------------|
| #6 | Active-State auf Nav-Link sichtbar machen | `good first issue` `polish` | ⭐ Easy |
| #7 | Sichtbarer Focus-Ring auf allen Elementen | `good first issue` `accessibility` | ⭐ Easy |
| #8 | Footer: Link zum Source-Repo | `good first issue` `polish` | ⭐ Easy |
| #9 | Hero: Scroll-driven Fade-In auf Home | `enhancement` `polish` | ⭐⭐ Medium |
| #10 | Pricing: Vierter Plan "Hobby" | `enhancement` | ⭐⭐ Medium |
| #11 | Login: Real-time Email-Validierung mit `:has()` | `enhancement` `accessibility` | ⭐⭐ Medium |
| #12 | Profile: Stat-Cards Hover-Lift | `enhancement` `polish` | ⭐⭐ Medium |
| #13 | Bug: cubic-bezier fehlender Wert | `bug` `advanced` | ⭐ Easy (hidden gem) |
| #14 | Dark-Mode-Toggle mit `:has()` + Checkbox | `enhancement` `advanced` | ⭐⭐⭐ Hard |
| #15 | 404-Page mit View-Transitions | `enhancement` `advanced` | ⭐⭐⭐ Hard |
| #16 | `@scope` auf Site-Nav | `enhancement` `advanced` | ⭐⭐⭐ Hard |

**Tag-Bedeutung:**

- 🟢 `good first issue` — wenn ihr noch nie ein PR gestellt habt, fangt hier an
- 🟦 `accessibility` — Web für alle, plus Senior-Move-Skills
- 💜 `polish` — kleine UX-Wins, sichtbarer Unterschied
- ✨ `enhancement` — neues Feature, baut auf existierendem Code auf
- 🐛 `bug` — etwas ist kaputt, ihr fixt es
- 🔥 `advanced` — geht tiefer, neues CSS-Feature aus der heutigen Lecture oder W1 Untaught

**Empfohlene Pfade:**

| Wenn ihr seid... | Macht... |
|------------------|----------|
| Beginner Tag 3, erstes Mal PR | #6, #8 oder #13 — alle drei in 30 min lösbar |
| Mid, comfortable mit CSS | #9 (Scroll-Fade) oder #11 (Email-Validierung) — beide nutzen Features die ihr schon kennt |
| Advanced, wollt euch fordern | #14 (Dark-Mode mit `:has()`) oder #16 (`@scope`) — Senior-CSS |

---

## TIER-SYSTEM

| Tier | Was ihr abliefert |
|------|---------------------|
| **Bronze** | Ein Issue gelöst, ein PR steht, beschreibt was ihr getan habt |
| **Silver** | Bronze + zweites Issue, zweiter PR, beide gemerged-fähig |
| **Gold** | Silver + ihr habt ein "advanced"-Issue (#14 / #15 / #16) drin |
| **Diamond** | Gold + ihr habt zusätzlich ein PR von einem Mitstudent reviewed (Comment auf seinem PR mit konkretem Vorschlag oder "looks good, ready to merge") |

Diamond ist nicht "mehr Code". Diamond ist "ich kann auch fremden Code lesen und meine Meinung dazu in einem Kommentar formulieren". Das ist die Senior-Skill.

---

## THEORIE — KURZ + RELEVANT

### Pull-Request-Mechanik (warum es wichtig ist)

Ein Pull-Request ist nicht "ich habe Code". Ein PR ist eine **Diskussion**: hier ist mein Vorschlag, könnt ihr drüberschauen, mergt ihr ihn. In Open-Source-Projekten und in jeder Firma sind PRs der Hauptkanal für Code-Review. Wer keine PR-Erfahrung hat, kann in einer Firma am ersten Tag nicht arbeiten.

Drei Eigenschaften eines guten PRs:
1. **Ein Thema pro PR.** Nicht "ich habe heute drei Sachen gemacht". Wenn ihr drei Sachen gemacht habt: drei PRs.
2. **Beschreibung erklärt das Warum, nicht das Wie.** "Closes #13. Old/new transitions waren asymmetrisch wegen fehlendem 4. Wert." Reviewer liest in fünf Sekunden.
3. **Verlinkt die Issue.** `Closes #N` ist Magic — GitHub schließt die Issue automatisch beim Merge.

### Scroll-driven Animations — Vertiefung

Wenn ihr Issue #9 (Hero Fade-In) macht: lest **diesen Artikel** vor dem Tippen. Dreißig Minuten investiert sparen euch zwei Stunden Verwirrung später.

> **Josh W. Comeau — "An Interactive Guide to Scroll-driven Animations"**
> https://www.joshwcomeau.com/animation/scroll-driven-animations/?ref=dailydev

Josh ist einer der besten Frontend-Educators im Web. Sein Artikel ist interaktiv — ihr scrollt durch und seht die Konzepte live. Er zeigt drei Sachen, die nicht in unserem Warmup waren:
- `animation-timeline: scroll()` (page-scroll als Timeline) vs `view()` (element-visibility als Timeline)
- Wie `animation-range` exakt zu lesen ist (entry, contain, exit, cover)
- Warum bestimmte CSS-Properties scroll-getrieben anders aussehen als zeit-getrieben

Wer Issue #9 ohne Joshs Artikel zu lesen löst, schreibt Code der "irgendwie funktioniert". Wer ihn liest, schreibt Code der **richtig** funktioniert.

### View Transitions — was ihr heute gelernt habt

Ein Snapshot-System. Browser fotografiert vor dem Page-Wechsel den alten Zustand, fotografiert nach dem Wechsel den neuen, animiert dazwischen. Drei CSS-Pseudo-Elemente:
- `::view-transition-old(root)` — alte Page
- `::view-transition-new(root)` — neue Page
- `::view-transition-group(NAME)` — wenn Elemente einen `view-transition-name` teilen

Der Brain-Explosion-Punkt: das funktioniert für **Multi-Page-Apps** automatisch — keine SPA, kein Router, kein useState. Vier echte HTML-Files mit `<a href>`-Links kriegen Transitions, sobald `@view-transition { navigation: auto; }` ausgerollt ist.

### `:has()` — Vorgriff auf Issues #11 und #14

`:has()` ist die Pseudo-Class, die "matched dieses Element wenn es ein Kind/Geschwister mit X enthält". Sie ist der Grund, warum JavaScript-Workarounds für "select parent element" 2026 nicht mehr nötig sind. Beispiele:

```css
/* Form-Field rot wenn Input invalid und nicht leer */
.field:has(input:not(:placeholder-shown):invalid) {
  border-color: red;
}

/* Body wechselt in Dark-Mode wenn Checkbox checked */
body:has(#theme-toggle:checked) {
  --color-bg: var(--slate-900);
  --color-text: var(--slate-50);
}
```

Beide Patterns sind Issue-Lösungen.

### `@scope` — Vorgriff auf Issue #16

`@scope (.site-nav)` heißt: "die Regeln in diesem Block wirken nur innerhalb von Elementen mit `.site-nav` als Vorfahre". Sobald ein zweites `<nav>` in der Page existiert, übernimmt es die Styles **nicht**. Das ist die Browser-native Antwort auf CSS-Modules in React.

```css
@scope (.site-nav) {
  a {
    color: var(--color-brand);
  }
}
```

Im obigen Block heißt `a` lokal — nur die `<a>` innerhalb von `.site-nav`. Außerhalb passiert nichts.

---

## RESOURCES — ALLE GETESTET, KEINE FILLER

### View Transitions
- **MDN — View Transitions API** — https://developer.mozilla.org/en-US/docs/Web/API/View_Transitions_API
- **Una Kravets — "View Transitions are now Multi-Page"** — https://developer.chrome.com/blog/cross-document-view-transitions
- **Bramus Van Damme — Cross-document Examples** — https://live-transitions.pages.dev/

### Scroll-driven Animations
- **★ Josh W. Comeau — Interactive Guide** — https://www.joshwcomeau.com/animation/scroll-driven-animations/?ref=dailydev
- **scroll-driven-animations.style** (Bramus' Demo-Sammlung) — https://scroll-driven-animations.style/

### `:has()` und CSS Selectors 2026
- **MDN — `:has()`** — https://developer.mozilla.org/en-US/docs/Web/CSS/:has
- **Kevin Powell — `:has()` opens new possibilities (12 Min)** — https://www.youtube.com/watch?v=OGJvhpoE8b4

### `@scope`
- **MDN — `@scope`** — https://developer.mozilla.org/en-US/docs/Web/CSS/@scope
- **Bramus — "Limit reach with @scope"** — https://web.dev/articles/at-scope

### Pull-Request-Workflow allgemein
- **GitHub Docs — Creating a pull request from a fork** — https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork
- **Conventional Commits** (Commit-Message-Standard) — https://www.conventionalcommits.org

---

## ABGABE — WIE IHR FERTIG WERDET

WhatsApp-Gruppe oder Zoom-Chat:

1. Tier (Bronze / Silver / Gold / Diamond)
2. Eure Fork-URL
3. Eure PR-URLs (eine pro Issue)
4. Eine Sache, die euch heute hängengeblieben ist — Bug, Aha-Moment, oder Stelle wo ihr "klick" gemacht habt. Eine Sache reicht.

**Deadline:** morgen Vormittag bis 09:00 — ich review im Vormittags-Block.

Bei Fragen heute Nachmittag bis 20:00 im Chat. Danach morgen ab 08:00.

---

## EINE LETZTE SACHE — DER PRODUKTIONS-PUNKT

Was ihr heute Nachmittag macht ist nicht "Hausaufgabe". Es ist der Workflow, der in jeder Firma der Welt läuft. Vercel, Stripe, Linear, Cal.com, Resend — alle haben Repositories mit Issues, alle akzeptieren PRs, alle reviewen vor dem Merge. Wer in einem Vorstellungsgespräch sagt "ich habe an Open-Source-Projekten beigetragen", öffnet automatisch das Gespräch über Workflow, Code-Review-Skills, und Senior-Verhalten.

Heute kriegt ihr genau diese Erfahrung. Mit echtem Repo, echten Issues, echtem Merge.

Bis morgen.

---

*Hausaufgabe Donnerstag 07.05.2026 | Advanced CSS Modul, Woche 1, Tag 3 | Morphos GmbH*
