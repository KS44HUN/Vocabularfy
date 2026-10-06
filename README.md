# Vocabularfy

Angol–magyar és magyar–angol szógyakorló egyetlen HTML fájlban. Nincs szerver, build lépés vagy függőségkezelés: megnyitod a fájlt a böngészőben, és mehet a gyakorlás.

[Magyar](#magyar) · [English](#english)

---

## Magyar

### Áttekintés

A Vocabularfy öt gyakorlási módot, kiejtés-felolvasást és napi sorozatkövetést ad egy könnyen hordozható, reszponzív felületen. Minden adat (saját szavak, beállítások, sorozat) a böngésző `localStorage`-ában marad, semmi nem kerül külső szerverre.

### Funkciók

- **Öt gyakorlási mód**, lásd az alábbi táblázatot.
- **Két irány:** angol → magyar és magyar → angol.
- **Állítható körhossz:** 5, 10, 20, 50, 100 szó vagy a teljes lista.
- **Napi sorozat:** a rendszer számolja, hány egymást követő napon gyakoroltál.
- **Kiejtés:** a kifejezések felolvasása a böngésző beépített beszédszintézisével (Web Speech API).
- **Világos és sötét téma:** alapból a rendszerbeállítást követi, kézzel is átkapcsolható.
- **Magyar és angol felület:** a fejlécben váltható, az utolsó választás megmarad. Alapértelmezett a magyar.
- **Saját szavak:** hozzáadás az alkalmazásból, valamint import és export JSON formátumban.
- **Hibák átismétlése:** a kör végén csak a hibásan megválaszolt szavakat is újra lehet gyakorolni.

### Gyakorlási módok

| Mód | Működés |
| --- | --- |
| Feleletválasztó | Négy válaszlehetőség közül kell kiválasztani a helyeset. |
| Gépelés | A fordítást be kell gépelni. A kis- és nagybetű, valamint a felesleges szóközök nem számítanak, az ékezetek igen. Ha egy szónak több jelentése van (vesszővel elválasztva), bármelyik elfogadott. Üres válasz nem ellenőrizhető, a „Nem tudom” gombbal viszont átugorható. |
| Kártya | Megfordítható kártyák „Tudtam” / „Nem tudtam” önértékeléssel. Billentyűzettel is használható (Enter vagy Space). |
| Igaz / Hamis | Egy szó–jelentés párról kell eldönteni, hogy helyes-e. |
| Párosító | Két oszlopban kell összekötni a kifejezéseket a jelentésükkel. |

### Első lépések

1. Töltsd le vagy klónozd a repót.
2. Nyisd meg a `vocabularfy.html` fájlt egy modern böngészőben (Chrome, Firefox, Safari, Edge).

Az első betöltéshez internetkapcsolat kell, mert a Tailwind CSS és a Font Awesome CDN-ről érkezik.

### Szavak importálása és exportálása

Az import és az export egyszerű JSON tömböt használ, szópáronként egy objektummal:

```json
[
  { "en": "ability", "hu": "képesség" },
  { "en": "abroad", "hu": "külföld, külföldön" }
]
```

Import során a hibás elemeket és a már létező párokat a program kihagyja. Az exportált fájl a teljes aktuális szólistát tartalmazza.

### Technikai megjegyzések

- **Stack:** HTML5 és vanilla JavaScript (ES6+), Tailwind CSS (CDN), Font Awesome 6.
- **Tárolás:** a `localStorage` a következő kulcsokat használja: `custom_words`, `theme`, `lang`, `practice_streak`, `last_practice_date`.
- **Napi sorozat:** a dátumot a program egy időszolgáltatástól kéri le. Ha ez nem érhető el, a helyi időre esik vissza.
- **Kiejtés:** a minőség és az elérhető nyelvek a böngészőtől és az operációs rendszertől függnek. Magyar hang nélkül a felolvasás az alapértelmezett hangot használja.

### Licenc

A projekt a **GNU General Public License v3.0** alatt érhető el. Szabadon használható, módosítható és terjeszthető, de a módosított változatokat is ugyanezen licenc alatt kell közzétenni.

&copy; 2026 – Vocabularfy by KS44

---

## English

### Overview

Vocabularfy is an English–Hungarian and Hungarian–English vocabulary trainer that lives in a single HTML file. There is no server, build step or dependency management: open the file in a browser and start practicing.

It offers five practice modes, text-to-speech pronunciation and daily streak tracking in a responsive, portable interface. All data (custom words, settings, streak) stays in the browser's `localStorage`; nothing is sent to an external server.

### Features

- **Five practice modes**, described in the table below.
- **Both directions:** English → Hungarian and Hungarian → English.
- **Adjustable round length:** 5, 10, 20, 50 or 100 words, or the whole list.
- **Daily streak:** tracks how many consecutive days you have practiced.
- **Pronunciation:** phrases are read aloud using the browser's built-in speech synthesis (Web Speech API).
- **Light and dark theme:** follows the system preference by default and can be toggled manually.
- **Hungarian and English UI:** switchable from the header, and your choice is remembered. Hungarian is the default.
- **Custom words:** add entries in the app, and import or export them as JSON.
- **Mistake review:** at the end of a round you can re-practice only the words you got wrong.

### Practice modes

| Mode | How it works |
| --- | --- |
| Multiple choice | Pick the correct translation out of four options. |
| Typing | Type the translation. Case and extra whitespace are ignored; accents are not. If a word has several meanings (comma-separated), any one of them is accepted. An empty answer can't be submitted, but you can skip it with the "I don't know" button. |
| Flashcards | Flip cards with "I knew it" / "I didn't know it" self-assessment. Keyboard accessible (Enter or Space). |
| True / False | Decide whether a given word–translation pair is correct. |
| Matching | Connect each phrase to its meaning across two columns. |

### Getting started

1. Download or clone the repository.
2. Open `vocabularfy.html` in a modern browser (Chrome, Firefox, Safari or Edge).

An internet connection is required on first load, since Tailwind CSS and Font Awesome are served from a CDN.

### Importing and exporting words

Import and export use a plain JSON array with one object per word pair:

```json
[
  { "en": "ability", "hu": "képesség" },
  { "en": "abroad", "hu": "külföld, külföldön" }
]
```

During import, malformed entries and pairs that already exist are skipped. The exported file contains the full current word list.

### Technical notes

- **Stack:** HTML5 and vanilla JavaScript (ES6+), Tailwind CSS (CDN), Font Awesome 6.
- **Storage:** `localStorage` keys in use: `custom_words`, `theme`, `lang`, `practice_streak`, `last_practice_date`.
- **Daily streak:** the current date is fetched from a time service, with a fallback to the local clock if it is unreachable.
- **Pronunciation:** quality and available languages depend on the browser and operating system. Without a Hungarian voice installed, speech falls back to the default voice.

### License

This project is licensed under the **GNU General Public License v3.0**. You are free to use, modify and distribute it, provided that modified versions are released under the same license.

&copy; 2026 – Vocabularfy by KS44
