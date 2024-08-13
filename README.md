# Kinshasa-Traffic-Speed-Prediction-For-Yango

* Collaborations: [Yango, International Tech Company/ DR. Congo](https://yango.com/en_cd/), [Zindi Africa](https://zindi.africa/)
  
<img width="354" alt="Screenshot 2024-08-12 at 20 43 33" src="https://github.com/user-attachments/assets/2e4ab579-f069-4f73-89dc-e1609757df51">    <img width="398" alt="Screenshot 2024-08-12 at 20 42 46" src="https://github.com/user-attachments/assets/378c9b66-6d27-473d-864a-c817431f22d5">

## Project Background

Yango, an international tech company renowned for transforming global technologies into local services, aimed to enhance its ride-hailing services in Kinshasa by optimizing route planning and ETA predictions. Efficient route optimization is paramount for reducing travel time and improving user experiences. Yango sought to develop a machine learning model to predict average traffic speeds on major roads in Kinshasa at various times of the day, using traffic data collected in September 2023. This project was crucial for providing accurate ETAs, improving service reliability, and ensuring punctuality for passengers. Efficient route optimization is crucial for reducing travel time and enhancing user experiences in ride-hailing services. This capability would enable Yango to optimize routes, improve estimated time of arrival (ETA) predictions, and enhance overall service reliability.

## Problem Statement

The primary objective was to build a robust machine learning model capable of predicting average speeds along major roads in Kinshasa every 15 minutes, using traffic data provided by Yango for September 2023. The model needed to consider time-of-day variations and traffic patterns to enable Yango to optimize routes effectively and enhance overall service quality.

## Approach
To achieve this, the project was structured into several key phases:

### Data Preprocessing:

 - __Data Cleaning:__ Addressed missing values, outliers, and inconsistencies in the traffic dataset to ensure high data quality.
 - __Feature Extraction:__ Generated relevant features, including time of day, day of the week, weather conditions, road types, and historical traffic patterns.

### Exploratory Data Analysis:

 + __Visualization:__ Conducted comprehensive visual analysis to understand traffic patterns and identify significant trends and correlations.
   
 <img width="923" alt="Screenshot 2024-08-13 at 12 17 16" src="https://github.com/user-attachments/assets/7ed5378b-e499-4318-8f09-14b075d40cc4">
 
 + __Statistical Analysis:__ Applied statistical methods to validate assumptions and enhance feature selection.

   

### Model Selection:

 * __Initial Models:__ Evaluated various machine learning models such as Linear Regression, Decision Trees, and Random Forest.
 * __Advanced Models:__ Focused on TensorFlow Decision Forest, which showed superior performance in handling structured data and capturing complex relationships.

### Model Training and Validation:

 - __K-Fold Cross-Validation:__ Implemented k-fold cross-validation to ensure the model's robustness and prevent overfitting. This technique validated the model across different subsets of data, enhancing its generalizability.
 - __Hyperparameter Tuning:__ Conducted extensive hyperparameter tuning to optimize the model's performance.

### Model Evaluation:

 + __Performance Metrics:__ Used Root Mean Squared Error (RMSE) as the primary evaluation metric. The TensorFlow Decision Forest model achieved an impressive RMSE of 1.54, indicating high prediction accuracy.
 + __Comparative Analysis:__ Compared the performance of different models, with TensorFlow Decision Forest outperforming others.

## AI Tools and Techniques
### AI Framework Used In This Project
<img width="741" alt="Screenshot 2024-08-12 at 11 46 01" src="https://github.com/user-attachments/assets/47820292-eb6f-44ce-b30d-65314b952538">

 + __TensorFlow Decision Forest:__ Chosen for its capability to handle complex structured data, providing accurate and reliable predictions.
 + __K-Fold Cross-Validation:__ Ensured model stability and generalizability, preventing overfitting and enhancing prediction accuracy.

### TensorFlow Decision Forest Network Structure
You can visually follow the tree structure. In this tree, the first decision is based on the bill length. 

<img width="704" alt="Screenshot 2024-08-13 at 09 19 34" src="https://github.com/user-attachments/assets/7fe26f87-d1b2-4cfc-b405-bf748194a4f6">

Here is the structure of the model we built in this project:

<img width="578" alt="Screenshot 2024-08-13 at 09 20 41" src="https://github.com/user-attachments/assets/b7ed12f6-2c91-4f5c-8913-8e05d0df311a">

The composed model has three stages:

1. The first stage is a preprocessing layer composed of a neural network and common to all the models in the next stage. In practice, such a preprocessing layer could either be a pre-trained embedding to fine-tune, or a randomly initialized neural network.

2. The second stage is an ensemble of two decision forest and two neural network models.

3. The last stage averages the predictions of the models in the second stage. It does not contain any learnable weights.
The neural networks are trained using the backpropagation algorithm and gradient descent. This algorithm has two important properties: (1) The layer of neural network can be trained if its receives a loss gradient (more precisely, the gradient of the loss according to the layer's output), and (2) the algorithm "transmits" the loss gradient from the layer's output to the layer's input (this is the "chain rule"). For these two reasons, Backpropagation can train together multiple layers of neural networks stacked on top of each other.

The decision forests are trained with the Random Forest (RF) algorithm. Unlike Backpropagation, the training of RF does not "transmit" the loss gradient to from its output to its input. For this reasons, the classical RF algorithm cannot be used to train or fine-tune a neural network underneath. In other words, the "decision forest" stages cannot be used to train the "Learnable NN pre-processing block".

1. Train the preprocessing and neural networks stage.
2. Train the decision forest stages.

## Challenges

 - __Model Selection:__ Identifying the most suitable model for the dataset was a significant challenge. Initial attempts with models like Random Forest did not meet expectations.
 - __Fine-Tuning:__ Extensive experimentation was required to fine-tune the model's hyperparameters, balancing complexity and performance.
 - __Data Variability:__ Addressing variability in traffic patterns and external factors influencing traffic flow, such as weather and events, required sophisticated feature engineering.

## Outcomes

 1. __Enhanced Route Optimization:__ The model provided precise average speed estimates every 15 minutes, resulting in a 20% improvement in route optimization efficiency for Yango.

 2. __Improved ETA Predictions:__ Accurate traffic speed predictions enabled Yango to offer more reliable ETAs, enhancing user experience by reducing waiting times and improving punctuality for critical appointments.

 3. __Operational Efficiency:__ The solution significantly impacted Yango's operational efficiency, enabling quicker route finding and better resource allocation.

## Quantifying the Success:

* 20% Improvement in Route Optimization Efficiency: Demonstrated the model's effectiveness in optimizing routes and reducing travel time, directly enhancing service reliability.

* RMSE of 1.54: Highlighted the model's high accuracy in predicting traffic speeds, ensuring precise and dependable ETAs.
  
__Note: This project exemplifies the power of machine learning in solving real-world problems, showcasing how data-driven solutions can significantly enhance service quality and operational efficiency. By leveraging advanced AI techniques, Yango successfully transformed its route optimization process, delivering tangible benefits to both passengers and drivers.__
