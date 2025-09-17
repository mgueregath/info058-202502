# 03 · Bucle for

El bucle `for` en Python nos sirve para **repetir instrucciones varias veces**.
Imagina que quieres dar 5 aplausos: en vez de escribir `print("👏")` cinco veces, un `for` lo hace por ti automáticamente.

## Sintaxis

```python
for variable in secuencia:
    # bloque
```

* **variable**: toma cada valor de la secuencia (uno por iteración).
* **secuencia**: puede ser una lista, una cadena de texto, un rango `range(...)`, etc.

---

## Ejemplos por tipo

> En cada ejemplo verás primero la **salida esperada** y luego el **código**.

### 1) Iterar con `range(stop)`

* **Ejemplo**: imprimir 3 aplausos

**Salida (ejemplo):**

```text
👏
👏
👏
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
for _ in range(3):
    print("👏")
```

</details>

* **Ejemplo**: mostrar índices 0..4

**Salida (ejemplo):**

```text
i = 0
i = 1
i = 2
i = 3
i = 4
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
for i in range(5):  # 0,1,2,3,4
    print("i =", i)
```

</details>

---

### 2) `range(inicio, fin, paso)`

* **Ejemplo**: cuenta regresiva de 5 a 1

**Salida (ejemplo):**

```text
5
4
3
2
1
¡Despegue! 🚀
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
for s in range(5, 0, -1):
    print(s)
print("¡Despegue! 🚀")
```

</details>

* **Ejemplo**: números pares entre 2 y 10

**Salida (ejemplo):**

```text
2
4
6
8
10
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
for n in range(2, 11, 2):
    print(n)
```

</details>

---

### 3) Recorrer listas

* **Ejemplo**: lista de compras

**Salida (ejemplo):**

```text
Comprar: pan
Comprar: leche
Comprar: huevos
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
compras = ["pan", "leche", "huevos"]
for item in compras:
    print("Comprar:", item)
```

</details>

* **Ejemplo**: promedio de calificaciones

**Salida (ejemplo):**

```text
Promedio: 5.45
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
notas = [5.0, 6.3, 4.8, 5.7]
suma = 0
for n in notas:
    suma += n
print("Promedio:", suma/len(notas))
```

</details>

---

### 4) Recorrer cadenas (strings)

* **Ejemplo**: deletrear un nombre

**Salida (ejemplo):**

```text
A
n
a
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
nombre = "Ana"
for ch in nombre:
    print(ch)
```

</details>

* **Ejemplo**: contar dígitos en un texto

**Salida (ejemplo):**

```text
Dígitos: 4
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
texto = "abc123x9"
cont = 0
for ch in texto:
    if ch.isdigit():
        cont += 1
print("Dígitos:", cont)
```

</details>

---

### 5) `enumerate` (índice + valor)

* **Ejemplo**: numerar pasos de una receta

**Salida (ejemplo):**

```text
Paso 1: Precalentar horno
Paso 2: Mezclar ingredientes
Paso 3: Hornear 20 min
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
pasos = ["Precalentar horno", "Mezclar ingredientes", "Hornear 20 min"]
for i, paso in enumerate(pasos, start=1):
    print(f"Paso {i}: {paso}")
```

</details>

* **Ejemplo**: revisar posiciones con validación

**Salida (ejemplo):**

```text
0 10 OK
1 -3 NEGATIVO
2 25 OK
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
valores = [10, -3, 25]
for idx, v in enumerate(valores):
    estado = "OK" if v >= 0 else "NEGATIVO"
    print(idx, v, estado)
```

</details>

---

### 6) `zip` (iterar en paralelo)

* **Ejemplo**: nombres y teléfonos

**Salida (ejemplo):**

```text
Ana: 111
Luis: 222
Marta: 333
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
nombres = ["Ana", "Luis", "Marta"]
telefonos = ["111", "222", "333"]
for nom, tel in zip(nombres, telefonos):
    print(f"{nom}: {tel}")
```

</details>

* **Ejemplo**: suma elemento a elemento de dos listas

**Salida (ejemplo):**

```text
[11, 22, 33]
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
a = [1, 2, 3]
b = [10, 20, 30]
c = []
for x, y in zip(a, b):
    c.append(x + y)
print(c)
```

</details>

---

### 7) Diccionarios (`dict.items()`)

* **Ejemplo**: precios por producto

**Salida (ejemplo):**

```text
pan: $1200
leche: $1100
huevos: $1800
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
precios = {"pan": 1200, "leche": 1100, "huevos": 1800}
for producto, precio in precios.items():
    print(f"{producto}: ${precio}")
```

</details>

* **Ejemplo**: formatear reporte clave→valor

**Salida (ejemplo):**

```text
host = localhost
port = 5432
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
cfg = {"host": "localhost", "port": 5432}
for k, v in cfg.items():
    print(f"{k} = {v}")
```

</details>

---

### 8) `break` y `continue`

* **Ejemplo**: buscar un producto y **parar** al encontrarlo

**Salida (ejemplo):**

