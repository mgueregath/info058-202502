# Control 1 INFO 058 – Resuelto ✅

Este documento contiene las respuestas y explicaciones del **Control 1 INFO 058**, preparado en formato Markdown para publicarse con **MkDocs** y **mkdocs-material**.

---

## I. Verdadero / Falso

1. **En Python, el símbolo `==` se usa para asignar valores a variables.**  
   ❌ **Falso** – `=` asigna valores, mientras que `==` compara.

2. **Las cadenas de texto (STR) se definen usando comillas simples o dobles.**  
   ✅ **Verdadero** – Ejemplo: `"hola"` o `'hola'`.

3. **El operador `<=` verifica si el valor a la izquierda es mayor o igual al de la derecha.**  
   ❌ **Falso** – `<=` significa *menor o igual que*.

4. **La función `print()` en Python se utiliza para imprimir resultados en consola.**  
   ✅ **Verdadero**.

5. **En Python, la declaración `if` se utiliza para ejecutar un bloque de código solo si una condición es verdadera.**  
   ✅ **Verdadero**.

6. **El operador `%` devuelve el resto de una división.**  
   ✅ **Verdadero** – Ejemplo: `10 % 3 = 1`.

---

## II. Preguntas de selección múltiple

7. **Código:**
   ```python
   x = "hello"
   y = "world"

   if x == y:
       print("x, y son iguales")
   else:
       print("Son diferentes")
   ```
   👉 Resultado: `"Son diferentes"` → **C**.

---

8. **¿Resultado de `10 % 3`?**  
   👉 Resto de la división → `1` → **B**.

---

9. **¿Qué sucede con `print('Hola' * 3)`?**  
   👉 Repite la cadena 3 veces → `"HolaHolaHola"` → **C**.

---

10. **Operador lógico para "y" en Python:**  
   👉 `and` → **B**.

---

11. **Salida de `print(type(3.14))`:**  
   👉 `<class 'float'>` → **B (float)**.

---

12. **¿Cuál NO es una palabra reservada en Python?**  
   👉 `enter` (no existe en Python) → **C**.

---

13. **Código:**
   ```python
   x = 5
   if x < 10:
       print("Mas")
   else:
       print("Menos")
   ```
   👉 Se cumple condición (`5 < 10`), imprime `"Mas"` → **B**.

---

14. **Función que convierte texto en número entero:**  
   👉 `int()` → **C**.

---

## III. Preguntas de código

15. ```python
   x = 10
   y = 4
   print(x / y)
   ```
   👉 División normal → `2.5`.

---

16. ```python
   x = 15
   print(x // 2)
   ```
   👉 División entera → `7`.

---

17. ```python
   x = 9
   if x % 2 == 0:
       print(6)
   else:
       print(9)
   ```
   👉 `9 % 2 = 1` (no es par), imprime → `9`.

---

18. ```python
   x = 2
   y = 3
   print(x * y)
   ```
   👉 Multiplicación → `6`.

---

## 🚀 Resumen rápido (chuleta)

- `=` asigna, `==` compara.  
- Cadenas → `'texto'` o `"texto"`.  
- `<=` = menor o igual, `>=` = mayor o igual.  
- `print()` → muestra en consola.  
- `if cond:` → ejecuta solo si la condición es verdadera.  
- `%` → resto de la división.  
- `*` con cadenas → repite texto.  
- Operadores lógicos: `and`, `or`, `not`.  
- Conversión de tipos: `int()`, `float()`, `str()`.

---

📘 Este README está diseñado para integrarse fácilmente en **MkDocs** con el tema **Material**.  

En tu `mkdocs.yml` puedes agregarlo así:

```yaml
site_name: Control 1 INFO 058
theme:
  name: material

nav:
  - Inicio: index.md
  - Control 1: README.md
```
