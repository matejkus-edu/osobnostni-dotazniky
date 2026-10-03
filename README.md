# Osobnostní dotazníky

Jednoduchá statická webová aplikace pro vyplňování osobnostních dotazníků studenty. Celá aplikace je jediný soubor `index.html` – bez serveru, databáze a externích knihoven.

Aktuálně obsahuje (česky i anglicky):

- **HEXACO-60** – 60 výroků, 6 dimenzí, 24 facet (Lee & Ashton)
- **HEXACO-100** – 100 výroků, 6 dimenzí, 24 facet + mezilehlá faceta Altruismus (do skóre dimenzí se nezapočítává).- **IPIP-NEO-60** – 60 výroků, Velká pětka, 30 facet (Maples-Keller et al., 2019; položky IPIP jsou volné dílo). Český překlad je pracovní a nevalidovaný. Pořadí výroků je střídané: nejdřív první výrok každé facety napříč dimenzemi, pak druhé.

## Jazyky

Přepínač CZ / EN je vpravo nahoře. Výchozí je čeština, poslední volba si prohlížeč pamatuje.
Pro anglickou třídu stačí poslat odkaz s parametrem `?lang=en`, např. `https://<vaše-jméno>.github.io/dotazniky/?lang=en`.
Jazyk lze přepnout i během vyplňování, protože odpovědi i skórování jsou na jazyku nezávislé.

## Co umí

- vyplňování po jednom výroku (na mobilu i počítači, klávesy 1–5 a šipky)
- průběžné ukládání v prohlížeči – dotazník lze přerušit a dokončit později
- výsledky: skóre šesti dimenzí a facet (průměry 1–5 po přepólování obrácených položek), krátký popis vyššího a nižšího pólu
- tisk / uložení do PDF, stažení CSV (oddělovač `;`, desetinná čárka – otevře se rovnou v českém Excelu)
- odkaz na výsledky: odpovědi jsou zakódované přímo v adrese (`#v=hexaco60-…`), takže student může výsledky poslat vyučujícímu odkazem

Žádná data se nikam neodesílají.

## Zveřejnění na GitHub Pages

1. Na GitHubu vytvořte nový repozitář (např. `dotazniky`).
2. Nahrajte do něj `index.html` (Add file → Upload files → Commit).
3. Settings → Pages → *Source*: Deploy from a branch, *Branch*: `main` / `(root)` → Save.
4. Za minutu bude aplikace na `https://<vaše-jméno>.github.io/dotazniky/`.

Stejně funguje na jakémkoli jiném hostingu – stačí nahrát soubor.

## Přidání dalšího dotazníku

V `index.html` najděte objekt `TESTS` a přidejte další položku se stejnou strukturou jako `hexaco60`:

- `items` – výroky v pořadí (pozice = číslo položky), zvlášť `cs` a `en`,
- texty jako `subtitle`, `instructions`, `high`/`low` ve tvaru `{cs: '…', en: '…'}`,
- `scale` – možnosti odpovědí,
- `factors` – dimenze, jejich facety a čísla položek (`"30R"` = obráceně skórovaná položka).

Na úvodní stránce se nový dotazník objeví automaticky.

## Podmínky použití HEXACO

Autoři HEXACO (hexaco.org) povolují bezplatné použití pro nekomerční akademický výzkum. Online verze nesmí být veřejně přístupné: musí být chráněné heslem, nebo nedohledatelné vyhledávači. Stránka proto obsahuje `noindex`. Výroky jsou ale čitelné i ve zdrojovém kódu veřejného repozitáře na GitHubu. Bezpečnější je repozitář soukromý (GitHub Pages ze soukromého repozitáře vyžaduje GitHub Pro, který mají učitelé zdarma přes GitHub Education). Pro výuku je dobré autorům krátce napsat o svolení.

## Licence nástroje

HEXACO-60 © Kibeom Lee & Michael C. Ashton, hexaco.org – volně použitelné pro nekomerční výzkumné a vzdělávací účely.
