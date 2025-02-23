# `fiz-rzut-ukosny` — symulacja rzutu ukośnego

### >> [Symulacja rzut ukośny (p5js)](https://editor.p5js.org/heymarcin/sketches/AGeHnNKgP)

## OPIS
Rzut ukośny to przykład ruchu w dwóch wymiarach, gdzie ciało porusza się zarówno w kierunku poziomym (X), jak i pionowym (Y). 
Podstawy fizyczne rzutu ukośnego można zrozumieć, analizując ruch wzdłuż obu tych kierunków niezależnie.

### Założenia:
1. Brak oporu powietrza.
2. Stałe przyspieszenie ziemskie ($g$) działające w dół.

### Kluczowe wielkości / jednostki / parametry symulacji:
- **Prędkość początkowa ($v_0$)** — prędkość, z jaką ciało jest wyrzucane pod kątem do poziomu
    - PARAMETR: `VELOCITY`
    - JEDNOSTKA: [m/s]
- **Kąt wyrzutu ($\theta$)** — kąt między kierunkiem prędkości początkowej a poziomem.
    - PARAMETR: `ANGLE`
    - JEDNOSTKA: [stopnie kątowe]
- **Przyspieszenie ziemskie ($g$)** — stała wartość około 9.81 m/s².
    - PARAMETR: `G`
    - JEDNOSTKA: [m/s²]

> [!TIP]  
> Zwróć uwagę, że równania i trajektoria ruchu 
**NIE ZALEŻĄ od masy obiektu** :scream: (ale tylko przy naszych uproszczonych założeniach)! 
</br>Faktycznie, w przypadku uwzględnienia oporów powietrza równania ruchu obiektu w polu grawitacyjnym zależą od jego masy oraz kształtu :relieved:.

### Ilustracja 
* Wektor Prędkości Początkowej: Strzałka wychodząca z punktu startowego pod kątem $\theta$ do poziomu. 
* Składowa Pozioma Prędkości: Wektor poziomy, oznaczony jako $v_{0x}$.
* Składowa Pionowa Prędkości: Wektor pionowy, oznaczony jako $v_{0y}$.
* Przyspieszenie Ziemskie: Wektor skierowany w dół, oznaczony jako $g$.

<figure>
    <img src="https://upload.wikimedia.org/wikipedia/commons/7/72/Tir_parab%C3%B2lic.png" alt="Rzut ukośny - ilustracja">
    <figcaption>
    <a href="https://pl.wikipedia.org/wiki/Rzut_uko%C5%9Bny_(fizyka)">źródło: Wikipedia - Rzut ukośny</a>
    </figcaption>
</figure>


## Interpretacja fizyczna
Prędkość początkowa może być rozłożona na dwie składowe: poziomą ($v_{0x}$) i pionową ($v_{0y}$).
- $v_{0x} = v_0 \cdot \cos(\theta)$
- $v_{0y} = v_0 \cdot \sin(\theta)$

### Ruch w kierunku poziomym (x):
- **Przyspieszenie**: $a_x = 0$ (brak przyspieszenia poziomego).
- **Prędkość pozioma**: $v_x = v_{0x}$.
- **Przebyta droga pozioma**: $x = v_{0x} \cdot t$.

### Ruch w kierunku pionowym (y):
- **Przyspieszenie**: $a_y = -g$ (przyspieszenie skierowane w dół).
- **Prędkość pionowa**: $v_y = v_{0y} - g \cdot t$.
- **Wysokość (y)**: $y = v_{0y} \cdot t - \frac{1}{2} \cdot g \cdot t^2$.

> [!TIP]  
> Trajektoria Ruchu w rzucie ukośnym jest **parabolą**, co wynika bezpośrednio z powyższego równania ruchu w kierunku pionowym — zależność kwadratowa od czasu ($t$).

### :pushpin: Parabola w matematyce 
W matematyce równanie paraboli to: 
- $y = a \cdot x^2 + b \cdot x + c$

podstawiając: 
- $t$ (czas) w miejsce zmiennej niezależnej $x$,
- $a = -\frac{1}{2} \cdot g$
- $b = v_{0y}$
- $c = 0$

uzyskujemy właśnie równanie ruchu w kierunku pionowym (y) :thumbsup:.


### Równania rzutu ukośnego:
1. **Pozioma składowa ruchu**: $x = v_0 \cdot \cos(\theta) \cdot t$
2. **Pionowa składowa ruchu**: $y = v_0 \cdot \sin(\theta) \cdot t - \frac{1}{2} \cdot g \cdot t^2$

### Zasięg rzutu:
Zasięg ($R$) to maksymalna odległość, na jaką ciało się przemieszcza w kierunku poziomym:
- $R = \frac{v_0^2 \cdot \sin(2\theta)}{g}$

### Maksymalna wysokość:
Maksymalna wysokość ($H$) osiągana przez ciało:
- $H = \frac{v_0^2 \cdot \sin^2(\theta)}{2 \cdot g}$


## ĆWICZENIA / PRZYKŁADY :computer:
Spróbuj przeprowadzić kilka eksperymentów korzystając z [Symulacja rzut ukośny (p5js)](https://editor.p5js.org/heymarcin/sketches/AGeHnNKgP).

### Rzut dyskiem
Czołowi na świecie sportowcy rzucający dyskiem mogą osiągnąć odległość rzutu 64,17-66,76 [m], przy prędkość wypuszczenia 23,88-25,71 m/s, kąt wypuszczenia 32,02°-37,23° [[1]](#1). 
1. Zobacz :eyes:, jak dobrze zgadza się to z symulacją i zastanów się z czego mogą wynikać różnice?
1. Sprawdź jaki wynik mogliby uzyskać na księżycu, gdzie przyśpieszenie grawitacyjne wynosi ~1,625 [m/s²]

### Zasięg i wysokość rzutu :star:
Spróbuj zrozumieć kod symulatora i zmodyfikuj go tak, żeby wyświetlić wartość maksymalnego zasięgu i wysokości rzutu.


## CIEKAWOSTKI :point_right:
* ...

## REFERENCJE
<a id="1" href="https://www.mdpi.com/1660-4601/18/24/13414">[1] Motion Analysis for Jumping Discus Throwing Correction.</a>
