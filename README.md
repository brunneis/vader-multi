# VADER Sentiment Analysis Multilanguage
VADER (Valence Aware Dictionary and sEntiment Reasoner) is a lexicon and rule-based sentiment analysis tool that is specifically attuned to sentiments expressed in social media.

> This version integrates the Google Translate API through the `translatte` Python library. It requires an active Internet connection in order to work. Text language is automatically detected so it behaves exactly like the original version.

## Installation
Uninstall first the original version so it is not instantiated instead of vader-multi:
```bash
pip uninstall vaderSentiment
pip install vader-multi
```

## Polarity Scores
### `class vaderSentiment.SentimentIntensityAnalyzer`
#### `polarity_scores(text)`
Returns a dictionary with the following keys: `{'neg': float, 'neu': float, 'pos': float, 'compound': float}`

```python
from vaderSentiment.vaderSentiment import SentimentIntensityAnalyzer

analyzer = SentimentIntensityAnalyzer()
analyzer.polarity_scores("VADER is smart, handsome, and funny.")
```

## Examples
```python
>>> from vaderSentiment.vaderSentiment import SentimentIntensityAnalyzer

>>> analyzer = SentimentIntensityAnalyzer()

>>> analyzer.polarity_scores("VADER is VERY SMART, handsome, and FUNNY!!!")
{'neg': 0.0, 'neu': 0.233, 'pos': 0.767, 'compound': 0.9342}

>>> analyzer.polarity_scores("¡¡¡VADER es MUY INTELIGENTE, guapo y DIVERTIDO!!!")
{'neg': 0.0, 'neu': 0.27, 'pos': 0.73, 'compound': 0.9387}

>>> analyzer.polarity_scores("VADER è MOLTO INTELLIGENTE, bello e DIVERTENTE!!!")
{'neg': 0.0, 'neu': 0.256, 'pos': 0.744, 'compound': 0.9481}

>>> analyzer.polarity_scores("VADER est TRÈS SMART, beau et drôle!!!")
{'neg': 0.0, 'neu': 0.276, 'pos': 0.724, 'compound': 0.9338}

>>> analyzer.polarity_scores("Вейдер очень умный, красивый и смешной!!!")
{'neg': 0.0, 'neu': 0.314, 'pos': 0.686, 'compound': 0.8989}

>>> analyzer.polarity_scores("ベイダーは非常にスマートで、ハンサムで面白いです!!!")
{'neg': 0.0, 'neu': 0.328, 'pos': 0.672, 'compound': 0.882}

>>> analyzer.polarity_scores("வேடர் மிகவும் ஸ்மார்ட், அழகான மற்றும் வேடிக்கையானது!!!")
{'neg': 0.0, 'neu': 0.314, 'pos': 0.686, 'compound': 0.8989}
```