```text
Encontrado: leche
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
busco = "leche"
for p in ["pan", "huevos", "leche", "arroz"]:
    if p == busco:
        print("Encontrado:", p)
        break
```

</details>

* **Ejemplo**: saltar negativos y procesar solo no negativos

**Salida (ejemplo):**

```text
OK: 5
OK: 0
OK: 7
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
datos = [5, -2, 0, 7, -6]
for d in datos:
    if d < 0:
        continue
    print("OK:", d)
```

</details>

---

### 9) `for ... else` (el `else` corre si NO hubo `break`)

* **Ejemplo**: buscar cupón válido

**Salida (ejemplo):**

```text
Cupón válido: OK-2025
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
cupones = ["CAD-2023", "PROMO10", "OK-2025"]
for c in cupones:
    if c.startswith("OK-"):
        print("Cupón válido:", c)
        break
else:
    print("No se encontró cupón válido")
```

</details>

* **Ejemplo**: primalidad muy simple (divisor en 2..n-1)

**Salida (ejemplo):**

```text
Primo
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
n = 13
for d in range(2, n):
    if n % d == 0:
        print("Compuesto")
        break
else:
    print("Primo")
```

</details>

---

### 10) Bucles anidados

* **Ejemplo**: mini tabla en la pizarra (1 a 3)

**Salida (ejemplo):**

```text
1x1=1  1x2=2  1x3=3  
2x1=2  2x2=4  2x3=6  
3x1=3  3x2=6  3x3=9  
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
for i in range(1, 4):
    for j in range(1, 4):
        print(f"{i}x{j}={i*j}", end="  ")
    print()
```

</details>

* **Ejemplo**: imprimir matriz identidad 3x3

**Salida (ejemplo):**

```text
[1, 0, 0]
[0, 1, 0]
[0, 0, 1]
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
n = 3
for i in range(n):
    fila = []
    for j in range(n):
        fila.append(1 if i == j else 0)
    print(fila)
```

</details>

---

## Ejercicios (30, dificultad incremental)

> Para los que **requieren entrada**, incluimos una **ejecución de ejemplo** con datos de muestra.

### E1. Imprime "Hola" 5 veces

**Salida (ejemplo):**

```text
Hola
Hola
Hola
Hola
Hola
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
for _ in range(5):
    print("Hola")
```

</details>

---

### E2. Números del 1 al 5

**Salida (ejemplo):**

```text
1
2
3
4
5
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
for n in range(1, 6):
    print(n)
```

</details>

---

### E3. Números del 0 al 4

**Salida (ejemplo):**

```text
0
1
2
3
4
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
for n in range(5):
    print(n)
```

</details>

---

### E4. Pares hasta el 10 (2,4,6,8,10)

**Salida (ejemplo):**

```text
2
4
6
8
10
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
for n in range(2, 11, 2):
    print(n)
```

</details>

---

### E5. Impares del 1 al 9

**Salida (ejemplo):**

```text
1
3
5
7
9
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
for n in range(1, 10, 2):
    print(n)
```

</details>

---

### E6. Recorrer e imprimir una lista simple

**Salida (ejemplo):**

```text
rojo
verde
azul
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
colores = ["rojo","verde","azul"]
for c in colores:
    print(c)
```

</details>

---

### E7. Recorrer letras de una palabra ingresada

**Ejecución (ejemplo):**

```text
Palabra: Hola
H
o
l
a
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
pal = input("Palabra: ")
for ch in pal:
    print(ch)
```

</details>

---

### E8. Contar elementos de una lista sin `len()`

**Salida (ejemplo):**

```text
4
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
nums = [3,7,1,9]
cont = 0
for _ in nums:
    cont += 1
print(cont)
```

</details>

---

### E9. Repetir un nombre `n` veces

**Ejecución (ejemplo):**

```text
Nombre: Ana
Veces: 3
Ana
Ana
Ana
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
nombre = input("Nombre: ")
n = int(input("Veces: "))
for _ in range(n):
    print(nombre)
```

</details>

---

### E10. Eco de 3 palabras

**Ejecución (ejemplo):**

```text
Palabra: hola
Eco: hola
Palabra: mundo
Eco: mundo
Palabra: python
Eco: python
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
for _ in range(3):
    p = input("Palabra: ")
    print("Eco:", p)
```

</details>

---

### E11. Suma del 1 al 10

**Salida (ejemplo):**

```text
55
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
s = 0
for n in range(1, 11):
    s += n
print(s)
```

</details>

---

### E12. Cuadrados del 1 al 5

**Salida (ejemplo):**

```text
1
4
9
16
25
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
for n in range(1, 6):
    print(n**2)
```

</details>

---

### E13. Índice y letra con `enumerate`

**Ejecución (ejemplo):**

```text
Texto: Sol
1 S
2 o
3 l
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
texto = input("Texto: ")
for i, ch in enumerate(texto, 1):
    print(i, ch)
```

</details>

---

### E14. Tabla de multiplicar (n del 1 al 10)

**Ejecución (ejemplo):**

