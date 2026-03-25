# Row/Col Sum In One Pass

```java
long[] rowTotals = new long[r];
long[] colTotals = new long[c];
long grandTotal = 0;

for (int i = 0; i < r; i++) {
    for (int j = 0; j < c; j++) {
        rowTotals[i] += grid[i][j];
        colTotals[j] += grid[i][j];
        grandTotal += grid[i][j];
    }
}
```

- [ [ 1, 2, 3], [2, 5, 6] ]

  > rt = [6, 13] </br>
  > ct = [3, 7, 9]
