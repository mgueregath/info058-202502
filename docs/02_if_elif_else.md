# 02 · Selección: if / elif / else

La **selección** permite que el programa **tome decisiones**: se ejecuta un bloque u otro según si se cumple una **condición** lógica.

En otras palabras:  
**"Si ocurre esto → haz esto; si no → haz otra cosa".**

---

## Sintaxis básica

```python
if condicion1:
    # bloque A
elif condicion2:
    # bloque B
else:
    # bloque C
```

- `if`: evalúa la primera condición.
- `elif`: (else if) permite encadenar más condiciones (pueden ser varias).
- `else`: se ejecuta si **ninguna** condición anterior fue verdadera.

---

## Conceptos clave

- Una **condición** es una expresión booleana (resultado `True` o `False`).  
  Ejemplos típicos: `x > 0`, `edad >= 18`, `nota >= 4.0 and nota <= 7.0`.
- Operadores lógicos:
  - `and` → **todas** las condiciones deben ser verdaderas.
  - `or`  → **al menos una** condición debe ser verdadera.
  - `not` → **niega** la condición (cambia `True` ↔ `False`).
- Precedencia común: comparaciones (`<`, `>`, `==`, etc.) → `not` → `and` → `or`. Usa **paréntesis** para dejar clara tu intención.

### Uso de `type()` (diagnóstico rápido)
`input()` devuelve **texto** (`str`). Convierte a número si lo requieres y verifica tipos al depurar:

```python
x = input("Ingresa un número: ")
print(type(x))         # <class 'str'>
n = float(x)
print(type(n))         # <class 'float'>
```

### Anotaciones de tipo (opcional, para claridad)
```python
edad: int = int(input("Edad: "))
if edad >= 18:
    print("Mayor de edad")
```

---

## Ejemplos

### Ejemplo 1: número positivo, negativo o cero
```python
n = int(input("n: "))

if n > 0:
    print("positivo")
elif n < 0:
    print("negativo")
else:
    print("cero")
```

### Ejemplo 2: tarifa simple por tramos
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

### Ejemplo 3: validación de entrada con rangos
```python
nota = float(input("Nota (1.0 a 7.0): "))

if nota < 1 or nota > 7:
    print("Error: fuera de rango")
elif nota >= 4:
    print("Aprobado")
else:
    print("Reprobado")
```

### Ejemplo 4: anidación de condiciones
```python
a = int(input("A: "))
b = int(input("B: "))

if a != 0:
    if b % a == 0:
        print("a divide a b")
    else:
        print("a no divide a b")
else:
    print("No se puede dividir por cero")
```

### Ejemplo 5: combinación `and` / `or`
```python
edad = int(input("Edad: "))

if edad >= 0 and edad < 18:
    print("Menor de edad")
elif 18 <= edad <= 65:
    print("Adulto")
else:
    print("Adulto mayor")
```

> Consejo: cuando tengas **muchas** condiciones, a veces es más claro calcular **banderas** (variables booleanas) antes y luego decidir con ellas.

---

## Ejercicios (45) con **requerimientos detallados**
Para cada ejercicio: primero el **enunciado** (qué debe hacer el programa) y luego una **posible solución**.  
Todos están pensados para practicar **selección** (if / elif / else).

---

### E1. Máximo de dos números
**Requerimiento**: Solicitar al usuario el ingreso de **dos números reales** y determinar cuál es mayor. Si ambos son iguales, indicarlo claramente.
<details><summary>Ver solución</summary>

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
**Requerimiento**: Pedir un **entero positivo**. Si no lo es, mostrar error. Si es válido, indicar si es **par** o **impar**.
<details><summary>Ver solución</summary>

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
**Requerimiento**: Solicitar dos números y una **operación** (`+`, `-`, `*`, `/`). Calcular el resultado. Si se intenta dividir por cero, mostrar mensaje de error.
<details><summary>Ver solución</summary>

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

---

### E4. Año bisiesto
**Requerimiento**: Ingresar un **año** y determinar si es **bisiesto** usando la regla: divisible por 4 y no por 100, salvo que también sea divisible por 400.
<details><summary>Ver solución</summary>

