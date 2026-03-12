SELECT ROUND(SUM(price),2) AS total_revenue
FROM olist_order_items_dataset;
SELECT COUNT(DISTINCT order_id) AS total_orders
FROM olist_order_items_dataset;

SELECT ROUND(SUM(oi.price)/COUNT(DISTINCT o.order_id),2) AS avg_order_value
FROM olist_orders_dataset o
JOIN olist_order_items_dataset oi
ON o.order_id = oi.order_id;

SELECT DATE_FORMAT(order_purchase_timestamp,'%y-%m') AS month,
       ROUND(SUM(oi.price),2) AS monthly_revenue
FROM olist_orders_dataset o
JOIN olist_order_items_dataset oi
ON o.order_id = oi.order_id
GROUP BY month
ORDER BY month;

SELECT o.order_id,
	  ROUND(SUM(oi.price),2) AS order_revenue
FROM olist_orders_dataset o
JOIN olist_order_items_dataset oi
ON o.order_id = oi.order_id
WHERE order_status = 'delivered'
GROUP BY o.order_id
ORDER BY order_revenue DESC;

SELECT 
COUNT(order_id) AS total_orders,
SUM(CASE WHEN order_status ='canceled' THEN 1 ELSE 0 END) AS caceled_orders,
ROUND(SUM(CASE WHEN order_status ='canceled' THEN 1 ELSE 0 END)/COUNT(order_id)*100,2) AS canceled_rate
FROM olist_orders_dataset;

SELECT 
      o.customer_id,
      ROUND(SUM(oi.price),2) AS customer_revenue
FROM olist_orders_dataset o
JOIN olist_order_items_dataset oi
ON o.order_id = oi.order_id
WHERE o.order_status = 'delivered'
GROUP BY o.customer_id
ORDER BY customer_revenue DESC;

SELECT o.customer_id,
       COUNT(DISTINCT o.order_id) AS order_count
FROM olist_orders_dataset o 
WHERE o.order_status = 'delivered'
GROUP BY o.customer_id;

WITH customer_stats AS(
SELECT o.customer_id,
       COUNT(DISTINCT o.order_id) AS order_count,
       ROUND(SUM(oi.price),2) AS total_revenue
FROM olist_orders_dataset o 
JOIN olist_order_items_dataset oi
ON o.order_id = oi.order_id
WHERE o.order_status = 'delivered'
GROUP BY o.customer_id
),
Ranked_customers AS(
SELECT order_count,
       total_revenue,
       customer_id,
       NTILE(10)OVER(ORDER BY total_revenue DESC) AS revenue_group 
FROM customer_stats
)
SELECT revenue_group,
       COUNT(customer_id) AS customer_count,
       ROUND(AVG(order_count),2) AS avg_order_count,
       ROUND(SUM(total_revenue),2) AS group_revenue
       FROM ranked_customers
       GROUP BY revenue_group
       ORDER BY revenue_group DESC;
       
       
WITH customer_stats AS(
SELECT o.customer_id,
       COUNT(DISTINCT o.order_id) AS order_count,
       ROUND(SUM(oi.price),2) AS total_revenue
FROM olist_orders_dataset o 
JOIN olist_order_items_dataset oi
ON o.order_id = oi.order_id
WHERE o.order_status = 'delivered'
GROUP BY o.customer_id
)
SELECT CASE 
      WHEN order_count>=3 THEN 'Highfrequency' ELSE'Lowfrequency' END AS frequency_group,
      COUNT(customer_id) AS customer_count,
      SUM(total_revenue) AS total_revenue,
      ROUND(SUM(total_revenue)/SUM(SUM(total_revenue))OVER()*100,2) AS revenue_percent
      FROM customer_stats
	  GROUP BY  
      CASE 
      WHEN order_count>=3 THEN 'Highfrequency' ELSE'Lowfrequency' END ;
      
WITH category_stats AS(
SELECT 
      p.product_category_name,
      COUNT(DISTINCT o.order_id) AS orders_count,
      SUM(oi.price) AS total_revenue
FROM olist_orders_dataset o 
JOIN olist_order_items_dataset oi
ON o.order_id = oi.order_id
JOIN olist_products_dataset p
ON p.product_id = oi.product_id
WHERE o.order_status = 'delivered'
GROUP BY p.product_category_name
)
SELECT 
    product_category_name,
    orders_count,
    ROUND(total_revenue,2) AS total_revenue,
    ROUND(total_revenue/orders_count,2) AS avg_order_value
    FROM category_stats
    ORDER BY total_revenue DESC;