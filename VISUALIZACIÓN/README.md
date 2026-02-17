# 📊 Proyecto de Análisis en Power BI  
## HR Analytics – Servicio de Consultoría Internacional

---

## 🏢 Contexto del Proyecto

Este proyecto se desarrolla simulando un escenario real de consultoría profesional.

Actuamos como una **consultora española especializada en análisis de datos y Business Intelligence**, prestando servicios a una empresa cliente ubicada en Estados Unidos.

Por este motivo:

- La documentación técnica del proyecto está redactada en **español**.
- El modelo de datos, métricas y dashboards en Power BI están desarrollados en **inglés**, ya que el cliente final es una empresa estadounidense.
- El enfoque del análisis sigue estándares profesionales de consultoría en BI: limpieza estructurada de datos, modelado eficiente y visualizaciones orientadas a la toma de decisiones.

---

# 🔄 Documentación del Proceso de Transformación en Power BI

> Este documento se actualizará progresivamente a medida que se realicen transformaciones en Power Query y en el modelo de datos.

---

## 1️⃣ Carga de Datos

### Fuente
- **Tipo de archivo:** CSV  
- **Nombre del archivo:** `hr_data_clean.csv`  
- **Método de importación:** Power BI Desktop → File → Get Data → Text/CSV → Transform Data

### Observaciones iniciales del dataset
- **Número de columnas:**  ~XX  
- **Número de registros:** 1252  
- **Codificación:** Western European (Windows)  
- **Separador:** Coma  
- **Comentarios iniciales:** Power BI crea automáticamente una columna adicional para conteo de filas (`column 0`).

---

## 2️⃣ Organización de Columnas

- Se movió la columna `employeenumber` al inicio del dataset.  
- Se trasladaron todas las columnas con valores en `$` al final del dataset para mayor claridad en dashboards.  

---

## 3️⃣ Cambio de Valores y Renombrado de Columnas

| Nombre original      | Nuevo nombre       | Transformación / Justificación                     |
|---------------------|------------------|--------------------------------------------------|
| `attrition`         | `employee status` | `yes → ex-employee`, `no → employee`           |
| `remote work`       | `workplace`       | Tipo de dato cambiado a **text**, `true → remote`, `false → on-site` |
| `standard hours`    | `workinghours`    | Cambio de nombre para mayor claridad            |

---

## 4️⃣ Eliminación de Columnas

> Columnas eliminadas por no aportar valor analítico o contener casi ningún dato:

| Columna             | Motivo de eliminación |
|--------------------|----------------------|
| `numberchildren`    | Sin datos            |
| `yearsincurrentrole`| Pocos datos          |
| `employeecount`     | No aporta valor      |
| `over18`            | No aporta valor      |
| `sameasmontlyincome`| Duplicada de `monthlyincome` |

---

## 5️⃣ Aplicación de Transformaciones

- Se aplicaron todos los cambios y se cerró Power Query (`Apply and Close`).  
- Se cargó un tema de colores personalizado (`Json`) en **View → Browse for Themes**.  
- Guardado inicial como: `dashboard_rotation_analysis.pbix`


---

## 6️⃣ Creación de Medidas DAX (Campos Calculados)

> Se crearon las siguientes medidas para analizar la rotación (attrition) y los niveles de satisfacción dentro de la organización.

---

### 📌 Métricas de Rotación

**Left Company**

```DAX
left company = 
CALCULATE(
    COUNTROWS('hr_data_clean'),
    'hr_data_clean'[attrition] = "ex-employee"
)

PT left = 
CALCULATE(
    [left company],
    'hr_data_clean'[workinghours] = "part time"
)

% PT left = 
DIVIDE(
    [PT left],
    [left company],
    0
)

attrition rate = 
DIVIDE(
    CALCULATE(
        COUNTROWS('hr_data_clean'),
        'hr_data_clean'[attrition] = "ex-employee"
    ),
    COUNTROWS('hr_data_clean')
)

