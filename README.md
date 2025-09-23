# Cricket Score Predictor

This project is a **Cricket Score Predictor** that forecasts the final first innings score of a T20 cricket match. Using match-specific data such as the batting and bowling teams, the current score, balls left, wickets remaining, and recent scoring trends, the predictor provides an estimated final score.

The model is accessible through an interactive **Streamlit web app**, where users can input relevant match data and get instant predictions.

## Dataset

The model is trained on a comprehensive dataset of historical T20 cricket matches. Each record in the dataset captures crucial in-game details that influence the final score prediction. Here's a snapshot of the dataset structure:

| batting_team | bowling_team | city     | current_score | balls_left | wickets_left | crr   | last_five | runs_x |
| ------------ | ------------ | -------- | ------------- | ---------- | ------------ | ----- | --------- | ------ |
| West Indies  | New Zealand  | Auckland | 123           | 3          | 4            | 6.31  | 43.0      | 126    |
| England      | Pakistan     | London   | 64            | 83         | 8            | 10.38 | 55.0      | 185    |

### Features in the Dataset:

- **batting_team**: The team currently batting.
- **bowling_team**: The team currently bowling.
- **city**: The venue where the match is being played.
- **current_score**: The number of runs scored by the batting team so far.
- **balls_left**: The number of balls remaining in the innings (120 balls in total in a T20 match).
- **wickets_left**: The number of wickets remaining for the batting team.
- **crr** (Current Run Rate): The current run rate of the batting team, calculated as runs per over.
- **last_five**: The number of runs scored in the last 5 overs, indicating the recent momentum of the batting team.
- **runs_x**: The actual final score achieved by the batting team, which is used as the target variable for training the model.

## Web Application

You can interact with the **Cricket Score Predictor** using the user-friendly **Streamlit web app**:

[**Try the Web App Here**](https://aayush-dhattarwal-t20-cricket-score-prediction-app-68tiqn.streamlit.app/)

## Dataset

https://www.kaggle.com/datasets/veeralakrishna/cricsheet-a-retrosheet-for-cricket?select=t20s

## How It Works

The **Cricket Score Predictor** leverages this historical data to predict the final score for the first innings of a T20 match. The model is trained using features such as:

- **Current Runs**: The total runs scored so far.
- **Wickets Left**: The number of remaining wickets.
- **Balls Left**: The number of balls remaining in the innings.
- **Current Run Rate (CRR)**: The run rate the batting team is currently maintaining.
- **Runs Scored in Last 5 Overs**: Helps account for recent momentum in the match.
- **Venue/City**: The city or stadium where the match is being played, which could influence the scoring pattern due to pitch conditions.

By combining these inputs, the model provides a reliable estimate of the final score.

## Features

- **Real-Time Predictions**: Get instant predictions of the final score as the match progresses.
- **Customizable Input Fields**: Users can input the batting team, bowling team, venue, current score, balls left, wickets left, and recent runs scored.
- **Momentum Factor**: The "runs scored in the last 5 overs" field helps the model account for sudden shifts in scoring momentum.

## Model Performance

The model was trained and evaluated on a test set of T20 matches and demonstrates excellent predictive performance:

| Metric                    | Value                                |
| ------------------------- | ------------------------------------ |
| Mean Absolute Error (MAE) | **1.64 runs**                        |
| R-squared (R²)            | **0.9877**                           |
| Accuracy                  | High across various match conditions |

## How to Use the Web App

1. Select the batting and bowling teams.
2. Choose the city where the match is being played.
3. Input the current score, balls left, wickets out, and runs scored in the last 5 overs.
4. Click **Predict Score** to get the projected final score.

## Future Enhancements

- **Second Innings Prediction**: Add functionality to predict scores in the second innings.
- **Live Data Integration**: Integrate live match data from APIs to provide real-time predictions without manual input.
- **Additional Features**: Include more features like weather conditions, player form, and team rankings to enhance prediction accuracy.
