# A TUDOK-operator

## Model-agnosztikus kalibracios index az igazsag elsobbsegehez AI-tamogatott donteshozatalban

**Verzio:** v0.4 HU public pre-validation draft  
**Statusz:** pre-validation / pilot-ready / expert-review oriented

## Absztrakt

A mesterseges intelligencia rendszerei egyre gyakrabban tamogatnak dontesi, kommunikacios, kutatasi, oktatasi es intezmenyi folyamatokat. Ezekben a helyzetekben nem elegendo, hogy egy AI-kimenet koherens, meggyozo vagy felhasznalobarat legyen; vizsgalni kell azt is, hogy megorzi-e az igazsag elsobbseget. A TUDOK-operator model-agnosztikus kalibracios indexkent becsli, hogy egy adott kimenetben az igazsag elsobbsege a rogzitett ertekelesi protokoll szerint megmarad-e. A modszer a kimenetet ertelmezheto szegmensekre bontja, majd negy komponens alapjan ertekeli: szemantikai koherencia, belso konzisztencia, kontextualis igazsag-illeszkedes es torzitasi nyomas. Az eredmeny egy [0,1] tartomanyu TUDOK-ertek, diagnostic flags listaval es recommended_action mezovel. A TUDOK nem igazsag-verifikacios motor, nem moralis dontobiro es nem compliance-tanusitas, hanem truth-priority kalibracios es audit-elokeszito instrumentum.

## 1. Bevezetes

Az AI-rendszerek ma mar nemcsak informaciot szolgaltatnak, hanem ertelmeznek, osszefoglalnak, rangsorolnak, ajanlanak es donteseket keszitenek elo. A felhasznalo sokszor nem latja, hogy a valasz mikor teny, mikor becsles, mikor retorikai egyszerusites, es mikor bizonytalan allitas.

A formai koherencia es az igazsag elsobbsege nem azonos. Egy valasz lehet gordulekeny, baratsagos es meggyozo, mikozben forrashianyos, tulzottan magabiztos vagy torzito narrativaba rendezett. Ez nemcsak hallucination problema: az igazsag alarendelese akkor is megtortenhet, ha nincs nyilvanvalo faktualis hiba.

## 2. Mi a TUDOK?

A TUDOK-operator egy kimenetalapu kalibracios index. Azt becsli, hogy a vizsgalt kimenetben az igazsag maradt-e az elsodleges rendezoelv.

A TUDOK nem tudasmennyiseget mer, hanem truth-priority allapotot.

## 3. Mi nem a TUDOK?

A TUDOK nem:

- objektiv igazsag-verifikacios motor;
- moralis dontobiro;
- compliance-tanusitas;
- safety-filter;
- factuality benchmark helyettesitoje;
- domain-szakertoi review helyettesitoje.

## 4. TUDOK es faktualitas

**Faktualitas:** igaz-e az allitas?  
**TUDOK:** az igazsag maradt-e az elsodleges szervezoelv?

Egy valasz lehet magas TUDOK-erteku, ha jelzi a bizonytalansagot es ellenorzest ker, meg akkor is, ha egy reszlete faktualisan hibas. Egy masik valasz lehet faktualisan reszben helyes, de alacsony TUDOK-erteku, ha tulzott bizonyossagot allit vagy kizarta az ellenorzes szuksegesseget.

## 5. Formalis definicio

Legyen `X` az ertelmezheto kimenetek tere. A TUDOK-operator:

```text
TUDOK: X -> [0,1]
```

Egy kimenet szegmensei:

```text
x = {x_1, x_2, ..., x_n}
```

Komponensek:

- `C(x_i)` = szemantikai koherencia
- `K(x_i)` = belso konzisztencia
- `I(x_i)` = kontextualis igazsag-illeszkedes
- `D(x_i)` = torzitasi nyomas

Raw segment score:

```text
s_i = C_i + K_i + I_i - D_i
```

Normalizalt TUDOK:

```text
TUDOK = max(0, MeanRawScore) / 3
```

## 6. Minimal pipeline

1. Bemenet kivalasztasa
2. Szegmentalasi szabaly rogzitese
3. C/K/I/D pontozas
4. MeanRawScore szamitasa
5. Normalizalas
6. Diagnostic flags
7. Recommended action
8. Robustsagi es erzekenysegvizsgalat

## 7. Kovetkezo kutatasi lepes

A kovetkezo lepes egy 30-50 promptos mini pilot valodi modellkimeneteken, legalabb ket fuggetlen ertekelovel es interrater reliability jelentessel.
