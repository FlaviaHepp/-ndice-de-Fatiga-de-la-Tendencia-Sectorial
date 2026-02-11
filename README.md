# 📉 Índice de Fatiga de la Tendencia Sectorial

## 📌Descripción general

Este proyecto implementa un indicador cuantitativo de agotamiento de tendencia a nivel sectorial, denominado “Índice de Fatiga”.
El objetivo es detectar sectores donde el precio continúa subiendo, pero la calidad interna del movimiento se deteriora: menor rango diario, menor volumen y señales claras de pérdida de convicción compradora.

Este patrón suele preceder reversiones violentas, correcciones rápidas o incluso flash crashes.

## ❓Hipótesis de mercado

Una tendencia alcista saludable debería mostrar:
- Rango diario estable o creciente
- Volumen consistente o en expansión
- Progresión sostenida del precio

Cuando ocurre lo contrario —precio sube, pero volatilidad y volumen caen— el mercado entra en una fase de fatiga estructural.

👉 Esto indica que:
- Los compradores fuertes ya participaron
- El avance se sostiene con menor liquidez
- El riesgo asimétrico aumenta significativamente

## 🧠Lógica del indicador

El script analiza datos recientes (últimos 5 días) y detecta sectores que cumplen simultáneamente:
- Rango diario estrechándose

Se mide como (High - Low) / Close

Debe ser inferior al promedio general del mercado

*Volumen decreciente*

El volumen promedio sectorial es menor al volumen promedio global

*Precio aún en ascenso*

El precio promedio actual es mayor que el de la semana anterior

La combinación de estas tres condiciones define un estado de fatiga de tendencia.

## 🔧 Consulta SQL

El análisis se construye en dos pasos:
- Normalización de métricas diarias
- Rango diario ajustado por precio
- Volumen
- Precio de cierre
- Agregación sectorial y filtros de fatiga

El resultado final devuelve únicamente los sectores que muestran agotamiento interno pese a precios elevados.

Output esperado

Para cada sector identificado, se obtiene:
- sector
- volatilidad_actual → rango diario promedio normalizado
- vol_actual → volumen promedio reciente
- Estos sectores deben considerarse zonas de alto riesgo, no oportunidades de continuación.

## 💼Valor de negocio

⚠️ Alerta temprana de reversión

🧠 Identificación de burbujas locales antes del colapso

📉 Mejora del timing en salidas de posiciones largas

🛡️ Gestión de riesgo en estrategias momentum

Especialmente útil para:
- Trading cuantitativo
- Gestión de portafolios sectoriales
- Sistemas de alertas automáticas
- Prevención de drawdowns abruptos

## ⚠️Advertencias

Este indicador no es una señal de venta directa, sino una señal de riesgo

Funciona mejor combinado con:
- Divergencias de momentum (RSI)
- Estructura de mercado
- Eventos macro o corporativos

## ✒️Conclusión

El Índice de Fatiga de la Tendencia no busca predecir el techo exacto, sino detectar cuándo una tendencia deja de ser confiable.
En mercados, sobrevivir suele ser más importante que acertar —y este insight está diseñado exactamente para eso.

## 👤Autora
Flavia Hepp Proyecto de SQL aplicó un análisis de riesgo basado en eventos.
