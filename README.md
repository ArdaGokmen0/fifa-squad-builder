# FIFA Player Selection Analysis — Budget-Constrained Youth Squad Builder

This project uses FIFA player data to build a budget-constrained youth football squad.

The goal is to create a 15-player squad under a €100M transfer budget and €600K weekly wage limit while prioritizing young, high-potential players.

## Project Objective

A fictional football club needs to build a squad from available player data.

The squad structure is:

- 11 Starting XI players
- 4 bench players
- Starting XI: 1 GK, 4 DEF, 3 MID, 3 ATK
- Bench: 1 GK, 1 DEF, 1 MID, 1 ATK

## Dataset

The dataset contains FIFA player information, including:

- Player name
- Age
- Nationality
- Club
- Position
- Overall rating
- Potential rating
- Market value
- Weekly wage
- Technical attributes

## Data Cleaning

The `Value` and `Wage` columns were originally stored as text values such as:

- `€110.5M`
- `€565K`

These values were converted into numeric columns:

- `Value_Num`
- `Wage_Num`

This made it possible to calculate transfer costs, wage costs, and budget constraints.

## Methodology

This project uses a rule-based recommendation system rather than a machine learning model.

Players are evaluated using:

- Current overall rating
- Potential rating
- Age
- Position group
- Market value
- Weekly wage
- Squad role
- Remaining transfer budget
- Remaining wage budget

Players are grouped into four position categories:

- GK
- DEF
- MID
- ATK

The final squad builder first selects a balanced squad using a scoring system, then uses an emergency filler step to complete missing squad roles if needed.

## Final Result

The final squad satisfies the main project constraints:

- Transfer budget used: approximately €99.2M / €100M
- Weekly wage used: approximately €230K / €600K
- Squad size: 15 players
- Missing positions: 0

## Visualizations

The notebook includes visualizations for:

- Position group distribution
- Transfer budget usage
- Weekly wage budget usage

## Strengths

- Builds a complete 15-player squad
- Respects the transfer budget
- Respects the wage limit
- Prioritizes young and high-potential players
- Maintains position balance
- Uses a clear rule-based selection logic

## Limitations

- The model does not account for real-life transfer negotiations.
- Player preference, club prestige, and league difficulty are not included.
- Some low-overall players may be selected due to budget constraints.
- The scoring system is rule-based and includes subjective weights.
- A more advanced optimization algorithm could improve squad quality.

## Future Improvements

Possible improvements include:

- Position-specific scoring formulas
- Better budget allocation by role
- Advanced optimization algorithms
- Team chemistry scoring
- League and club prestige factors
- Player resale value estimation
- Interactive dashboard with Streamlit or Gradio

## Tools Used

- Python
- Pandas
- Matplotlib
- Jupyter Notebook
- VS Code

## Project Type

Data Analysis / Rule-Based Recommendation System
test