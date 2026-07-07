# Netflix-content-Recommender
A content-based recommendation engine that suggests similar Netflix titles based on genre, cast, director, and description — built as part of an AI/Data Science internship task. 
How It Works

The system treats each title's metadata as a "bag of features" and measures similarity between titles using text-vector math — no user ratings or watch history needed, which makes it a pure content-based filtering approach.

Pipeline:


Feature Preparation — Combine genres, type, director, cast, and description into a single text field per title. Genres are weighted more heavily since they matter most for "similar content."
Vectorization (TF-IDF) — Convert the combined text into numerical vectors using TfidfVectorizer, which down-weights common words and highlights distinctive terms.
Similarity Scoring — Compute pairwise cosine_similarity between every title's vector to build a full similarity matrix.
Recommendation Generation — For a selected title, rank all other titles by similarity score and return the top 5.
Evaluation — Score recommendation quality using a genre-overlap metric (% of top-5 results sharing at least one genre with the source title) and average similarity score.
