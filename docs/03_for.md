# 03 · Bucle for

El bucle `for` en Python nos sirve para **repetir instrucciones varias veces**.
Imagina que quieres dar 5 aplausos: en vez de escribir `print("👏")` cinco veces, un `for` lo hace por ti automáticamente.

## Sintaxis
```python
for variable in secuencia:
    # bloque
```
- **variable**: toma cada valor de la secuencia (uno por iteración).
- **secuencia**: puede ser una lista, una cadena de texto, un rango `range(...)`, etc.

---

## Ejemplos por tipo

### 1) Iterar con `range(stop)`
- **Ejemplo**: imprimir 3 aplausos
```python
for _ in range(3):
    print("👏")
```
- **Ejemplo**: mostrar índices 0..4
```python
for i in range(5):  # 0,1,2,3,4
    print("i =", i)
```

---

### 2) `range(inicio, fin, paso)`
- **Ejemplo**: cuenta regresiva de 5 a 1
```python
for s in range(5, 0, -1):
    print(s)
print("¡Despegue! 🚀")
```
- **Ejemplo**: números pares entre 2 y 10
```python
for n in range(2, 11, 2):
    print(n)  # 2,4,6,8,10
```

---

### 3) Recorrer listas
- **Ejemplo**: lista de compras
```python
compras = ["pan", "leche", "huevos"]
for item in compras:
    print("Comprar:", item)
```
- **Ejemplo**: promedio de calificaciones
```python
notas = [5.0, 6.3, 4.8, 5.7]
suma = 0
for n in notas:
    suma += n
print("Promedio:", suma/len(notas))
```

---

### 4) Recorrer cadenas (strings)
- **Ejemplo**: deletrear un nombre
```python
nombre = "Ana"
for ch in nombre:
    print(ch)
```
- **Ejemplo**: contar dígitos en un texto
```python
texto = "abc123x9"
cont = 0
for ch in texto:
    if ch.isdigit():
        cont += 1
print("Dígitos:", cont)  # 4
```

---

### 5) `enumerate` (índice + valor)
- **Ejemplo**: numerar pasos de una receta
```python
pasos = ["Precalentar horno", "Mezclar ingredientes", "Hornear 20 min"]
for i, paso in enumerate(pasos, start=1):
    print(f"Paso {i}: {paso}")
```
- **Ejemplo**: revisar posiciones con validación
```python
valores = [10, -3, 25]
for idx, v in enumerate(valores):
    estado = "OK" if v >= 0 else "NEGATIVO"
    print(idx, v, estado)
```

---

### 6) `zip` (iterar en paralelo)
- **Ejemplo**: nombres y teléfonos
```python
nombres = ["Ana", "Luis", "Marta"]
telefonos = ["111", "222", "333"]
for nom, tel in zip(nombres, telefonos):
    print(f"{nom}: {tel}")
```
- **Ejemplo**: suma elemento a elemento de dos listas
```python
a = [1, 2, 3]
b = [10, 20, 30]
c = []
for x, y in zip(a, b):
    c.append(x + y)  # [11, 22, 33]
print(c)
```

---

### 7) Diccionarios (`dict.items()`)
- **Ejemplo**: precios por producto
```python
precios = {"pan": 1200, "leche": 1100, "huevos": 1800}
for producto, precio in precios.items():
    print(f"{producto}: ${precio}")
```
- **Ejemplo**: formatear reporte clave→valor
```python
cfg = {"host": "localhost", "port": 5432}
for k, v in cfg.items():
    print(f"{k} = {v}")
```

---

### 8) `break` y `continue`
- **Ejemplo**: buscar un producto y **parar** al encontrarlo
```python
busco = "leche"
for p in ["pan", "huevos", "leche", "arroz"]:
    if p == busco:
        print("Encontrado:", p)
        break  # detiene el for
```
- **Ejemplo**: saltar negativos y procesar solo no negativos
```python
datos = [5, -2, 0, 7, -6]
for d in datos:
    if d < 0:
        continue  # salta a la siguiente iteración
    print("OK:", d)
```

---

### 9) `for ... else` (el `else` corre si NO hubo `break`)
- **Ejemplo**: buscar cupón válido
```python
cupones = ["CAD-2023", "PROMO10", "OK-2025"]
for c in cupones:
    if c.startswith("OK-"):
        print("Cupón válido:", c)
        break
else:
    print("No se encontró cupón válido")
```
- **Ejemplo**: primalidad muy simple (divisor en 2..n-1)
```python
n = 13
for d in range(2, n):
    if n % d == 0:
        print("Compuesto")
        break
else:
    print("Primo")
```

---

### 10) Bucles anidados
- **Ejemplo**: mini tabla en la pizarra (1 a 3)
```python
for i in range(1, 4):
    for j in range(1, 4):
        print(f"{i}x{j}={i*j}", end="  ")
    print()
```
- **Ejemplo**: imprimir matriz identidad 3x3
```python
n = 3
for i in range(n):
    fila = []
    for j in range(n):
        fila.append(1 if i == j else 0)
    print(fila)
```

---

## Ejercicios (30, dificultad incremental)

> Los primeros 10 son **muy iniciales**. Luego aumenta gradualmente la dificultad.

