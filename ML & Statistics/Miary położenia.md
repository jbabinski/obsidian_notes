Estymacja (na podstawie danych, próbki) vs miara (pełen obraz, wszystkie dane z populacji)

## Miary
**Średnia arytmetyczna** (mean)

![[Pasted image 20220503174954.png]]

**Średnia ucinana** - pomijamy *p* największych i najmniejszych wartości (np. oceny w sporcie) 

![[Pasted image 20220503201010.png]]

**Średnia ważona** - $w_{i}$ oznacza wagę obserwacji. Używana, kiedy chcemy nadać większe znaczenie części obserwacji

![[Pasted image 20220503201138.png]]

**Mediana**:
- wartość środkowa z posortowanej listy wartości
- **odporny** (**robust**) estymator, bo pozwala pominąć wpływ wartości odstających (**outliers**, extreme cases)

Podobnie jak mediany, żeby osiągnąć odporny estymator, można zastosować średnią z odciętymi np. max i min 10% wartości.

KOD - średnia, średnia ucięta, mediana
```
# Compute the mean, trimmed mean, and median for Population. For `mean` and `median` we can use the _pandas_ methods of the data frame. The trimmed mean requires the `trim_mean` function in _scipy.stats_.

state = pd.read_csv(STATE_CSV)

print(state['Population'].mean())

print(trim_mean(state['Population'], 0.1))

print(state['Population'].median())
```

KOD - średnia ważona 

```
# Weighted mean is available with numpy. For weighted median, we can use the specialised package `wquantiles` (https://pypi.org/project/wquantiles/).

print(state['Murder.Rate'].mean())

print(np.average(state['Murder.Rate'], weights=state['Population']))

print(wquantiles.median(state['Murder.Rate'], weights=state['Population']))
```
