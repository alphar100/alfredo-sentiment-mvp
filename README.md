# Alfredo Sentiment MVP (Streamlit)

**Objetivo:** Buscar un ticker y obtener la lectura de sentimiento a corto plazo con datos de X (Twitter) y Reddit.
Guarda un historial agregado para evaluar en el futuro la precisión frente al precio.

## Cómo correr

```bash
cd /mnt/data/alfredo_sentiment_mvp
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt

python -c "import nltk; nltk.download('vader_lexicon')"
streamlit run app.py
```

## Variables de entorno (para datos reales)

Crea un archivo `.env` con:

```
# X (Twitter) API v2
X_BEARER_TOKEN=xxxxx

# Reddit (PRAW)
REDDIT_CLIENT_ID=xxxxx
REDDIT_CLIENT_SECRET=xxxxx
REDDIT_USER_AGENT=alfredo-mvp/0.1
```

Si no configuras APIs, la app usa **datos de muestra** (`sample_data.json`).

## Roadmap

- Integrar precios (Yahoo Finance/Polygon) y correlacionar score vs. precio.
- Backtesting con ventanas móviles (24h/7d).
- Ponderación por fuente/influencia.
- Detección de idioma (ES/EN) y normalización.
- Panel de calidad de señal por ticker.
