**Battle Royai**
A battle royal for ai

# Introduction
Battle royai is a battle royal playing with 'Robot' likes BB8 in top view. Each client control one BB8 at a time.
A game last around 1 to 5 minutes. The log of the game need to be saved.
## Team
## Context
## Objectif
## But

## Constraint
### Time
12 days

### Language
Python

# Specifications
## Overview
```
[Royai]---------[SRV]-------Websocket---------[client]
```
_Connection to server

```
[Royai]---------------[client]
```
_Learning mode_

## BB8
Controle
- x (-1 - 1)
- y (-1 - 1)
- Fire
- Rotate the canon right
- Rotate the canon left

## Map
- uniform floor
- rock protection
- bonus (bullet + hp)
- map shrinking
- hole 

## Library
- process positions
- process damages
- Return
    - Map center
    - Radius (zone)
    - Radius max
    - Items positions (holes, rocks, bonus)
    - Damages
    - Kills
    - Positions

## Server
Use the library and provide the infos through a websocket. And process inputs

## Websocket
Communication between server and clients
### Messages
- Server info
```json5
{
  own_players: [{
    id: int,
    x: int,
    y: int,
    damages: int,
    score: int,
    teamid: int
  }],
  players: [
    {
      x: int,
      y: int,
      teamid: int
    }
  ],
  map: {
    center: {
      x: int,
      y: int
    },
    radius_zone: int,
    items: [
      {
        type: string,
        position: {x: int, y: int}
      }
    ]
  }
}
```

- client control
```json5
[
  {
    id_player: int,
    type: string,
    data: float
  }
]
```


## Client
### View
Simple web app to show the current state of the game.

### Controle
Manual control using keyboard for human input.

# Tasks
- Library
- Server
- Frontend
- Models


