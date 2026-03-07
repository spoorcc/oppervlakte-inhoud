# Oppervlakte & Inhoud - Leerplatform voor Groep 7

## Project Overview
- **Project naam**: Oppervlakte & Inhoud Calculator
- **Type**: Interactief educatief platform
- **Kern functionaliteit**: Stap-voor-stap uitleg van oppervlakte en inhoud berekeningen voor verschillende geometrische vormen
- **Target gebruikers**: Kinderen in groep 7 (10-11 jaar)
- **Taal**: Nederlands

## UI/UX Specification

### Layout Structuur
- **Header**: Logo/titel, navigatie tabs (Oppervlakte/Inhoud), sterren teller, reset knop, π instelling
- **Home view**: Welcome banner + shapes grid
- **Lesson view**: Term explanation + Steps + Calculator + Solved questions + Flappy game
- **Footer**: Credits

### Responsive Breakpoints
- Mobile: < 768px
- Tablet: 768px - 1024px
- Desktop: > 1024px

### Visuele Design

#### Kleurenpalette
- **Primary**: #6C5CE7 (Vibrant Purple)
- **Secondary**: #00CEC9 (Teal/Turquoise)
- **Accent 1**: #FDCB6E (Warm Yellow)
- **Accent 2**: #E17055 (Coral Orange)
- **Accent 3**: #00B894 (Mint Green)
- **Background**: #F0F3FF (Light Purple-Gray)
- **Card Background**: #FFFFFF
- **Text Primary**: #2D3436
- **Text Secondary**: #636E72

#### Typografie
- **Font Family**: 'Nunito' (Google Fonts) - vriendelijk en modern
- **Headings**: 700-800 weight
- **Body**: 400/600 weight

#### Visuele Effecten
- Card shadows: 0 10px 40px rgba(108, 92, 231, 0.15)
- Hover transitions: 0.3s ease
- Shape card hover: translateY(-8px)
- Confetti burst bij correct antwoord
- Background pattern met gradient circles

### Iconen
- **Oppervlakte tab**: 📏 (liniaal)
- **Inhoud tab**: 📦 (doos)
- **Sterren**: ⭐
- **Reset**: ♻️ (recycle)
- **Tabs**: actief = gevulde kleur

### Components

#### 1. Navigatie Tabbladen
- Twee tabs: "Oppervlakte" en "Inhoud"
- Active state: gevulde primary kleur met box-shadow
- Hover: lichte achtergrond kleur

#### 2. Vorm Selectie Kaarten (Shapes Grid)
- 4 kaarten voor Oppervlakte, 4 voor Inhoud
- Icoon (SVG) + naam + korte beschrijving
- Status indicator: checkmark ✅ voor voltooid, "X/5" voor voortgang
- Hover: schaalvergroting + verhoogde schaduw

#### 3. Term Explanation Box
- Gradient achtergrond (primary → secondary)
- SVG diagram van de vorm met gelabelde maten
- Lijst met termen en definities

#### 4. Lesson Steps
- Genummerde stappen (1, 2, 3...)
- Fade-in animatie per stap
- Formule box met pulse animatie
- Stap-voor-stap uitleg

#### 5. Question Card (Oefenmodule)
- Vraag SVG diagram (280×280px) met daadwerkelijke waarden gelabeld
- Vraagtekst met waarden
- Input veld + controleer knop
- 3 kansen (❤️❤️❤️)
- Resultaat tonen (correct/wrong)

#### 6. Solved Questions Lijst
- Toont alle vragen van de sessie
- ✅/❌ markering
- Juiste antwoord + berekening
- **Bij fout**: gele achtergrond + stapsgewijze uitleg
- pogingen teller (groen = 1, geel = meer)

#### 7. Mascotte
- Vaste positie: rechtsonder
- Drie states: normaal, blij (happy), verdrietig (sad)
- Speech bubble met berichten
- Verdwijnt tijdens Flappy game

#### 8. Flappy Vorm Mini-game
- In-page game (geen modal)
- Speel als beloning na 5 correcte antwoorden
- Speler = vorm in de kleur van de les
- Obstakels = groene pijpen met andere vormen
- 5 levens, score teller
- Besturing: klik of spatie

## Vormen & Formules

