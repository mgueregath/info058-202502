# 01 · Secuencia simple

Una **secuencia** ejecuta instrucciones **en orden**, de arriba hacia abajo.  
Es el bloque más básico: *lee datos → procesa → muestra resultados*.

## Ejemplo 1: sumar dos números
```python
a = int(input("Ingresa A: "))
b = int(input("Ingresa B: "))
suma = a + b
print("La suma es", suma)
```

## Ejemplo 2: área de un rectángulo
```python
base = float(input("Base: "))
altura = float(input("Altura: "))
area = base * altura
print("Área =", area)
```

---

## Ejercicios

### E1. Conversión de unidades
Pide una cantidad en **pies** y convierte a **metros** (1 pie = 0.3048 m).

<details>
<summary>Ver solución</summary>

```python
pies = float(input("Pies: "))
metros = pies * 0.3048
print("Metros:", metros)
```
</details>

---

### E2. Promedio de tres números
Lee tres números y muestra su promedio (como `float`).

<details>
<summary>Ver solución</summary>

```python
x = float(input("x: "))
y = float(input("y: "))
z = float(input("z: "))
prom = (x + y + z) / 3
print("Promedio:", prom)
```
</details>

---

### E3. Saludo personalizado
Pide el **nombre** de la persona y muestra:  
`"Me alegro de conocerte <nombre>"`.

<details>
<summary>Ver solución</summary>

```python
nombre = input("¿Cuál es tu nombre? ")
print(f"Me alegro de conocerte {nombre}")
```
</details>
