# Detección de Anomalías en Datos Eléctricos

Proyecto de análisis y detección de anomalías aplicado a datos de voltaje y corriente eléctrica, utilizando técnicas de aprendizaje no supervisado tanto univariadas como multivariadas.

## Descripción del Proyecto

Este proyecto implementa y compara diferentes técnicas de detección de anomalías para identificar patrones inusuales en mediciones eléctricas (voltaje y corriente). El análisis se realiza utilizando métodos estadísticos clásicos y algoritmos de machine learning.

### Objetivos

- Implementar técnicas univariadas de detección de anomalías (Media Móvil, Z-Score)
- Aplicar técnicas multivariadas avanzadas (Isolation Forest, Local Outlier Factor)
- Comparar la efectividad de diferentes métodos en la detección de valores atípicos
- Analizar patrones ocultos en series temporales de datos eléctricos

## Estructura del Proyecto

```
clustering-unsupervised-learning/
│
├── README.md                                    # Documentación del proyecto
├── clustering-comparison-unsupervised.ipynb     # Notebook principal con análisis
├── requirements.txt                             # Dependencias del proyecto
│
└── data/
    ├── dataset.csv                              # Dataset de voltaje/corriente
    └── README.md                                # Descripción de los datos
```

## 🛠️ Tecnologías y Métodos Utilizados

### Técnicas Implementadas

1. **Métodos Univariados**
   - **Media Móvil**: Detección de anomalías mediante suavizado temporal
   - **Z-Score**: Identificación de outliers basada en desviación estándar

2. **Métodos Multivariados**
   - **Isolation Forest**: Algoritmo basado en árboles de decisión para aislamiento de anomalías
   - **Local Outlier Factor (LOF)**: Detección basada en densidad local de puntos

### Stack Tecnológico

- **Python 3.8+**: Lenguaje principal
- **NumPy**: Operaciones numéricas y álgebra lineal
- **Pandas**: Manipulación y análisis de datos
- **Scikit-learn**: Algoritmos de machine learning
- **Matplotlib & Seaborn**: Visualización de datos

## Dataset

El proyecto utiliza un dataset de mediciones eléctricas que incluye:

- **Variables de Voltaje**: VL1, VL2, VL3 (voltajes de línea)
- **Variables de Corriente**: IL1, IL2, IL3 (corrientes de línea)
- **Voltajes entre líneas**: VL12, VL23, VL31
- **Corriente neutra**: INUT
- **Timestamps**: Registros temporales de las mediciones

### Características del Dataset
- Datos de series temporales
- Múltiples variables correlacionadas
- Presencia de valores faltantes (NaN)
- Alta dimensionalidad (10 variables eléctricas)

## Instalación y Uso

### Requisitos Previos

- Python 3.8 o superior
- pip (gestor de paquetes de Python)

### Pasos de Instalación

1. **Clonar el repositorio**
```bash
git clone https://github.com/tu-usuario/clustering-unsupervised-learning.git
cd clustering-unsupervised-learning
```

2. **Crear un entorno virtual (recomendado)**
```bash
# En Linux/Mac
python -m venv venv
source venv/bin/activate

# En Windows
python -m venv venv
venv\Scripts\activate
```

3. **Instalar dependencias**
```bash
pip install -r requirements.txt
```

4. **Ejecutar el notebook**
```bash
jupyter notebook clustering-comparison-unsupervised.ipynb
```

## Resultados Principales

### Técnicas Univariadas

- **Media Móvil**: Efectiva para detectar cambios abruptos en series temporales
- **Z-Score**: Identifica valores que se desvían significativamente de la media (umbral típico: |z| > 3)

### Técnicas Multivariadas

- **Isolation Forest**: 
  - Parámetro de contaminación: 5%
  - Efectivo para detectar anomalías en espacios de alta dimensión
  - Menor complejidad computacional

- **Local Outlier Factor (LOF)**:
  - Considera la densidad local de vecinos
  - Mejor para detectar anomalías contextuales
  - Más sensible a la configuración de parámetros

### Comparación de Métodos

| Método | Tipo | Complejidad | Interpretabilidad | Escalabilidad |
|--------|------|-------------|-------------------|---------------|
| Media Móvil | Univariado | Baja | Alta | Excelente |
| Z-Score | Univariado | Baja | Alta | Excelente |
| Isolation Forest | Multivariado | Media | Media | Muy Buena |
| LOF | Multivariado | Alta | Baja | Limitada |

## 🔬 Investigación Relacionada

Este proyecto se fundamenta en técnicas establecidas de detección de anomalías con aplicaciones en:

- Monitoreo de infraestructura eléctrica
- Detección de fallos en sistemas industriales
- Análisis de calidad de energía
- Mantenimiento predictivo

> **Nota**: El análisis incluye referencias a artículos científicos posteriores a 2015 sobre aplicaciones prácticas de detección de anomalías en diferentes dominios.

## Metodología

1. **Exploración de Datos**: Análisis estadístico descriptivo y visualización
2. **Preprocesamiento**: Limpieza de datos, manejo de valores faltantes
3. **Aplicación de Técnicas**: Implementación de los 4 métodos de detección
4. **Evaluación**: Comparación de resultados y análisis de sensibilidad
5. **Conclusiones**: Recomendaciones sobre la mejor técnica según el caso de uso

## Contexto Académico

Este proyecto fue desarrollado como parte del **Máster en Inteligencia Artificial**, específicamente en el módulo de Aprendizaje No Supervisado y Detección de Anomalías.

### Competencias Desarrolladas

- Implementación de algoritmos de machine learning no supervisado
- Análisis exploratorio de datos multivariados
- Evaluación y comparación de modelos de detección
- Visualización efectiva de resultados
- Documentación técnica y científica

## Contribuciones

Las contribuciones son bienvenidas. Si deseas mejorar este proyecto:

1. Fork el repositorio
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## Contacto

**Tu Nombre** - [LinkedIn](www.linkedin.com/in/sadam-pérez-romero) - sadam.perez.romero@gmail.com

Link del Proyecto: [https://github.com/tu-usuario/clustering-unsupervised-learning](https://github.com/tu-usuario/clustering-unsupervised-learning)

## Referencias

- Scikit-learn Documentation: [Novelty and Outlier Detection](https://scikit-learn.org/stable/modules/outlier_detection.html)
- Chandola, V., Banerjee, A., & Kumar, V. (2009). Anomaly detection: A survey. ACM computing surveys (CSUR), 41(3), 1-58.

## Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

---

⭐ Si este proyecto te ha sido útil, considera darle una estrella en GitHub
