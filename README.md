# Agrupación automática de vehículos por características visuales

Práctica del 2do parcial de Inteligencia Artificial (UMSS) · Grupo 14
Área: Aprendizaje No Supervisado · Subárea: Visión por Computadora

## ¿Qué hace?
Toma fotos de vehículos (Stanford Cars) y las agrupa solo, sin etiquetas:

1. **ResNet-50** preentrenada convierte cada foto en un vector de 2048 números.
2. **PCA** reduce esos vectores a 50 dimensiones.
3. **K-Means** forma los grupos (K elegido con codo y silueta).
4. Se evalúa con silhouette, Davies-Bouldin y Calinski-Harabasz.
5. Un **prototipo (Gradio)** recibe una foto y dice a qué grupo pertenece y muestra 5 vehículos parecidos.

## Cómo correrlo (Google Colab)
1. Abrir `clustering_vehiculos.ipynb` en [colab.research.google.com](https://colab.research.google.com) (Archivo → Subir cuaderno).
2. Activar GPU: Entorno de ejecución → Cambiar tipo de entorno de ejecución → GPU.
3. Ejecutar las celdas en orden (Ejecutar todo).
4. Los gráficos y tablas quedan en la carpeta `resultados/`.

Parámetros en la primera celda: `N_IMAGES` (cuántas fotos), `N_COMP` (componentes PCA), `K_MANUAL` (forzar K).

## Resultados para el informe (carpeta `resultados/`)
| Archivo | Sección del informe |
|---|---|
| `01_ejemplos.png` | 5.3 Dataset y preprocesamiento |
| `02_pca_varianza.png` | 5.5 PCA |
| `03_codo_silueta.png` | 5.6 K-Means |
| `04_metricas.csv` | 5.7 Evaluación |
| `05_grupos_2d.png`, `06_mosaico_grupos.png` | 5.8 Resultados |
| Capturas de la app Gradio | 5.9 Prototipo |

## Herramientas
Python 3 · PyTorch/torchvision (ResNet-50) · scikit-learn (PCA, K-Means, métricas) · Matplotlib · Pillow · Pandas · Gradio · Google Colab
