# Prijava incidenta — SRC Kibernetska varnost

Samostojno spletno orodje (ena HTML datoteka, brez zaledja) za prijavo in
obravnavo kibernetskih incidentov v podjetju **SRC d.o.o.** — Oddelek
kibernetske varnosti.

## Zavihki

- **Prijava incidenta** — zaposleni izbere, kaj opaža, in dobi korake
  "Naredi zdaj" / "Tega ne počni", prilagojene konkretni vrsti incidenta,
  ter pripravljeno e-poštno/telefonsko prijavo.
- **Moje prijave** — lokalna zgodovina zabeleženih prijav (shranjeno v
  brskalniku uporabnika), z izvozom posamezne prijave v PDF.
- **Navodila za zaposlene** — splošna uradna navodila: zlato pravilo,
  osnovna načela, stopnje kritičnosti, odziv po korakih, prepovedana dejanja.
- **FAQ** — pogosta vprašanja o prijavljanju incidentov.
- **Kontakt** — telefon in e-pošta SOC ekipe.
- **SOC playbooki** _(označeno Interno/Zaupno)_ — operativni postopki za
  SOC/IT osebje po tipih groženj (triaža, izolacija, odprava, povrnitev,
  po-incidentne aktivnosti), s filtri po stopnji/vrsti grožnje in delovnim
  prostorom za čiščenje IOC-jev.

## Zagon

Ni potreben strežnik ali gradnja (build). Odpri `index.html` neposredno v
brskalniku, ali datoteko postavi na interni spletni strežnik / intranet.
Izvoz v PDF deluje brez internetne povezave (knjižnica jsPDF je vgrajena
neposredno v datoteko).

## Nastavitve

Kontaktni podatki SOC ekipe in (neobvezen) webhook URL za Teams/Slack se
urejajo na vrhu `<script>` dela v `index.html`, v objektu `SOC_CONTACT`:

```js
const SOC_CONTACT = {
  email: "cybersec@src.si",
  phone: "+386 41 685 662",
  phoneDisplay: "+386 41 685 662",
  portal: "",
  webhookUrl: ""   // pusti prazno, da se gumb skrije
};
```

## Zasebnost podatkov

Aplikacija nima zaledja: napredek pri korakih in zgodovina "Moje prijave"
se shranjujeta izključno lokalno v brskalniku posameznega uporabnika
(`sessionStorage` / `localStorage`) in nista sinhronizirana med napravami
ali uporabniki.

## ⚠️ Zaupnost

Ta repozitorij vsebuje interne operativne postopke SOC ekipe (zavihek
"SOC playbooki", razdelek 4 vira), ki so v izvornem dokumentu označeni kot
**Interno / Zaupno — samo za SOC in IT varnostno osebje**. Repozitorij naj
bo **zaseben (private)** in dostopen samo pooblaščenemu osebju — ne
objavljaj javno na GitHubu ali drugam.

## Licenca

Glej [`LICENSE`](./LICENSE) — interna lastniška programska oprema podjetja
SRC d.o.o., ni odprtokodna.
