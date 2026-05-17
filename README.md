# Trabajo de ML: Preguntas, Generadores y Respuestas

**Autor:** Michael Stiven Tabares Tobón
**Correo:** michael.tabares@udea.edu.co  
**Curso:** Modelos y Simulación — Programación con LLMs

---

## Descripción

Este repositorio contiene dos fases del trabajo:

- **Fase 1:** 4 preguntas de Machine Learning propias, cada una con su generador de casos de uso en Python. Los generadores producen pares `(input_dict, output_esperado)` aleatorios para evaluar automáticamente una función solución.
- **Fase 2:** Implementaciones de soluciones a preguntas de compañeros, ubicadas en `myanswers/`.

## Preguntas

| # | Función | Tema | Librerías |
|---|---------|------|-----------|
| 1 | `aplicar_target_encoding` | Target encoding out-of-fold con KFold | pandas, sklearn |
| 2 | `generar_curvas_aprendizaje` | Curvas de aprendizaje para diagnóstico sesgo-varianza | numpy, pandas, sklearn |
| 3 | `agrupar_jerarquicamente` | Clustering jerárquico aglomerativo + perfiles por cluster | pandas, sklearn |
| 4 | `imputar_con_knn` | Imputación de valores faltantes con KNNImputer | pandas, sklearn |

## Estructura

```
README.md
myquestions/
  question-0001.txt                      # Enunciado: aplicar_target_encoding
  question-0001-usecase-generator.py
  question-0002.txt                      # Enunciado: generar_curvas_aprendizaje
  question-0002-usecase-generator.py
  question-0003.txt                      # Enunciado: agrupar_jerarquicamente
  question-0003-usecase-generator.py
  question-0004.txt                      # Enunciado: imputar_con_knn
  question-0004-usecase-generator.py
myanswers/
  answer-0252.py                         # optimizar_y_proyectar
  answer-0258.py                         # predecir_riesgo_cuantil
  answer-0317.py                         # resumir_ventas_mensuales
  answer-0558.py                         # calcular_racha_maxima
```

## Uso

Cada generador se puede ejecutar de forma independiente:

```bash
python myquestions/question-0001-usecase-generator.py
python myquestions/question-0002-usecase-generator.py
python myquestions/question-0003-usecase-generator.py
python myquestions/question-0004-usecase-generator.py
```

Para evaluar una función solución con un caso generado:

```python
from myquestions.question-0001-usecase-generator import generar_caso_de_uso_aplicar_target_encoding

input_dict, output_esperado = generar_caso_de_uso_aplicar_target_encoding()
resultado = aplicar_target_encoding(**input_dict)
```

## Fase 2 — Respuestas a preguntas de compañeros

| Archivo | Función | Tema | Librerías |
|---------|---------|------|-----------|
| `answer-0252.py` | `optimizar_y_proyectar` | Imputación + escalado + PCA; retorna varianza explicada acumulada | numpy, pandas, sklearn |
| `answer-0258.py` | `predecir_riesgo_cuantil` | Regresión cuantil con GradientBoosting; retorna modelo, predicciones y pinball loss | numpy, sklearn |
| `answer-0317.py` | `resumir_ventas_mensuales` | Agrupación mensual por categoría con suma, media y conteo | pandas |
| `answer-0558.py` | `calcular_racha_maxima` | Racha máxima de eventos consecutivos por usuario | pandas |

Cada archivo incluye un bloque `if __name__ == "__main__"` que carga el generador del compañero desde `questionsToAnswer/` y ejecuta 5 casos de prueba con validación automática.

### Ejecutar una respuesta

```bash
python myanswers/answer-0252.py
python myanswers/answer-0258.py
python myanswers/answer-0317.py
python myanswers/answer-0558.py
```

## Dependencias

```
pandas
numpy
scikit-learn
```
# programacion-llms-Mafe
