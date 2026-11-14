# KvetyKáva — design notes (verzia 3)

Demo web pre KvetyKáva (na výklade „KVETY & KÁVA“), kvetinárstvo s kaviarňou, Komenského 8, Košice.
Jeden statický `index.html` (CSS + JS v ňom), `images/`, `robots.txt`. Noindex.

Verzia 3 mení iba vzhľad a rozloženie. Obsah (texty, telefón, e-mail, hodiny, odkazy, mapa, ukážkový pruh)
ostáva z verzie 2. Pridané sú len: nový nadpis v hero „Kvety a káva na Komenského.“ (na želanie klienta),
infopruh pod hero zo zadaných údajov a dekoratívne čísla sekcií 01–05 (`aria-hidden`).

## Vizuálna referencia

| Web | URL | Čo beriem (iba princípy) |
|-----|-----|--------------------------|
| Posy (platená Framer šablóna, demo „Larkspur Flower Co.“) | https://posyflowers.framer.website/ | Fotka cez celú prvú obrazovku s tmavým prechodom; obrovský tučný grotesk vľavo dole; krátky text a jedno tlačidlo vpravo dole; tenký infopruh pod hero; striedanie tmavých a svetlých sekcií; obrovské číslice ako typografický prvok; jedna sýta akcentová farba. |

Z referencie sa nepreberá kód, texty, obrázky, logo, ružová farba ani jej fonty (Bricolage Grotesque / Hanken Grotesk).
Výskum malých susedských kvetinárstiev z verzie 2 (Florista Café, Pom'Violette, Flour Flower,
Kvetinárstvo u Dagmary, Čarokvet) platí pre obsah a poradie: hodiny, telefón a mapa sú hlavný obsah.

## Reference lock

```text
Primary reference/direction: Posy — tmavá, fotografická, typograficky hlasná stránka jedného kvetinárstva.
Preserve:
  - hero: hero.jpg cez celú šírku a výšku prvej obrazovky, tmavý prechod zdola
  - H1 ~120 px desktop / ~52–56 px mobil, tučný grotesk, 2–3 riadky, tesný riadkovanie
  - vpravo dole: krátky text + jedno výrazné tlačidlo „Zavolať a objednať kyticu“
  - tenký svetlý infopruh pod hero
  - striedanie tmavá / svetlá sekcia, žiadne karty, rámčeky ani tiene — iba 1px linky
  - obrovské číslice 01–05 pri nadpisoch sekcií
Role rules:
  - zelená lístka = jediný akcent: tlačidlá „Zavolať“, číslice sekcií, veľký telefón, stav „otvorené“, dnešný deň v tabuľke
  - všetko ostatné neutrálne (takmer čierna, takmer biela, sivé texty)
Media: hero.jpg (hero, na desktope zarovnané hore, aby bola vidieť tabuľa), kytica.jpg + kytica2.jpg veľké na tmavom
  (mobil cez celú šírku pod sebou, desktop vedľa seba 4:5), predajna.jpg v Kaviarni.
Reject: serif, script, béžové karty, tiene, ružová, kopírovanie čohokoľvek z šablóny.
```

## Tokeny

| Token | Hodnota | Rola |
|-------|---------|------|
| `--dark` | `#151715` | tmavé sekcie, hero podklad |
| `--light` | `#f2f2ef` | svetlé sekcie, infopruh, pätička |
| `--on-dark-soft` / `--on-light-soft` | `#aeb2ad` / `#565a56` | sekundárny text |
| `--leaf` | `#78ac6c` | akcent; navzorkované z lístka na tabuli (hero.jpg, medián ~ rgb(126,175,119)) |
| `--leaf-deep` | `#44743a` | tá istá zelená stmavená, iba čísla sekcií na svetlých plochách (kontrast) |
| Nadpisy | Schibsted Grotesk 800 | H1, H2, čísla, položky zoznamov |
| Text | Public Sans 400/600/700, 18 px | všetko ostatné |
| Radius | 4 px iba tlačidlá | — |

## Overené podklady (jediný zdroj obsahu)

Adresa Komenského 8, 040 01 Košice · tel. 0905 260 694 · info@naturedecor.sk ·
Ut–Pi 10:00–17:00 (obed 12:00–12:30), Po, So, Ne zatvorené · e-shop naturedecor.sk ·
Google Maps 5,0 (19 recenzií) · Instagram instagram.com/kvetykava
