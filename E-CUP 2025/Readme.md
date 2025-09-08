## This is my solution for E-CUP 2025 OZON competition in recommendation track

# This is more light version of my ideas)

This code implements a simple recommendation system for the Ozon platform based on historical data (interaction tracker, orders, items, and categories). It:

Loads and processes data, filtering popular items and determining time frames for train/val.
Builds interaction matrices and trains models: ALS for collaborative filtering, BM25 for item-to-item, Annoy for embedding search.
Generates candidates for users (blend of ALS, I2I, KNN by embeddings), adding features (popularity, categories, similarity).
Optionally reranks candidates with CatBoost (if available), otherwise uses blended score.
Outputs top-100 recommendations for test users, supplementing with top-popular if necessary, and saves to CSV file.