```python
anio = int(input("Año: "))

if (anio % 4 == 0 and anio % 100 != 0) or (anio % 400 == 0):
    print("Bisiesto")
else:
    print("No bisiesto")
```
</details>

---

### E5. Aprobado/Reprobado
**Requerimiento**: Pedir una **nota** entre 1.0 y 7.0. Si `nota ≥ 4.0`, mostrar "Aprobado"; en caso contrario, "Reprobado". Si está fuera de rango, advertir.
<details><summary>Ver solución</summary>

```python
nota = float(input("Nota (1–7): "))

if nota < 1 or nota > 7:
    print("Fuera de rango")
elif nota >= 4.0:
    print("Aprobado")
else:
    print("Reprobado")
```
</details>

---

### E6. Categoría de edad
**Requerimiento**: Pedir la **edad** y clasificar: "Menor de edad" (<18), "Adulto" (18–65), "Adulto mayor" (>65).
<details><summary>Ver solución</summary>

```python
edad = int(input("Edad: "))

if edad < 18:
    print("Menor de edad")
elif edad <= 65:
    print("Adulto")
else:
    print("Adulto mayor")
```
</details>

---

### E7. Signo zodiacal (simplificado)
**Requerimiento**: Ingresar un **mes** (1–12) y mostrar un signo zodiacal **aproximado** asociado al mes. (Ejercicio de práctica de `if`).
<details><summary>Ver solución</summary>

```python
mes = int(input("Mes (1-12): "))

if mes == 1:
    print("Capricornio/Acuario")
elif mes == 2:
    print("Acuario/Piscis")
else:
    print("Otro signo (simplificado)")
```
</details>

---

### E8. Máximo de tres
**Requerimiento**: Solicitar **tres números reales** e informar cuál es el **mayor**.
<details><summary>Ver solución</summary>

```python
a = float(input("a: "))
b = float(input("b: "))
c = float(input("c: "))

if a >= b and a >= c:
    print("Mayor:", a)
elif b >= a and b >= c:
    print("Mayor:", b)
else:
    print("Mayor:", c)
```
</details>

---

### E9. Nota en letras
**Requerimiento**: Ingresar una **calificación** 0–100 y mapear: A (90–100), B (80–89), C (70–79), D (<70).
<details><summary>Ver solución</summary>

```python
nota = int(input("Nota (0–100): "))

if nota >= 90:
    print("A")
elif nota >= 80:
    print("B")
elif nota >= 70:
    print("C")
else:
    print("D")
```
</details>

---

### E10. Dentro de un rango
**Requerimiento**: Pedir un **entero** y verificar si está entre 10 y 20 (inclusive). Indicar "Dentro" o "Fuera".
<details><summary>Ver solución</summary>

```python
n = int(input("n: "))

if 10 <= n <= 20:
    print("Dentro del rango")
else:
    print("Fuera del rango")
```
</details>

---

### E11. Descuento por monto
**Requerimiento**: Dado un **monto**: si `monto ≥ 100000` aplicar 10% de descuento; si `monto ≥ 50000` aplicar 5%; si no, 0%. Mostrar el **descuento** calculado.
<details><summary>Ver solución</summary>

```python
monto = float(input("Monto: "))

if monto >= 100000:
    desc = monto * 0.10
elif monto >= 50000:
    desc = monto * 0.05
else:
    desc = 0.0

print("Descuento:", desc)
```
</details>

---

### E12. Mayoría de edad según país
**Requerimiento**: Leer **país** (`cl` o `usa`) y **edad**. En Chile la mayoría es `≥18`, en USA `≥21`. Indicar si es **mayor** o **menor** de edad según el país.
<details><summary>Ver solución</summary>

```python
pais = input("País (cl/usa): ").lower()
edad = int(input("Edad: "))

if pais == "cl":
    if edad >= 18:
        print("Mayor de edad")
    else:
        print("Menor de edad")
elif pais == "usa":
    if edad >= 21:
        print("Mayor de edad")
    else:
        print("Menor de edad")
else:
    print("País no soportado")
```
</details>

