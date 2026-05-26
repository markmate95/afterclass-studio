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


## Új szekciók

4. `04-services-widget.html` -> Services / Szolgáltatások full-width container HTML widgetje.
5. `05-tablo-widget.html` -> Table / Tablófotózás full-width container HTML widgetje.

Fontos az új részeknél:

- A Services snippet tartalmazza a legfrissebb közös CSS-t is, ezért a Services widget legyen a Tabló widget előtt.
- A Tabló snippet végén van az új kiegészítő JavaScript a services typewriter, spotlight, heavy-scroll és tabló board animációkhoz.
- A hamburger menü nincs használatban; a menü továbbra is a külön navigációs képernyőn jelenik meg.
