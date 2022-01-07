# eCommerce-User-Behavior-Analysis
As an online e-commerce platform or, any merchandiser in this digitalized era, being able to identify the high-value customers and the pattern of this group of people is key to a profitable business. And not only for the high-value groups, but a deep-dive user behavior analysis can also help with segmenting customers into different groups based on relative dimensions more accurately and for better-personalized ad contents. 

While there are quite a few approaches for user clusterings, for instance, the RFM model, which will be covered later in this report, there seems a lack of utilization of such findings. For instance, how to understand the churn properly and how to reduce it. Companies usually apply a re-engagement strategy accordingly based on different types of churns, basically reaching out to customers by email with some recovery promotions or new customers incentives. But with deep dive into the churn group, the analysis can tell what’s the activity churn, i.e. how many customers became inactive this month. In this way, a more efficient impact can be made in a timely manner. When it comes to eCommerce, a lower price at the first glance is attractive for new customer acquisition, but store owner needs to balance between promotion and branding. Limitless sales can only harm the business as well as the market as a whole.

From this online grocery store user behavior dataset, we wanted to find out:
1. If there is a specific pattern of users’ purchasing behavior. The dataset contains information such as user_id, category_code, event_type, event_time, etc. 
2. If there is a relation between the number of orders made by users and the event_time of the “purchase” event_type. What would be the most active time period of the day for this store?
3. The dataset is rich for helping us to classify the users into different groups. For instance, which type of users would be the core value customers of the store, and which group of customers would be the churns.
4. The brand and category fields can be applied for association rules. We can apply the apriori model to see what itemsets are within the top popular buys.

