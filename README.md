# e-Commerce-Marketing-Campaign-Analysis
In this project, we will be using a custom-built and extremely rich e-commerce database to help steer the decisions of a business by analysing traffic sources, marketing channels, measuring website performance, analysing business patterns/seasonality and exploring the product portfolio. we will use SQL to understand how customers access and interact with the site, analyse landing page performance and conversion, and explore product-level sales.

**_Disclaimer_**: _All datasets and reports do not represent any company, institution or country, but just a dummy dataset from Maven Analytics to demonstrate capabilities in SQL._


# Data Exploration

We will be working with 6 related tables containing e-commerce data about;
- website activity
- products
- orders and refunds

### 1. orders table: 
This is where purchases placed by customers are stored, and contains variables like the timestamp of the order, the website session, item purchased, price and cost of goods sold  in US dollars. This is a very critical table as this is where the revenue comes from and we will be linking this table to other tables to discover what kind of marketing activities are driving these orders, how well is the website performing to drive those orders, etc.

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/a8782c39faaa4667b7c4da261e2079663e1ebc04/orders_table.png)

### 2. order_items table: 
Within an order, we have various order items. A customer could purchase multiple items, we link this table with the orders table to find what order those items are part of.

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/a8782c39faaa4667b7c4da261e2079663e1ebc04/order_items_table.png)

### 3. products table: 
Contains the name of the products in company's portfolio, the date those products where released and an identification number to link with other tables.

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/a8782c39faaa4667b7c4da261e2079663e1ebc04/products_table.png)

### 4. order_item_refunds table: 
This is usually for when they have complaints from customers and refunds have to be made. It contains the date of refund, refund amount in US dollars, and the order item too.

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/a8782c39faaa4667b7c4da261e2079663e1ebc04/order_item_refunds_table.png)

### 5. website_sessions table: 
This is another very important table as it contains data that helps us track where traffic is coming from and which of those traffic sources are helping us generate orders. so every session representing visits to the website by a customer has an identification number associated with it, timestamp the session was created, whether its a repeat session or not, utm (Urchine Tracking Module) parameters tagged with paid traffic to measure the performance of online marketing campaigns, device type and browser.

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/a8782c39faaa4667b7c4da261e2079663e1ebc04/webiste_sessions_table.png)

### 6. website_pageviews table: 
Contains data for the web pages viewed during each sessions

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/a8782c39faaa4667b7c4da261e2079663e1ebc04/website_pageviews_table.png)



# Traffic Source Analysis 

We aim to understand where our customers are coming from and which channels (emails, social, search, direct) are driving the highest quality traffic. Then a conversion analysis is done to see how valuable the traffic is. we will also compare user behaviour patterns across traffic sources to inform creative and messaging strategy, and identify opportunities to eliminate wasted spend or scale high-converting traffic.
When businesses run paid marketing campaigns, they often obsess over performance and measure everything; how much they spend, how well traffic converts to sales, etc... Paid traffic is commonly tagged with tracking (UTM) parameters, which are appended to URLs and allow us to tie website activity back to specific traffic sources and campaigns.

-- We want to see which ad(utm source) drives the most traffic

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/aee85036a8d1319788f4a0008ac604a2c84cacb3/1.%20AdWithMostTraffic.png)

This shows that "g_ad_1" drives most traffic, accounting for 59.7% of total sessions while direct traffic/non-paid traffic/organic searches (reflected in the data for utm parameters with "Null" values) accounts for 17.6% of total sessions. This means total paid traffic accounts for 82.4% of the total sessions.

Total sessions: 472,871
Organic traffic: 9.1%
Direct traffic: 8.4%
Paid traffic: 82.3%


### Bid optimization: 
Here we seek to understand the value of various segments of paid traffic, so we can optimize our marketing budget. using conversion rate and revenue per click analyses, we try to figure out how much we should spend per click to acquire customers, how website and products perform for various subsegments of traffic (i.e desktop vs mobile) to optimize within channels, analyzing the impact that bid changes have on our ranking in the auctions, and the volume of customers driven to our site.

-- Next we look at the session to order conversion rate to see how much of our sessions are potentially converted to sales orders

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/875ba94e3fbad49d67fa06d15e72a4a8ab37168f/2.%20SessionToOrderConversionRate.png)

Though "g_ad_1" accounts for the highest number of sessions and order, only 6.6% of those sessions are converted to sales orders. Other paid traffics like "b_ad_2" and "g_ad_2" had the highest conversion rates at 8.8% and 7.5% respectively. While "social_ad_1" has the lowest conversion rate at just 1%.

-- If we further break this down by device type

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/875ba94e3fbad49d67fa06d15e72a4a8ab37168f/3.%20ConvByDeviceType.png)

Most sales orders are placed on desktop, meaning that users are more likely to complete a purchase on larger screens than on mobile devices



# Website Performance

The objective here is about understanding which pages are seen the most by our users so we know where to focus on improving our business. Identifying the most common entry pages to our website - the first thing a user sees. For most viewed pages and most common entry pages, understanding how those pages perform for our business is very crucial.
We can analyze our pageviews data and grooup by url to see which pages are viewed the most. to find top entry pages, we will limit to just the first page a user sees during a given session.

-- most viewed website pages, ranked by session volume

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/3453d938e44dc8e054f03ca165ba0234bec7e218/MostViewedWebPage.png)


