# Osobnostní dotazníky

Jednoduchá statická webová aplikace pro vyplňování osobnostních dotazníků studenty. Celá aplikace je jediný soubor `index.html` – bez serveru, databáze a externích knihoven.

Aktuálně obsahuje (česky i anglicky):

- **HEXACO-60** – 60 výroků, 6 dimenzí, 24 facet (Lee & Ashton)
- **HEXACO-100** – 100 výroků, 6 dimenzí, 24 facet + mezilehlá faceta Altruismus (do skóre dimenzí se nezapočítává).
- **IPIP-NEO-60** – 60 výroků, Velká pětka, 30 facet (Maples-Keller et al., 2019; položky IPIP jsou volné dílo). Český překlad je pracovní a nevalidovaný. Pořadí výroků je střídané: nejdřív první výrok každé facety napříč dimenzemi, pak druhé.
- **IPIP-NEO-120** – 120 výroků, Velká pětka, 30 facet po 4 výrocích (Johnson, 2014; položky IPIP jsou volné dílo). Český překlad je pracovní a nevalidovaný, výroky společné s IPIP-NEO-60 mají stejné znění. Pořadí výroků je střídané stejně jako u verze 60.
- **Asertivita (SRAS)** – 30 výroků, jedno celkové skóre na škále 1–6 (Simple Rathus Assertiveness Schedule, McCormick 1985, podle Rathus 1973). Upraveno pro dospívající: výroky 2, 11, 12, 13 a 19 jsou přeformulované, v 27 je kino místo divadla. Český překlad je pracovní a nevalidovaný. Výsledky upozorňují, že výroky 7 a 28 měří spíš bojovnost než asertivitu.
- **Mezilidské dovednosti (ICQ)** – 40 situací, 5 oblastí po 8 položkách: navazování vztahů, svěřování se, ohrazení se, podpora druhých, zvládání konfliktů; škála 1–5 („jak dobře to zvládám“), bez obrácených položek (Interpersonal Competence Questionnaire, Buhrmester, Furman, Wittenberg & Reis, 1988). Upraveno pro dospívající: „companion“ → kamarád/ka, místo telefonování i psaní zpráv, spolubydlící → spolužáci, volba povolání → volba školy či oboru. Český překlad je pracovní a nevalidovaný.
- **Komunikační kompetence (ICCS)** – 30 výroků, 10 oblastí po 3 výrocích (sebeodhalení, empatie, sociální uvolněnost, asertivita, zaměření na druhého, vedení rozhovoru, výraznost, podporující komunikace, bezprostřednost, prosazení cílů) a celkové skóre; škála 1–5 podle četnosti (Interpersonal Communication Competence Scale, Rubin & Martin, 1994). Výroky jsou promíchané podle doporučení autorů. Výrok „Při rozhovoru se mi toulají myšlenky“ se skóruje obráceně, přestože ho původní klíč neoznačuje. Oblasti mají nízkou spolehlivost (α 0,41–0,72), výsledky na to upozorňují. Český překlad je pracovní a nevalidovaný.

## Odkazy na jednotlivé dotazníky

Každý dotazník má vlastní odkaz, který otevře rovnou jeho pokyny:

| Dotazník | Odkaz |
|---|---|
| HEXACO-60 | `…/osobnostni-dotazniky/#hexaco-60` |
| HEXACO-100 | `…/osobnostni-dotazniky/#hexaco-100` |
| IPIP-NEO-60 | `…/osobnostni-dotazniky/#ipip-neo-60` |
| IPIP-NEO-120 | `…/osobnostni-dotazniky/#ipip-neo-120` |
| Asertivita (SRAS) | `…/osobnostni-dotazniky/#asertivita` |
| Mezilidské dovednosti (ICQ) | `…/osobnostni-dotazniky/#icq` |
| Komunikační kompetence (ICCS) | `…/osobnostni-dotazniky/#iccs` |

Anglickou verzi otevře `?lang=en` před `#`, např. `…/osobnostni-dotazniky/?lang=en#asertivita`. Odkaz se dá zkopírovat i tlačítkem „🔗 Odkaz na dotazník“ na úvodní stránce (zkopíruje ho v právě zvoleném jazyce).

Pokud student dotazník už rozpracoval, odkaz ho vrátí tam, kde skončil; pokud ho dokončil, ukáže mu jeho výsledky.

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
