# 02 · Selección: if / elif / else

La **selección** permite decidir qué bloque ejecutar según una **condición**.

## Sintaxis
```python
if condicion1:
    # bloque A
elif condicion2:
    # bloque B
else:
    # bloque C
```

## Ejemplo 1: número positivo, negativo o cero
```python
n = int(input("n: "))

if n > 0:
    print("positivo")
elif n < 0:
    print("negativo")
else:
    print("cero")
```

## Ejemplo 2: tarifa simple por tramos
```python
edad = int(input("Edad: "))

if edad < 12:
    tarifa = 1000
elif edad <= 65:
    tarifa = 2000
else:
    tarifa = 1500

print("Tarifa:", tarifa)
```

---

## Ejercicios

### E1. Máximo de dos números
Lee dos números e imprime cuál es **mayor**, o si son **iguales**.

<details>
<summary>Ver solución</summary>

```python
a = float(input("a: "))
b = float(input("b: "))

if a > b:
    print("Mayor: a")
elif b > a:
    print("Mayor: b")
else:
    print("Son iguales")
```
</details>

---

### E2. Par o impar (solo positivos)
Pide un entero positivo e indica si es **par** o **impar** (rechaza no positivos).

<details>
<summary>Ver solución</summary>

```python
n = int(input("n (positivo): "))

if n <= 0:
    print("Debe ser positivo")
elif n % 2 == 0:
    print("par")
else:
    print("impar")
```
</details>

---

### E3. Calculadora mínima
Pide `a`, `b` y una **operación** (`+`, `-`, `*`, `/`) y muestra el resultado; maneja división por cero.

<details>
<summary>Ver solución</summary>

```python
a = float(input("a: "))
b = float(input("b: "))
op = input("Operación (+ - * /): ").strip()

if op == "+":
    print(a + b)
elif op == "-":
    print(a - b)
elif op == "*":
    print(a * b)
elif op == "/":
    if b == 0:
        print("Error: división por cero")
    else:
        print(a / b)
else:
    print("Operación no válida")
```
</details>
