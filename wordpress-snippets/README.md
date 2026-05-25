# AfterClass Studio - Elementor HTML widget snippets

Másolási sorrend WordPress / Elementor alatt:

1. `01-hero-widget.html` -> első, Hero nevű full-width container HTML widgetje.
2. `02-navbar-widget.html` -> második, Navbar nevű full-width container HTML widgetje.
3. `03-about-widget.html` -> harmadik, About nevű full-width container HTML widgetje.

Fontos:

- A Hero snippet tartalmazza a közös CSS-t, ezért annak kell először szerepelnie az oldalon.
- Az About snippet végén van a JavaScript, ezért az legyen a három közül az utolsó.
- A container-ek Elementorban legyenek full width / 100% szélességűek.
- Később a menüpontokhoz tartozó szekcióknál add meg ezeket az ID-kat: `tablofotozas`, `szalagavato`, `selfiegep`, `ajanlatkeres`.
- A kód class nevei `acs-` prefixet használnak, hogy kevésbé ütközzenek WordPress/Elementor stílusokkal.
