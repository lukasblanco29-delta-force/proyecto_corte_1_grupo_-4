## Reto 5: Nomina-Express

### Pseudocódigo

**Inicio**
1. Definir constantes:
   - `VALOR_HORA`
   - `SMMLV`
   - `AUX_TRANSPORTE`
   - `TOPE_AUX = 2 * SMMLV`
2. Crear listas vacías:
   - `nombres`
   - `horas`
3. Mostrar menú en ciclo `while` con opciones:
   - 1. Ingresar 5 empleados
   - 2. Calcular nómina
   - 3. Ver empleados ordenados
   - 4. Salir
4. Si opción = 1:
   - Vaciar listas.
   - Repetir 5 veces:
     - Leer nombre.
     - Leer horas trabajadas.
     - Si horas < 0, mostrar error y solicitar de nuevo.
     - Guardar nombre y horas en listas.
5. Si opción = 2:
   - Si no hay 5 empleados, mostrar mensaje y volver al menú.
   - Inicializar `total_empresa = 0`.
   - Recorrer empleados con `for`:
     - Si horas > 48:
       - `ordinarias = 48`
       - `extras = horas - 48`
     - Si no:
       - `ordinarias = horas`
       - `extras = 0`
     - Calcular pago ordinario.
     - Calcular pago de extras al 125%.
     - `subtotal = pago_ordinario + pago_extra`
     - Si `subtotal < TOPE_AUX`, agregar auxilio.
     - Si no, auxilio = 0.
     - `total_empleado = subtotal + auxilio`
     - Acumular `total_empresa`.
     - Mostrar desprendible por empleado.
   - Mostrar total de nómina de la empresa.
6. Si opción = 3:
   - Si no hay 5 empleados, mostrar mensaje y volver al menú.
   - Unir datos (nombre, horas).
   - Ordenar alfabéticamente con `.sort()`.
   - Mostrar listado ordenado.
7. Si opción = 4:
   - Finalizar programa.
8. Si opción inválida:
   - Mostrar mensaje de error.
**Fin**

### Diagrama de flujo

```mermaid
flowchart TD
    A[Inicio] --> B[Mostrar menu while]
    B --> C{Opcion}

    C -->|1| D[Ingresar 5 empleados]
    D --> E{Horas >= 0}
    E -->|No| D
    E -->|Si| F[Guardar nombre y horas]
    F --> G{Faltan empleados}
    G -->|Si| D
    G -->|No| B

    C -->|2| H{Hay 5 empleados}
    H -->|No| I[Mostrar mensaje]
    I --> B
    H -->|Si| J[Inicializar total empresa]
    J --> K[Recorrer empleados con for]
    K --> L{Horas > 48}
    L -->|Si| M[Calcular ordinarias y extras]
    L -->|No| N[Calcular solo ordinarias]
    M --> O[Calcular subtotal]
    N --> O
    O --> P{Subtotal < 2 SMMLV}
    P -->|Si| Q[Agregar auxilio]
    P -->|No| R[Sin auxilio]
    Q --> S[Calcular total empleado]
    R --> S
    S --> T[Acumular total empresa]
    T --> U[Mostrar desprendible]
    U --> V{Faltan empleados}
    V -->|Si| K
    V -->|No| W[Mostrar total nomina empresa]
    W --> B

    C -->|3| X{Hay 5 empleados}
    X -->|No| Y[Mostrar mensaje]
    Y --> B
    X -->|Si| Z[Ordenar nombres con sort]
    Z --> AA[Mostrar listado ordenado]
    AA --> B

    C -->|4| AB[Fin]
    C -->|Otro| AC[Opcion invalida]
    AC --> B

