# Chat con Gemini (Google Generative AI)

Este script en Python permite interactuar con un modelo de lenguaje de Google Gemini usando la API de `google.generativeai`.

## Ejecutar en Google Colab

Haz clic en el siguiente botón para ejecutar este script en Google Colab:

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1e2GrY9cXbkKevw4JtXRPMuwUtcocrA8E#scrollTo=vgfmWywbV0b9)

## Requisitos

- Python 3.7 o superior
- Biblioteca `google-generativeai`

Puedes instalar la librería requerida con:

```bash
pip install google-generativeai
```

## Configuración

1. Obtén tu clave de API desde [Google AI Studio](https://makersuite.google.com/app).
2. Reemplaza la línea correspondiente con tu clave:

```python
genai.configure(api_key="TU_CLAVE_API")
```

> ⚠️ **No compartas tu clave API en repositorios públicos.**

## Uso

El script selecciona el modelo `gemini-2.0-flash-lite-001` y lanza un bucle de conversación por consola.

### Ejecución

```bash
python nombre_del_script.py
```

### Ejemplo de conversación

```
¡Hola! Soy un modelo de lenguaje. Escribe 'salir' para terminar.
Tú: ¿Qué es Python?
Modelo: Python es un lenguaje de programación versátil y fácil de aprender...
```

## Estructura del código

- **Configuración del modelo:**
  Se inicializa el modelo Gemini usando tu clave API.
- **Función `chat_with_gemini(prompt)`:**
  Envía el texto ingresado por el usuario y retorna la respuesta generada por el modelo.
- **Bucle de conversación:**
  Permite al usuario interactuar continuamente con el modelo hasta escribir "salir".

## Notas

- Puedes cambiar el modelo (`gemini-2.0-flash-lite-001`) por otro compatible según tus necesidades.
- La respuesta se obtiene con `generate_content(prompt)` y se accede vía `response.text`.

---

© 2025 | Script de demostración para interacción con modelos Gemini de Google.
