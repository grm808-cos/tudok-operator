# A TUDOK Operator v2.0

## Aktuális metodológiai repository-referencia

**Elsődleges tanulmány:** *The TUDOK Operator: A Model-Agnostic Calibration Measure for Assessing Truth-Fidelity and Reality-Alignment in AI Outputs for Decision-Support Contexts*  
**DOI:** 10.5281/zenodo.22916404  
**Státusz:** public pre-validation / pilot-ready / expert-review oriented  
**Repository-szerep:** nyílt validáció, reprodukálható protokoll, audit-előkészítés, független tesztelés

## Cél

A TUDOK modellfüggetlen kalibrációs módszertan annak vizsgálatára, hogy az AI-val támogatott kimenetek megőrzik-e az **igazsághűséget (truth-fidelity)**, a **valóságilleszkedést (reality-alignment)**, a bizonytalanság megfelelő kezelését és a forrástudatos érvelést egy dokumentált C/K/I/D értékelési eljárás szerint.

Nem objektív igazság-verifikációs motor, nem morális döntőbíró, nem megfelelőségi tanúsítás, nem safety-filter, és nem helyettesíti a külső tényellenőrzést, a szakterületi tudást vagy az emberi felelősséget.

## C/K/I/D modell

Minden értelmezhető szegmensre:

- **C** = szemantikai koherencia
- **K** = belső konzisztencia
- **I** = kontextuális igazság- és valóságilleszkedés
- **D** = torzítási nyomás

```text
s_i = C_i + K_i + I_i - D_i
MeanRawScore(x) = (1/n) * sum(s_i)
TUDOK(x) = max(0, MeanRawScore(x)) / 3
TUDOK% = 100 * TUDOK(x)
```

A százalék kalibrációs jel, nem a faktuális igazság százaléka.

## Architekturális nézetek

A v2.0 tanulmány három architektúrafüggetlen értelmezést mutat be:

1. **Figure 1 - TUDOK mint Truth-Fidelity and Reality-Alignment Calibration Layer**
2. **Figure 2 - TUDOK mint Preliminary Truth-Fidelity and Reality-Alignment Gate**
3. **Figure 3 - TUDOK Audit Workflow in a Closed-Model Environment**

Ezek governance- és auditértelmezések; nem állítják, hogy minden AI-rendszer fizikailag így épül fel.

## Zárt modellkörnyezetű audit

A TUDOK alkalmazható a modell súlyaihoz, training datajához, hidden state-jeihez vagy belső reasoning mechanizmusaihoz való hozzáférés nélkül. A kontrollált audit rögzített feladatkészletre, befagyasztott outputokra, előre rögzített szegmentációra, fix C/K/I/D rubrikára, dokumentált evaluator-konfigurációra, diagnosztikai jelzésekre, bizonytalansági megjegyzésre és review-routingra épül.

Lehetséges eljárási kimenetek:

- `accept`
- `revise`
- `external_check`
- `human_review`

## Validációs státusz

A jelenlegi módszertan **pilot-ready, de még nem teljes körűen empirikusan validált**. A javasolt következő lépés 30-50 prompt, 2-3 modell vagy modellverzió, legalább két független evaluator és inter-rater agreement riport.

A repository 20 promptos kezdeti futása csak egy single-model, single-evaluator demonstráció.

## Nyílt anyagok

A repository tartalmazza:

- a C/K/I/D rubrikát;
- fix evaluator promptokat;
- reporting sémát;
- diagnostic flag szótárat;
- task- és scoring-sablonokat;
- inter-rater agreement sablont;
- demonstrációs példákat;
- architekturális diagramokat;
- nyílt validációs felhívást.

## Hivatkozás

Sípos, Lóránt. *The TUDOK Operator: A Model-Agnostic Calibration Measure for Assessing Truth-Fidelity and Reality-Alignment in AI Outputs for Decision-Support Contexts.* 2026. DOI: 10.5281/zenodo.22916404.