### E1. Imprime "Hola" 5 veces
<details><summary>Ver solución</summary>

```python
for _ in range(5):
    print("Hola")
```
</details>

---

### E2. Números del 1 al 5
<details><summary>Ver solución</summary>

```python
for n in range(1, 6):
    print(n)
```
</details>

---

### E3. Números del 0 al 4
<details><summary>Ver solución</summary>

```python
for n in range(5):
    print(n)
```
</details>

---

### E4. Pares hasta el 10 (2,4,6,8,10)
<details><summary>Ver solución</summary>

```python
for n in range(2, 11, 2):
    print(n)
```
</details>

---

### E5. Impares del 1 al 9
<details><summary>Ver solución</summary>

```python
for n in range(1, 10, 2):
    print(n)
```
</details>

---

### E6. Recorrer e imprimir una lista simple
Dada `colores = ["rojo","verde","azul"]`, imprímelos uno por línea.
<details><summary>Ver solución</summary>

```python
colores = ["rojo","verde","azul"]
for c in colores:
    print(c)
```
</details>

---

### E7. Recorrer letras de una palabra ingresada
<details><summary>Ver solución</summary>

```python
pal = input("Palabra: ")
for ch in pal:
    print(ch)
```
</details>

---

### E8. Contar elementos de una lista sin `len()`
Dada `nums = [3,7,1,9]`, cuenta cuántos elementos tiene.
<details><summary>Ver solución</summary>

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
<details><summary>Ver solución</summary>

```python
nombre = input("Nombre: ")
n = int(input("Veces: "))
for _ in range(n):
    print(nombre)
```
</details>

---

### E10. Eco de 3 palabras
Lee 3 palabras (una por vez) e imprímelas con el prefijo `"Eco:"`.
<details><summary>Ver solución</summary>

```python
for _ in range(3):
    p = input("Palabra: ")
    print("Eco:", p)
```
</details>

---

### E11. Suma del 1 al 10
<details><summary>Ver solución</summary>

```python
s = 0
for n in range(1, 11):
    s += n
print(s)
```
</details>

---

### E12. Cuadrados del 1 al 5
<details><summary>Ver solución</summary>

```python
for n in range(1, 6):
    print(n**2)
```
</details>

---

### E13. Índice y letra con `enumerate`
Muestra el índice (desde 1) y la letra para el texto ingresado.
<details><summary>Ver solución</summary>

```python
texto = input("Texto: ")
for i, ch in enumerate(texto, 1):
    print(i, ch)
```
</details>

---

### E14. Tabla de multiplicar (n del 1 al 10)
<details><summary>Ver solución</summary>

```python
n = int(input("n: "))
for i in range(1, 11):
    print(f"{n} x {i} = {n*i}")
```
</details>

---

### E15. Suma del 1 al 100
<details><summary>Ver solución</summary>

```python
s = 0
for n in range(1, 101):
    s += n
print(s)
```
</details>

---

### E16. Contar cuántos pares hay entre 1 y 30
<details><summary>Ver solución</summary>

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
<details><summary>Ver solución</summary>

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
<details><summary>Ver solución</summary>

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
<details><summary>Ver solución</summary>

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
<details><summary>Ver solución</summary>

```python
for n in range(10, 0, -1):
    print(n)
```
</details>

---

### E21. Contar palabras por frase
Para cada frase en `["hola mundo","python es genial","me gusta programar"]`, imprime cuántas palabras tiene.
<details><summary>Ver solución</summary>

```python
frases = ["hola mundo", "python es genial", "me gusta programar"]
for f in frases:
    print(len(f.split()))
```
</details>

---

### E22. Promedio de 5 notas
<details><summary>Ver solución</summary>

```python
s = 0
for i in range(5):
    s += float(input(f"Nota {i+1}: "))
print("Promedio:", s/5)
```
</details>

---

### E23. Triángulo de estrellas de tamaño `n`
<details><summary>Ver solución</summary>

```python
n = int(input("n: "))
for i in range(1, n+1):
    print("*" * i)
```
</details>

---

### E24. Producto de todos los números de 1..n
<details><summary>Ver solución</summary>

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
<details><summary>Ver solución</summary>

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
<details><summary>Ver solución</summary>

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
<details><summary>Ver solución</summary>

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
<details><summary>Ver solución</summary>

```python
palabras = input("Frase: ").split()
for i, w in enumerate(palabras, 1):
    print(f"{i}: {w} ({len(w)})")
```
</details>

---

### E29. Combinar listas con `zip` y formar cadenas
Dadas dos listas `nombres = ["Ana","Luis"]` y `edades = [20, 25]`, imprime `"Ana (20)"`, `"Luis (25)"`.
<details><summary>Ver solución</summary>

```python
nombres = ["Ana","Luis"]
edades = [20,25]
for nom, edad in zip(nombres, edades):
    print(f"{nom} ({edad})")
```
</details>

---

### E30. Mini tabla 1..3 (bucles anidados)
Imprime productos `i x j` para `i,j` en 1..3.
<details><summary>Ver solución</summary>

```python
for i in range(1, 4):
    for j in range(1, 4):
        print(f"{i}x{j}={i*j}", end="  ")
    print()
```
</details>
