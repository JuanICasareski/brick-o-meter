# Ideas clave

## Hipótesis central

¿Es cierta la creencia popular **"pagás en ladrillos lo que comprás en ladrillos"**?
→ ¿UVA y precio del m² realmente evolucionan juntos?

## Tesis del trabajo

### Lo que SÍ se cumple
- El **UVA** se ajusta por **CER** (inflación).
- El **ICC** (costo de construcción en pesos) también sigue a la inflación.
- En el **largo plazo**, UVA e ICC en pesos se mueven en paralelo.

### Donde se ROMPE el mito
- El **precio del m² se cotiza en USD**, no en pesos.
- El **dólar** en Argentina **no sigue linealmente a la inflación** (cepo, brecha, saltos cambiarios).
- Ante un salto del dólar: UVA sube con la inflación, pero el m² en USD se queda quieto o **baja** (ej. 2018-2020, 2023).
- **Resultado:** los deudores UVA terminaron debiendo **más m² de los que compraron**.

## Frase resumen

> *"El UVA sigue a la inflación; el m² sigue al dólar. Y en Argentina, inflación y dólar no siempre bailan el mismo tango."*

## Conclusión esperada

- Las series **se acoplan** en períodos de **estabilidad cambiaria**.
- Las series **se desacoplan** en **shocks devaluatorios**.
- Ahí es donde el crédito UVA se vuelve un **problema para el tomador**.
- **Valor para Gerencia Comercial/Técnica:** identificar **cuándo conviene ofrecer/tomar financiación UVA y cuándo no**.

## Variables / series del estudio

| Variable | Unidad | Frecuencia nativa | Cobertura |
|---|---|---|---|
| UVA / CER | índice | diaria | Nacional |
| ICC (costo construcción m²) | pesos | mensual | GBA (no varía por barrio) |
| Precio m² | USD | mensual / trimestral | Gran Buenos Aires (GBA) — CABA por barrio + partidos del conurbano |
| Dólar | ARS/USD | diaria | Nacional |

## Fuentes de datos

> **Prioridad:** 🟢 Oficial > 🟡 Sectorial / Cámara > 🟠 Privado.
> Validar URLs en navegador antes de bajar — la web pública de organismos públicos cambia de path con frecuencia.

### 1. Costo de construcción — ICC

**🟢 Oficiales**
- **INDEC — ICC Gran Buenos Aires (publicación + bases de microdatos):** https://www.indec.gob.ar/indec/web/Nivel4-Tema-3-5-33
- **INDEC — bases de datos / series históricas:** https://www.indec.gob.ar/indec/web/Institucional-Indec-BasesDeDatos
- **Datos Argentina — ICC (CSV mensual, replica de INDEC):** https://datos.gob.ar/dataset/sspm-indice-costoconstruccion-icc
- **Datos Argentina — IPC nacional (para deflactar / comparar):** https://datos.gob.ar/dataset/sspm-indice-precios-al-consumidor-nacional
- **Dirección General de Estadística y Censos — GCBA (ICBA, índice porteño):** https://www.estadisticaciudad.gob.ar/eyc/?cat=99

**🟡 Sectorial / Cámara**
- **Cámara Argentina de la Construcción (CAC) — Índice CAC:** https://www.camarco.org.ar/
- **Índice CAC histórico (agregador no oficial):** https://ikiwi.net.ar/indice-cac/

- *Cobertura:* GBA — los costos de materiales y mano de obra no varían por barrio. ICC INDEC es el estándar académico; CAC es el estándar del sector privado.

### 2. UVA / CER — Tasa de actualización

**🟢 Oficiales**
- **BCRA — Principales variables (UVA, CER, UVI diarios):** https://www.bcra.gob.ar/PublicacionesEstadisticas/Principales_variables.asp
- **BCRA — Serie histórica CER / UVA / UVI (descarga XLS):** https://www.bcra.gob.ar/PublicacionesEstadisticas/Cer_uva_diario.asp
- **BCRA — Publicaciones estadísticas (raíz):** https://www.bcra.gob.ar/PublicacionesEstadisticas
- **Datos Argentina — CER + UVA + UVI (CSV):** https://datos.gob.ar/dataset/sspm-cer-uva-uvi

**🟠 Privado (conveniencia, no fuente primaria)**
- **estadisticasbcra.com — API REST (token gratis):** https://estadisticasbcra.com/api/documentacion

- *Valor único nacional, frecuencia diaria. Para el TPO usar BCRA directo como fuente primaria y citar.*

### 3. Precio del m² — Gran Buenos Aires (GBA)

**🟢 Oficiales — CABA**
- **Dirección General de Estadística y Censos GCBA — mercado inmobiliario (índice general):** https://www.estadisticaciudad.gob.ar/eyc/?cat=129
- **GCBA — Precio de venta de departamentos por barrio (2017→):** https://www.estadisticaciudad.gob.ar/eyc/?p=157955
- **GCBA — Operaciones de compraventa (escrituras inscriptas, mensual):** https://www.estadisticaciudad.gob.ar/eyc/?cat=130
- **Buenos Aires Data — mercado inmobiliario (datasets abiertos GCBA):** https://data.buenosaires.gob.ar/dataset/mercadoinmobiliario

