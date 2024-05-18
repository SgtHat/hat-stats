---
share: "true"
noteType: game
tournament: Toms
gameID: 1
opponents: Grut
gameType: Pool
ourScore: 12
theirScore: 9
---

```dataviewjs
const currentNote = dv.current().file.frontmatter; 
const tournament = currentNote.tournament; 
const gameID = currentNote.gameID;

// Filter notes based on the tournament and gameID from the current note
const cleanHolds = dv.pages("") .filter(p => p.tournament == tournament && p.gameID == gameID && p.weStart == "O" && p.offensiveTurns == 0 && p.whoScores == "Chev") .length;

const breaks = dv.pages("") .filter(p => p.tournament == tournament && p.gameID == gameID && p.weStart == "D" && p.whoScores == "Chev") .length;

const turns = dv.pages("") .filter(p => p.tournament == tournament && p.gameID == gameID && p.weStart == "D" && p.offensiveTurns != 0) .length;


dv.span(`Clean Holds: ${cleanHolds}<br>`);
dv.span(`Breaks: ${breaks}<br>`);
dv.span(`Points with Turns: ${turns}<br>`);
```

Started on O

# O-Scores
```leaflet
id: grut_o_scores
image: [[Pitch.png]]
bounds: [[0,0], [640,1000]]
height: 450px
width: 100%
lat: 320
long: 500
minZoom: -1.5
maxZoom: 18
defaultZoom: -1
zoomDelta: 0.5
darkMode: false
```

# D-Scores
```leaflet
id: grut_d_scores
image: [[Pitch.png]]
bounds: [[0,0], [640,1000]]
height: 450px
width: 100%
lat: 320
long: 500
minZoom: -1.5
maxZoom: 18
defaultZoom: -1
zoomDelta: 0.5
darkMode: false
```

# Turns
```leaflet
id: grut_turns
image: [[Pitch.png]]
bounds: [[0,0], [640,1000]]
height: 450px
width: 100%
lat: 320
long: 500
minZoom: -1.5
maxZoom: 18
defaultZoom: -1
zoomDelta: 0.5
darkMode: false
```

# Ds
```leaflet
id: grut_ds
image: [[Pitch.png]]
bounds: [[0,0], [640,1000]]
height: 450px
width: 100%
lat: 320
long: 500
minZoom: -1.5
maxZoom: 18
defaultZoom: -1
zoomDelta: 0.5
darkMode: false
```

```dataview
TABLE WITHOUT ID puller, pullHangTime as "Hang Time (Seconds)"
from "Tournaments"
where (tournament = "Toms")
where (gameID = 1)
where (weStart = "D")
```
