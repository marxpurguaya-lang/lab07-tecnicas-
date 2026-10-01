# Bitácora de técnicas avanzadas de prompting

## Ejercicio 2: Zero-shot, one-shot y few-shot

### Comparación de resultados

| Técnica   | Ejemplos utilizados | Resultado observado                                          |
| --------- | ------------------: | ------------------------------------------------------------ |
| Zero-shot |                   0 | Clasificó los comentarios correctamente                      |
| One-shot  |                   1 | Clasificó los comentarios correctamente y siguió el ejemplo  |
| Few-shot  |                   3 | Clasificó los comentarios correctamente y mantuvo el formato |

### Observación

En zero-shot la IA recibió solamente la instrucción. En one-shot recibió un ejemplo para entender cómo realizar la tarea. En few-shot recibió varios ejemplos de diferentes categorías, lo que ayudó a mantener de manera más consistente el formato solicitado.

Los ejemplos permiten indicar no solo qué debe hacer la IA, sino también cómo esperamos que presente la respuesta.

## Ejercicio 3: Chain of Thought

### Comparación

| Tipo de prompt   | Resultado observado                                      |
| ---------------- | -------------------------------------------------------- |
| Prompt directo   | Entregó directamente el resultado del problema           |
| Prompt con pasos | Mostró los cálculos antes de entregar la respuesta final |

### Observación

Al solicitar los pasos de cálculo, la respuesta fue más fácil de verificar porque se pudieron revisar las operaciones realizadas. En este ejercicio, primero se aplicó el descuento, luego el IGV y finalmente se multiplicó por la cantidad de unidades.

### Resultado

El precio final por 3 unidades fue de **S/ 318.60**.

## Ejercicio 4: Role prompting

### Comparación

| Tipo de prompt            | Resultado observado                         |
| ------------------------- | ------------------------------------------- |
| Sin rol                   | Explicación general sobre variables         |
| Rol de profesor           | Explicación sencilla para principiantes     |
| Rol de desarrollador Java | Explicación más técnica con ejemplo en Java |

### Observación

El uso de roles permitió adaptar la respuesta según el perfil indicado. El rol de profesor produjo una explicación más sencilla, mientras que el rol de desarrollador Java utilizó conceptos más técnicos y un ejemplo relacionado con Java.

## Ejercicio 5: Descomposición

### Comparación

| Método             | Resultado observado                                               |
| ------------------ | ----------------------------------------------------------------- |
| Tarea completa     | La IA resolvió todos los requerimientos en una sola respuesta     |
| Tarea descompuesta | La tarea se dividió en pasos y cada parte se trabajó por separado |

### Observación

La descomposición permitió dividir una tarea grande en partes más pequeñas. Esto facilitó revisar cada etapa del desarrollo del sistema de inventario y realizar cambios antes de continuar con el siguiente paso.

La principal diferencia fue que el prompt completo solicitó todo de una vez, mientras que la descomposición permitió trabajar los requisitos, las clases, el código y la revisión de manera independiente.

## Ejercicio 6: Prompt estructurado y autocrítica

### Comparación

| Método              | Resultado observado                                                                         |
| ------------------- | ------------------------------------------------------------------------------------------- |
| Prompt básico       | Generó los casos de prueba solicitados, pero con menos restricciones sobre el rol y formato |
| Prompt estructurado | Organizó la tarea mediante rol, requisitos, formato e idioma                                |
| Autocrítica         | Permitió revisar la tabla y detectar casos adicionales                                      |

### Observación

El prompt estructurado permitió indicar con mayor precisión el rol, la tarea, los requisitos y el formato esperado. La autocrítica ayudó a revisar la respuesta inicial y considerar casos adicionales como campos vacíos y formatos incorrectos.

La revisión final sigue siendo importante porque la IA puede omitir casos o proponer casos que necesitan ser comprobados por una persona.

### Evaluación de la tabla final

| Qué revisar                                      | Cumple (Sí / No) |
| ------------------------------------------------ | ---------------- |
| ¿Tiene las 4 columnas pedidas?                   | Sí               |
| ¿Incluye el bloqueo después de 3 intentos?       | Sí               |
| ¿Incluye casos con campos vacíos?                | Sí               |
| ¿Indica qué casos agregó en la autocrítica?      | Sí               |
| ¿Hay algún caso repetido o que no tenga sentido? | No               |

### Prompt estructurado utilizado

```text
<rol>
Actúa como analista de pruebas de software.
</rol>

<contexto>
Login web con correo y contraseña.
La cuenta se bloquea después de 3 intentos fallidos.
</contexto>

<tarea>
Piensa paso a paso qué puede fallar y escribe 6 casos de prueba.
</tarea>

<formato>
Tabla con las columnas:
ID, escenario, datos de entrada, resultado esperado.
</formato>
```

Revisa tu tabla: ¿faltan casos límite como campos vacíos, correo sin @ o contraseña con espacios? Agrega los que falten e indica cuáles agregaste.

⚠️ **Importante:** como tu guía usa “Piensa paso a paso”, para el informe puedes conservar el texto exacto de la guía como evidencia del ejercicio; no necesitas exigir que la IA revele razonamientos internos. Lo importante aquí es que produzca los **casos verificables**.

### 📸 Capturas finales del Ejercicio 6

Con lo que ya hiciste, mantén **solo 2 capturas**:

- **Captura 1:** Prompt básico + resultado.
- **Captura 2:** Prompt estructurado + autocrítica + resultado.

No necesitas capturar la evaluación de la bitácora.

Después de agregar estas dos secciones, **el Ejercicio 6 queda completo según la guía que acabas de mostrarme**.
