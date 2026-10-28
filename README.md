# Recipe Recommendation System

A small web app that suggests recipes based on the nutrition targets, tastes and restrictions you enter. It builds a prompt from the fields you fill in and asks Google's Gemini model, through LangChain, for detailed recipes for 5 dishes.

## Features

- **Nutrition targets:** calories, fat, carbohydrates, protein and fiber
- **Preferences:** veg / non-veg, preferred cuisine, preferred ingredients, meal type (breakfast, lunch, dinner, snack) and cooking time
- **Dietary restrictions:** ingredients to leave out
- Only the fields you fill in are sent to the model
- Simple [Streamlit](https://streamlit.io/) interface

## Tech stack

Python · Streamlit (UI) · LangChain (prompt and chain) · Google Generative AI (`gemini-1.0-pro`)

## Getting started

```bash
git clone https://github.com/Zahid9966/Recipie-Recommendation-System.git
cd Recipie-Recommendation-System
pip install -r requirements.txt
export GOOGLE_API_KEY="your_key_here"
streamlit run app.py
```

## API key

The app needs a Google Generative AI key. Create one in [Google AI Studio](https://aistudio.google.com/) and provide it in **one** of these ways (checked in this order):

1. an environment variable: `export GOOGLE_API_KEY="your_key_here"`
2. a `.env` file next to `app.py` containing `GOOGLE_API_KEY=your_key_here` (the file is git-ignored)
3. a Streamlit secret named `GOOGLE_API_KEY` (for example on Streamlit Community Cloud: Settings → Secrets)

Never commit your key to the repository. If the key is missing, the app shows an error instead of starting.

## Notes

- The model name in `app.py` is `gemini-1.0-pro`. Google retires older model names over time, so if the app reports a model error, update the name to a current Gemini model.
- Recipes are AI-generated. Check allergens, ingredients and nutrition values yourself before cooking.

## Project files

| File | Purpose |
|---|---|
| `app.py` | The Streamlit app |
| `requirements.txt` | Python dependencies |
| `img.jpg`, `backimg.jpg` | Image files kept in the repository (not referenced by the current `app.py`) |
