# SignalFusion Ultimate v3.0

**Indicador avanzado de TradingView** que combina múltiples estrategias con sistema de puntuación, doble confirmación, soportes/resistencias dinámicos y adaptación automática por timeframe.


## Características principales

- **Modos de trading adaptativos**: Conservative • Standard • Aggressive
- **Detección automática de timeframe** con parámetros optimizados (1m, 5m, 15m, 30m, 1h, 2h, 4h+)
- **Sistema de scoring balanceado** (RSI + EMAs + Bollinger + MACD + volumen)
- **Doble confirmación** configurable para evitar señales falsas
- **Soportes y Resistencias dinámicos** con conteo de toques y limpieza automática
- **Gestión de SL/TP** basada en ATR (multiplicadores por modo)
- **Filtros avanzados**: horario, volumen, volatilidad, tendencia principal, ATR mínimo
- **Tabla informativa compacta** con scores, posición actual, SL/TP y más
- **Alertas nativas** con precio, SL y TP

## Modos de operación

| Modo          | Señales | Riesgo | Multiplicador umbral | SL (más ancho) | TP (más conservador) |
|---------------|---------|--------|-----------------------|----------------|-----------------------|
| Conservative  | Pocas   | Bajo   | ×1.3                  | ×1.2           | ×0.9                  |
| **Standard**  | Balance | Medio  | ×1.0                  | ×1.0           | ×1.0                  |
| Aggressive    | Muchas  | Alto   | ×0.75                 | ×0.85          | ×1.3                  |

## Requisitos

- TradingView (web o app)
- Pine Script **versión 6**
- Recomendado: timeframes entre **1 minuto y 4 horas**

## Instalación (cómo añadirlo a TradingView)

1. Abre **TradingView** → ve a la parte inferior → pestaña **Pine Editor**
2. Borra cualquier código que esté ahí
3. Copia y pega todo el contenido del archivo [`SignalFusion_Ultimate_v3.0.pine`](SignalFusion_Ultimate_v3.0.pine)
4. Haz clic en **Add to Chart** (o el botón con el símbolo +)
5. ¡Listo! Ya deberías ver las EMAs, señales y la tabla en la esquina superior derecha.

## Cómo usarlo – Configuración recomendada

### Principiantes / Menor riesgo
```text
Modo Trading     → Conservative
Require double confirmation → ON
Confirmation bars      → 2–3
Balance de Señales     → Balanced
Mostrar Señales        → ON
Mostrar SL/TP lines    → ON
Mostrar Info Debug     → ON (al principio)
Filtro de Tendencia    → ON (si operas en tendencia)

Day Trading / Scalping (1m–15m)
Modo Trading     → Standard o Aggressive
Require double confirmation → OFF o 1 barra
Balance de Señales     → Balanced o Long/Short Bias según mercado
Filtro Volumen         → ON (1.3–1.6)
Filtro Volatilidad     → ON (1.1–1.3)

Swing / Posicional (1h–4h)
Modo Trading     → Conservative o Standard
Require double confirmation → ON (2–4 barras)
Filtro de Tendencia    → ON (EMA 200)
Mostrar S/R lines      → ON

Alertas (cómo configurarlas)

Haz clic derecho en el gráfico → Add Alert
Condition → selecciona SignalFusion Ultimate v3.0
Elige: LONG Signal o SHORT Signal
Mensaje sugerido:text
Recomendaciones importantes
{{strategy.order.alert_message}}
Ticker: {{ticker}}
Precio: {{close}}
SL: {{plot_0}}   TP: {{plot_1}}

No uses el indicador solo. Combínalo con análisis de estructura, noticias y gestión de riesgo.
En timeframes muy bajos (1m–5m) → activa filtro de volumen y volatilidad.
En cripto o activos volátiles → prueba modo Conservative + doble confirmación.
Revisa la tabla de debug para entender por qué se genera o no una señal.
Las líneas S/R se limpian automáticamente (máximo configurable).



Contribuciones
¡Son bienvenidas! Si encuentras mejoras, bugs o quieres añadir funcionalidades (por ejemplo: backtesting integrado, más filtros, integración con volumen profile, etc.), abre un issue o un pull request.

Última actualización: febrero 2026
Versión del indicador: 3.0
Creado con ♥ para la comunidad de TradingView
text
