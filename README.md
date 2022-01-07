# eCommerce-User-Behavior-Analysis
#### Abstract
As an online e-commerce platform or, any merchandiser in this digitalized era, being able to identify the high-value customers and the pattern of this group of people is key to a profitable business. And not only for the high-value groups, but a deep-dive user behavior analysis can also help with segmenting customers into different groups based on relative dimensions more accurately and for better-personalized ad contents. 

While there are quite a few approaches for user clusterings, for instance, the RFM model, which will be covered later in this report, there seems a lack of utilization of such findings. For instance, how to understand the churn properly and how to reduce it. Companies usually apply a re-engagement strategy accordingly based on different types of churns, basically reaching out to customers by email with some recovery promotions or new customers incentives. But with deep dive into the churn group, the analysis can tell what’s the activity churn, i.e. how many customers became inactive this month. In this way, a more efficient impact can be made in a timely manner. When it comes to eCommerce, a lower price at the first glance is attractive for new customer acquisition, but store owner needs to balance between promotion and branding. Limitless sales can only harm the business as well as the market as a whole.

From this online grocery store user behavior dataset, we wanted to find out:
1. If there is a specific pattern of users’ purchasing behavior. The dataset contains information such as user_id, category_code, event_type, event_time, etc. 
2. If there is a relation between the number of orders made by users and the event_time of the “purchase” event_type. What would be the most active time period of the day for this store?
3. The dataset is rich for helping us to classify the users into different groups. For instance, which type of users would be the core value customers of the store, and which group of customers would be the churns.
4. The brand and category fields can be applied for association rules. We can apply the apriori model to see what itemsets are within the top popular buys.

#### Methodology
Briefly, we applied four approaches to tackle the aforementioned issues. To define the users’ purchasing behavior, we applied the AARRR model to see all five stages for this online store. For instance, in the first letter “A” which stands for acquisition, we divided by date and to see the new customers acquired for each day. The event_type field of this dataset is helpful to calculate the conversion rate between each event type. From the time dimensions of the DateTime value, we divided the data by week, date, and hour, to find if there are any specific patterns on purchasing, viewing, and the click rate. To define segments for users, we applied the RFM model, which calculates recency, frequency, and monetary scores separately in the first place, and then sum up all three scores and obtain a total score. Customers can then be filtered by this final score into different groups. Lastly, to see if there’s any association among items, we applied the Apriori rule with tested minimum support value, minimum confidence value, and the minimum length required for each itemset. We assume that these approaches are reasonable to analyze this eCommerce grocery store.

#### Coding Steps

###### Part I - RFM Model

1. As the column information shows that columns &quot;category\_code&quot;, &quot;brand&quot;, and &quot;user\_session&quot; contain missing values, which impacts the dataset as a whole for further analysis. We decided to first drop all NaN values for both datasets.
2. Union the two data frames as the raw data
3.
  - Drop unnecessary columns
  - create a new data frame
  - query only the purchase event type
  - Convert event\_time to DateTime
4. Aggregate data by user\_session
5. RFM analysis - recency, frequency, and monetary calculation
6. RFM data description
7. Apply RFM user segmentation
8. Define user segmentation
9. Visualization of RFM user segmentation

###### Part II - Apriori Model

1. 
  a. Generate a new data frame for Apriori analysis only
  b. Split the category\_code column by the period, &#39;.&#39;, and create a new column named items
  c. Create a new data frame for user\_id and items
2. Find the frequency of the items bought
3. Visualize the frequency of the items bought
4.
  a. Create a new data frame with event\_time added
  b. Group the data frame by user\_id and event\_time, and concatenate the items bought
5. Apply apriori model with:
    1. Min\_support = 0.005: so that the itemset occurs in 0.5% of the transactions.
    2. Min\_confidence = 0.2: so that we know 20% of the times a customer also bought such item before and after.
    3. Min\_length = 2: so the least number of items that a rule should have is 2.
6. Display all the RelationRecord of the association rule.