---

### E13. Tipo de triángulo por lados
**Requerimiento**: Ingresar **tres lados**. Si **no** cumplen la desigualdad triangular, advertir. Si cumplen, clasificar: **equilátero**, **isósceles** o **escaleno**.
<details><summary>Ver solución</summary>

```python
a = float(input("Lado a: "))
b = float(input("Lado b: "))
c = float(input("Lado c: "))

if a + b <= c or a + c <= b or b + c <= a:
    print("No forman un triángulo válido")
elif a == b == c:
    print("Equilátero")
elif a == b or b == c or a == c:
    print("Isósceles")
else:
    print("Escaleno")
```
</details>

---

### E14. Validar contraseña
**Requerimiento**: Pedir una **clave** y comprobar si coincide exactamente con `"secreta"`. Mostrar "Acceso concedido" o "Acceso denegado".
<details><summary>Ver solución</summary>

```python
clave = input("Clave: ")

if clave == "secreta":
    print("Acceso concedido")
else:
    print("Acceso denegado")
```
</details>

---

### E15. Calificación con estrellas
**Requerimiento**: Pedir un número entero 1–5. Si está en rango, imprimir la cantidad de **"★"** correspondiente; si no, advertir valor fuera de rango.
<details><summary>Ver solución</summary>

```python
n = int(input("Calificación (1-5): "))

if 1 <= n <= 5:
    print("★" * n)
else:
    print("Valor fuera de rango")
```
</details>

---

### E16. Cambiar mayúscula/minúscula
**Requerimiento**: Solicitar un **carácter**. Si es letra mayúscula, mostrarla en minúscula; si es minúscula, mostrarla en mayúscula; si no es letra, avisar.
<details><summary>Ver solución</summary>

```python
letra = input("Letra: ")

if letra.isupper():
    print(letra.lower())
elif letra.islower():
    print(letra.upper())
else:
    print("No es una letra")
```
</details>

---

### E17. Divisible por 3 y/o 5
**Requerimiento**: Ingresar un entero y decir si es divisible por **3 y 5**, solo por 3, solo por 5, o por ninguno.
<details><summary>Ver solución</summary>

```python
n = int(input("n: "))

if n % 3 == 0 and n % 5 == 0:
    print("Divisible por 3 y 5")
elif n % 3 == 0:
    print("Divisible por 3")
elif n % 5 == 0:
    print("Divisible por 5")
else:
    print("No divisible por 3 ni 5")
```
</details>

---

### E18. Hora válida
**Requerimiento**: Pedir **hora** (0–23) y **minuto** (0–59). Indicar si la combinación representa una hora válida.
<details><summary>Ver solución</summary>

```python
h = int(input("Hora: "))
m = int(input("Minutos: "))

if 0 <= h < 24 and 0 <= m < 60:
    print("Hora válida")
else:
    print("Hora inválida")
```
</details>

---

### E19. IMC con categorías
**Requerimiento**: Calcular **IMC = peso/altura²** y clasificar: <18.5 Bajo peso; [18.5,25) Normal; [25,30) Sobrepeso; ≥30 Obesidad.
<details><summary>Ver solución</summary>

```python
peso = float(input("Peso (kg): "))
altura = float(input("Altura (m): "))
imc = peso / (altura**2)

if imc < 18.5:
    print("Bajo peso")
elif imc < 25:
    print("Normal")
elif imc < 30:
    print("Sobrepeso")
else:
    print("Obesidad")
```
</details>

---

### E20. Tarifa de cine con descuentos
**Requerimiento**: Pedir **edad** y si es **estudiante** (`s/n`). Si es estudiante o menor de 12: tarifa 2000. Si mayor de 65: 1500. Restantes: 3000.
<details><summary>Ver solución</summary>

```python
edad = int(input("Edad: "))
est = input("¿Es estudiante? (s/n): ").lower()

if edad < 12 or est == "s":
    print("Tarifa: 2000")
elif edad > 65:
    print("Tarifa: 1500")
else:
    print("Tarifa: 3000")
```
</details>

