Analysis of Chemical Components Project Proposal Created by: MTE

Review the following project proposal, which outlines the details of this project.
Project Description Buying new cosmetic products is difficult.
 It can even be scary for those who have sensitive skin and are prone to skin trouble. The information needed to alleviate this problem is on the back of each product, but it's tough to interpret those ingredient lists unless you have a background in chemistry. Instead of buying and hoping for the best, we can use data science to help us predict which products may be good fits for us. In this Project, you are going to create a content-based recommendation system where the 'content' will be the chemical components of cosmetics. Specifically, you will process ingredient lists for 1472 cosmetics on Sephora via word embedding, then visualize ingredient similarity using a machine learning method called t-SNE and an interactive visualization library called Bokeh.ProjectTasks•1. Cosmetics, chemicals... it's complicated•2. Focus on one product category and one skin type•3. Tokenizing the ingredients•4. Initializing a document-term matrix (DTM)•5. Creating a counter function•6. The Cosmetic-Ingredient matrix!•7. Dimension reduction with t-SNE•8. Let's map the items with Bokeh•9. Adding a hover tool•10. Mapping the cosmetic items•11. Comparing two products

Task1:InstructionsImport and inspect the dataset.

•Import pandas aliased as pd and numpy as np. Import TSNE from sklearn.manifold.
•Read the CSV file, "datasets/cosmetics.csv", into a pandas Data Frame and name it df.
•Display a sample of five rows of the data using the sample() method insidethe display() function.
•Display counts of types of product using the value_counts() method on the Label columnof df.

Task2:InstructionsFilter the data for moisturizers and dry skin.

•Filter df for "Moisturizer" in the Label column and store the result in moisturizers.
•Filter moisturizers for 1 in the Dry column and store the result in moisturizers_dry.
•Drop the current index of moisturizers_dry and replace it with a new one usingthe reset_index() method, setting drop = True.

Task3:InstructionsTokenize the ingredients and create a bag of words.

•Inside the outer for loop:
•Make each product's ingredients list lowercase.
•Split the lowercase text into tokens by specifying ', ' as the separator.
•Append tokens (which itself is a list) to the list corpus.
•Inside the inner for loop, if the ingredient is not yet in ingredient_idx dictionary:
•Add an entry to ingredient_idx with the key being the new ingredient and thevalue being the current idx value.
•Increment idx by 1.

Task4:InstructionsInitialize a document-term matrix.
•Get the total number of products in the moisturizers_dry DataFrame. Assign it to M.
•Get the total number of ingredients in the ingredient_idx dictionary. Assign it to N.
•Create a matrix of zeros with size MxN. Assign it to A.

Task5:InstructionsCreate a function named oh_encoder.

•Initialize a matrix of zeros with width N (i.e., the same width as matrix A).
•Get the index values for each ingredient from ingredient_idx.•Put 1 at the corresponding indices.•Return the matrix x.

Task6:InstructionsGet the binary value of the tokens for each row of the matrix A.

•Inside the for loop:
•Apply oh_encoder() to get a one-hot encoded matrix for each listof tokens in corpus (i.e., each product's ingredients list).
•Increment i by 1.

Task7:InstructionsReduce the dimensions of the matrix using t-SNE.

•Create a TSNE instance with n_components = 2, learning_rate = 200,and random_state = 42. Assign it to model.
•Apply the fit_transform() method of model to the matrix A. Assign the resultto tsne_features.
•Assign the first column of tsne_features to moisturizers_dry['X'].
•Assign the second column of tsne_features to moisturizers_dry['Y'].

Task 8: InstructionsPlot a scatter plot with the vectorized items.

•Create a ColumnDataSource with moisturizers_dry. Assign it to source.
•Label the x-axis as T-SNE 1 and the y-axis as T-SNE 2.
•Add a circle renderer using plot.circle(), setting x = 'X', y = 'Y', and source tothe ColumnDataSource you created.

Task 9: InstructionsAdd a hover tool.

•Set the tooltips argument to ('Item', '@Name'), ('Brand','@Brand'), ('Price', '$@Price'), and ('Rank', '@Rank').
•Add the new hover object to the plot.

Task 10: InstructionsDisplay the plot.

•Use the show() function to display the plot.

Task 11: InstructionsPrint out the ingredients for two similar products.

•Run the cell as is to print out the data and ingredients for Color Control Cushion CompactBroad Spectrum SPF 50+ and BB Cushion Hydra Radiance SPF 50.

Dataset and Jupiter Notebook Files -Download from link below
https://drive.google.com/uc?export=download&id=1-OBlj1fTfFwciscLKIZIvWbIeHwBUzif
