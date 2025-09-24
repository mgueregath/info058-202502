# 01 · Secuencia simple

Una **secuencia** ejecuta instrucciones **en orden**, de arriba hacia abajo. Es el bloque más básico de un programa:

**leer datos → procesar → mostrar resultados**.

---

## Ideas clave (express)
- **Entrada**: `input()` siempre devuelve **texto** (`str`). Si necesitas números, **convierte**: `int(...)`, `float(...)`.
- **Procesamiento**: realiza operaciones aritméticas, fórmulas, reglas de tres, etc.
- **Salida**: `print(...)`. Usa f-strings para formato: `print(f"Área = {area:.2f} m²")`.
- **Operadores**: `+ - * / // % **`. Precedencia: `**` → `* / // %` → `+ -`. Si dudas, **usa paréntesis**.
- **Redondeo y formato**: `round(x, 2)` o `f"{x:.2f}"`.
- **Errores frecuentes**:
  - Olvidar **convertir** el `input` a número.
  - Esperar decimales usando división entera `//`.
  - Escribir coma `,` como separador decimal (en Python se usa **punto**).

---

## Tipos y `type()` (muy importante)
En secuencia trabajamos con **datos**: números, texto, booleanos. Python es **dinámico**, pero conviene saber **qué tipo** tenemos:

```python
x = input("Edad: ")
print(type(x))     # <class 'str'>  ← input retorna texto
y = int(x)
print(type(y))     # <class 'int'>
z = float("3.14")
print(type(z))     # <class 'float'>
s = "hola"
print(type(s))     # <class 'str'>
```

- `type(obj)` **muestra el tipo** en tiempo de ejecución.
- Úsalo para **diagnosticar**: si una operación falla, imprime `type(...)` de tus variables.

### Anotaciones de tipo (opcional)
Puedes **anotar** el tipo esperado (ayuda a leer y a usar linters):

```python
a: int = int(input("A: "))
b: int = int(input("B: "))
suma: int = a + b
print(suma)
```

> Las **anotaciones** no cambian la ejecución, pero clarifican intenciones y ayudan a herramientas como `mypy` o el IDE.

---

## Ejemplos antes de los ejercicios

### Ejemplo A: concatenación vs suma
```python
x = input("Ingresa 2 y luego 3: ")
y = input("Ingresa 3: ")
print("Concatenación:", x + y)      # "23"
print("Suma:", int(x) + int(y))     # 5
```

### Ejemplo B: formato de salida con f-strings
```python
pi = 3.141592653589793
r = 2.5
area = pi * r * r
print(f"Área con 2 decimales = {area:.2f}")
```

### Ejemplo C: precedencia y paréntesis
```python
print(2 + 3 * 4)      # 14 (primero multiplicación)
print((2 + 3) * 4)    # 20 (forzamos suma primero)
```

### Ejemplo D: `type()` para depurar
```python
valor = input("Número: ")
print(type(valor))     # str
valor_num = float(valor)
print(type(valor_num)) # float
```

### Ejemplo E: casting seguro (simple)
```python
texto = "42"
num = int(texto)       # ok
decimal = float("4.20")# ok
```

---

## Ejemplos guiados (base)

### Ejemplo 1: sumar dos números
```python
a = int(input("Ingresa A: "))
b = int(input("Ingresa B: "))
suma = a + b
print("La suma es", suma)
```

### Ejemplo 2: área de un rectángulo
```python
base = float(input("Base: "))
altura = float(input("Altura: "))
area = base * altura
print("Área =", area)
```

---

## Ejercicios (40). Solo **secuencia** (sin `if`/`for`).  
Para cada uno, se incluye un **enunciado claro** y una **posible solución**.

> Sugerencia: cuando el resultado sea decimal, muestra 2–3 decimales con `f"{x:.2f}"`.

---

### E1. Conversión de unidades
**Enunciado**: Solicita al usuario una longitud en **pies** y **muestra el equivalente en metros** (1 pie = 0.3048 m).
<details><summary>Ver solución</summary>

```python
pies = float(input("Pies: "))
metros = pies * 0.3048
print("Metros:", metros)
```
</details>