---

### E21. Conversión millas ↔ kilómetros (opción)
**Requerimiento**: Pedir al usuario si quiere convertir `"mi→km"` o `"km→mi"`. Luego solicitar el valor y convertir. (1 milla = 1.60934 km). Validar opción.
<details><summary>Ver solución</summary>

```python
op = input("Conversión (mi→km / km→mi): ").strip().lower()
if op == "mi→km" or op == "mi->km":
    mi = float(input("Millas: "))
    km = mi * 1.60934
    print(f"{km:.3f} km")
elif op == "km→mi" or op == "km->mi":
    km = float(input("Kilómetros: "))
    mi = km / 1.60934
    print(f"{mi:.3f} mi")
else:
    print("Opción no válida")
```
</details>

---

### E22. Valor absoluto (sin `abs()`)
**Requerimiento**: Pedir un número real y mostrar su **valor absoluto** usando solo `if` (no usar `abs()`).
<details><summary>Ver solución</summary>

```python
x = float(input("x: "))

if x >= 0:
    print(x)
else:
    print(-x)
```
</details>

---

### E23. Clasificar carácter
**Requerimiento**: Pedir un carácter e indicar si es **vocal**, **consonante**, **dígito** o **otro símbolo**.
<details><summary>Ver solución</summary>

```python
ch = input("Carácter: ")

if ch.isdigit():
    print("Dígito")
elif ch.isalpha():
    if ch.lower() in "aeiou":
        print("Vocal")
    else:
        print("Consonante")
else:
    print("Otro símbolo")
```
</details>

---

### E24. Orden ascendente de tres números (sin sort)
**Requerimiento**: Pedir tres números y mostrarlos en **orden ascendente** usando solo `if/elif/else`.
<details><summary>Ver solución</summary>

```python
a = float(input("a: "))
b = float(input("b: "))
c = float(input("c: "))

# muchas variantes posibles; una simple por casos
if a <= b <= c:
    print(a, b, c)
elif a <= c <= b:
    print(a, c, b)
elif b <= a <= c:
    print(b, a, c)
elif b <= c <= a:
    print(b, c, a)
elif c <= a <= b:
    print(c, a, b)
else:
    print(c, b, a)
```
</details>

---

### E25. Mediana de tres
**Requerimiento**: Pedir tres números y mostrar la **mediana** (el valor que queda al medio al ordenar).
<details><summary>Ver solución</summary>

```python
a = float(input("a: "))
b = float(input("b: "))
c = float(input("c: "))

if (a <= b <= c) or (c <= b <= a):
    print("Mediana:", b)
elif (b <= a <= c) or (c <= a <= b):
    print("Mediana:", a)
else:
    print("Mediana:", c)
```
</details>

---

### E26. Cuadrante cartesiano
**Requerimiento**: Ingresar `x` e `y` (reales) y decir en qué **cuadrante** está el punto. Si está en ejes o en el origen, indicarlo.
<details><summary>Ver solución</summary>

```python
x = float(input("x: "))
y = float(input("y: "))

if x == 0 and y == 0:
    print("Origen")
elif x == 0:
    print("Eje Y")
elif y == 0:
    print("Eje X")
elif x > 0 and y > 0:
    print("I cuadrante")
elif x < 0 and y > 0:
    print("II cuadrante")
elif x < 0 and y < 0:
    print("III cuadrante")
else:
    print("IV cuadrante")
```
</details>

---

### E27. Función a trozos
**Requerimiento**: Dado `x` real, evaluar:
- si `x < 0`: `f(x) = -x`
- si `0 ≤ x ≤ 1`: `f(x) = x**2`
- si `x > 1`: `f(x) = 2*x + 1`
<details><summary>Ver solución</summary>

```python
x = float(input("x: "))

if x < 0:
    fx = -x
elif x <= 1:
    fx = x**2
else:
    fx = 2*x + 1

print(f"f(x) = {fx}")
```
</details>

