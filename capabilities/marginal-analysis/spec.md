Purpose
This workbook decides how much tomatoes, carrots, and mescluns to plant
Inputs
Tomato_Bed_Cap: 20 beds (Source: Stage 1.1 table)
Carrot_Bed_Cap: 20 beds (Source: Stage 1.1 table)
Mesclun_Bed_Cap: 30 beds (Source: Stage 1.1 table)
Tomato_Revenue_Per_Bed: $8,800 per bed (Source: Stage 1.1 table)
Carrot_Revenue_Per_Bed: $2,094 per bed (Source: Stage 1.1 table)
Mesclun_Revenue_Per_Bed: $2,700 per bed (Source: Stage 1.1 table)
Tomato_Field_Hours: 2.5 hours per week per bed (Source: Stage 1.1 table)
Carrot_Field_Hours: 0.833 hours per week per bed (Source: Stage 1.1 table)
Mesclun_Field_Hours: 1.25 hours per week per bed (Source: Stage 1.1 table)
Tomato_Fertilizer_Per_Bed: $880 per bed (Source: Stage 1.1 table)
Carrot_Fertilizer_Per_Bed: $440 per bed (Source: Stage 1.1 table)
Mesclun_Fertilizer_Per_Bed: $880 per bed (Source: Stage 1.1 table)
Tomato_Diminishing_Rate: 10% (Source: Stage 1.1 table)
Carrot_Diminishing_Rate: 2.5% (Source: Stage 1.1 table)
Mesclun_Diminishing_Rate: 1.25% (Source: Stage 1.1 table)
Season_Weeks: 36 weeks (Source: Stage 2 page 2)
Own_Labor_Hours: 720 hours (Source: Stage 2 page 2)
Own_Labor_Rate: $34.72 per hour (Source: Stage 2 page 2)
Temp_Labor_Rate: $17.36 per hour (Source: Perfect Competition - Decision Analysis Table)
Structure
Inputs: holds the 19 input names, values, and sources used by the workbook
Beds: holds the bed counts for tomatoes, carrots, and mescluns
Fertilizer: holds cost per bed
Revenue: holds price per crop
Field_Hours: holds hours
Checks: shows whether bed and labor limits are met
Labor: calculates the total labor hours needed for each crop
Labor_Cost: shows the total money spent on labor
Marginal_Cost: shows the extra cost of adding a bed compared with the revenue that bed earns
Optimization: shows the best bed mix that gives the highest profit
Calculation Logic
Tomato_Hours_Used = Tomato_Beds_Planted x Tomato_Field_Hours x Season_Weeks x (1 + Tomato_Diminishing_Rate)^Tomato_Beds_Planted
Carrot_Hours_Used = Carrot_Beds_Planted x Carrot_Field_Hours x Season_Weeks x (1 + Carrot_Diminishing_Rate)^Carrot_Beds_Planted
Mesclun_Hours_Used = Mesclun_Beds_Planted x Mesclun_Field_Hours x Season_Weeks x (1 + Mesclun_Diminishing_Rate)^Mesclun_Beds_Planted
Total_Field_Hours_All = Tomato_Hours_Used + Carrot_Hours_Used + Mesclun_Hours_Used
Farmer's hours: Maximum 720 hours, but if the farm needs less than 720 hours, the farmer can work all those hours
Temporary workers' hours: If the farm needs more than 720 hours, temporary workers cover the remainder
Tomato_Fertilizer_Cost = Tomato_Beds_Planted x Tomato_Fertilizer_Per_Bed
Carrot_Fertilizer_Cost = Carrot_Beds_Planted x Carrot_Fertilizer_Per_Bed
Mesclun_Fertilizer_Cost = Mesclun_Beds_Planted x Mesclun_Fertilizer_Per_Bed
Total_Fertilizer_Cost = Tomato_Fertilizer_Cost + Carrot_Fertilizer_Cost + Mesclun_Fertilizer_Cost
Tomato_Revenue = Tomato_Beds_Planted x Tomato_Revenue_Per_Bed
Carrot_Revenue = Carrot_Beds_Planted x Carrot_Revenue_Per_Bed
Mesclun_Revenue = Mesclun_Beds_Planted x Mesclun_Revenue_Per_Bed
Total_Revenue = Tomato_Revenue + Carrot_Revenue + Mesclun_Revenue
Total_Own_Cost = Own_Hours_Used x Own_Labor_Rate
Total_Temp_Cost = Temp_Hours_Used x Temp_Labor_Rate
The blended labor rate is calculated by dividing the total labor cost by the total labor hours
Total_Profit = Total_Revenue - Total_Fertilizer_Cost - Total_Own_Cost - Total_Temp_Cost
Checks
The Checks sheet shows whether own hours and temp hours stay within their limits
The total number of tomato, carrot, and mesclun beds planted must not exceed 64 beds
Each crop has its own maximum number of beds: tomatoes is 20 beds, carrots is 20 beds, and mesclun is 30 beds
The farm can use a maximum of 4 temporary workers
The number of beds planted for each crop must be a whole number
Marginal Cost
The Marginal Cost shows the cost for each added bed
Optimization
The Optimization sheet shows the best bed mix that gives the highest profit.
Excel solver is used to find the best bed mix of tomato, carrot, and mesclun beds that produces the highest profit while following the farm's limits 
Excel solver will use the GRG Nonlinear solving method to find the most profitable mix of crops
Excel solver will be tested at two different starting points. The first test: 0 tomato beds, 0 carrot beds, and 0 mesclun beds. The second test: 20 tomato beds, 0 carrot beds, and 0 mesclun beds.
The model's best mix is 10 tomato beds, 20 carrot beds, and 30 mesclun beds.
The best mix gives total profit of $62,775.16.
My hypothesis was 16 tomatoes, 20 carrots, and 28 mescluns, but the model's best mix is 10 tomatoes, 20 carrots, and 30 mescluns. 
Tomatoes changed from 16 to 10 because the added tomatoes cost more with labor pay and fertilizer compared to $8,800 revenue per bed.
