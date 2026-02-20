# Diseño Lógico - Taller Corte 1
## Retos Seleccionados: Reto 3 (Dolar-Track) y Reto 5 (Nomina-Express)

---

## Reto 3: Dolar-Track

### Pseudocódigo

**Inicio**
1. Crear lista `trm_semana` vacía.
2. Mostrar menú en ciclo `while` con opciones:
   - 1. Ingresar TRM de 7 días
   - 2. Analizar semana
   - 3. Ver TRM ordenada
   - 4. Salir
3. Si opción = 1:
   - Vaciar `trm_semana`.
   - Repetir 7 veces:
     - Leer TRM.
     - Si TRM <= 0, mostrar error y solicitar de nuevo.
     - Si TRM válida, guardar en lista.
4. Si opción = 2:
   - Si no hay 7 datos, mostrar mensaje y volver al menú.
   - Calcular promedio semanal.
   - Recorrer lista con `for`:
     - Contar cuántos valores están por encima del promedio.
     - Contar cuántos valores están por debajo del promedio.
   - Calcular volatilidad = valor máximo - valor mínimo.
   - Mostrar resultados.
5. Si opción = 3:
   - Si no hay 7 datos, mostrar mensaje y volver al menú.
   - Copiar lista.
   - Ordenar copia con `.sort()`.
   - Mostrar lista ordenada.
6. Si opción = 4:
   - Finalizar programa.
7. Si opción inválida:
   - Mostrar mensaje de error.
**Fin**

### Diagrama de flujo

```mermaid
flowchart TD
    A[Inicio] --> B[Mostrar menu while]
    B --> C{Opcion}

    C -->|1| D[Ingresar 7 TRM]
    D --> E{TRM > 0}
    E -->|No| D
    E -->|Si| F[Guardar en lista]
    F --> G{Faltan dias}
    G -->|Si| D
    G -->|No| B

    C -->|2| H{Hay 7 datos}
    H -->|No| I[Mostrar mensaje]
    I --> B
    H -->|Si| J[Calcular promedio]
    J --> K[Contar arriba y abajo con for]
    K --> L[Calcular volatilidad max-min]
    L --> M[Mostrar resultados]
    M --> B

    C -->|3| N{Hay 7 datos}
    N -->|No| O[Mostrar mensaje]
    O --> B
    N -->|Si| P[Copiar y ordenar con sort]
    P --> Q[Mostrar lista ordenada]
    Q --> B

    C -->|4| R[Fin]
    C -->|Otro| S[Opcion invalida]
    S --> B



