# Montagehandleiding 660-4-10-00001 (roll-up)

Interactieve, geanimeerde 3D-montagehandleiding, gegenereerd uit `660-4-10-00001.stp`.

## Gebruik

Open `index.html` direct in een browser (ook offline, geen server of internet nodig).
Werkt op telefoon/tablet: één vinger = draaien, twee vingers = zoomen/pannen.
Grote "Vorige/Volgende"-knoppen onderin lopen door de 7 montagestappen; elk nieuw onderdeel
valt oranje gemarkeerd op zijn plek.

## Op GitHub zetten

1. Maak een nieuwe repository aan (bijv. `roll-up-handleiding`).
2. Zet `index.html` in de root van de repository.
3. Zet in de repo-instellingen **Settings → Pages → Branch: main /(root)** aan.
4. De handleiding is dan bereikbaar op `https://<gebruikersnaam>.github.io/roll-up-handleiding/`.
5. Updates: bestand aanpassen, committen en pushen — GitHub Pages ververst automatisch.

Er is maar één bestand (`index.html`) nodig: het 3D-model en alle benodigde scripts zitten
er al in verwerkt, dus niets kan losraken bij het kopiëren.

## Montagevolgorde aanpassen

De volgorde is automatisch afgeleid uit de onderdeelnummers in het STEP-bestand en moet
nog gecontroleerd worden door iemand die het product kent. Open `index.html` in een
teksteditor en zoek naar `const STEPS = [`. Elke stap heeft:

- `title` — koptekst van de stap
- `desc` — instructietekst voor de monteur
- `parts` — de exacte onderdeelnamen zoals ze in het 3D-bestand staan (bepaalt welk deel
  oranje oplicht en animeert)
- `partsLabel` — wat er in de onderdelenlijst op het scherm getoond wordt (nummer, omschrijving, aantal)

Stappen verplaatsen, samenvoegen of herschrijven kan door dit blok aan te passen — geen
verdere technische kennis nodig, het is gewone JSON/tekst.

## Herkomst onderdelen (automatisch gegroepeerd)

| Groep | Onderdeelnummers | Aantal |
|---|---|---|
| Basisframe | 660-1-40-00011 | 1 |
| Rolmechaniek | 660-1-40-00007-001 t/m -012 | 12 (waarvan -011 6x) |
| Kogellager | 28-1-60-61803 | 1 |
| Assen | 02-1-25-00010 (150 mm) | 3 |
| Eindkappen | 08-1-60-00001 / -00002 | 2 |
| Bevestiging | 01-1-57-00320 / -00520 / -02512 / -00312, 01-1-12-00310, 01-1-35-02295 | 24 |
| Koord | draadje, draadje 2 | 4 |

Controleer vooral groep "Rolmechaniek" en "Koord" — dat zijn onderdelen specifiek voor
dit product, waarvan de exacte functie niet uit het STEP-bestand valt af te leiden.
