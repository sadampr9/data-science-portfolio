# Dataset - Mediciones de Voltaje y Corriente

## Descripción General

Este directorio contiene el dataset utilizado para el análisis de detección de anomalías en mediciones eléctricas.

## Archivo de Datos

**Nombre**: `CurrentVoltage.csv`

**Formato**: CSV (Comma-Separated Values)

**Tamaño aproximado**: Dependiendo de la frecuencia de muestreo y período de medición

## Estructura del Dataset

### Variables Incluidas

| Variable | Tipo | Descripción | Unidad |
|----------|------|-------------|--------|
| `Date` | Temporal | Fecha de la medición | - |
| `Time` | Temporal | Hora de la medición | - |
| `VL1` | Numérica | Voltaje de línea 1 | Voltios (V) |
| `VL2` | Numérica | Voltaje de línea 2 | Voltios (V) |
| `VL3` | Numérica | Voltaje de línea 3 | Voltios (V) |
| `IL1` | Numérica | Corriente de línea 1 | Amperios (A) |
| `IL2` | Numérica | Corriente de línea 2 | Amperios (A) |
| `IL3` | Numérica | Corriente de línea 3 | Amperios (A) |
| `VL12` | Numérica | Voltaje entre líneas 1 y 2 | Voltios (V) |
| `VL23` | Numérica | Voltaje entre líneas 2 y 3 | Voltios (V) |
| `VL31` | Numérica | Voltaje entre líneas 3 y 1 | Voltios (V) |
| `INUT` | Numérica | Corriente neutra | Amperios (A) |

### Características del Dataset

- **Tipo de datos**: Series temporales multivariadas
- **Valores faltantes**: Presentes (codificados como `?` o `NaN`)
- **Separador**: Coma (`,`)
- **Sistema eléctrico**: Trifásico
- **Frecuencia de muestreo**: Variable (especificar según el dataset real)

## Preprocesamiento Necesario

Antes de utilizar el dataset, se recomienda:

1. **Conversión temporal**: Combinar las columnas `Date` y `Time` en una única columna `datetime`
   ```python
   df['datetime'] = pd.to_datetime(df['Date'] + ' ' + df['Time'])
   ```

2. **Manejo de valores faltantes**:
   ```python
   # Reemplazar '?' por NaN
   df.replace('?', np.nan, inplace=True)
   
   # Eliminar filas con NaN o imputar valores
   df_clean = df.dropna()
   ```

3. **Conversión de tipos**:
   ```python
   # Convertir columnas numéricas
   numeric_cols = ['VL1', 'VL2', 'VL3', 'IL1', 'IL2', 'IL3', 
                   'VL12', 'VL23', 'VL31', 'INUT']
   df[numeric_cols] = df[numeric_cols].astype(float)
   ```

## Estadísticas Descriptivas (Ejemplo)

```python
import pandas as pd

# Cargar el dataset
df = pd.read_csv('muinar07_act3_CurrentVoltage.csv')

# Estadísticas básicas
print(df.describe())

# Información del dataset
print(df.info())

# Verificar valores faltantes
print(df.isnull().sum())
```

## Consideraciones Importantes

### Calidad de los Datos

- **Valores atípicos**: El dataset puede contener anomalías reales que son de interés para el análisis
- **Ruido**: Las mediciones eléctricas pueden tener ruido inherente del sistema de adquisición
- **Balanceo de fases**: En un sistema trifásico equilibrado, VL1 ≈ VL2 ≈ VL3

### Validaciones Físicas

Las mediciones deben cumplir con ciertas relaciones físicas:

1. **Ley de Kirchhoff para corrientes**: 
   - En un sistema equilibrado: IL1 + IL2 + IL3 ≈ 0
   - La corriente neutra (INUT) debería ser cercana a cero en condiciones normales

2. **Relaciones de voltaje**:
   - VL12 = VL1 - VL2
   - VL23 = VL2 - VL3
   - VL31 = VL3 - VL1

3. **Rangos típicos**:
   - Voltaje de línea: 220-240V (sistema monofásico) o 380-400V (sistema trifásico)
   - Corriente: Depende de la carga conectada

## Privacidad y Uso de Datos

- Este dataset se utiliza únicamente con fines educativos y de investigación
- Los datos pueden estar anonimizados o provenir de sistemas de prueba
- Cualquier uso comercial debe verificar las licencias correspondientes

## Cómo Citar este Dataset

Si utilizas este dataset en tu investigación o proyecto, considera citarlo adecuadamente:

```
Dataset de Mediciones Eléctricas - Detección de Anomalías
Proyecto: Clustering Unsupervised Learning
Año: 2024-2025
```

## Recursos Adicionales

- [Documentación de Pandas para CSV](https://pandas.pydata.org/docs/reference/api/pandas.read_csv.html)
- [Manejo de Series Temporales en Python](https://pandas.pydata.org/docs/user_guide/timeseries.html)
- [Sistemas Eléctricos Trifásicos](https://en.wikipedia.org/wiki/Three-phase_electric_power)

## Contacto

Para preguntas sobre el dataset o solicitudes de acceso a versiones adicionales, contactar al responsable del proyecto.

---

**Última actualización**: Enero 2025