---

### E28. Clave con requisitos mínimos
**Requerimiento**: Pedir una contraseña y validar: al menos **8** caracteres y contiene **al menos un dígito**. Indicar si cumple o no (simplificado).
<details><summary>Ver solución</summary>

```python
pwd = input("Contraseña: ")
tiene_digito = any(c.isdigit() for c in pwd)

if len(pwd) >= 8 and tiene_digito:
    print("Contraseña válida (reglas mínimas)")
else:
    print("No cumple requisitos")
```
```
</details>

---

### E29. Envío gratis con membresía
**Requerimiento**: Pedir **monto** de compra y si el usuario tiene **membresía** (`s/n`). Envío **gratis** si `monto ≥ 50000` o si tiene membresía. Si no, envío 2990.
<details><summary>Ver solución</summary>

```python
monto = float(input("Monto: "))
mem = input("¿Membresía? (s/n): ").lower()

if monto >= 50000 or mem == "s":
    print("Envío: GRATIS")
else:
    print("Envío: 2990")
```
</details>

---

### E30. Impuesto por tramos (simple)
**Requerimiento**: Dado un **ingreso** mensual, calcular **tasa**:  
`<500k → 0%`, `[500k, 1M) → 5%`, `[1M, 2M) → 10%`, `≥2M → 15%`. Mostrar el **impuesto** a pagar.
<details><summary>Ver solución</summary>

```python
ing = float(input("Ingreso mensual (CLP): "))

if ing < 500_000:
    tasa = 0.0
elif ing < 1_000_000:
    tasa = 0.05
elif ing < 2_000_000:
    tasa = 0.10
else:
    tasa = 0.15

imp = ing * tasa
print(f"Tasa: {tasa*100:.0f}%  Impuesto: {imp:.2f}")
```
</details>

---

### E31. Nota con “+” o “-”
**Requerimiento**: Ingresar un puntaje 0–100 y mostrar letra con sufijo:  
A (≥90), B (80–89), C (70–79), D (<70). Si el **último dígito** es ≥7: agregar `"+"`; si ≤2: agregar `"-"`; si no, sin sufijo.
<details><summary>Ver solución</summary>

```python
p = int(input("Puntaje (0-100): "))

if p >= 90:
    letra = "A"
elif p >= 80:
    letra = "B"
elif p >= 70:
    letra = "C"
else:
    letra = "D"

ultimo = p % 10
if ultimo >= 7:
    suf = "+"
elif ultimo <= 2:
    suf = "-"
else:
    suf = ""

print(letra + suf)
```
</details>

---

### E32. Validar fecha simplificada (no años bisiestos)
**Requerimiento**: Pedir **día**, **mes**, **año**. Verificar si la fecha es válida asumiendo meses con 31: (1,3,5,7,8,10,12); 30: (4,6,9,11); y febrero 28. Indicar válida/ inválida.
<details><summary>Ver solución</summary>

```python
d = int(input("Día: "))
m = int(input("Mes: "))
a = int(input("Año: "))

if m < 1 or m > 12 or d < 1:
    print("Fecha inválida")
elif m in (1,3,5,7,8,10,12) and d <= 31:
    print("Fecha válida")
elif m in (4,6,9,11) and d <= 30:
    print("Fecha válida")
elif m == 2 and d <= 28:
    print("Fecha válida (sin bisiestos)")
else:
    print("Fecha inválida")
```
</details>

---

### E33. Redondeo bancario simplificado
**Requerimiento**: Leer un **real** `x`. Si su parte decimal es `≥ 0.5`, redondear hacia **arriba**; si es `< 0.5`, hacia **abajo**. (No usar `round()`).
<details><summary>Ver solución</summary>

```python
x = float(input("x: "))
ent = int(x)
frac = x - ent

if x >= 0:
    if frac >= 0.5:
        print(ent + 1)
    else:
        print(ent)
else:
    # para negativos, -2.7 → -3 ; -2.4 → -2
    if abs(frac) >= 0.5:
        print(ent - 1)
    else:
        print(ent)
