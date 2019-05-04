Fork of PathFinding.js
------------

Original repo: https://github.com/qiao/PathFinding.js/

This fork adds an option for passing a custom `DiagonalMovement` logic.
It might be useful if you want to display your grid as a hexagonal one and therefore you need to limit some diagonal movements.

Supported for `AStarFinder` only.

```javascript
  const grid = new PF.Grid(matrix);
  const finder = new PF.AStarFinder({
    diagonalMovement: PF.DiagonalMovement.Custom,
    diagFn: node => {
      return {
        d0: node.y % 2 === 0,
        d1: node.y % 2 !== 0,
        d2: node.y % 2 !== 0,
        d3: node.y % 2 === 0,
      };
    }
  });
  return finder.findPath(start.x, start.y, end.x, end.y, grid);
```

Where:

d0: ↖

d1: ↗

d2: ↘

d3: ↙