```text
n: 3
3 x 1 = 3
3 x 2 = 6
...
3 x 10 = 30
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
n = int(input("n: "))
for i in range(1, 11):
    print(f"{n} x {i} = {n*i}")
```

</details>

---

### E15. Suma del 1 al 100

**Salida (ejemplo):**

```text
5050
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
s = 0
for n in range(1, 101):
    s += n
print(s)
```

</details>

---

### E16. Contar cuántos pares hay entre 1 y 30

**Salida (ejemplo):**

```text
15
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
cont = 0
for n in range(1, 31):
    if n % 2 == 0:
        cont += 1
print(cont)
```

</details>

---

### E17. Contar espacios en un texto

**Ejecución (ejemplo):**

```text
Texto: hola mundo python
2
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
t = input("Texto: ")
esp = 0
for ch in t:
    if ch == " ":
        esp += 1
print(esp)
```

</details>

---

### E18. Solo vocales del texto ingresado

**Ejecución (ejemplo):**

```text
Texto: Programar es divertido
oaaeiuieo
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
t = input("Texto: ")
v = "aeiouáéíóúAEIOUÁÉÍÓÚ"
for ch in t:
    if ch in v:
        print(ch, end="")
print()
```

</details>

---

### E19. Contar vocales en el texto

**Ejecución (ejemplo):**

```text
Texto: Python
1
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
t = input("Texto: ")
v = "aeiouAEIOUáéíóúÁÉÍÓÚ"
cnt = 0
for ch in t:
    if ch in v:
        cnt += 1
print(cnt)
```

</details>

---

### E20. Descendente 10..1

**Salida (ejemplo):**

```text
10
9
8
7
6
5
4
3
2
1
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
for n in range(10, 0, -1):
    print(n)
```

</details>

---

### E21. Contar palabras por frase

**Salida (ejemplo):**

```text
2
3
3
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
frases = ["hola mundo", "python es genial", "me gusta programar"]
for f in frases:
    print(len(f.split()))
```

</details>

---

### E22. Promedio de 5 notas

**Ejecución (ejemplo):**

```text
Nota 1: 5
Nota 2: 6
Nota 3: 4
Nota 4: 7
Nota 5: 6
Promedio: 5.6
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
s = 0
for i in range(5):
    s += float(input(f"Nota {i+1}: "))
print("Promedio:", s/5)
```

</details>

---

### E23. Triángulo de estrellas de tamaño `n`

**Ejecución (ejemplo):**

```text
n: 4
*
**
***
****
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
n = int(input("n: "))
for i in range(1, n+1):
    print("*" * i)
```

</details>

---

### E24. Producto de todos los números de 1..n

**Ejecución (ejemplo):**

```text
n: 5
120
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
n = int(input("n: "))
prod = 1
for i in range(1, n+1):
    prod *= i
print(prod)
```

</details>

---

### E25. Suma hasta que se lea un 0 (usa `break`)

**Ejecución (ejemplo):**

```text
Número (0 para terminar): 3
Número (0 para terminar): 5
Número (0 para terminar): 0
Suma: 8
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
suma = 0
for _ in range(10**6):  # límite alto para permitir muchos ingresos
    x = int(input("Número (0 para terminar): "))
    if x == 0:
        break
    suma += x
print("Suma:", suma)
```

</details>

---

### E26. Máximo en una lista sin usar `max()`

**Salida (ejemplo):**

```text
9
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
valores = [3, 7, 2, 9, 5]
mx = valores[0]
for v in valores[1:]:
    if v > mx:
        mx = v
print(mx)
```

</details>

---

### E27. Palíndromo (igual al revés) usando `for`

**Ejecución (ejemplo):**

```text
Texto: radar
Es palíndromo
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
s = input("Texto: ")
inv = ""
for ch in s:
    inv = ch + inv
print("Es palíndromo" if s == inv else "No es palíndromo")
```

</details>

---

### E28. Contar letras por cada palabra (usa `enumerate`)

**Ejecución (ejemplo):**

```text
Frase: hola mundo
1: hola (4)
2: mundo (5)
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
palabras = input("Frase: ").split()
for i, w in enumerate(palabras, 1):
    print(f"{i}: {w} ({len(w)})")
```

</details>

---

### E29. Combinar listas con `zip` y formar cadenas

**Salida (ejemplo):**

```text
Ana (20)
Luis (25)
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
nombres = ["Ana","Luis"]
edades = [20,25]
for nom, edad in zip(nombres, edades):
    print(f"{nom} ({edad})")
```

</details>

---

### E30. Mini tabla 1..3 (bucles anidados)

**Salida (ejemplo):**

```text
1x1=1  1x2=2  1x3=3  
2x1=2  2x2=4  2x3=6  
3x1=3  3x2=6  3x3=9  
```

**Código:**

<details><summary><strong>Ver código</strong></summary>

```python
for i in range(1, 4):
    for j in range(1, 4):
        print(f"{i}x{j}={i*j}", end="  ")
    print()
```

</details>