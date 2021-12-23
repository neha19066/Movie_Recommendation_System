# Movie Recommendation System
As a part of Data Mining course at IIITD a movie recommendation system built using Association Rule Mining.

Contributors:
Neha Goel                                          
Raghav Nakra

Problem statement can be found in DMG_Assignment_2.pdf.

#### Part 1.
Performed exploratory data analysis on the dataset to spot NaN values, movies with no genres, find frequency distribution of various columns and print correlation matrices between numerical columns.


#### Part 2.
To recommend four movies that a user would watch based on the movies they have already watched, we did the following:

For rule mining, we took each itemset to be the set of all movies watched by a single user. Then the itemsets were one-hot encoded. Using the Fp-Growth algorithm, frequent itemsets with minimum support of 10% were filtered. Then rules were created using lift for score evaluation.

We sorted the rules in descending order of lift. For every input we got in the form of movies previously watched by a user we first tried to find an exact match from the antecedents in the rules. If that did not give us four consequent movies to recommend, we tried to find a subset of the input which might be an antecedent and further recommend their consequents. If still more movies need to be recommended, we find rules whose antecedents are supersets of the input and recommend their consequents.

Some cases still might not be covered by any rules. For such cases, we found movies of similar genre and recommended the highest user rated movies from them.
 
 
#### Part 3.
A partial visualisation of the FP tree’s maximal frequent itemsets using graphviz. We took at most 10 maximal itemsets only for each level of the FP tree. Since the visualization is partial, the incomplete edges would be incorrect, hence, we haven’t shown them. By removing the hard-coded upper limit of 10, we can show the entire tree. The itemsets displayed were movieIds. The visualization can be found in g1.dot.