---

### E2. Promedio de tres números
**Enunciado**: Pide **tres números** reales y **calcula el promedio** (`float`).
<details><summary>Ver solución</summary>

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
**Enunciado**: Pide el **nombre** de la persona y **muestra** `Me alegro de conocerte <nombre>`.
<details><summary>Ver solución</summary>

```python
nombre = input("¿Cuál es tu nombre? ")
print(f"Me alegro de conocerte {nombre}")
```
</details>

---

### E4. Celsius → Fahrenheit
**Enunciado**: Solicita una temperatura en **°C** y **convierte** a **°F** usando `F = C * 9/5 + 32`.
<details><summary>Ver solución</summary>

```python
c = float(input("°C: "))
f = c * 9/5 + 32
print(f"°F = {f:.2f}")
```
</details>

---

### E5. Perímetro y área de un círculo
**Enunciado**: Pide el **radio** y **calcula** el **perímetro** y el **área** del círculo.
<details><summary>Ver solución</summary>

```python
pi = 3.141592653589793
r = float(input("Radio: "))
per = 2 * pi * r
area = pi * r * r
print(f"Perímetro={per:.3f}  Área={area:.3f}")
```
</details>

---

### E6. km/h → m/s
**Enunciado**: Lee una **velocidad en km/h** y **convierte** a **m/s** (`* 1000/3600`).
<details><summary>Ver solución</summary>

```python
kmh = float(input("Velocidad (km/h): "))  # type: float
ms = kmh * (1000/3600)
print(f"{ms:.3f} m/s")
```
</details>

---

### E7. Regla de tres simple (directa)
**Enunciado**: Dado que **a** corresponde a **b**, solicita **a**, **b** y un nuevo **c**, y **calcula** a cuánto corresponde **c** por proporcionalidad directa.
<details><summary>Ver solución</summary>

```python
a = float(input("a: "))
b = float(input("b: "))
c = float(input("c: "))
x = (b * c) / a
print("Resultado:", x)
```
</details>

---

### E8. IMC
**Enunciado**: Pide **peso (kg)** y **altura (m)** y **calcula** el **IMC = peso / altura²**.
<details><summary>Ver solución</summary>

```python
peso = float(input("Peso (kg): "))
altura = float(input("Altura (m): "))
imc = peso / (altura ** 2)
print(f"IMC = {imc:.2f}")
```
</details>

---

### E9. Descuento
**Enunciado**: Pide un **precio** y un **% de descuento** y **muestra** el **total final**.
<details><summary>Ver solución</summary>

```python
precio = float(input("Precio: "))
desc = float(input("% descuento: "))
final = precio * (1 - desc/100)
print(f"Total: {final:.2f}")
```
</details>

---

### E10. Minutos → h y min
**Enunciado**: Solicita un **entero** con el total de **minutos** y **muestra** cuántas **horas** y **minutos** representan.
<details><summary>Ver solución</summary>

