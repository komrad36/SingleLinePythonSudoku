# SingleLinePythonSudoku
Single-line Python Sudoku solver. Reasonably fast (~1 second worst case) and unreasonably tiny.

Input as a flat list of 81 ints. Use 0 for empty cells.

Returns 0 for no solution. For puzzles with multiple possible solutions, returns one of them.

Requires Python 3.8 or above.

```
f=lambda s:s if all(s)else next((x for a,i in min(([(z,i)for z in set(range(10))-set(s[i-i%9:][:9]+s[i%9::9]+sum((s[i-i%27+i%9-i%3+g:][:3]for g in(0,9,18)),[]))]for i in range(81)if s[i]<1),key=lambda x:len(x))if(x:=f(s[:i]+[a]+s[i+1:]))),0)
```

Example input/output:

```
In:
003020600900305001001806400008102900700000008006708200002609500800203009005010300
```

```
Out:
483921657967345821251876493548132976729564138136798245372689514814253769695417382
```