### Landing page performance and testing: 
We probe further to understand the performance of our landing page and then test with other landing pages to identify improvement opportunities.

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/08477431be219d3f7c1d018cebfa4b0cc2602bca/1.%20bounceRate.png)

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/08477431be219d3f7c1d018cebfa4b0cc2602bca/2.%20bounceRate.png)

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/08477431be219d3f7c1d018cebfa4b0cc2602bca/3.%20bounceRate.png)

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/08477431be219d3f7c1d018cebfa4b0cc2602bca/4.%20bounceRate.png)

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/08477431be219d3f7c1d018cebfa4b0cc2602bca/5.%20bounceRate.png)


The bounce rate calculation for the landing page shows 41.6% of sessions don't go beyond the landing page

-- performing an A/B testing, comparing the bounce rate performance for other landing pages against the /home page

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/c8b181902282bc8c7628926e713efa6083c03801/6.%20bounceRate.png)

At 53.2%, "/lander-1" tops the list for landing page with highest bounce rate, "/home" being at 41.6%, about 5% worse than "/lander-5" which has the best performance in terms of bounce rate


### Analyzing and testing conversion funnels: 
We deep futher to understand and opotimize each step of our user's experience on their journey toward purchasing our products. We identify the most common paths customers take before purchasing our products, identifying how many of our users continue on to each next step in our conversion flow, and how many users abandon at each step. Also, optimizing critical pain points where users are abandoning, so that we can convert more users and sell more products.

-- we want to know where the biggest pain points are for our customers as they journey towards purchasing our products. we will consider their journey from landing page "/home" to "/cart" page

Step 1: we will select all pageviews for relevant sessions

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/5f0f92c29374d34a420b11994e64b768b07d48aa/clickthru1.png)

Step 2: identify each relevant pageview as the specific funnel step

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/5f0f92c29374d34a420b11994e64b768b07d48aa/clickthru2.png)


Step 3: create the session-level conversion funnel view

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/5f0f92c29374d34a420b11994e64b768b07d48aa/clickthru3.png)


step 4: aggregate the data to assess funnel performance

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/5f0f92c29374d34a420b11994e64b768b07d48aa/clickthru4.png)


58.4% of users made it to "/cart" from "/the-original-mr-fuzzy" page and 62% made it to "/the-original-mr-fuzzy" from "/products" page and 82% made it to "/products" page from the "/home" page
but generally, only 29.8% made it to "/cart" out of 318,577 sessions from the landing page "/home".



# Business patterns and seasonality

We deep dive into tthe data to gain insights regarding efficiency optimization and future trends to look out for. This will also helps us know how much support staff  we should have at different times of the day or days of the week, and to better prepare for upcoming spikes or slow downs in demand.


-- monthly trend of sessions, orders, conversion rate, organic traffic, direct traffic and paid traffic

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/c3a0ff432e9fe2d08d107854c5e4f8bf7b9c6740/trend.png)

The monthly trend shows session increases with months, peaking in November every year.


-- average website session volume, by hour of day and by day week so that we can staff appropriately

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/bf87941070dc0c47b10cceede7e964f5eb2a127e/trend2.png)

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/bf87941070dc0c47b10cceede7e964f5eb2a127e/trend3.png)

Result shows that during the day across  workdays of the week, average session volume begins to significantly increase from 8am (17 to 20) and is at it's highest between the hours of 10am to 5pm (31 to 37), compared to saturdays and sundays where average session volume ranges between 5 and 16.



# Product portfolio analysis

This will help us understand how each product contributes to our business, and how product launches impact the overall portfolio. Here we will analyze sales and revenue by product, monitor impact of adding a new product to our portfolio and watching product sales trend to understand the overall health of our business.


-- We will be looking at our order data, and tie in the specific product(s) driving sales. we will want to know how much of our order volume comes from each product, and the overall revenue and margin generated.

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/3059699f50c02f6dde0cdd3e1749a1ce86f08a11/product1.png)

Product 1: The Original Mr. Fuzzy
Product 2: The Forever Love Bear
Product 3: The Birthday Sugar Panda
Product 4: The Hudson River Mini bear

Product 2 has the highest average order value of $66.2 per order compared to $59.5 per order for the company's first product

-- trended analysis showing monthly order volume, overall conversion rates, revenue per session, and a breakdown of sales by product, to better understand the impact of new product launches on conversion rate and revenue per session.

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/3059699f50c02f6dde0cdd3e1749a1ce86f08a11/product2.png)

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/3059699f50c02f6dde0cdd3e1749a1ce86f08a11/product3.png)

The introduction of more products consistently led to increase in nconversion rate from as low as 3% in march, 2012 to 8.3% as at march, 2015. Revenue per session also increased from $1.6 to $5.2 in same time period.


-- here we look into products and their conversion rate in terms of viewed_product_to_order_rate to see how well each product converts customers

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/a6c8125f8df599146b8657acab4abf1024be080b/product5.png)

Product 1: The Original Mr. Fuzzy
Product 2: The Forever Love Bear
Product 3: The Birthday Sugar Panda
Product 4: The Hudson River Mini bear

Product 4 has the highest viewed_product_to_order_rate at 22% compared to product 3 at 18%, product 2 at 16% and product 1 at 14.6%. Its important to note that product 4 has only spent 4 months on the market, product 3 (16 months), product 2 (27 months) and product 1 (37 months)

