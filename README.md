# andrewmurphy.net

Static site, no build step. Edit the HTML, commit, GitHub Pages publishes it.

## Files

| File | What it is |
|---|---|
| `index.html` | Home. The primary entity page. |
| `green-hydrogen-black-numbers.html` | The named framework. The single most important page on the site. See "Strategy" below. |
| `hydrogen-strategy-executive.html` | Hydrogen expertise: standards, infrastructure, geologic hydrogen, techno-economics, FAQ. |
| `cleantech-executive-board-advisor.html` | Advisory, board and diligence work. |
| `resume.html` | Full CV. Print stylesheet included, so "Print or save as PDF" gives a clean document. |
| `speaking.html` | Talks and panels. Copy-paste block below. |
| `writing.html` | Articles, publications, press. Copy-paste block below. |
| `contact.html` | Contact, including the independence and conflicts statement. |
| `inclusion-and-disability-advocacy.html` | Carer and disability inclusion. |
| `404.html` | GitHub Pages serves this automatically. |
| `style.css` | All styling. One file. |
| `llms.txt` | Plain-language summary for AI retrieval systems. Update when your roles change. |
| `robots.txt` | Explicitly permits AI crawlers. |
| `sitemap.xml` | Update `lastmod` when you make a substantial change. |

---

## Strategy: why the framework page exists

The competitor research is unambiguous. Search "hydrogen expert" and you get
university faculty databases, consultancy directories and listicles. Search
"hydrogen consultant UK" and you get Arup, Ricardo, RPS and Frazer-Nash. No
individual's personal site ranks for either. Individuals do not win those queries
with a good About page.

Michael Liebreich is the exception, and the mechanism is worth copying exactly.
He does not rank because of his biography. He ranks because of the **Clean
Hydrogen Ladder**: one named, versioned artefact published under Creative Commons
with a mandatory attribution string and a required link back. Everyone reproduces
it. Every reproduction carries his name and a link to his site. It has been cited
in regulatory filings, reproduced by trade bodies and translated. The artefact
does the ranking work and the person inherits the authority.

`green-hydrogen-black-numbers.html` applies that mechanism to you. It is:

- **Named.** "Green Hydrogen, Black Numbers" is memorable, it is yours, and
  nobody else is competing for the phrase.
- **Versioned.** Version 1.0, 2026. Versions give people a reason to link again.
- **Usable.** Five sequential tests with pass, conditional and fail. Someone can
  put it in an investment committee pack tomorrow.
- **Licensed for reuse** under CC BY 4.0, with the attribution string spelled out
  and a link back required.
- **Authentically yours.** It is your CERAWeek 2026 talk title.

To make it work you have to push it. Post the framework on LinkedIn, present it
at every speaking slot, offer it to trade press, and put the attribution line on
every slide that uses it. Issue Version 1.1 when you have feedback worth
incorporating, and announce the version change.

---

## Add a LinkedIn article

Open `writing.html`. Find `<ul class="entries">` in section 01. Paste this as the
**first** item so the newest article is at the top.

```html
        <li class="entry">
          <div class="entry-date">PUBLISH_DATE</div>
          <div>
            <h3 class="entry-title"><a href="ARTICLE_URL" rel="noopener">ARTICLE_TITLE</a></h3>
            <p class="entry-meta">LinkedIn</p>
            <p>SUMMARY</p>
          </div>
        </li>
```

Replace `ARTICLE_URL`, `ARTICLE_TITLE`, `PUBLISH_DATE` (e.g. `14 July 2026`) and
`SUMMARY`. Delete the template row already there once you have added a real
article.

Then add a matching entry to the JSON-LD block at the bottom of the file, inside
`"hasPart"`, so search engines and AI systems record you as the author:

```json
    {
      "@type": "Article",
      "headline": "ARTICLE_TITLE",
      "url": "ARTICLE_URL",
      "datePublished": "YYYY-MM-DD",
      "abstract": "SUMMARY",
      "author": { "@id": "https://andrewmurphy.net/#person" }
    }
```

Separate multiple entries with a comma. Use `YYYY-MM-DD` here, unlike the visible
date above.

---

## Add a speaking engagement

Open `speaking.html`. Section 02 is upcoming, section 03 is past. Paste this as
the first item inside the relevant `<ul class="entries">`:

```html
        <li class="entry">
          <div class="entry-date">DD MONTH YYYY</div>
          <div>
            <h3 class="entry-title">TALK OR PANEL TITLE</h3>
            <p class="entry-meta">EVENT NAME &middot; CITY, COUNTRY</p>
            <p>ONE OR TWO SENTENCES ON WHAT THE SESSION COVERS.</p>
          </div>
        </li>
```

Move events from section 02 to section 03 once they have happened. For upcoming
events also add an `Event` block to the JSON-LD in the head of the file, copying
one of the two already there.

---

## Change your role

Search the whole folder for `Oxford Hydrogen`, `GeoKiln` and `Managing Director
Europe`. The role appears in `index.html` (eyebrow, role line, record list, and
`jobTitle` plus `worksFor` in the JSON-LD), `resume.html`, `contact.html`,
`llms.txt`, and the `<meta name="description">` of several pages.

---

## Getting found: the order of operations

1. **Push the framework.** Everything above.
2. **Get linked to.** Links from event programmes, industry bodies, trade press
   and university pages are the strongest signal there is. When you speak
   somewhere, ask the organiser to link to `andrewmurphy.net` rather than only to
   LinkedIn. The Churchill Fellowship profile already links to you, which is a
   good one.
3. **Consolidate the entity.** "Andrew Murphy" is a common name and search
   engines need help knowing which one you are. Every profile you control should
   carry the same name string, the same photo and the same one-line description,
   and link to `andrewmurphy.net`. Then add each URL to the `sameAs` array in the
   JSON-LD in `index.html`. Currently listed: LinkedIn and the Churchill
   Fellowship. Worth adding: Google Scholar, ORCID, Crunchbase, Companies House,
   the British Speakers Bureau profile, the Oxford Hydrogen and GeoKiln team
   pages, Energy Institute, and any conference speaker profiles.
4. **Get into the directories.** The queries you want are won by directories
   rather than personal sites. Get listed on expert databases, speaker bureaux
   and industry "top voices" lists.
5. **Set up Google Search Console.** Free. Submit the sitemap, then watch which
   queries actually bring people in.

### What was removed and why

The old `Andrew-Murphy-Hydrogen-Guru-Awards` file repeated your name more than
eighty times in a page of unattributed praise. That is keyword stuffing under
Google's spam policies and it carried real risk of a manual action against the
whole domain. It was unlinked, so nothing was gaining from it. It is gone.

The old site also had five pages saying substantially the same thing. Duplicate
content between your own pages splits ranking signal rather than multiplying it.
Every page here now answers a different question.
