# Banco de Ejercicios 
**Enfoque:** Secuencia simple, `if/elif/else` (principal) y `for` (ampliado).  
**Formato estilo evaluación:** V/F, alternativas, completar condición/código y predecir salida. **Sin soluciones**.

> Recomendación: ejecuta cada fragmento en tu editor/IDE y valida tu respuesta con `print(...)` y casos de prueba.

---

## Parte A · Secuencia simple (12)
Ejercicios introductorios de entrada → procesamiento → salida. **No usar `if` ni `for`**.

A1. Solicita un nombre y muestra `Hola, <nombre>!`  
A2. Lee dos enteros y muestra su suma.  
A3. Ingresa base y altura de un rectángulo; muestra el área con 2 decimales.  
A4. Convierte °C a °F y muestra con formato `f"{f:,.2f}"`.  
A5. Pide distancia (km) y tiempo (h); muestra velocidad media (km/h).  
A6. Ingresa precio neto y % IVA; muestra precio bruto.  
A7. Pide un número real y muestra su parte entera y su parte decimal.  
A8. Convierte tiempo total en **minutos** a `h` y `min` usando // y %.  
A9. Calcula IMC = peso/(altura^2) y muéstralo con 2 decimales.  
A10. Pide monto en MB y muestra KB y bytes (base 1024).  
A11. Dado un número (ms por frame), aproxima fps = 1000/ms.  
A12. Dado un ángulo en grados, conviértelo a radianes.

---

## Parte B · Selección (if / elif / else) (63)
**Énfasis total en condicionales**, estilo de control/prueba: V/F, alternativas, predecir salida y completar código.

### B1) Verdadero/Falso (10)
Indica V o F sin ejecutar:
B1.1. `==` compara igualdad y `=` asigna.  
B1.2. `!=` es “distinto de”.  
B1.3. `if` ejecuta un bloque cuando la condición es verdadera.  
B1.4. `elif` es “sino si”; se evalúa solo si el `if` falló.  
B1.5. `else` no lleva condición.  
B1.6. En `if x % 2 == 0:`, la condición es verdadera si x es par.  
B1.7. `and` requiere que ambas condiciones sean verdaderas.  
B1.8. `or` requiere al menos una verdadera.  
B1.9. En Python, los bloques se definen por **indentación**.  
B1.10. `if x:` es verdadero si `x != 0` para enteros.

### B2) Alternativas (12)
Marca la correcta.
B2.1. ¿Qué imprime?
```python
x = 5
if x > 0:
    print("A")
else:
    print("B")
```
a) A  b) B  c) Nada  d) Error

B2.2. ¿Cuál condición detecta número **negativo**?  
a) `x > 0`  b) `x == 0`  c) `x < 0`  d) `x <= 0`

B2.3. ¿Qué operador es **división entera**?  
a) `/`  b) `//`  c) `%`  d) `**`

B2.4. Si `x = 6`, ¿qué imprime?
```python
if x % 2 == 0:
    print("Par")
else:
    print("Impar")
```
a) Par  b) Impar  c) Nada  d) Error

B2.5. Para “Niño (<12), Adolescente (12–17), Adulto (>=18)”, ¿qué va primero?  
a) `x >= 18`  b) `x < 12`  c) `x <= 17`  d) `x == 12`

B2.6. Completa para detectar múltiplos de 3: `if ________: print("M3")`  
a) `x // 3 == 0`  b) `x % 3 == 0`  c) `x / 3 == 0`  d) `x * 3 == 0`

B2.7. ¿Qué imprime?
```python
x = 4
if x > 10:
    print("X")
elif x > 5:
    print("Y")
else:
    print("Z")
```
a) X  b) Y  c) Z  d) Nada

B2.8. ¿Qué operador **niega** una condición?  
a) `and`  b) `or`  c) `not`  d) `!=`

B2.9. ¿Qué imprime?
```python
x = 0
if x:
    print("T")
else:
    print("F")
```
a) T  b) F  c) Nada  d) Error

B2.10. Mejor orden para rangos:  
a) `if x >= 0 ... elif x > 10 ...`  
b) `if x > 10 ... elif x >= 0 ...`  
c) Depende del problema  
d) Siempre al revés

B2.11. ¿Cuál detecta **no par**?  
a) `x % 2 == 0`  b) `x % 2 != 0`  c) `x // 2 != 0`  d) `not x`

