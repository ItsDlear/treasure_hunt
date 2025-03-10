# Treasure Hunt
A tutorial project for creating a casual game using enterprise patterns

## About the Game

*Diamant/Incan Gold* is a "push-your-luck" type of board game. It is a casual game with simple mechanics and a small number of components.

You can find more information about the game on its [BGG page](https://boardgamegeek.com/boardgame/15512/incan-gold).

The official rulebook can be found [here](https://s3.amazonaws.com/geekdo-files.com/bgg16624?response-content-disposition=inline%3B%20filename%3D%22Diamant_Rules.pdf%22&response-content-type=application%2Fpdf&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAJYFNCT7FKCE4O6TA%2F20250310%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250310T221458Z&X-Amz-SignedHeaders=host&X-Amz-Expires=120&X-Amz-Signature=69ebc8f5f280c5054f8bbebd10658f5fc1829f6d16d85064c6cbdbf99a0f4c3a).

## Matchmaking Requirements

1. The game should have a lobby system.
2. Players must register to participate in a game.
3. Each player should have access to their game history.
4. The system should be able to reproduce any game step by step.
5. To join a specific lobby, a player must enter the lobby code.
6. Players can join any public lobby.
7. All lobbies are public.

## Game Requirements

1. The game consists of multiple rounds.
2. Each round consists of multiple rooms.
3. A round ends when one of the following conditions occurs:
   - All surviving players have retreated, and all other players are dead.
   - A second trap of the same type is revealed.
4. Passing through a room follows these stages:
   - **Room opening**
   - **Player decisions**
   - **Decision resolution**
   - **Round-end check**
5. If a player dies, they lose all treasures they were carrying.
6. If a player retreats, they save all treasures in their chest.
7. When players retreat, they evenly split all remaining treasures from previously opened rooms.
8. There are three types of rooms:
   - **Treasury** – Treasure is split among all participants.
   - **Trap** – If it is the first trap of its type, nothing happens.
   - **Artifact** – Added to the pool of a single retreating player.
9. After each room, the remaining players in the room must vote to continue or retreat.
10. The winner is the player with the highest amount of treasures in their chest at the end of the final round.


## Basic Entities

[Game Entity Diagram](https://app.diagrams.net/#G1n3Qmm5_TNAr4qJunv2p0TMi7zO3t1ne2#%7B%22pageId%22%3A%22bs2XWfqp56Sr83UUAT6_%22%7D)  
