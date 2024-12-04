- accessing distribution parameters is ugly as sin

``` python
E_phot = Poisson('E_phot', 1.5)
lam = E_phot.pspace.distribution.args[0]
```

- sympy has its own Float type, so `lam` needs to be cast 

``` python
# doesnt work
t.full((5, 5), E_phot.pspace.distribution.args[0])
# works
t.full((5, 5), float(E_phot.pspace.distribution.args[0]))
```
