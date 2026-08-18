# OmniBlock — Fișa din magazin (Română)

Text tradus pentru fișele în limba română din Chrome Web Store și AMO.
Ambele magazine acceptă fișe pe limbă -- vezi `submission-runbook.md`
pentru procesul de completare. Structura, limitele de caractere,
categoria, capturile de ecran, imaginile promoționale și declarația
privind colectarea datelor rămân în `listing.md` (în engleză, sursa de
adevăr pentru proces) -- acest fișier conține doar textul orientat către
utilizator, cel introdus efectiv pentru fiecare limbă.

## Nume

```
OmniBlock
```

## Descriere scurtă (Chrome Web Store, ≤132 caractere)

127 caractere:

```
Blocare reclame, elemente de urmărire și amenințări: 6 niveluri de protecție, Security Shield, liste proprii, control per site.
```

## Rezumat (AMO, ≤250 caractere)

232 caractere:

```
Blochează reclame, elemente de urmărire și site-uri rău-intenționate cunoscute pe 6 niveluri de protecție, plus un Security Shield independent. Liste proprii, încredere per site, selector de elemente. Zero telemetrie, complet local.
```

## Descriere completă (ambele magazine)

```
OmniBlock este un blocator de conținut multi-browser: reclame, elemente
de urmărire, bannere de cookie-uri și site-uri rău-intenționate
cunoscute, cu un regulator de protecție de la 0 la 5, un Security Shield
independent și permanent activ, control per site, abonamente la liste de
filtre proprii și un selector de elemente prin simplă apăsare.

SINCERI DESPRE DIFERENȚELE DINTRE PLATFORME

Pe Chrome, Edge, Brave și alte browsere bazate pe Chromium, OmniBlock
rulează pe API-ul nativ declarativeNetRequest din Manifest V3. Nicio
extensie Manifest V3 -- inclusiv OmniBlock -- nu poate egala ce reușea
uBlock Origin în era MV2, deoarece Chrome a eliminat API-ul de filtrare
dinamică ce făcea asta posibilă. Concurența reală a OmniBlock pe Chromium
sunt uBO Lite și ABP-MV3, iar obiectivul nostru este să le depășim la
profunzimea listelor de filtre, la ergonomia nivelurilor de protecție și
la controlul per site, rulând totodată la viteza nativă DNR: zero
JavaScript pe calea cererilor, ceea ce este strict mai rapid decât orice
potrivire evaluată prin JS a unui blocator din era MV2.

Pe Firefox, OmniBlock folosește webRequest cu blocare completă și motorul
său propriu de filtrare, situându-se cu adevărat în aceeași clasă cu
uBlock Origin: suport complet pentru sintaxa listelor de filtre, reguli
nelimitate și un motor de potrivire care, potrivit propriilor
benchmark-uri publicate de Ghostery, este mai rapid decât cel al uBO.

Preferăm să vă spunem asta direct, decât să aflați pe calea cea grea.

FUNCȚII

- 6 niveluri de protecție (de la Dezactivat la Fortăreață), fiecare
  cumulativ și precompilat -- schimbarea nivelului este instantanee,
  fără repornire
- Security Shield independent: fluxuri de informații despre amenințări
  (malware, phishing, fraudă, magazine false) care rămân active chiar și
  la nivelul de protecție Dezactivat, pentru că securitatea nu este o
  preferință legată de blocarea reclamelor
- Abonamente la liste de filtre proprii -- abonează-te la orice URL de
  listă în sintaxă adblock sau hosts
- Filtrele mele -- scrie-ți propriile reguli de filtrare de mână,
  validate linie cu linie
- Selector de elemente -- apasă pentru a ascunde orice a scăpat unei
  liste de filtre
- Control per site -- ai încredere deplină într-un site cu un singur
  clic, exceptându-l complet de la blocare
- Panou local de statistici -- istoricul cererilor blocate și domeniile
  cele mai blocate (Firefox; vezi nota de pe pagina Statistici despre
  motivul pentru care Chromium nu poate expune aceste date niciunei
  extensii)
- Importă/exportă setările tale ca un singur fișier
- Interfață Rift exclusiv în temă întunecată (sistemul de design
  OmniVex, albastrul caracteristic OmniBlock), gândită pentru un popup
  rapid și fără fricțiuni

CONFIDENȚIALITATE

Zero colectare de date. Fără telemetrie, fără analitice, fără conturi,
fără server. Listele de filtre sunt descărcate ca text în sintaxă
adblock de la întreținătorii lor publici (EasyList, listele de filtre
ale uBlock Origin, listele de blocare DNS ale HaGeZi). Biblioteca de
scriptlets la care aceste reguli pot face referire este inclusă direct
în extensie, fixată la o versiune anume, verificată -- iar din orice
listă la care te abonezi tu însuți, liniile care invocă scriptlets sunt
eliminate înainte ca motoarele de blocare ale OmniBlock să apuce să le
vadă. Politica completă: vezi fila Confidențialitate a acestei fișe.
```