```python
mins = int(input("Minutos: "))
h = mins // 60
m = mins % 60
print(f"{h} h {m} min")
```
```
</details>

---

### E11. Interés simple
**Enunciado**: Ingresa **capital inicial (P)**, **tasa anual r (%)** y **tiempo t (años)**. **Calcula** `M = P*(1+r*t)`.
<details><summary>Ver solución</summary>

```python
P = float(input("Principal: "))
r = float(input("Tasa anual (%): ")) / 100
t = float(input("Tiempo (años): "))
M = P * (1 + r * t)
print(f"Monto: {M:.2f}")
```
</details>

---

### E12. Promedio ponderado
**Enunciado**: Solicita **3 notas** con sus **pesos** y **calcula** el **promedio ponderado**.
<details><summary>Ver solución</summary>

```python
n1 = float(input("Nota 1: ")); p1 = float(input("Peso 1: "))
n2 = float(input("Nota 2: ")); p2 = float(input("Peso 2: "))
n3 = float(input("Nota 3: ")); p3 = float(input("Peso 3: "))
prom = (n1*p1 + n2*p2 + n3*p3) / (p1+p2+p3)
print(f"Promedio: {prom:.2f}")
```
</details>

---

### E13. Hipotenusa
**Enunciado**: Pide los **catetos a y b** de un triángulo rectángulo y **calcula** la **hipotenusa** `h = sqrt(a^2 + b^2)`.
<details><summary>Ver solución</summary>

```python
a = float(input("Cateto a: "))
b = float(input("Cateto b: "))
h = (a*a + b*b) ** 0.5
print(f"Hipotenusa: {h:.3f}")
```
</details>

---

### E14. Segundos → h:m:s
**Enunciado**: Solicita un tiempo en **segundos** y **convierte** a formato **horas:minutos:segundos**.
<details><summary>Ver solución</summary>

```python
s = int(input("Segundos: "))
h = s // 3600
s = s % 3600
m = s // 60
s = s % 60
print(f"{h}:{m}:{s}")
```
</details>

---

### E15. Neto → Bruto (IVA)
**Enunciado**: Pide un **neto** y un **% de IVA**, y **calcula** el **bruto**.
<details><summary>Ver solución</summary>

```python
neto = float(input("Neto: "))
iva = float(input("% IVA: ")) / 100
bruto = neto * (1 + iva)
print(f"Bruto: {bruto:.2f}")
```
</details>

---

### E16. USD → CLP
**Enunciado**: Solicita un monto en **USD** y una **tasa de cambio** (CLP por USD) y **convierte** a **CLP**.
<details><summary>Ver solución</summary>

```python
usd = float(input("USD: "))
tasa = float(input("CLP por USD: "))
clp = usd * tasa
print(f"CLP: {clp:.2f}")
```
</details>

---

### E17. Distancia (MRU)
**Enunciado**: Pide **velocidad (m/s)** y **tiempo (s)** y **calcula** la **distancia** `d = v * t`.
<details><summary>Ver solución</summary>

```python
v = float(input("Vel (m/s): "))
t = float(input("Tiempo (s): "))
d = v * t
print(f"Distancia: {d:.2f} m")
```
</details>

---

### E18. Grados → radianes
**Enunciado**: Ingresa un ángulo en **grados** y **convierte** a **radianes**.
<details><summary>Ver solución</summary>

```python
pi = 3.141592653589793
deg = float(input("Grados: "))
rad = deg * pi / 180
print(f"Radianes: {rad:.6f}")
```
</details>

---

### E19. Media geométrica
**Enunciado**: Solicita **a** y **b** (≥ 0) y **calcula** la **media geométrica** `g = sqrt(a*b)`.
<details><summary>Ver solución</summary>

```python
a = float(input("a: "))
b = float(input("b: "))
g = (a*b) ** 0.5
print(f"Media geométrica: {g:.4f}")
```
</details>

---

### E20. MB → KB → bytes
**Enunciado**: Pide un tamaño en **MB** y **muestra** su equivalente en **KB** y **bytes** (base 1024).
<details><summary>Ver solución</summary>

```python
mb = float(input("MB: "))
kb = mb * 1024
bytes_ = kb * 1024
print(f"{kb:.2f} KB  |  {bytes_:.0f} bytes")
```
</details>

---

### E21. Energía potencial
**Enunciado**: Pide **masa (kg)** y **altura (m)** y **calcula** la **energía potencial** `E = m*g*h` (usa `g = 9.81`).
<details><summary>Ver solución</summary>

```python
m = float(input("Masa (kg): "))
h = float(input("Altura (m): "))
g = 9.81
E = m * g * h
print(f"E = {E:.2f} J")
```
</details>

---

### E22. Precio unitario
**Enunciado**: Solicita un **total** y una **cantidad**, y **calcula** el **precio por unidad**.
<details><summary>Ver solución</summary>

```python
total = float(input("Total: "))
cant = float(input("Cantidad: "))
pu = total / cant
print(f"Precio unitario: {pu:.3f}")
```
</details>

---

### E23. Escala 0–100 → 1–7
**Enunciado**: Lee una **nota en 0–100** y **mapea linealmente** a la **escala 1.0–7.0** (0→1.0, 100→7.0).
<details><summary>Ver solución</summary>

```python
raw = float(input("Nota (0-100): "))
nota = 1.0 + (raw/100)*(7.0-1.0)
print(f"Escala 1-7: {nota:.2f}")
```
</details>

---

### E24. Promedio armónico
**Enunciado**: Pide **a**, **b** y **c** y **calcula** el **promedio armónico** `H = 3 / (1/a + 1/b + 1/c)`.
<details><summary>Ver solución</summary>

```python
a = float(input("a: "))
b = float(input("b: "))
c = float(input("c: "))
H = 3 / (1/a + 1/b + 1/c)
print(f"H = {H:.4f}")
```
</details>

---

### E25. Decimal grados → DMS
**Enunciado**: Solicita **grados decimales** (positivos o negativos) y **convierte** a **grados-minutos-segundos (DMS)**.
<details><summary>Ver solución</summary>

```python
x = float(input("Grados decimales: "))
s = -1 if x < 0 else 1
x = abs(x)
d = int(x)
m_float = (x - d) * 60
m = int(m_float)
s2 = (m_float - m) * 60
print(f"{'-' if s<0 else ''}{d}° {m}' {s2:.2f}\"")
```
</details>

---

### E26. Billetes
**Enunciado**: Pide un **monto en CLP** y **descompón** en billetes de **20k**, **10k**, **5k** y **2k**; **muestra** también el **resto**.
<details><summary>Ver solución</summary>

```python
m = int(input("Monto CLP: "))
b20000 = m // 20000; m %= 20000
b10000 = m // 10000; m %= 10000
b5000  = m // 5000;  m %= 5000
b2000  = m // 2000;  m %= 2000
print(b20000, b10000, b5000, b2000, "resto:", m)
```
</details>

---

### E27. Velocidad media con tramos
**Enunciado**: Ingresa **dos tramos** con distancia y tiempo (en las mismas unidades) y **calcula** la **velocidad media total**.
<details><summary>Ver solución</summary>

```python
d1 = float(input("d1 (km): "))
t1 = float(input("t1 (h): "))
d2 = float(input("d2 (km): "))
t2 = float(input("t2 (h): "))
vm = (d1 + d2) / (t1 + t2)
print(f"Vel media: {vm:.2f} km/h")
```
</details>

---

### E28. hp → kW
**Enunciado**: Pide **potencia en hp** y **convierte** a **kW** (usa 1 hp ≈ 0.7457 kW).
<details><summary>Ver solución</summary>

```python
hp = float(input("hp: "))
kw = hp * 0.7457
print(f"{kw:.3f} kW")
```
</details>

---

### E29. Mezcla de soluciones
**Enunciado**: Ingresa **volumen y concentración (%)** de **dos soluciones** y **calcula** la **concentración final** de la mezcla.
<details><summary>Ver solución</summary>

```python
V1 = float(input("V1 (L): "))
C1 = float(input("C1 (%): "))
V2 = float(input("V2 (L): "))
C2 = float(input("C2 (%): "))
C = (V1*C1 + V2*C2) / (V1 + V2)
print(f"Concentración final: {C:.2f}%")
```
</details>

---

### E30. PPU comparativo
**Enunciado**: Pide **precio** y **gramos** de **dos productos** y **muestra** el **precio por 100 g** de cada uno.
<details><summary>Ver solución</summary>

```python
p1 = float(input("Precio 1: "))
g1 = float(input("Gramos 1: "))
p2 = float(input("Precio 2: "))
g2 = float(input("Gramos 2: "))
ppu1 = p1 / g1 * 100
ppu2 = p2 / g2 * 100
print(f"PPU1={ppu1:.2f} $/100g | PPU2={ppu2:.2f} $/100g")
```
</details>

---

### E31. Decimal → binario (8 bits)
**Enunciado**: Pide un entero **0–255** y **muestra** su **binario de 8 bits** (sin usar `bin()`).
<details><summary>Ver solución</summary>

```python
n = int(input("0..255: "))
b7 = n // 128; n %= 128
b6 = n // 64;  n %= 64
b5 = n // 32;  n %= 32
b4 = n // 16;  n %= 16
b3 = n // 8;   n %= 8
b2 = n // 4;   n %= 4
b1 = n // 2;   n %= 2
b0 = n
print(f"{b7}{b6}{b5}{b4}{b3}{b2}{b1}{b0}")
```
</details>

---

### E32. Grados centesimales → sexagesimales
**Enunciado**: Ingresa **grados centesimales (g)** y **convierte** a **sexagesimales (°)** multiplicando por **0.9**.
<details><summary>Ver solución</summary>

```python
g = float(input("Grados centesimales: "))
deg = g * 0.9
print(f"{deg:.4f}°")
```
</details>

---

### E33. Consumo
**Enunciado**: Pide **km recorridos** y **litros consumidos** y **calcula** **km/L** y **L/100km**.
<details><summary>Ver solución</summary>

```python
km = float(input("Km: "))
L  = float(input("Litros: "))
kml = km / L
l100 = (L / km) * 100
print(f"{kml:.2f} km/L  |  {l100:.2f} L/100km")
```
</details>

---

### E34. Bruto → Líquido (simple)
**Enunciado**: Pide un **bruto** y un **% de descuento** y **calcula** el **líquido**.
<details><summary>Ver solución</summary>

```python
bruto = float(input("Bruto: "))
desc = float(input("% desc: ")) / 100
liquido = bruto * (1 - desc)
print(f"Líquido: {liquido:.2f}")
```
</details>

---

### E35. Nota requerida
**Enunciado**: Dado tu **promedio actual p**, el **peso del examen w (%)** y la **meta final m**, **calcula** la **nota x** mínima requerida en el examen.
<details><summary>Ver solución</summary>

```python
p = float(input("Promedio actual: "))
w = float(input("Peso examen (%): ")) / 100
m = float(input("Meta final: "))
x = (m - (1 - w)*p)/w
print(f"Necesitas: {x:.2f}")
```
</details>

---

### E36. rpm → Hz
**Enunciado**: Solicita **revoluciones por minuto (rpm)** y **convierte** a **Hertz (Hz)** (`/ 60`).
<details><summary>Ver solución</summary>

```python
rpm = float(input("rpm: "))
hz = rpm / 60
print(f"{hz:.3f} Hz")
```
</details>

---

### E37. Suma de dígitos (3 cifras)
**Enunciado**: Pide un **entero entre 100 y 999** y **suma** sus **tres dígitos**.
<details><summary>Ver solución</summary>

```python
n = int(input("Número (100..999): "))
c = n // 100
d = (n % 100) // 10
u = n % 10
s = c + d + u
print("Suma dígitos:", s)
```
</details>

---

### E38. Temperatura media
**Enunciado**: Ingresa **temperatura mínima** y **máxima** y **calcula** la **media**.
<details><summary>Ver solución</summary>

```python
tmin = float(input("Tmin: "))
tmax = float(input("Tmax: "))
med = (tmin + tmax) / 2
print(f"Media: {med:.1f} °C")
```
</details>

---

### E39. ms por frame → fps
**Enunciado**: Pide el **tiempo por frame en milisegundos** y **aproxima** los **fps** como `1000/ms`.
<details><summary>Ver solución</summary>

```python
ms = float(input("ms por frame: "))
fps = 1000 / ms
print(f"{fps:.1f} fps")
```
</details>

---

### E40. Interés compuesto (anual)
**Enunciado**: Ingresa **P**, **r (%)** anual y **t (años)** y **calcula** `M = P*(1+r)^t` (capitalización una vez por año).
<details><summary>Ver solución</summary>

```python
P = float(input("Principal: "))
r = float(input("Tasa anual (%): ")) / 100
t = float(input("Años: "))
M = P * ((1 + r) ** t)
print(f"Monto: {M:.2f}")
```
</details>

---

## Consejos finales
- Estructura tus scripts así:
  1) **Leer** con `input()` → convierte (`int/float`).
  2) **Procesar** con operaciones/fórmulas.
  3) **Mostrar** con `print(...)` formateado.
- Usa `type(...)` cuando algo “no cuadra” para confirmar el tipo real.
- Prueba con valores simples (0, 1, 10) para validar.
