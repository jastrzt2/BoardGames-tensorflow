### Description

The aim of this project is to extend the analysis of the [Board Game Number of Voters Prediction](https://github.com/jastrzt2/BoardGames-Analysis) by finding the optimal neural network architecture.  
I developed and tested five simple neural networks, with training configured for a maximum of 5000 epochs and an early stopping patience of 1000 epochs. The high patience value was intentionally chosen to ensure that each architecture has sufficient time to learn effectively.  
The best-performing model was selected and trained with a scheduled learning rate to help it escape local minima and find globally better solutions.

### Preprocessing

Before training, I applied preprocessing steps based on my earlier analysis of the dataset, which included excluding outliers, processing columns, and splitting the dataset.

### Project Structure

The project consists of two Jupyter notebooks: one for training neural networks and the second for loading models and using them for prediction on the test subset. Both notebooks use the `bg_info.csv` dataset.


### Results

Below is a table comparing the performance of the neural network models with the best prediction results obtained using Random Forest and Gradient Boosting:

| Model                                | RMSE on test  |  
|--------------------------------------|---------------|  
| 2 Hidden Layers                      | 208.2         |  
| 4 Hidden Layers                      | 202.8         |  
| 5 Hidden Layers                      | 201.3         |  
| 6 Hidden Layers                      | 186.3         |  
| 8 Hidden Layers                      | 210.4         |  
| 6 Hidden Layers with scheduled lr    | 214.1         |  
| Best Random Forest                   | 233.1         |  
| Best Gradient Boosting               | 225.9         |

The best results were achieved by a simple model with just 6 hidden layers and 504 hidden neurons in total. This model significantly outperformed both the Random Forest and Gradient Boosting models based on RMSE. Other architectures were slightly better than the two aforementioned models.
