# What can a homeowner do to improve their sale price?

For this project, I am pretending that I am advising homeowners, specifically in Ames, Iowa, who want to improve the sale value of their home through home improvement and diy projects.  The most pertinent question is this:  What projects can I spend my limited resources on that will improve my home's value so that I can profit from its sale?  In short, what projects will give me the most bang for my buck?

The process begins by cleaning the data, sourced from here (https://www.kaggle.com/c/dsir-202021214-e-project-2-regression-challenge/data), examining outliers and adjusting nulls.  The training data was over 2051 rows long, and the given 80 columns made it a little too feature rich to be really malleable. Thus, I limited my scope to under 40 columns.  I engineered a couple interaction terms, as well as one-hot encoded a feature concerning masonry veneer.  The target variable in this scenario is the Sale Price of the house.


I built four models:  the first was a simple linear regression, unscaled and and unregularized.  The second, a linear regression model with standard scaling applied to the features.  Third and fourth, a Lasso and a Ridge model.  Of all these, the basic linear model performed the best on the testing data.  All the models had r2 scores over 80, and better on the side of the testing data, but the linear one was the most reliable.  The scaled model performed better by an extremely small margin, so in the interest of simplicity I did not rely upon it. I then examined the coefficients and relationships of the features that could be improved by a homeowner, such as garage quality and condition, porch square footage and type, and general property condition.

## In Conclusion
Ultimately, I found that a homeowner has limited ability to improve the sale price on their own.  The general condition of their home can help avoid a bankrupting low price, but going beyond the average standards for condition and quality do not greatly increase value.  As such, my recommendation is to make sure your home meets those average standards, and not to spend much of your money making the condition and quality of your home exceptional.  This way, you have the best chance of the best return on your investment.
In the future, if I were to take this model into production, I would take time to include more of the features provided by the original dataset, and I would also hope to get similar housing data from other small cities throughout the midwest.  As it stands, the model would only be useful in Ames, Iowa, but the tool would be more useful if it could be applied more generally to different places.

## Notebook
https://git.generalassemb.ly/sehyeager/project_2/blob/master/Samuel-yeager-Code.ipynb

## Dictionary
| Key             | Description                                                            |
|-----------------|------------------------------------------------------------------------|
| ID              | Identifying Number for the Property                                    |
| Lot Frontage    | Linear feet of street connected to property                            |
| Lot Area        | Lot size in square feet                                                |
| Overall Qual    | Rates the overall material and finish of the house                     |
| Overall Cond    | Rates the overall condition of the house                               |
| Year Built      | Original construction date                                             |
| Year Remod/Add  | Remodel date (same as construction date if no remodeling or additions) |
| Mas Vnr Type    | Masonry veneer type                                                    |
| Bsmt Qual       | Evaluates the height of the basement                                   |
| Bsmt Cond       | Evaluates the general condition of the basement                        |
| Tot Bsmt Sf     | Total square feet of basement area                                     |
| 1st Flr SF      | First floor square footage                                             |
| 2nd Flr SF      | Second floor square footage                                            |
| Low Qual Fin Sf | Low Quality Finished Square Feet                                       |
| Bsmt Full Bat   | Full bathrooms in the basement                                         |
| Bsmt Half Bath  | Half bathrooms in the basement                                         |
| Full Bath       | Full bathrooms above ground                                            |
| Half Bath       | Half bathrooms above ground                                            |
| Bedroom         | Bedrooms above ground (does NOT include basement bedrooms)             |
| Kitchen         | Kitchens above ground                                                  |
| Kitchen Qual    | Overall quality of the kitchens                                        |
| TotRmsAbvGrd    | Total rooms above grade (does not include bathrooms)                   |
| Fireplaces      | Total number of fireplaces                                             |
| Fireplace Qu    | Quality of fireplaces                                                  |
| Garage Cars     | Size of garage in car capacity                                         |
| Garage Area     | Size of garage in square feet                                          |
| Garage Qual     | Quality of garage                                                      |
| Garage Cond     | Condition of garage                                                    |
| Wood Deck Sf    | Wood deck area in square feet                                          |
| Open Porch SF   | Open porch area in square feet                                         |
| Enclosed Porch  | Enclosed porch area in square feet                                     |
| 3-SSn Porch     | Three season porch area in square feet                                 |
| Screen Porch    | Screen porch area in square feet                                       |
| Pool Area       | Pool area in square feet                                               |
| Pool QC         | Pool quality                                                           |
| SalePrice       | Sale price of the property                                             |

## Sources
http://jse.amstat.org/v19n3/decock/DataDocumentation.txt
## Presentation
https://youtu.be/R91M-vR9Fe0