# Housing Price Prediction with Vertex AI  

## 1. Project Overview  
Built a housing price prediction model using **Vertex AI AutoML regression**, enabling real-time property valuation and replacing slow manual methods.  

## 2. Business Problem  
- **Pain Point:** Real estate valuation is often manual, time-consuming, and inconsistent across agents.  
- **Existing Methods:** Traditional SPSS/SQL workflows require hours of cleaning, feature engineering, and manual modeling, making them unscalable for quick decision-making.  
- **Opportunity:** An automated ML solution that can predict housing prices instantly, increasing accuracy and efficiency for lenders, brokers, and investors.  

## 3. Solution   
- **Tools Used:** Vertex AI (AutoML Regression), Cloud Storage, Cloud Shell, JSON API calls.
1. **Data Prep**: Uploaded CSV dataset into GCS bucket.
2. **Model Training**: Used Vertex AI AutoML Tabular (regression mode).
   - AutoML tested multiple algorithms (linear, boosted trees, DNNs).
   - Automated hyperparameter tuning & evaluation.
3. **Model Registry**: Best model stored in Vertex Model Registry.
4. **Deployment**: Deployed model as an endpoint in Vertex AI.
5. **Prediction**: Created a sample `input.json` and fetched predictions using:
   - `gcloud ai endpoints predict`
   - Python SDK (`predict.py`)

## 4. Input and Output example

Input:
```json
{
  "Square_Footage": "1500",
  "Num_Bedrooms": "3",
  "Num_Bathrooms": "2",
  "Year_Built": "2005",
  "Lot_Size": "0.75",
  "Garage_Size": "1",
  "Neighborhood_Quality": "4"

}
```

Output:
```
{
  "predictions": [
    {
      "value": 347485.43,
      "upper_bound": 367028.31,
      "lower_bound": 329450
    }
  ]
}
```

## 5. Screenshots
📎 [View full project screenshots (PDF)] [Predictive analytics.pdf](https://github.com/user-attachments/files/23121742/Predictive.analytics.pdf)

