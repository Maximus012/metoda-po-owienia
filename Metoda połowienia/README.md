# Metoda połowienia

## 1. Wprowadzenie
**Metoda połowienia** (również **metoda równego podziału**) jest to jedna z metod rozwiązywania równań. **Metoda połowienia** służy znajdowaniu miejsca zerowego funkcji w podanym przedziale.

### Wymagania:
- Funkcja jest **ciągła** w podanym przedziale (tj. jej wykresem jest ciągła linia).
- Funkcja przyjmuje **różne znaki** na końcu przedziału (tj. funkcja przynajmniej raz przekracza oś X).

## 2. Zasada działania metody połowienia
$f(x)$ – badana funkcja

$[a,b]$ – badany przedział

$\epsilon$ – dokładność szukania (często ograniczona przez możliwości obliczeniowe komputera)

### Przebieg działania algorytmu:
1. Sprawdzenie, czy $c = \frac{a + b}{2}$ jest miejscem zerowym, czyli czy $f(c) = 0$.
   Jeśli tak jest, $c$ jest szukanym rozwiązaniem równania, a algorytm kończy działanie.
2. W przeciwnym wypadku, dopóki nie zostanie osiągnięta żądana dokładność, czyli dopóki $|a - b| > \epsilon$:
    - Przedział $[a,b]$ jest dzielony na dwa mniejsze przedziały: $[a,c]$ i $[c,b]$.
    - Wybierany jest przedział, w którym końce przyjmują różne znaki (zgodnie z wymaganiami algorytmu), tj.
         - Jeśli $f(a)f(c) < 0$, to $b = c$,
         - Jeśli $f(b)f(c) < 0$, to $a = c$.
3. Algorytm jest powtarzany dla nowego przedziału aż do odnalezienia miejsca zerowego lub osiągnięcia żądanej dokładności. Miejsce zerowe wynosi wtedy $\frac{a + b}{2}$.

![Obrazowy przebieg działania algorytmu](https://upload.wikimedia.org/wikipedia/commons/f/f0/Bisektion_Ani.gif)

### Przykład
Znaleźć miejsce zerowe równania $x^3 - 2x^2 + 2x - 4$ w przedziale $[-4,4]$.

#### Kroki działania algorytmu:
1. Sprawdzenie, czy $c = \frac{-4 + 4}{2} = 0$ jest miejscem zerowym:
      - $f(c) = 0^3 - 2 * 0^2 + 2 * 0 - 4 = -4$.
2. $c$ nie jest miejscem zerowym, dlatego przedział jest dzielony na dwie części: $[-4,0]$ i $[0,4]$.
3. Wybranie przedziału, na którego końcach znaki są różne:
     - $f(-4)f(0) = (-108) * (-4) = 432 > 0$ (niespełniony warunek).
     - $f(0)f(4) = (-4) * (36) = -144 < 0$ (spełniony warunek).
4. Algorytm jest ponownie stosowany dla przedziału $[0,4]$:
      - $c = \frac{0 + 4}{2} = 2$.
      - $f(c) = 2^3 - 2 * 2^2 + 2 * 2 - 4 = 0$.
5. $c = 2$ jest szukanym miejscem zerowym.

## 3. Implementacja metody połowienia w Pythonie
