# MBA-BDM
###### [Ezhilan Wilson - 22121128](https://github.com/EzhianWilson)
###### [Tejasvi B - 22121006](https://github.com/tejbasu)

## **Introduction:**

As a Business Analyst, I have been tasked with planning the database structure for an online shopping domain. Online shopping has become a rapidly growing industry in recent years, with more and more people choosing to shop online for the convenience it offers. Therefore, it is essential to have a well-designed and efficient database structure to ensure that the online shopping experience is seamless for customers.

## **Domain/Industry:** Online Shopping

#### **Attributes:**

* **Customer:** name, address, email, phone number, payment information
* **Product:** name, description, category, price, brand, availability
* **Order:** order number, order date, total amount, status
* **Order Item:** quantity, unit price
* **Cart:** cart ID, date created, total amount
* **Payment:** payment ID, payment date, payment method, amount
* **Shipping:** shipping ID, tracking number, shipping date, address
* **Review:** review ID, product rating, review text
* **Wishlist:** wishlist ID, date created
* **Promotion:** promotion ID, discount percentage, start and end date


#### **Entities:**

1. Customer
2. Product
3. Order
4. Order Item
5. Cart
6. Payment
7. Shipping
8. Review
9. Wishlist
10. Promotion




## ER Diagram - ONLINE SHOPPING
![ER DIAGRA, drawio (1)](https://user-images.githubusercontent.com/125994880/235347923-ec282fd2-329a-45f9-90f0-dd4b9a98c1ea.png)


## Table design for ER Diagram

**TABLE : CUSTOMER**
EX:
|CUSTOMER_ID| NAME          | E_MAIL                |PAYMENT_INFO  |
|----------:| ------------- | ---------------------:|-------------:|
||    |           |   |                   

CUSTOMER_ID : VARCHAR PRIMARY KEY <br>
NAME        : VARCHAR <br>
EMAIL       : VARCHAR <br>
PAYMENT_INFO: VARCHAR <br>

**TABLE : PHONE_NO**
EX:
|PHONE_NO_ID|CUSTOMER_ID|PHONE_NUMBER|
|-----------|-----------|------------|
|        || |

PHONE_NO_ID  : INT PRIMARY KEY <br>
CUSTOMER_ID  : VARCHAR <br>
PHONE_NUMBER : VARCHAR <br>

**TABLE : ADDRESS**
EX:
|ADDRESS_ID| CUSTOMER_ID|  SHIPPING_ID| PLOT_STREET_BUILDING_NO| FIRST_LINE| SECOND_LINE| PINCODE|
| | | | | | | |

ADDRESS_ID                : INT PRIMARY KEY <br>
CUSTOMER_ID               : VARCHAR FOREIGN KEY <br>
SHIPPING_ID               : VARCHAR FOREIGN KEY <br>
PLOT_STREET_BUILDING_NO   : VARCHAR <br>
FIRST_LINE                : VARCHAR <br>
SECOND_LINE               : VARCHAR <br>
PINCODE                   : VARCHAR <br>

**TABLE : PRODUCT**
EX:
|PRODUCT_ID| NAME          | DESCRIPTION                                             | CATEGORY              |PRICE     | BRAND        | AVAILABILITY |
|----------| ------------- |:--------------------------------------------------:     | ---------------------:|---------:|-------------:|-------------:|
|PROD001   |Laptop         |Thin and light laptop with long battery life             |Electronics            |899.99    |Dell          | TRUE         |

PRODUCT_ID   : VARCHAR
NAME         : VARCHAR
DESCRIPTION  : TEXT
CATEGORY     : VARCHAR
PRICE        :
BRAND        : VARCHAR
AVAILABLE    :

**TABLE : ORDER_TABLE**

Order_id- Varchar <br>
Order_Date- Dtae <br>
TotL_amount - Decimal<br>
Order_Status - Varchar <br>
Customer_ID - Varchar<br>
| ORDER_ID  | ORDER_DATE    | TOTAL AMOUNT    |ORDER_STATUS     |CUSTOMER_ID| 
| --------- |:-------------:| ---------------:|----------------:|-----------|
|INV001     |2022-01-01     | 129.99          |Paid             |CUST001    | 
|INV002     |2022-01-02     | 49.99           |Paid             |CUST003    |          
|INV003     |2022-01-03     |899.99           |Paid             |CUST005    | 
|INV004     |2022-01-04     |249.99           |Pending          |CUST002    | 
|INV005     |2022-01-05     |29.99            |Paid             |CUST007    | 

**TABLE : ORDER_ITEMS**

Order_item_id - Varchar <br>
Oder_Iten_Unitprice - Decimal <br>
Order_item_quantity- Integer<br>
Order_id- Varchar <br>
Product_id - Varchar <br>
|ORDER_ITEMS_ID | ORDER_ITEM-UNITPRICE  | ORDER_ITEM_QTY   | ORDER_ID | PRODUCT_ID |
|---------------| --------------------- |:----------------:|----------|------------|
|OI001          | 129.99                | 1                |INV001    |PROD007     |
|OI002          | 49.99                 | 2                |INV002    |PROD010     |
|OI003          | 899.99                | 1                |INV003    |PROD001     |
|OI003          |899.99                 | 1                |INV003    |PROD001     |
|OI005          |29.99                  | 3                |INV005    |PROD007     |


**TABLE : CART**

Card_id - Varchar <br>
Dte_created - Date <br>
Customer_id- Varchar <br>
Total_amount - Decimal<br>

|CART_ID| DATE_CREATED |CUSTOMER_ID | TOTAL_AMOUNT |
|-------|--------------|------------|--------------|
|CART001|2022-01-01    | 129.99     |CUST001       |
|CART002|2022-01-02    | 49.99      |CUST003       |
|CART003|2022-01-03    | 899.99     |CUST005       |
|CART004|2022-01-04    | 249.99     |CUST002       |
|CART005|2022-01-05    | 29.99      |CUST007       |

**TABLE : PAYMENT**

Payment_Id -Varchar <br> 
Payment _date - Date <br> 
Payment_method - Varchar <br> 
Payment_amount - Decimal <br>
Order_id- Varchar <br>

|PAYMENT_ID| PAYMENT_DATE| PAYMENT_METHOD| PAYMENT_AMOUNT| ORDER_ID |
|----------|-------------|---------------|---------------|----------|
|1         |2022-01-15   |Credit Card    | 129.99        |INV001    |
|2         |2022-01-16   |PayPal         | 49.99         |INV002    |
|3         |2022-01-17   |Credit Card    | 899.99        |INV003    |
|4         |2022-01-18   |PayPal         | 249.99        |INV004    |
|5         |2022-01-19   |Credit Card    | 89.97         |INV005    |

**TABLE : SHIPPPING**

Shipping_ID - Varchar <br>
Shipping_date - Date <br>
Tracking_id - Varchar <br>
Shipping _Address- Varchar <br>
Order_ID- Varchar

|SHIPPING_ID| SHIPPING_DATE | TRACKING_NUMBER | SHIPPING_ADDRESS | ORDER_ID |
|-----------|---------------|-----------------|------------------|----------|
|GSA682879  |2023-02-25     |YGHDA56A8790A8765|PUNE              |23998     |
|BKL890879  |2023-06-04     |JKJQHS567889087GD|BHOPAL            |98767     |
|WET678979  |2023-01-29     |BHDKN637891980914|BENGALURU         |34569     |
|HJJ098765  |2023-03-15     |HGSBND09823481DKN|BIHAR             |78656     |
|ETY986590  |2023-04-06     |QIUO89346419DN234|GUJURAT           |46759     |

**TAGLE : REVIEW**

Review_ID- Varchar<br>
Customer_ID- Varchar<br>
Product_ID- Varchar <br>
Product_Rating - Decimal <br> 
Review _text - Varchar

|REVIEW_ID|CUSTOMER_ID | PRODUCT_ID |PRODUCT_RATING | REVIEW_TEXT | 
|---------|----------- |------------|----------------|------------|
|567896   | 101        |  860       |3.5/5           |GOOD        |
|676899   | 102        |  346       |3.8/5           |BETTER      |
|096449   | 103        |  246       |2.0/5           |BAD         |
|096489   | 104        |  098       |3.6/5           |GOOD        |
|754280   | 104        |  346       |1.0/5           |WORST       |

**TABLE : WISHLIST**

Wishlist_ID - Varchar <br>
Date_created - Date <br> 
Customer_ID- Varchar 

|WISHLIST_ID | DATE_CREATED |CUSTOMER_ID |
|------------|--------------|------------|
|HJAH465776  |2023-02-15    |101         |
|JHDSB09875  |2023-06-01    |102         |
|OIUHJ98765  |2023-01-24    |103         |
|IQWUDGH567  |2023-03-10    |104         |
|WUYGH09861  |2023-04-04    |105         |

**TABLE : PROMOTION**

Promomtion_ID - Varchar<br>
Start_date - Date <br> 
End_Date - Data <br>
Discount_percentage - Decimal<br>
Product_ID- Varchar
|PROMOTION_ID | START_DATE | END_DATE | DISCOUNT_PERCENTAGE |PRODUCT_ID |
|-------------|------------|----------|---------------------|-----------|
|GB262772     |2021-12-09  |2020-12-12|6%                   | 860       |
|UA456885     |2019-02-21  |2021-07-04|12%                  | 346       |
|QT456895     |2015-03-19  |2019-04-01|3%                   | 246       |
|QG833790     |2019-13-13  |2023-01-04|25%                  | 104       |
|JN987648     |2017-07-01  |2021-02-05|30%                  | 105       |

