# Model

The simulation is a scent economy on a tile grid, wrapped in a survival loop.

## Grid

64x64 surface, 41x41 underground. Tiles: 0 dirt, 1 grass, 2 pebble, 3 twig, 4 water, 5 thorn, 6 sand, 7 leaf litter.

Movement multipliers: water 0.45, sand 0.70, grass/litter 0.88, else 1.0. Thorns deal 4 damage per second. Water drains stamina.

## Exposure

Standing on dirt, sand, water or thorn with no grass, litter or twig within two tiles raises heat 8 per second. At 100 heat, health drains 5 per second. Shade sheds 14 per second. Open ground is a real cost.

## Scent

Three Float32Arrays, one per colony. Every 0.25 seconds all values decay by 0.93, then each nest emits with strength falling linearly to its radius edge. Garrisons emit at a quarter radius. A tile belongs to the argmax above a floor of 0.06.

Rival nests flood at 3x strength and +5 radius for 26 seconds on a 50-75 second timer, sending three soldiers at the nearest player hill. A hill whose neighbourhood goes two-thirds hostile for seven seconds reverts to its original owner.

## Predators

Each species carries hp, speed, damage, sight, reach, armour, flight and lunge. Attacks are telegraphed by a windup timer, cancelled by a heavy bite and beaten by a dodge with i-frames. Sight is short and per-species, so most of the map is a surprise.

## Progression

Food deposits raise brood levels at 12/30/60/100/150. Each brood adds workers, widens scent radius, and is the only way to afford garrisons, since guards come out of the worker pool.

## Reading

- Grasse, stigmergy and the colony as emergent computation.
- Bonabeau et al., trail-based foraging models.
- Ant-scale geometry: why a lawn is a forest.