B2.12. ¿Qué imprime?
```python
x = "hello"
y = "world"
if x == y:
    print("Iguales")
else:
    print("Distintas")
```
a) Iguales  b) Distintas  c) Nada  d) Error

### B3) Predecir salida (15)
Indica **exactamente** qué se imprime.
B3.1.
```python
x = 5
if x > 0:
    if x % 2 == 0:
        print("Naranja")
    else:
        print("Pera")
else:
    print("Manzana")
```
B3.2.
```python
x = 7
if x % 2 == 0:
    print("Día")
else:
    print("Noche")
```
B3.3.
```python
x, y, z = 3, 7, 5
if x < y and y > z:
    if z > x:
        print("x < z < y")
    elif z < x:
        print("z < x < y")
    else:
        print("x == z < y")
else:
    print("No se cumple")
```
B3.4.
```python
n = 0
if n:
    print("A")
else:
    print("B")
```
B3.5.
```python
s = "Python"
if len(s) > 3:
    print("Largo")
else:
    print("Corto")
```
B3.6.
```python
a, b = 10, 10
if a > b:
    print("Mayor")
elif a < b:
    print("Menor")
else:
    print("Iguales")
```
B3.7.
```python
x = -3
if x < 0:
    print("Negativo")
if x % 2 == 0:
    print("Par")
```
B3.8.
```python
x = 12
if x % 3 == 0 and x % 4 == 0:
    print("M12")
elif x % 3 == 0:
    print("M3")
else:
    print("Otro")
```
B3.9.
```python
x = 15
if not (x % 5):
    print("M5")
else:
    print("No M5")
```
B3.10.
```python
x = 9
if x > 10:
    print(">10")
elif x > 5:
    print(">5")
print("Fin")
```
B3.11.
```python
x = 18
if x >= 18:
    print("Adulto")
elif x >= 12:
    print("Adolescente")
else:
    print("Niño")
```
B3.12.
```python
x = 12
if x % 2 == 0:
    if x % 3 == 0:
        print("ParM3")
    else:
        print("Par")
else:
    print("Impar")
```
B3.13.
```python
x = 5
if x < 0:
    print("Negativo")
elif x < 10:
    print("Menor10")
elif x < 20:
    print("Menor20")
```
B3.14.
```python
a = 3
b = 5
if a == 3 or b == 3:
    print("OK")
else:
    print("NO")
```
B3.15.
```python
x = 0
if x < 0:
    print("A")
elif x == 0:
    print("B")
else:
    print("C")
```

### B4) Completar condición/código (14)
Completa `_____` para que cumpla el enunciado.
B4.1. Imprimir “Negativo” si `n` es menor que 0: `if _____: print("Negativo")`  
B4.2. “Par” si divisible por 2, si no “Impar”.  
B4.3. “M3 y M5” si múltiplo de 3 **y** de 5; si no, “Otro”.  
B4.4. Clasificar edad: `<12: Niño`, `12–17: Adolescente`, `>=18: Adulto`.  
B4.5. Dado `nota` (1.0–7.0): `>=6.0 Excelente`, `>=4.0 Aprobado`, otro `Reprobado`.  
B4.6. Si `x` está **en [10, 20]** muestra “Rango”; si no, “Fuera”.  
B4.7. Si `a == b` y `b == c` muestra “Tri-Iso”; si no, “Otro”.  
B4.8. Leer tres números y mostrar el **mayor** (usa if/elif/else).  
B4.9. Indicar si un año es **bisiesto** (simplificado: divisible por 4).  
B4.10. Si `prom >= 5.5` imprime “Beca”, si `prom >= 4.0` “Regular”, si no “Reprobado”.  
B4.11. Dado `x` real, si `x == 0` imprime “Cero”; si `x > 0` “Positivo”; si no “Negativo”.  
B4.12. Si `clave` es “python123” imprime “OK”; si no, “DENEGADO”.  
B4.13. Si `n` en {1,3,5,7,9} muestra “Impar chico”; si en {2,4,6,8} “Par chico”; otro “Otro”.  
B4.14. Lee dos horas (0–23) y di si están en el **mismo turno**: `mañana [6–11]`, `tarde [12–19]`, `noche [20–5]`.