```
</details>

---

### E34. Tres lados: ¿triángulo rectángulo?
**Requerimiento**: Dados tres lados, primero confirmar si forman **triángulo**. Si forman, determinar si es **rectángulo** (Teorema de Pitágoras).
<details><summary>Ver solución</summary>

```python
a = float(input("a: "))
b = float(input("b: "))
c = float(input("c: "))

# ordenar para que c sea el mayor
if a > b and a > c:
    a, c = c, a
elif b > c and b > a:
    b, c = c, b

if a + b <= c:
    print("No es triángulo")
else:
    # Pitágoras (con tolerancia simple)
    if abs((a*a + b*b) - (c*c)) < 1e-9:
        print("Triángulo rectángulo")
    else:
        print("No rectángulo")
```
</details>

---

### E35. Unión de intervalos
**Requerimiento**: Pedir `x` real e indicar si pertenece a la **unión** de intervalos `[0,2] ∪ (3,5)`. Incluir/ excluir extremos según notación.
<details><summary>Ver solución</summary>

```python
x = float(input("x: "))

if (0 <= x <= 2) or (3 < x < 5):
    print("Pertenece")
else:
    print("No pertenece")
```
</details>

---

### E36. Multa por velocidad
**Requerimiento**: Dada **velocidad** `v` y **límite** `L`, calcular mensaje:  
- `v ≤ L`: "OK"  
- `L < v ≤ L+20`: "Infracción leve"  
- `L+20 < v ≤ L+40`: "Infracción grave"  
- `v > L+40`: "Infracción gravísima"
<details><summary>Ver solución</summary>

```python
v = float(input("Velocidad: "))
L = float(input("Límite: "))

if v <= L:
    print("OK")
elif v <= L + 20:
    print("Infracción leve")
elif v <= L + 40:
    print("Infracción grave")
else:
    print("Infracción gravísima")
```
</details>

---

### E37. Precio con cupones
**Requerimiento**: Leer **precio** y **cupón** (`"NONE"`, `"DESC5"`, `"DESC10"`). Aplicar 0%, 5% o 10% de descuento según corresponda. Si el cupón no es válido, advertir.
<details><summary>Ver solución</summary>

```python
precio = float(input("Precio: "))
cupon = input("Cupón (NONE/DESC5/DESC10): ").upper()

if cupon == "NONE":
    total = precio
elif cupon == "DESC5":
    total = precio * 0.95
elif cupon == "DESC10":
    total = precio * 0.90
else:
    print("Cupón no válido")
    total = precio

print(f"Total: {total:.2f}")
```
</details>

---

### E38. Comparar fechas (mismo formato)
**Requerimiento**: Ingresar **dos fechas** (día y mes, mismo año). Indicar cuál ocurre **antes**, o si son **iguales** (no considerar años bisiestos).
<details><summary>Ver solución</summary>

```python
d1 = int(input("Día 1: "))
m1 = int(input("Mes 1: "))
d2 = int(input("Día 2: "))
m2 = int(input("Mes 2: "))

if m1 < m2 or (m1 == m2 and d1 < d2):
    print("Fecha 1 es anterior")
elif m1 == m2 and d1 == d2:
    print("Fechas iguales")
else:
    print("Fecha 2 es anterior")
```
</details>

---

### E39. Aprobación préstamo simplificado
**Requerimiento**: Pedir **ingreso mensual** y **antigüedad laboral** (años). Aprobar si `ingreso ≥ 800k` **y** `antigüedad ≥ 1`. En otro caso, rechazar.
<details><summary>Ver solución</summary>

```python
ing = float(input("Ingreso (CLP): "))
ant = float(input("Antigüedad (años): "))

if ing >= 800_000 and ant >= 1:
    print("Aprobado")
else:
    print("Rechazado")
```
</details>

---

### E40. Juego: piedra, papel o tijera (1 ronda)
**Requerimiento**: Leer jugada del **usuario** (`piedra/papel/tijera`) y de la **máquina** (misma codificación). Mostrar **ganador** o empate. (No validar mayúsculas minúsculas).
<details><summary>Ver solución</summary>

```python
u = input("Tú (piedra/papel/tijera): ").lower()
m = input("Máquina (piedra/papel/tijera): ").lower()

