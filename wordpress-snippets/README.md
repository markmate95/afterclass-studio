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


6. `06-szalagavato-widget.html` -> Szalagavató fotó & videó full-width container HTML widgetje.

A Szalagavató snippet tartalmazza a saját CSS-t és JS-t is, mert új heavy-scroll kaput hoz létre a Tabló szekcióból a Szalagavató szekcióba, valamint kezeli a spotlight és kép-parallax interakciót.


## Központi scroll vezérlő

7. `07-scroll-controller-widget.html` -> Központi scroll vezérlő, utolsó HTML widget.

**FONTOS:** Ezt a widgetet kell UTOLSÓNAK elhelyezni az Elementor oldalon, az összes szekció-widget után.

Ez egyetlen központi karmesterként kezeli az ÖSSZES szekció közötti scroll-átmenetet:

Intro → Menü → Bemutatkozás → Szolgáltatások → Tabló → Szalagavató

Miért volt szükséges: korábban a scroll logika 3 külön widgetben volt (About, Tabló, Szalagavató), mindegyik saját `window.addEventListener("wheel", ...)` listenerrel és saját `gateCooldown` időzítővel. Emiatt egy egyetlen scroll-lendület egyszerre több szekciót is átugrott, mert a három külön metronóm nem tudott egymásról.

A központi vezérlő **capture fázisban** elfogja a wheel/touch eventeket, tehát ha a régi widgetek még nincsenek frissítve, a controller akkor is felülírja a működésüket. De a tiszta megoldás az, hogy a 03, 05, 06 widgeteket is újra beilleszted a frissített verziókkal (amelyekből ki lettek véve a scroll listenerek).
