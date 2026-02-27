# ♟️ Chess Opening Suggestion & Blunder Prediction

A machine learning project that suggests the best chess openings based on player style and predicts potential blunders during a game — helping players improve their chess strategy and avoid costly mistakes.

---

## ✨ Features

### 🎯 Opening Suggestion
- Recommends the best chess openings based on player ELO rating
- Classifies openings from game PGN data
- Trained on real chess game data

### ⚠️ Blunder Prediction
- Predicts whether a move is likely to be a blunder
- Analyzes board positions using Stockfish engine evaluation
- Uses player ELO and position features to assess move quality

---

## 📁 Project Structure

```
ML/
├── src/
│   ├── features.py        # Feature extraction from board positions
│   ├── preprocessing.py   # Data cleaning and preparation
│   ├── train.py           # Model training
│   ├── predict.py         # Blunder & opening predictions
│   └── elo.py             # ELO rating utilities
├── models/
│   ├── blunder_model.pkl          # Trained blunder prediction model
│   └── chess_opening_model.pkl    # Trained opening suggestion model
├── data/raw/
│   ├── positions.csv      # Chess position dataset
│   └── sample_game.pgn    # Sample game in PGN format
├── blunder.ipynb          # Full ML pipeline notebook
├── app.py                 # App entry point
└── requirements.txt       # Python dependencies
```

---

## ⚙️ Setup Instructions

### Step 1: Clone the Repository

```bash
git clone https://github.com/PramodyaKarunathilake/Chess_OpeningSuggestion_BlunderPrediction.git
cd Chess_OpeningSuggestion_BlunderPrediction
```

### Step 2: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 3: ⚠️ Download Stockfish (Required for Blunder Prediction)

The Stockfish chess engine is **not included** in this repository due to its large file size. You must download it manually.

**Steps:**
1. Go to the official Stockfish website: https://stockfishchess.org/download/
2. Download the version for your operating system:
   - **Windows:** `stockfish-windows-x86-64-avx2.exe`
   - **Mac/Linux:** Download the appropriate binary
3. Place the file in this exact path inside the project:

```
backend/engine/stockfish/stockfish-windows-x86-64-avx2.exe
```

> **Note for Mac/Linux users:** Update the Stockfish path inside `app.py` to match your binary's location.

---

## 🚀 How to Run

### Option 1: Run the Jupyter Notebook (Recommended)

This walks through the full ML pipeline — data loading, feature extraction, training, and prediction:

```bash
jupyter notebook blunder.ipynb
```

### Option 2: Train the Models

```bash
cd ML
python src/train.py
```

### Option 3: Run Predictions

```bash
cd ML
python src/predict.py
```

---

## 🤖 How the Models Work

### Opening Suggestion Model
- Takes player ELO and past game history as input
- Classifies and recommends the most suitable opening (e.g. Sicilian Defense, Queen's Gambit)
- Trained using a Random Forest classifier on PGN game data

### Blunder Prediction Model
- Extracts board features from each position
- Uses Stockfish engine to evaluate position scores
- Predicts if a move drops the evaluation significantly (a blunder)

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| ML Models | Python, scikit-learn, pandas |
| Chess Engine | Stockfish |
| Data Format | PGN, CSV |
| Notebook | Jupyter |

---

## 📌 Requirements

- Python 3.x
- Jupyter Notebook
- Stockfish chess engine (downloaded separately — see setup above)
- All pip packages listed in `requirements.txt`

---

## 👩‍💻 Author

**Pramodya Karunathilake**  
[GitHub](https://github.com/PramodyaKarunathilake)