if u == m:
    print("Empate")
elif (u == "piedra" and m == "tijera") or \
     (u == "tijera" and m == "papel") or \
     (u == "papel" and m == "piedra"):
    print("Ganas tú")
else:
    print("Gana la máquina")
```
</details>

---

### E41. Clasificar temperatura ambiente
**Requerimiento**: Dada `t` (°C): `t < 0` → "Congelante"; `0 ≤ t < 15` → "Fría"; `15 ≤ t < 25` → "Agradable"; `25 ≤ t < 35` → "Cálida"; `t ≥ 35` → "Calurosa".
<details><summary>Ver solución</summary>

```python
t = float(input("Temperatura (°C): "))

if t < 0:
    print("Congelante")
elif t < 15:
    print("Fría")
elif t < 25:
    print("Agradable")
elif t < 35:
    print("Cálida")
else:
    print("Calurosa")
```
</details>

---

### E42. Conversión horas a periodo del día
**Requerimiento**: Ingresar **hora** (0–23) y clasificar: `0–5` → "Madrugada", `6–11` → "Mañana", `12–17` → "Tarde", `18–23` → "Noche". Validar rango.
<details><summary>Ver solución</summary>

```python
h = int(input("Hora (0-23): "))

if 0 <= h <= 23:
    if h <= 5:
        print("Madrugada")
    elif h <= 11:
        print("Mañana")
    elif h <= 17:
        print("Tarde")
    else:
        print("Noche")
else:
    print("Hora inválida")
```
</details>

---

### E43. Clasificar texto por longitud
**Requerimiento**: Leer una **frase** y clasificar su longitud: `<10` → "Corta", `10–20` → "Media", `>20` → "Larga".
<details><summary>Ver solución</summary>

```python
txt = input("Frase: ")
n = len(txt)

if n < 10:
    print("Corta")
elif n <= 20:
    print("Media")
else:
    print("Larga")
```
</details>

---

### E44. Clamping de valor a rango
**Requerimiento**: Leer número real `x` y un **rango** `[a, b]` (a ≤ b). Si `x < a`, mostrar `a`; si `x > b`, mostrar `b`; en caso contrario, mostrar `x` (recorte a rango).
<details><summary>Ver solución</summary>

```python
x = float(input("x: "))
a = float(input("a: "))
b = float(input("b: "))

if a > b:
    print("Rango inválido")
elif x < a:
    print(a)
elif x > b:
    print(b)
else:
    print(x)
```
</details>

---

### E45. Tarifa eléctrica por bloques (simplificada)
**Requerimiento**: Leer **consumo kWh** y calcular precio total por bloques:  
- 0–100 kWh: $120/kWh  
- 101–300 kWh: $150/kWh (solo el exceso)  
- >300 kWh: $200/kWh (solo el exceso)  
Mostrar total a pagar.
<details><summary>Ver solución</summary>

```python
kwh = float(input("Consumo (kWh): "))

if kwh <= 0:
    total = 0.0
elif kwh <= 100:
    total = kwh * 120
elif kwh <= 300:
    total = 100 * 120 + (kwh - 100) * 150
else:
    total = 100 * 120 + 200 * 150 + (kwh - 300) * 200

print(f"Total: ${total:.0f}")
```
</details>

---

## Consejos finales
- Revisa el **tipo** con `type(...)` cuando una comparación falle sin explicación.
- Prefiere `elif` a `if` anidados cuando las condiciones son **excluyentes**.
- Usa **paréntesis** en condiciones complejas para mejorar la **legibilidad**.
- Valida **rango** de datos de entrada antes de operar con ellos.
- Piensa primero en **casos borde** (0, extremos, negativos) y pruébalos.

---

> ¿Quieres este material también en **PDF** o como **cuaderno Jupyter (.ipynb)** con celdas ejecutables?

