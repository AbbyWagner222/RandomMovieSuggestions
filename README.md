Goal: to create a random movie recommendation for when I have no idea what to watch

Inputs used:
1. A csv file with movies that you like. For me, I used the csv created in my letterboxd Year Comparisons project which includes films I've seen that were at or above my 3rd quartile rating.
2. A csv with random film titles and their overviews

What the code does:
A film that you like is chosen at random. Using the imdb python library, the name of the film is queried into the imdb database to find the id, which is used to find the summary.
The TfidfVectorizer is used from scikit-learn library to create a matrix based on the words in the summaries of movies in the random film title csv and the random film that you like.
A similarity matrix is then used to compare each film summary to each other. From this, the films with the highest similarity score to the film you like can returned.

What you get back:
A list of suggestions that are similar to a film that you've liked in the past. 

Notes: the formatting of the two csvs used matters. In this case, the movies you like csv should have a 'Name" column. The random movies csv should have a "title' and a 'overview' column.

Next steps:
I plan to use this more regularly, swapping out my list of films I've liked as these interests change and the random movies csv as I find better data sets with more/different movies. 
I hope to iron out some of the errors (e.g. if a movie that I like is already in  the random movie list, if a movie is not found on imdb with the title its listed under on my liked movie list, etc.).
A potential next direction could be looking up films by same director of liked movie or weighting the films in the random movie list differently if I'm able to search their imdb ratings.