### B5) Programación breve (12)
Escribe un programa para cada enunciado.
B5.1. Lee un entero y muestra si es **positivo, negativo o cero**.  
B5.2. Lee un entero y muestra si es **par o impar**.  
B5.3. Lee dos enteros y muestra **el mayor** o “iguales”.  
B5.4. Lee tres enteros y muestra **el menor**.  
B5.5. Dado un puntaje 0–100, mapea a 1.0–7.0 (lineal) y clasifica “aprobado” si ≥4.0.  
B5.6. Dado un precio y un cupón (`"DESC10"`, `"DESC20"`), aplica 10% o 20%; otro: 0%.  
B5.7. Calcula tarifa según edad: `<12: $1000`, `12–65: $2000`, `>65: $1500`.  
B5.8. Calcula costo de envío: `<1kg: $2.000`, `1–5kg: $4.000`, `>5kg: $7.000`.  
B5.9. Clasifica temperatura (°C): `<0: “Bajo cero”`, `0–30: “Normal”`, `>30: “Calor”`.  
B5.10. Determina tipo de triángulo por lados: equilátero, isósceles, escaleno.  
B5.11. Verifica acceso por **usuario/clave** (valores fijos).  
B5.12. Simula semáforo: lee color (`"rojo"|"amarillo"|"verde"`) y muestra acción.

---

## Parte C · Bucle for (30)
Iteraciones sobre rangos/listas; contadores y acumuladores simples.

### C1) Predecir salida (10)
C1.1.
```python
for i in range(3):
    print(i)
```
C1.2.
```python
for i in range(2, 6):
    print(i, end="-")
```
C1.3.
```python
s = 0
for x in [3, 1, 4]:
    s += x
print(s)
```
C1.4.
```python
for i in range(5, 0, -2):
    print(i)
```
C1.5.
```python
p = 1
for x in [2, 2, 3]:
    p *= x
print(p)
```
C1.6.
```python
out = ""
for c in "ABC":
    out += c.lower()
print(out)
```
C1.7.
```python
cnt = 0
for x in [0, 2, 4, 6]:
    if x % 4 == 0:
        cnt += 1
print(cnt)
```
C1.8.
```python
for i in range(1, 5):
    print(i*i)
```
C1.9.
```python
s = 0
for i in range(1, 6):
    s += i
print(s)
```
C1.10.
```python
for i in range(3):
    for j in range(2):
        print(i, j)
```

### C2) Completar código (10)
Rellena `_____`.
C2.1. Imprimir números del 1 al 10: `for i in _____: print(i)`  
C2.2. Imprimir pares del 2 al 20.  
C2.3. Sumar los números del 1 al 100 y mostrar la suma.  
C2.4. Contar cuántos múltiplos de 3 hay entre 1 y 30.  
C2.5. Construir una cadena `"aaaaa"` con cinco `'a'` usando un `for`.  
C2.6. Mostrar tabla de multiplicar del `n` (1..10).  
C2.7. Calcular el **factorial** de `n` (asume 0 ≤ n ≤ 10).  
C2.8. Dada una lista de enteros, contar cuántos son negativos.  
C2.9. Dada una lista de palabras, concatenarlas separadas por coma.  
C2.10. Dados `m` y `n`, imprimir el rectángulo de `m` filas y `n` columnas de `*`.

### C3) Programación breve (10)
C3.1. Imprime los enteros de **N a 1** (descendente).  
C3.2. Cuenta cuántos enteros en `1..N` son múltiplos de 2 **y** de 5.  
C3.3. Calcula la suma de los **cuadrados** de `1..N`.  
C3.4. Muestra los **divisores** de un entero positivo `n`.  
C3.5. Genera una **progresión aritmética**: inicio `a`, paso `d`, `k` términos.  
C3.6. Lee `k` notas (float) y muestra el **promedio**.  
C3.7. Lee `k` números y muestra el **máximo** (inicializa con `None` o primer valor).  
C3.8. Dibuja un **triángulo** de altura `h` con `*` (ej.: h=3 → `*`, `**`, `***`).  
C3.9. Imprime solo las **consonantes** de un texto (ignora vocales y espacios).  
C3.10. Genera los primeros `N` términos de **Fibonacci** (iterativo).

---

## Cómo practicar
1) Intenta cada ejercicio **sin correr el código** (predicción).  
2) Luego **implementa/prueba** en tu editor.  
3) Crea **variantes** (más casos, límites, entradas inválidas).

**Sugerencia de estilo:** f-strings, indentación de 4 espacios, nombres descriptivos.  
**Python 3.**

---

### Créditos y alcance
Material de práctica basado en los contenidos del curso INFO058 (Secuencias, If/Elif/Else, For). Sin soluciones para promover estudio activo.
