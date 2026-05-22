# Progreso TPO — Ciencia de Datos

**Última actualización:** 2026-05-22 (scope ampliado a GBA)

**Leyenda:** `[ ]` pendiente · `[~]` en curso · `[x]` completo

---

## Fase 0 — Pre-condiciones ✅

- [x] Conformación del grupo de trabajo
- [x] Asignación de roles por integrante (cada uno expone su área de influencia)
- [x] Definir fecha de entrega exacta
- [x] Crear repositorio en GitHub (versionado)
- [x] Definir metodología ágil de trabajo (Scrum/Kanban, tablero, sprints)

## Fase 1 — Definición del proyecto

- [x] Selección del dominio del negocio → **mercado inmobiliario / financiación UVA**
- [x] Hipótesis definida → *"¿UVA y precio del m² evolucionan juntos?"*
- [x] Audiencia identificada → **Gerencia Comercial y Técnica**
- [x] Propuesta de valor → identificar cuándo conviene ofrecer/tomar UVA
- [x] Selección de fuentes de datos (ICC, BCRA/UVA, IDECBA m² CABA + Reporte Inmobiliario/Zonaprop/Properati para conurbano) — ver `IDEAS_HIPOTESIS.md`
- [x] Recorte geográfico definido → **Gran Buenos Aires (GBA)** = CABA por barrio + partidos del conurbano

## Fase 2 — Ingesta y preparación de datos

- [ ] Descargar dataset ICC (Datos Argentina / INDEC / CAC)
- [ ] Descargar serie histórica UVA (BCRA / API estadísticasbcra)
- [ ] Descargar serie m² por barrio CABA (IDECBA, 2017–2026)
- [ ] Descargar serie m² para partidos del conurbano (Reporte Inmobiliario / Zonaprop Index / Properati Data)
- [~] **Homogeneización de fuentes m² CABA ↔ conurbano** (decisión 2026-05-22)
  - [ ] Comparar metodologías: tipo de inmueble (depto vs casa), tipología (1/2/3 amb), estado (usado/a estrenar), unidad (USD/m²), frecuencia
  - [x] Definir denominador común → **USD/m², frecuencia mensual** (tipología NO fijada: se conservan todas las tipologías disponibles para análisis posterior) — decisión 2026-05-22
  - [ ] Validar solapamiento temporal entre fuentes (¿todas cubren 2017–2026?)
  - [ ] Cruzar zonas donde haya overlap (ej. Zonaprop tiene CABA + conurbano) para detectar gaps de nivel entre fuentes
  - [ ] Aplicar factor de ajuste / normalización si hay sesgo sistemático entre fuentes
  - [ ] Documentar supuestos y limitaciones de la homogeneización (va al informe final)
- [ ] Descargar serie histórica del dólar (oficial + CCL/MEP)
- [ ] Resamplear todas las series a frecuencia mensual
- [ ] Unificar unidades (USD o índice base 100)
- [ ] Limpieza de nulos/outliers
- [ ] Construcción del dataset consolidado

## Fase 3 — Arquitectura de la solución

- [ ] Diagramar la **tubería de datos** (ingesta → transformación → modelado → visualización)
- [ ] Definir plataforma de ejecución (Google Colab / Jupyter / VS Code)
- [ ] Definir herramienta de visualización (Power BI / Looker / Plotly / matplotlib)

## Fase 4 — Análisis exploratorio (EDA)

- [ ] Estadísticos descriptivos de cada serie
- [ ] Visualización de las 3 series en el tiempo (mismo eje normalizado)
- [ ] Identificar shocks devaluatorios (2018-2020, 2023) y períodos de estabilidad
- [ ] Matriz de correlaciones (UVA vs ICC vs m² USD vs dólar)
- [ ] Análisis por zona del GBA: qué barrios de CABA y qué partidos del conurbano se acoplan más/menos al ICC/UVA

## Fase 5 — Técnica de minería / modelado

- [ ] Elegir técnica (correlación rolling, cointegración, clustering de barrios, modelo de series de tiempo, regresión)
- [ ] Implementar el modelo
- [ ] Validar resultados
- [ ] Cuantificar el desacople en shocks vs estabilidad

## Fase 6 — Visualización + storytelling

- [ ] Gráficos finales que cuenten la historia (UVA-inflación vs m²-dólar)
- [ ] Identificar visualmente los momentos de desacople
- [ ] Mensaje accionable para Gerencia Comercial/Técnica

## Fase 7 — Aplicación funcional

- [ ] Definir tipo de app (dashboard interactivo / notebook con widgets / web app Streamlit)
- [ ] Implementar la app
- [ ] Permitir al usuario explorar zonas del GBA (barrios CABA + partidos conurbano) y períodos
- [ ] Que entregue valor percibible (recomendación de cuándo conviene UVA)

## Fase 8 — Presentación (15 min)

- [ ] Armar slides (PowerPoint / Google Slides)
- [ ] Distribuir secciones por integrante (cada uno expone su rol)
- [ ] Incluir: dominio, problemática, propuesta, arquitectura, EDA, modelo, conclusión, demo de la app
- [ ] Ensayo de tiempos (15 min)
- [ ] Revisar ortografía y prolijidad

## Fase 9 — Entrega final

- [ ] Repo de GitHub público/compartido con docente
- [ ] Notebook ejecutable de punta a punta
- [ ] App funcional disponible
- [ ] Presentación lista
- [ ] Backup de todo el material (no quedar afuera por problemas técnicos)

---

## Notas y bloqueos

_(El usuario va reportando avances acá; Claude actualiza el archivo)_

- 2026-05-08: archivo de progreso creado a partir de las consignas del TPO y la hipótesis UVA/ICC/m².
- 2026-05-08: Fase 0 completa (grupo, roles, fecha de entrega, repo GitHub y metodología ágil definidos).
- 2026-05-22: Scope geográfico ampliado de CABA a **Gran Buenos Aires (GBA)** = CABA por barrio + partidos del conurbano. Implica sumar fuentes (Reporte Inmobiliario / Zonaprop / Properati) y homogeneizar metodologías de m² entre CABA y conurbano.
- 2026-05-22: **Decisión:** se mantiene scope GBA completo y se homogeneizan las fuentes (opción a). Sub-tareas de homogeneización agregadas en Fase 2. Riesgo a vigilar: que el gap metodológico entre IDECBA y fuentes privadas sea demasiado grande → si pasa, replantear a fuente única (Zonaprop o Properati).
- 2026-05-22: **Denominador común fijado** → unidad **USD/m²**, frecuencia **mensual**. **Tipología NO se fija** (se conservan 1/2/3 amb, usado/a estrenar, etc., y queda como variable de segmentación para el análisis).
- 2026-05-22: **Lista de fuentes ampliada y jerarquizada** en `IDEAS_HIPOTESIS.md` (Oficial 🟢 > Sectorial 🟡 > Privado 🟠). Se agrega sección 4 para Dólar (variable de control: BCRA A3500 + CCL/MEP). Se prioriza INDEC, BCRA, GCBA, PBA y Colegios de Escribanos sobre fuentes privadas.