### Oppervlakte (4 vormen)
1. **Vierkant**: zijde × zijde (a²)
2. **Rechthoek**: lengte × breedte (l × b)
3. **Driehoek**: (basis × hoogte) ÷ 2
4. **Cirkel**: π × straal²

### Inhoud (4 vormen)
1. **Kubus**: zijde³ (alle ribben gelijk)
2. **Blok**: lengte × breedte × hoogte (3D rechthoek)
3. **Cilinder**: π × straal² × hoogte (ronde vorm)
4. **Piramide**: (lengte × breedte × hoogte) ÷ 3 (met punt)

## Functionality Specification

### Core Features

#### 1. Vormselectie
- Klik op shape card → lesson view
- Toont termen, stappen, calculator

#### 2. Stap-voor-stap Uitleg
- Termen en definities met diagrammen
- Genummerde stappen met animatie
- Formule visualisatie

#### 3. Interactieve Oefening
- Willekeurige waarden per vraag
- Controleer knop met Enter toets
- 3 kansen per vraag
- Directe feedback (correct/wrong)
- Mascotte reacties

#### 4. Voortgang Systeem
- **correctInRow**: telt correcte antwoorden achterelkaar per vorm
- **completedShapes**: Shape is voltooid na 5 correct achterelkaar
- **Sterren**: +1 per correct antwoord na 5 = voltooid
- **localStorage**: alle voortgang blijft bewaard

#### 5. Flappy Vorm Beloning
- Start automatisch na 5 correcte antwoorden
- Kan afgesloten worden met X knop
- Reset correctInRow bij sluiten
- Auto-start na 500ms vertraging

#### 6. Vraag Diagram
- Toont SVG van de vorm
- Labels met daadwerkelijke waarden uit de vraag
- Duidelijke maat-lijnen (lengte, breedte, etc.)

#### 7. Uitwerkingen bij Fout
- Gele achtergrond voor foute vragen
- Stapsgewijze berekening:
  - Stap 1, Stap 2, etc.
  - Met tussentijdse resultaten
- Aantal pogingen getoond per vraag
- Kleur: groen (1 poging), geel (meer pogingen)

#### 8. Settings
- **π keuze**: 3 of 3,14 (belangrijk voor cirkel/cilinder berekeningen)
- **Reset knop**: wist alle voortgang (met bevestiging)

### Data Storage (localStorage)
- `oppervlakteInhoud_stars`: totaal sterren
- `oppervlakteInhoud_correctInRow`: per vorm
- `oppervlakteInhoud_completedShapes`: voltooide vormen

### User Interactions
- Tabbladen schakelen
- Shape cards klikken
- Enter toets in input veld
- Controel knop
- Spatie/klik voor Flappy game
- Reset knop met confirm()

### Animaties
- Page transitions: fade + slide
- Step reveal: sequential fade-in (0.2s delay per stap)
- Success: confetti burst (30 particles)
- Formula pulse: infinite animation
- Shape card hover: scale + translateY
- Mascotte bounce: infinite

## Technical Details

### Bestandsstructuur
- Enkel bestand: index.html (HTML + CSS + JS inline)
- Externe dependency: Google Fonts (Nunito)

### SVG Grafieken
- Term diagrams: statisch per shape
- Question diagrams: dynamisch met waarden
- Flappy game: canvas rendering

### Event Listeners
- Tab clicks
- Shape card clicks
- Input keypress (Enter)
- Button clicks
- Flappy canvas click
- Keyboard (Space for Flappy)

## Acceptance Criteria

### Voltooid ✅
- [x] Website laadt zonder fouten
- [x] Alle 4 oppervlakte-vormen werken
- [x] Alle 4 inhoud-vormen werken (inclusief piramide)
- [x] Stap-voor-stap uitleg is duidelijk
- [x] Interactieve berekeningen werken correct
- [x] Responsive op mobile/tablet/desktop
- [x] Animaties zijn vloeiend
- [x] Kindvriendelijke taal gebruikt
- [x] Mascotte verschijnt op juiste momenten
- [x] Flappy game werkt als beloning
- [x] Vraag diagrammen tonen waarden
- [x] Uitwerkingen bij fout met stappen
- [x] pogingen teller per vraag
- [x] Gele styling voor foute antwoorden
- [x] localStorage werkt correct
- [x] π instelling werkt
- [x] Reset functionaliteit werkt
