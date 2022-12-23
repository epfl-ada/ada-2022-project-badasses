# It’s a beer’s, beer’s, beer’s world

*A project by Louis, Aurelien, Donglin and Benjamin.*

Hey there! 😈😈😈😈😈😈😈

Check out our data story [here](https://aureliensoenen.github.io/ADA_RateBeer.github.io/)!!!

The main supporting notebook is `Supporting Notebook.ipynb`. We've also left our milestone 2 and another data exploration work in respective folders for reference.

## Goal:
What if we re-arranged the world through beer taste? What would be the map resulting from it? What countries will be linked per their beer’s love? Can natural enemies become friends over a nice cold beverage?

This project will have two phases: the first will be to find the best method to compute the favorite beer style per country, and the second to reassemble them according to the latter results.

For the first one, we will analyze several ways to find, and try to be as accurate as possible with the dataset given: we plan to try various methods and libraries to generate the results, and compare the resultings insights we find, and hopefully tell an awesome, easy-to-follow story using a combination of maps and statistics.

Then, we will use those various methods to cluster the different countries, and observe the new world beer map!

## Research Questions:
1. What is the favorite style of beer per country?
2. What happens if we draw the world’s boundaries using beer preferences?

## How we intend to work towards answering the questions:

**What’s the best way to determine each country’s beer preferences?**
1. Work out the best parameters for cleaning and filtering the data
    - Two thresholds seem unskippable to make analysis over country : the number of users per country to have a sufficient representative sample, and the number of ratings per user to be a reliable source of information as citizen’s taste. 
    - We study the sensibility of the 2 thresholds onto the data and try to find a compromise : best pecision will still have sufficient data to make the analysis.
    - if number of country too low after filtering, we consider the sub-region of the world to be able to make further analysis
2. Identify each country’s favorite beer style:
    - For each set of beer reviews corresponding to users from one country, calculate the mean rating for each beer style and identify the beer style with the highest mean ratings
    - Is every user’s rating “worth” the same? We  observe the results with weighted users based on their number and non-binarity (0 or 20 ratings)
    - Again, we do the analysis of the top styles of beer per location (country and sub-region)
3. Visualize these preferences on a map:
    - To have the best visualization, we show on a interactive map the evolution of top style of beer in time, and try to interpret the results.

**What happens if we draw the world’s boundaries using beer preferences?**
1. Clustering by favorite beer styles
    - We can join together the boundaries of adjacent countries which share the same favorite beer styles, thereby creating subregions/clusters.
    - If data sparsity is not an issue, we can try performing this visualization over different periods of time to understand how these clusters have been changing.
2. Clustering by average beer preferences
    - We can construct vectors for each country, where values represent the average ratings for each beer style, and cluster countries by either euclidean distance or cosine similarity.
    - We can simplify these vectors using scikit-learn’s PCA library to transform each vector into a two dimensional space, and plot the resulting clusters in a way that is easier to visualize.
3. Analysis of clusters
    - Depending on the results, we might be able to identify how clusters with similar beer preferences may share other similar characteristics (e.g. proximity to the coast, influence from particular countries through colonialism, climate etc.)

## Additional dataset:

[Dataset of the geographical coordinates of each country’s centroid](https://github.com/lukes/ISO-3166-Countries-with-Regional-Codes/blob/master/all/all.csv)

[world_vis0.geojson](https://gist.github.com/Retsediv/0e40bcbf41e0bfb2c49963bf4a5dd9fd?short_path=5978422)

## Organization within the team:
For milestones one and two we decided to split the work into two sub-teams, in order to benefit from the efficiency of teamwork and to work in parallel. Each sub-team is responsible for doing its own part of the work, and we meet regularly with the whole group to share our progress, methods and discuss the next steps to be taken. This allows us to provide feedback to each other while working on the same topic.

For milestone 3, we divided the work into four parts, each working on their part individually and after a few days we got together to find out what had been done and what was left to do. Then we divided the work again so that we could finish the work with our datastory in time. 

Overall, the work was divided up as follows:
- Benjamin Lim: Clustering of countries
- Dangling Ruan: Map of the best beers
- Aurélien Soenen: Making the site, time analysis
- Louis Van Den Abbeele: Users analyses and interactive plots

## Notes on running the code
- The main notebook is found in `Supporting Notebook.ipynb`.
- Some blocks have been commented out to reduce the filesize of the notebook to be within the limits of Github uploads
- Some raw data has been omitted from the repository, but can be directly imported from the original raw data source for RateBeer reviews. This is due to the file sizes being > 100 MB.
