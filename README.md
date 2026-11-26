# Portfolio Camp for TCAS 1

Static landing page for Hamster Hub. The implementation follows [planning.md](planning.md) and uses HTML, CSS, and vanilla JavaScript in `index.html`.

## Local preview

```sh
python3 -m http.server 8765
```

Open `http://localhost:8765/`.

The page keeps the existing registration and LINE destinations. The registration destination returned HTTP 404 on 27 November 2026, so launch is blocked until the event team supplies a working URL. The price, registration deadline, grade eligibility, privacy link, ARAYA artwork, senior profiles, and actual portfolio examples are not displayed until confirmed. The site includes seven full-length student clips that autoplay muted and loop while visible selected from the user-provided spreadsheet and a guest portrait supplied by the user, plus two licensed illustrative photos. See [planning.md](planning.md) for the current checklist and [assets-sources.md](assets-sources.md) for media provenance.

Do not push to `main` or deploy without authorization.
