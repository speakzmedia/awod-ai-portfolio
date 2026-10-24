# awod-ai-portfolio

Die Repo-Karte: was das ist, Befehle, Layout, wer was macht. Was flottenweit gilt (Git, PR,
Issues, Schreiben), lädt aus `~/.claude/rules/` und steht hier nicht. `AGENTS.md` ist ein
Symlink auf diese Datei.

## Was das ist

Portfolio- und Buchungsseite von AWOD.AI (Awedis Mosoyan, extern, KI-Video und -Bilder):
Startseite mit Showreel, Portfolio, Leistungen, Über, Kontakt, Impressum und Datenschutz.
Gebucht wird über Calendly, Kontakt per `mailto:`; es gibt kein Backend und keine Datenbank.
Next 16 (App Router) mit `motion`, auf Vercel unter awod-ai-portfolio.vercel.app.

**Das Repo ist öffentlich.** Nichts Internes hineinschreiben, keine Kundendaten, keine
Zugänge, auch nicht in Commit-Nachrichten.

## Befehle

```bash
npm ci
npm run dev      # localhost:3000
npm run build
npm run lint
```

Es gibt keine CI. Was vor dem Livegang erfüllt sein muss, steht in `LAUNCH_CHECKLIST.md`
(Stand 24.10.2026: kein Punkt abgehakt).

## Layout

```
src/data/site.ts      Name, Texte, Calendly, E-Mail, Socials, SEO-Begriffe: der Inhalt an einer Stelle
src/app/              Seiten (portfolio, services, about, contact, impressum, datenschutz), OG-Bilder, Sitemap, robots
src/components/       Kopf, Fuss, Hero-Video, Showreel, Calendly-Einbettung
src/lib/site-url.ts   Basis-URL aus NEXT_PUBLIC_SITE_URL
public/               Medien
briefing.txt          das ausgefüllte Briefing vom 23.02.2026, Quelle für Copy und Struktur
```

## Secrets

Keine. `.env.example` (erzeugt von `env-beispiel`) nennt nur `NEXT_PUBLIC_SITE_URL`.

## Wer macht was

Awedis ist der Kunde und liefert Inhalte und Medien. Vincent ist Maintainer: er reviewt und
merged. Only the maintainer merges: alle anderen Sitzungen markieren einen fertigen PR mit
`✅ READY FOR MERGE`. Issues sind in diesem Repo abgeschaltet; Befunde gehen an Vincent.
