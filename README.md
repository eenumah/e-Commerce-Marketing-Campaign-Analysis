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

Pictures here

### 2. order_items table: 
Within an order, we have various order items. A customer could purchase multiple items, we link this table with the orders table to find what order those items are part of.

pictures here

### 3. products table: 
Contains the name of the products in company's portfolio, the date those products where released and an identification number to link with other tables.

pictures here

### 4. order_item_refunds table: 
This is usually for when they have complaints from customers and refunds have to be made. It contains the date of refund, refund amount in US dollars, and the order item too.

pictures here

### 5. website_sessions table: 
This is another very important table as it contains data that helps us track where traffic is coming from and which of those traffic sources are helping us generate orders. so every session representing visits to the website by a customer has an identification number associated with it, timestamp the session was created, whether its a repeat session or not, utm (Urchine Tracking Module) parameters tagged with paid traffic to measure the performance of online marketing campaigns, device type and browser.

pictures here

### 6. website_pageviews table: 
Contains data for the web pages viewed during each sessions

pictures here


# Traffic Source Analysis 

We aim to understand where our customers are coming from and which channels (emails, social, search, direct) are driving the highest quality traffic. Then a conversion analysis is done to see how valuable the traffic is. we will also compare user behaviour patterns across traffic sources to inform creative and messaging strategy, and identify opportunities to eliminate wasted spend or scale high-converting traffic.
When businesses run paid marketing campaigns, they often obsess over performance and measure everything; how much they spend, how well traffic converts to sales, etc... Paid traffic is commonly tagged with tracking (UTM) parameters, which are appended to URLs and allow us to tie website activity back to specific traffic sources and campaigns.

-- We want to see which ad(utm source) drives the most traffic

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/aee85036a8d1319788f4a0008ac604a2c84cacb3/1.%20AdWithMostTraffic.png)

This shows that "g_ad_1" drives most traffic, accounting for 59.7% of total sessions while direct traffic/non-paid traffic/organic searches (reflected in the data for utm parameters with "Null" values) accounts for 17.6% of total sessions. This means total paid traffic accounts for 82.4% of the total sessions.


## Bid optimization: 
Here we seek to understand the value of various segments of paid traffic, so we can optimize our marketing budget. using conversion rate and revenue per click analyses, we try to figure out how much we should spend per click to acquire customers, how website and products perform for various subsegments of traffic (i.e desktop vs mobile) to optimize within channels, analyzing the impact that bid changes have on our ranking in the auctions, and the volume of customers driven to our site.

-- Next we look at the session to order conversion rate to see how much of our sessions are potentially converted to sales orders

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/875ba94e3fbad49d67fa06d15e72a4a8ab37168f/2.%20SessionToOrderConversionRate.png)

Though "g_ad_1" accounts for the highest number of sessions and order, only 6.6% of those sessions are converted to sales orders. Other paid traffics like "b_ad_2" and "g_ad_2" had the highest conversion rates at 8.8% and 7.5% respectively. While "social_ad_1" has the lowest conversion rate at just 1%.

-- If we further break this down by device type

![](https://github.com/eenumah/e-Commerce-Marketing-Campaign-Analysis/blob/875ba94e3fbad49d67fa06d15e72a4a8ab37168f/3.%20ConvByDeviceType.png)

Most sales orders are placed on desktop, meaning that users are more likely to complete a purchase on larger screens than on mobile devices



# Website Performance

The objective here is about understanding which pages are seen the most by our users to identify where to focus on improving our business, identifying the most common entry
pages to our website - the first thing a user sees. for most viewed pages and most common entry pages, understanding how those pages perform for our business is very crucial.





## Landing page performance and testing: 
We probe further to understand the performance of our key landing pages and then test to improve results.







## Analyzing and testing conversion funnels: 
We deep futher to understand and opotimize each step of our user's experience on their journey toward purchasing our products. We identify the most common paths customers take before purchasing our products, identifying how many of our users continue on to each next step in our conversion flow, and how many users abandon at each step. Also, optimizing critical pain points where users are abandoning, so that we can convert more users and sell more products.





# Analyzing channel portfolios

This is about bidding efficiently and using data to maximize the effectiveness of our marketing budget. The business could have different marketing channels like email, social networks, search and direct typing and will cost us different amounts. Our job as analyst will be to figure out which one cost the most, which is most effective and optimize the bidding.

To tackle this, we will investigate which marketing channels are driving the most sessions and orders through our website, try to understand differences in user characteristics and conversion performance across our marketing channels, optimizing bids and allocating marketing spend across a multi-channel portfolio to achieve maximum performance.









## Analyzing Direct Traffic: 
Here we analyze our branded or direct traffic to see how our brand is doing with customers and how well our brand drives business.
We will be identifying how much revenue we are generating from direct traffic - as this is high margin revenue without a direct cost of customer acquisition.

To identify traffic coming to your site that you are not paying for with marketing campaigns, we will again turn to our utm parameters.
For non-paid traffic (i.e organic search, direct type in), we can analyze data where the utm parameters are NULL.




# Business patterns and seasonality

We deep dive into tthe data to gain insights regarding efficiency optimization and future trends to look out for. This will also helps us know how much support staff  we should have at different times of the day or days of the week, and to better prepare for upcoming spikes or slow downs in demand.






# Product portfolio analysis

This will help us understand how each product contributes to our business, and how product launches impact the overall portfolio. Here we will analyze sales and revenue by product, monitor impact of adding a new product to our portfolio and watching product sales trend to understand the overall health of our business