**🟢 Oficiales — Conurbano (PBA) y nacionales**
- **Dirección Provincial de Estadística — PBA (indicadores económicos y vivienda):** https://www.estadistica.ec.gba.gov.ar/
- **ARBA — Catastro PBA (valuaciones fiscales, no precio de mercado, sirve de control):** https://www.arba.gov.ar/
- **INDEC — Censo Nacional 2022 (stock y características de viviendas):** https://www.censo.gob.ar/
- **Ministerio de Desarrollo Territorial y Hábitat — datos de vivienda (si sigue activo el portal):** https://www.argentina.gob.ar/habitat

**🟡 Sectorial / Cámara**
- **CUCICBA — Informe Mensual de Operaciones Inmobiliarias (CABA):** https://www.cucicba.com.ar/
- **Colegio de Escribanos CABA — escrituras mensuales (volumen y monto):** https://www.colegio-escribanos.org.ar/
- **Colegio de Escribanos PBA — escrituras provincia:** https://www.colescba.org.ar/
- **Cámara Inmobiliaria Argentina (CIA):** https://www.cira.org.ar/

**🟠 Privados (sirven sobre todo para conurbano, donde no hay oficial granular)**
- **Reporte Inmobiliario — valores por zona (CABA + GBA):** https://reporteinmobiliario.com/nuke/cat39-valores-por-zona.html
- **Zonaprop Index (mensual, CABA + GBA + ciudades):** https://www.zonaprop.com.ar/blog/zpindex/
- **Argenprop — Índice de precios:** https://www.argenprop.com/
- **Properati Data (dataset abierto, histórico de avisos):** https://blog.properati.com.ar/properati-data-informacion-abierta-y-actualizada-sobre-el-mercado-inmobiliario-2/
- **Mercado Libre Inmuebles (datos vía API/scraping, alta granularidad):** https://www.mercadolibre.com.ar/inmuebles/

- *GCBA es el único oficial con desagregación por barrio + tipología + estado (trimestral desde 2017).*
- *Para conurbano, **Zonaprop Index** es el privado con mejor cobertura por partido y solapa metodológicamente con CABA → buen candidato para anclar la homogeneización.*
- *Colegio de Escribanos = volumen real de transacciones (escrituras), útil como **control de validez** del precio publicado.*

### 4. Dólar — Tipo de cambio (variable de control)

**🟢 Oficiales**
- **BCRA — Tipo de cambio mayorista (Com. "A" 3500, referencia oficial):** https://www.bcra.gob.ar/PublicacionesEstadisticas/Tipo_de_cambio_minorista_2.asp
- **BCRA — Tipo de cambio diario (histórico descargable):** https://www.bcra.gob.ar/PublicacionesEstadisticas/Tipo_de_cambio_diario.asp
- **BCRA — Tipos de cambio de referencia (todas las monedas):** https://www.bcra.gob.ar/PublicacionesEstadisticas/Cotizacion_Monedas.asp
- **Datos Argentina — Tipos de cambio bilaterales (CSV):** https://datos.gob.ar/dataset/sspm-tipos-cambio-bilaterales

**🟡 Sectorial / Mercado**
- **BYMA — cotizaciones de bonos para derivar CCL/MEP:** https://www.byma.com.ar/
- **Bolsas y Mercados Argentinos — Indices y datos:** https://www.bolsar.info/

**🟠 Privados (para CCL, MEP y blue, que no son oficiales)**
- **Ámbito Financiero — series históricas de dólar:** https://www.ambito.com/contenidos/dolar-historico.html
- **Rava Bursátil — series con CCL/MEP:** https://www.rava.com/
- **DolarHoy — blue y financieros (diario):** https://dolarhoy.com/historico-dolar-blue
- **estadisticasbcra.com — dólar oficial + brecha (API):** https://estadisticasbcra.com/api/documentacion

- *Para el TPO se necesitan **al menos 2 series**: oficial mayorista (BCRA A3500) y un dólar financiero (CCL o MEP) que refleje la brecha. El blue es opcional como contexto.*

## Notas metodológicas

- **Frecuencias distintas:** UVA diaria, ICC mensual, m² mensual/trimestral → **resamplear a mensual**.
- **Unidades mixtas:** ICC en pesos nominales, m² en USD → **pasar todo a una misma unidad** (USD o índice base 100) antes de correlacionar.
- **Análisis por zona/partido:** ICC y UVA son globales; lo que varía geográficamente es el precio del m². Pregunta interesante: **¿en qué zonas del GBA (barrios de CABA + partidos del conurbano) el m² se acopla más al ICC/UVA y en cuáles se desacopla?**
- **Heterogeneidad de fuentes:** los datos de m² de CABA (IDECBA) y los del conurbano (Reporte Inmobiliario / Zonaprop / Properati) tienen metodologías distintas → documentar y, si es posible, homogeneizar antes de comparar.

## Preguntas abiertas que el análisis puede responder

1. ¿En qué períodos exactos UVA y m² estuvieron acoplados/desacoplados?
2. ¿Hay zonas/partidos "refugio" en el GBA cuyo m² se mueve menos en USD (más estables)?
3. ¿Qué tan grande fue la pérdida real para un deudor UVA en los shocks de 2018, 2020, 2023?
4. ¿Existe una regla simple para Gerencia: "si dólar sube X% en N meses → no recomendar UVA"?
