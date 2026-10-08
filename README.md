# 🎬 Movie Recommender

> **A hybrid movie recommendation system that combines your personal preferences with the behavior of similar viewers to discover movies you'll love.**

🌐 **Live Demo:** [Movie Recommender](https://movierecommender-mu.vercel.app/)

---

## 📌 Overview

**Movie Recommender** is a web-based recommendation system designed to help users discover movies based on their individual tastes.

Instead of relying on a single recommendation technique, the application combines two approaches:

* 🎭 **Content-Based Filtering** — analyzes movie characteristics such as genres and mood/intensity.
* 👥 **Collaborative Filtering** — finds viewers with similar movie-rating patterns and uses their preferences to generate recommendations.

These signals are combined into a **hybrid recommendation score**, producing a ranked list of movies tailored to the user's preferences.

---

## ✨ Features

### 🎭 Personalized Genre Preferences

Users can tune their movie preferences using interactive controls.

The system currently allows users to adjust preferences such as:

* Adventure
* Romance
* Comedy
* Intensity

These preference values are used to build the user's **taste profile**.

### ⭐ Movie Ratings

Users can rate movies they have watched.

These ratings provide the collaborative filtering system with information about the user's preferences and help identify viewers with similar tastes.

### 🧠 Hybrid Recommendation Engine

The recommendation engine combines multiple signals to produce the final ranking:

```text
                 ┌─────────────────────┐
                 │   User Preferences  │
                 │ Genres / Mood       │
                 └──────────┬──────────┘
                            │
                            ▼
                  ┌──────────────────┐
                  │ Content-Based    │
                  │ Filtering        │
                  └────────┬─────────┘
                           │
                           │
                           ▼
                     ┌─────────────┐
                     │   HYBRID    │
                     │   SCORING   │
                     └──────┬──────┘
                            │
                           ▲
                           │
                  ┌────────┴─────────┐
                  │ Collaborative    │
                  │ Filtering        │
                  └────────┬─────────┘
                           │
                           ▼
                  ┌──────────────────┐
                  │ Similar Viewers  │
                  │ & Ratings        │
                  └──────────────────┘
```

The final recommendations are ranked using a combination of both approaches.

### ⚡ Instant Preference Updates

Preference controls update the user's taste profile instantly, allowing the recommendation model to respond dynamically to changes.

### 📊 Recommendation Ranking

Movies are ranked according to the combined hybrid score, allowing the highest-scoring recommendations to appear first.

### 🔄 Reset Preferences

The application provides a reset option to quickly clear the current filters and start over.

---

## 🧠 How It Works

The system follows a hybrid recommendation approach.

### 1. Define Your Taste

The user selects or adjusts preferred genres and other preference signals.

For example:

```text
Adventure  → 65
Romance    → 20
Comedy     → 35
Intensity  → 65
```

These values form the user's preference vector.

---

### 2. Content-Based Filtering

The content-based component compares the user's preference vector with movie metadata.

Conceptually:

```text
User Taste Vector
       ↓
Movie Metadata
       ↓
Similarity Calculation
       ↓
Content Score
```

Movies whose characteristics are closer to the user's preferences receive higher scores.

---

### 3. Collaborative Filtering

The collaborative filtering component analyzes the movies rated by the user.

It searches for other viewers whose rating patterns are similar.

```text
User Ratings
     ↓
Find Similar Viewers
     ↓
Analyze Their Highly-Rated Movies
     ↓
Collaborative Score
```

This allows the system to recommend movies that the user may not have explicitly selected but that similar viewers enjoyed.

---

### 4. Hybrid Scoring

The final recommendation combines both signals:

```text
Hybrid Score
     =
Content-Based Score
     +
Collaborative Score
```

The movies are then ranked according to the resulting score.

This approach attempts to balance:

**"Movies that match your preferences"**

with

**"Movies liked by people with similar tastes."**

---

## 📊 Recommendation Pipeline

```text
              USER INPUT
                  │
        ┌─────────┴─────────┐
        │                   │
        ▼                   ▼
 Genre / Mood           Movie Ratings
 Preferences                 │
        │                    │
        ▼                    ▼
 Content-Based       Collaborative
    Filtering           Filtering
        │                    │
        └─────────┬──────────┘
                  │
                  ▼
           Hybrid Scoring
                  │
                  ▼
          Ranked Recommendations
                  │
                  ▼
             🎬 Movies
```

---

## 🛠️ Technology

The application is deployed as a web application and uses a recommendation-engine approach centered around content similarity and collaborative filtering.

### Core Concepts

* Content-Based Recommendation
* Collaborative Filtering
* Hybrid Recommendation Systems
* User Preference Vectors
* Similarity Scoring
* Movie Metadata
* Recommendation Ranking

### Deployment

The application is deployed using **Vercel**.

🌐 **Live Application:**
https://movierecommender-mu.vercel.app/

---

## 🎯 Example Use Case

Imagine a user prefers:

```text
Adventure  → 80
Romance    → 20
Comedy     → 40
Intensity  → 70
```

The user then rates several movies.

The system can:

1. Build a profile based on the selected preferences.
2. Compare that profile against available movies.
3. Analyze the user's movie ratings.
4. Find viewers with similar rating patterns.
5. Identify movies enjoyed by those viewers.
6. Combine the content and collaborative signals.
7. Rank the movies.
8. Display the highest-scoring recommendations.

---

## 📂 Project Structure

A typical structure for the project can be documented as:

```text
movie-recommender/
│
├── public/
│
├── src/
│   ├── components/
│   ├── data/
│   ├── utils/
│   └── ...
│
├── package.json
├── README.md
└── ...
```

> Update the structure above if your repository uses different folders or files.

---

## 🚀 Getting Started

### Prerequisites

Make sure you have the required development environment installed.

```bash
git
Node.js
npm
```

### Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

```bash
cd movie-recommender
```

### Install Dependencies

```bash
npm install
```

### Run the Development Server

```bash
npm run dev
```

The application should then be available on the local development server.

---

## 🌐 Live Demo

Try the application here:

👉 **https://movierecommender-mu.vercel.app/**

---

## 🔮 Future Improvements

Some possible improvements for future versions include:

* 🔐 User authentication and persistent profiles
* 💾 Saving user ratings and preferences
* 🎬 Larger movie catalog
* 🎯 More detailed movie attributes
* 🤖 More advanced recommendation algorithms
* 📈 Recommendation performance analytics
* ⭐ User watchlists
* ❤️ Favorite movie collections
* 🔍 Movie search and filtering
* 📱 Improved mobile experience
* 🧠 Deep-learning-based recommendation models
* 🎞️ Integration with movie databases such as TMDB
* 🔄 Continuous personalization based on user interactions

---

## ⚠️ Limitations

The current application uses a limited active movie catalog, so recommendations are constrained by the movies available to the recommendation engine.

The quality of collaborative recommendations also depends on the amount and quality of available rating data.

As more user interaction data becomes available, the collaborative filtering component can potentially produce more meaningful recommendations.

---

## 👨‍💻 Author

**Spidey**

Built with ❤️ for movie lovers and recommendation-system enthusiasts.

---

## ⭐ Support

If you found this project interesting, consider giving the repository a ⭐ on GitHub!

---

## 📄 License

This project is available under the license specified in the repository.
