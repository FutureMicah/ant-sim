# The Hole

A browser ant-colony survival game. One ant, one hole, one dead colony.

You forage, you grow a brood, you take ground off two rival colonies, and at the bottom of your own tunnels is the reason the hill was a ruin before you got here.

No build step. No dependencies. Open index.html.

## Pillars

- Survive — sun exposure, water, thorns, wind, rain, and eleven kinds of predator.
- Grow — food becomes brood, brood widens your scent and staffs your borders.
- Conquer — scent is territory; break a rival hill's guard and stand in its hall to take it.
- Rule — garrisons hold ground you cannot babysit. Hold all three hills.
- The twist — the larva at the bottom of the nest faked a queen's pheromone. Its gland is a choice, not a trophy.

## Controls

| Key | Action |
|---|---|
| WASD | move |
| Q / E or mouse | turn |
| Left click | bite |
| Right click | heavy bite (stamina) |
| Shift | dodge (i-frames) |
| R | acid spray |
| Space | sprint |
| F | enter nest / claim hall |
| G | post a garrison |
| V or Tab | toggle third / first person |
| 1 / 2 | final choice |

First person is a raycaster over the same world grid — grass and pebbles occlude, sprites are depth-sorted against a z-buffer.

## Running it

git clone <your-repo-url>
cd the-hole
open index.html

A local server is not required, but pointer lock behaves better over http.

## Systems

- Scent field — three float arrays over the tile grid. Every hill emits, everything decays, each tile belongs to the strongest scent. Rival hills periodically flood theirs and send a squad.
- Terrain — dirt, grass, pebble, twig, water, thorn, sand, leaf litter, each with its own movement, exposure and damage rules.
- Predators — telegraph windups, per-species sight and reach, armour, lunges, flight, and one ambusher that strikes where you were standing.
- Colony — food, brood levels, workers that forage autonomously, garrisons that hold ground.

## Known gaps

- Captured ground is defended by scent alone; the AI never plans a multi-stage assault.
- Both endings are text, with no playable aftermath.
- The raycaster has no verticality — a pebble is a wall as tall as a grass blade.
- Balance is untuned past brood three.

## License

MIT. See LICENSE.
