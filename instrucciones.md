# Tarea: Convolución y Operaciones Morfológicas

## 📁 Estructura del repositorio

Estructura mínima:

```
📁 tu_repositorio/
├── demo.ipynb            # Cuaderno con desarrollo completo de los ejercicios
├── utils.py              # Funciones implementadas de convolución y operaciones morfológicas
├── images/               # Carpeta opcional con imágenes utilizadas
└── README.md             # Breve descripción del repositorio y nivel de uso de IA (si se usó)
```

## Objetivo

El objetivo de esta tarea es comprender y aplicar los conceptos de **convolución** y **operaciones morfológicas** en imágenes digitales.

---

## Parte 1: Convolución manual vs. OpenCV

### Ejercicio 1: Implementación de la convolución

1. Implementa una función `convolve_manual(image, kernel)` en `utils.py` que aplique una convolución a una imagen en escala de grises, usando únicamente `numpy` y ciclos `for`.
2. Prueba tu función con al menos cinco kernels. Entre ellos debe estar:
   * Filtro de suavizado promedio ( 3 \times 3 )
   * Detección de bordes verticales (ej. Sobel vertical)
   * Detección de bordes horizontales (ej. Sobel horizontal)

3. Compara visualmente los resultados con la función `cv2.filter2D` de OpenCV.
4. Mide el tiempo de ejecución de ambas versiones.
5. Implementa una función en `utils.py` llamada `calcular_tamaño_salida` que reciba:

   * El tamaño de la imagen de entrada `(alto, ancho)`
   * El tamaño del kernel `(alto_kernel, ancho_kernel)`
   * El `stride` (un número entero mayor que 0)

   Y retorne el tamaño de la imagen de salida `(alto_salida, ancho_salida)`
   
   * En el cuaderno `demo.ipynb`, muestra un ejemplo para los siguientes casos: i) Imagen de entrada de tamaño (100 \times 100), kernel (3 \times 3), stride 1, y ii) Imagen de entrada de tamaño (100 \times 100), kernel (3 \times 3), stride 2

   * Explica con tus palabras por qué el tamaño disminuye cuando se usa un stride mayor a 1.

### ¿Qué debes mostrar en el cuaderno?

* Visualización de cada resultado (imagen original, convolucionada manualmente y con OpenCV).
* Tiempos de ejecución para cada kernel.
* Comentarios sobre la similitud de los resultados y eficiencia.

---

## Parte 2: Análisis estadístico sobre imágenes a color

### Ejercicio 2: Descriptores estadísticos y convolución

1. Aplica la convolución (manual o con OpenCV) a **cada canal** de una imagen a color (RGB).
2. Calcula y compara los siguientes descriptores **antes y después** de la convolución:

   * Media por canal
   * Varianza por canal
   * Histograma por canal (256 bins)
3. Realiza gráficas comparativas para los histogramas.

### ¿Qué debes mostrar en el cuaderno?

* Imagen original y convolucionada.
* Tabla con estadísticas antes/después.
* Gráficas de histogramas.
* Comentario sobre cómo afecta la convolución los descriptores de color.

---

## Parte 3: Operaciones morfológicas

### Ejercicio 3: Implementación con OpenCV y análisis visual

Usa `cv2.erode`, `cv2.dilate`, `cv2.morphologyEx` con las siguientes operaciones:

* Erosión
* Dilatación
* Apertura
* Cierre

Aplica las operaciones a una imagen binaria (puede ser una imagen con formas blancas sobre fondo negro o viceversa).

1. Muestra el efecto de cada operación individualmente.
2. Cambia el tamaño del elemento estructurante (ej. 3x3, 5x5, 7x7) y comenta el efecto visual.
3. Crea una imagen con ruido blanco y negro, y muestra cómo apertura y cierre pueden ayudar a limpiarla.
4. Compara las similitudes y diferencias entre la operación de **convolución** y las **operaciones morfológicas** (erosión, dilatación, apertura y cierre), tanto desde el punto de vista conceptual como en su efecto sobre una imagen binaria. Incluye ejemplos visuales y comentarios breves que expliquen cuándo puede preferirse una u otra técnica según el tipo de procesamiento deseado.

###  ¿Qué debes mostrar en el cuaderno?

* Imagen binaria original.
* Resultado de cada operación morfológica con diferente elemento estructurante.
* Comparación visual clara.
* Comentarios sobre el efecto de cada operación.

---

## Entrega

Sube todo tu desarrollo al repositorio y asegúrate de incluir:

* `demo.ipynb` completo con visualizaciones y análisis.
* `utils.py` con tus implementaciones.
* `README.md` con:

  * Descripción general del trabajo realizado.
  * Sección final con el siguiente encabezado:

```markdown
## Nivel de uso de herramientas de inteligencia artificial
Describe aquí si usaste herramientas de IA para apoyarte (ChatGPT, Copilot, etc.), y cómo las utilizaste.
```

---