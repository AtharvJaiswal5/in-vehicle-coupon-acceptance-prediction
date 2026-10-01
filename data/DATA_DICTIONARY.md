# Data dictionary

One row is a survey scenario response. There are 25 input columns and one target. Category bands are preserved as recorded; do not infer exact ages or incomes from band labels. Fields are based on the UCI description and observed CSV names.

| Column | Meaning / representation |
|---|---|
| destination | Driving destination: home, work, or no urgent place |
| passanger | Passenger category (source spelling retained) |
| weather | Weather category |
| temperature | Scenario temperature: 30, 55 or 80 (source page does not explicitly label the unit) |
| time | Scenario time of day |
| coupon | Type of offered coupon |
| expiration | Expiry: 2 hours (`2h`) or 1 day (`1d`) |
| gender | Reported gender category |
| age | Reported age band/category, including `below21` and `50plus` |
| maritalStatus | Reported marital status |
| has_children | Child indicator (0/1) |
| education | Education category |
| occupation | Occupation category |
| income | Income band |
| car | Sparse vehicle description; excluded when over 90% missing in training |
| Bar | Monthly bar visit frequency |
| CoffeeHouse | Monthly coffeehouse visit frequency |
| CarryAway | Monthly takeaway frequency |
| RestaurantLessThan20 | Monthly visits to restaurants costing under $20 per person |
| Restaurant20To50 | Monthly visits to restaurants costing $20–$50 per person |
| toCoupon_GEQ5min | Indicator for a coupon location at least 5 minutes away; constant in this dataset |
| toCoupon_GEQ15min | Indicator for a coupon location at least 15 minutes away |
| toCoupon_GEQ25min | Indicator for a coupon location at least 25 minutes away |
| direction_same | Coupon location is in the same direction as the destination |
| direction_opp | Opposite-direction indicator; redundant with direction_same |
| Y | Target: stated acceptance (1), decline (0) |

Visit-frequency categories: `never`, `less1`, `1~3`, `4~8`, and `gt8`; missing values are explicitly imputed inside the modelling pipeline. The two direction columns are retained for source fidelity; their redundancy can divide permutation importance. No respondent ID is available.
