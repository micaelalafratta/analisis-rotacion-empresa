# 📊 Employee Retention Analysis: ABC Corporation (End-to-End)

## 🏢 Contexto del Proyecto
Este proyecto simula un escenario real de consultoría profesional para una empresa cliente ubicada en Estados Unidos. Debido a la naturaleza internacional del encargo:
- La documentación técnica está en **español**.
- El modelo de datos, métricas y dashboards en Power BI están en **inglés**.

El objetivo principal es identificar patrones de rotación y proporcionar soluciones accionables basadas en datos para reducir la fuga de talento.

---

## 📂 Estructura del Repositorio
El proyecto se organiza de forma modular para facilitar la auditoría y replicabilidad:

* **`CONSULTORÍA/`**: Contiene las diapositivas de presentación y el informe ejecutivo con acciones clave para RRHH.
* **`EDA_LIMPIEZA_ANALISIS_SQL/`**:
    * `Fase_1_EDA.ipynb`: Exploración inicial de datos.
    * `Fase_2_limpieza_datos.ipynb`: Limpieza y preprocesamiento de `hr_raw_data.csv`.
    * `Fase_3_analisis_descriptivo.ipynb`: Análisis profundo y visualización estática.
    * `Fase_4_codigo_sql.ipynb` & `Fase_4_bbdd_sql.sql`: Implementación de la base de datos en **MySQL**.
* **`VISUALIZACIÓN/`**: Dashboard interactivo (`.pbix`) desarrollado en Power BI.
* **`images/`**: Recursos visuales y capturas del proyecto.

---

## 🛠️ Stack Tecnológico
* **Análisis y Limpieza:** Python (`pandas`, `numpy`, `matplotlib`, `seaborn`).
* **Base de Datos:** MySQL.
* **Business Intelligence:** Power BI Desktop (DAX & Power Query).

---

## 💡 Insights y Conclusiones Clave
A través del análisis, detectamos puntos críticos de abandono en la organización:

* **⚠️ El "Abismo del Talento":** Empleados de alto desempeño, sin acciones (stock options) y con más de 4 años sin promoción presentan una tasa de rotación del 31.82%.
* **📍 Impacto de la Distancia:** Los trayectos de 12 a 28 km incrementan significativamente la probabilidad de renuncia.
* **🕒 Jornada Laboral:** El personal *part-time* representa el 62% de las salidas de la empresa.
* **🎂 Factor Edad:** La mayor rotación se concentra en jóvenes entre 18 y 22 años, mientras que la estabilidad máxima ocurre entre los 38 y 41 años.

<img width="2030" height="1147" alt="image" src="https://github.com/user-attachments/assets/085357ca-20b8-4ed9-b716-c5398d01c9a0" />

---

## 🚀 Próximos Pasos Recomendados
1.  **Plan de Carrera 360º**: Especialmente para roles con alta rotación como *Sales Representatives* y *Human Resources*.
2.  **Incentivos Estratégicos**: Ofrecer *stock options* (niveles 1-2) para reducir la fuga de talento clave.
3.  **Flexibilidad Geográfica**: Implementar modelos híbridos para empleados que viven lejos de la oficina.

---

## 👥 Equipo de Consultoría
Este proyecto fue desarrollado por:

* **ARIANA CALDEIRA** | [GitHub](https://github.com/ariana-caldeira)
* **ELENA PAVÓN** | [GitHub](https://github.com/elenapavonfernandez-ui)
* **MARÍA GÓMEZ** | [GitHub](https://github.com/mariagmzm)
* **MICAELA LAFRATTA** | [GitHub](https://github.com/micaelalafratta)
* **NIEVES PÉREZ** | [GitHub](https://github.com/NievesPerez-Data)

---
> **Nota del Profe:** "Los datos no mienten, pero solo dicen la verdad si haces las preguntas correctas". Este proyecto es una prueba de ello.
