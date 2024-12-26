# Movie Recommendation System Project 🎥

This project focuses on building a Recommendation System for movies recommendations. The dataset includes **9742 movies** and **610 users**. The goal is to build a recommendation system using both **content-based filtering** and **collaborative filtering** techniques, and compare the results of multiple algorithms, such as **NMF**, **SVD**, **Item-Item Collaborative**, and **User-User Collaborative** filtering.

Additionally, a **weighted average** method was implemented to calculate the top 10 movies based on implicit ratings derived from user preferences, interaction data (clicks, views, etc.), and explicit ratings provided by the user.

---

## 📝 Problem Statement  
Build an end-to-end recommendation system for movie recommendations using content-based filtering and collaborative filtering techniques. The system aims to suggest relevant movies to users based on their previous interactions and movie features (content). The system also includes hybird based filtering for best recommendation systems and a weighted average method for determining the top movies based on implicit and explicit ratings.

---

## 🔍 Steps Followed  

### 1️⃣ Understanding the Dataset  
- The dataset includes **9742 movies** and **610 users**, with interaction data (ratings, views, etc.) between users and movies.  
- Cleaned the data by removing **users with fewer than 100 interactions** and **movies with fewer than 10 interactions** to focus on **active users** and **engaged items**.  

### 2️⃣ Data Preprocessing  
- **Text Cleaning**: Cleaned movie descriptions by converting text to lowercase, removing stopwords and punctuation, and performing lemmatization.  
- **TF-IDF Vectorization**: Applied **TF-IDF** on the movie descriptions for content-based filtering to capture the important features for recommendation.  

### 3️⃣ Recommendation System Models  

#### **Recommendation System Models**:  
- **Weighted Average Filtering** method was implemented to determine the **top 10 movies** based on weighted average ratings. 
- **Content-Based Filtering** Calculated similarity between specific movie and all other movies to get most similar content on result of tf_idf.  
- **Item-Item Collaborative Filtering**: Calculated similarity between items (movies) based on user interactions.  
- **User-User Collaborative Filtering**: Calculated similarity between users based on their interaction history.  
- **Hybrid Model**: Combined content-based filtering and user-user collaborative filtering with a weight of 0.7 for user-user.  


### 4️⃣ Matrix Factorization Techniques  

#### **NMF (Non-Negative Matrix Factorization)**:  
- Applied NMF to decompose the user-item interaction matrix, capturing latent features for users and items.  
- Evaluated the model using **Mean Squared Error (MSE)** for reconstruction.  

#### **SVD (Singular Value Decomposition)**:  
- Used SVD to perform matrix factorization and predict missing ratings based on latent factors.  
- Evaluated using **MSE** for model performance.  

### 5️⃣ Results  

| **Model**                     | **Top 5 Recommendations**                                                                                         | **Similarity with User Preferences**                                                                                           | **Relevance to User's Actual Likes**                                                  |
|-------------------------------|--------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|
| **Content-Based Filtering**   | *Jean de Florette (1986)*, *Secrets & Lies (1996)*, *Unbearable Lightness of Being (1988)*, *Lone Star (1996)*, *All About My Mother (1999)*  | Focuses on item characteristics (genre, director, actors), works well for suggesting similar content.                         | **Low** relevance to user's actual tastes, recommendations are more **artsy/foreign** films. |
| **Item-Item Collaborative**   | *Matrix, The (1999)*, *Breakfast Club, The (1985)*, *Trainspotting (1996)*, *There's Something About Mary (1998)*, *As Good as It Gets (1997)* | Finds similar items based on users’ interactions, mostly **action** and **comedy**.                                               | **Moderate** relevance, some **action/comedy** overlap but not as focused on **drama**. |
| **User-User Collaborative**   | *Matrix, The (1999)*, *Shawshank Redemption (1994)*, *Pulp Fiction (1994)*, *Forrest Gump (1994)*, *Silence of the Lambs (1991)* | Focuses on **user profiles** and finds similar users to suggest movies.                                                           | **High** relevance, recommendations like *Pulp Fiction* align with user's **drama** preference. |
| **Hybrid (Content + User-User)** | *Matrix, The (1999)*, *Shawshank Redemption (1994)*, *Pulp Fiction (1994)*, *Forrest Gump (1994)*, *Silence of the Lambs (1991)* | Combines content-based and collaborative filtering, balancing **genre-based** and **user similarity**.                            | **High** relevance, provides a mix of **action**, **comedy**, and **drama** films.  |
| **NMF (Matrix Factorization)** | *Matrix, The (1999)*, *Aliens (1986)*, *Blade Runner (1982)*, *Star Wars: Episode V* (1980), *Memento (2000)*       | Focuses on **latent factors** for both users and items. Skewed towards **action** and **sci-fi** genres.                        | **Moderate** relevance, some overlap with **sci-fi** but missing user's preference for **drama**. |
| **SVD (Matrix Factorization)** | *Matrix, The (1999)*, *Breakfast Club, The (1985)*, *Trainspotting (1996)*, *There's Something About Mary (1998)*, *Big Lebowski (1998)* | Similar to NMF, finds latent factors but focused more on **action** and **comedy**.                                              | **Moderate** relevance, similar to NMF, with a **comedy** and **action** focus. |

---

#### 6️⃣ Types of Usage  
- **Weighted Average Filtering** method was implemented to determine the **top 10 movies** based on implicit ratings (derived from user interactions such as clicks, views, time spent on the website, and movie length) and explicit ratings provided by users.  
- **Content-Based** filtering is used if the user has clicked on a movie (e.g., based on movie features).  
- **Collaborative Filtering** is used if the user has interacted with at least **100 items** (views, movie length, number of clicks, time on the website). This interaction data is used to calculate implicit ratings, which are then factored into the weighted average to recommend movies.


---

## 🔧 Tools and Libraries  
- **Python**: Pandas, NumPy, Scikit-learn, NMF, SVD, Matplotlib, Seaborn.  
- **Models**: Content-based Filtering, Item-Item Collaborative Filtering, User-User Collaborative Filtering, NMF, SVD.  
- **Evaluation Metric**: Mean Squared Error (MSE).  

---


## 🎯 Conclusion  
- The hybrid recommendation model (combining content-based and user-user collaborative filtering) provides the most relevant recommendations with a balanced approach.  
- **User-User Collaborative Filtering** and **Hybrid Models** are well-suited for the user preferences, especially for **classic dramas** and **thrillers**.  
- Further improvements can be made by tuning the model and exploring **advanced matrix factorization techniques** like **ALS (Alternating Least Squares)** for better performance.
