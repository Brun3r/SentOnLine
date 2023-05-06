# Análisis de sentimiento de comentarios en línea

import nltk
from nltk.sentiment.vader import SentimentIntensityAnalyzer

# Cargar el conjunto de datos de comentarios
comentarios = [
  "¡Me encantó esta película, definitivamente la recomiendo!",
  "No me gustó mucho esta serie, me pareció aburrida",
  "La atención al cliente de esta compañía es excelente",
  "No volvería a comprar en esta tienda, el servicio es muy malo"
]

# Crear una instancia del analizador de sentimientos
sia = SentimentIntensityAnalyzer()

# Analizar cada comentario y determinar su sentimiento
for comentario in comentarios:
  resultado = sia.polarity_scores(comentario)
  if resultado['compound'] > 0.5:
    print(comentario + " - Sentimiento positivo")
  elif resultado['compound'] < -0.5:
    print(comentario + " - Sentimiento negativo")
  else:
    print(comentario + " - Sentimiento neutral")
