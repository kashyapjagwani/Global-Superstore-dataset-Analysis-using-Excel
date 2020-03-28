# Global-Superstore-dataset-Analysis-using-Excel
This is a practice project which I did to polish up my Excel skills.
#### I downloaded the Global Superstore Orders 2016.xlsx onto my desktop. The data has 51290 rows, and 24 columns. The description of data is as follows:
*"Global Superstore is a customer-centric dataset, which has the data of all the orders that have been placed through different locations all around the world, starting from 2012 till 2015"*

We will use the follwing process-flow to guide us through the project:
1. Understand the Problem/Ask Interesting Questions
2. Data Gathering & Preparation
3. Data Analysis

Let's say we are hired as a consulting partner to help out a client "Global Superstores". Below are the problems they are facing & need our help with:
*(I will mention the questions followed by the solutions I came up with)*
### 1. In order to increase our sales, we want to hire more salespeople. In which location should we invest to build up our sales team?
#### Solution 1A:
1. Let’s assume that the city in which the order is placed, is the location of a store of the Global Super Store Pvt. Ltd.
Moreover, let’s assume that each city has only 1 store.
Thus, we need to determine which city/store generates the most orders so that we can focus our investments in that city in order to build up a sales team.

2. Now, the most obvious approach that I could think of within a minute was to create a 2D chart in which the X-axis represents the different cities & the Y-axis represents the number of stores.
However, this chart turns out to be very congested & no vital information is visible.

3. The second approach is to use built-in Excel functions.
So using the formula - <b>{ =SUMPRODUCT(1/COUNTIF(A2:A51291,A2:A51291))}</b> *(refer sheet Quest 1)* we find out the number of unique cities in which an order has been placed.

4. Next, we use the formula - <b>{=INDEX(A2:A51291,MODE(MATCH(A2:A51291,A2:A51291,0)))}</b> to find out the the city which occurs the most number of times.

5. Hence, we get our answer; <b>New York City</b> is the city that is responsible for the maximum number of orders - *915*.
Thus, Global Superstore Pvt. Ltd. needs to hire salespeople in NYC to further boost sales. 

6. However, if Global Superstores want to find out the city in which they have received the least number of orders then we can use the following formula - <b>{=INDEX(A2:A51291,MATCH(MIN(COUNTIF(A2:A51292,A2:A51291)),COUNTIF(A2:A51291),0))}</b>
The above formula gives <b>Kamina</b> as the output. Thus, Global Stores recorded only *1* sale from the Kamina city and hence can focus their investments in that city to grow their market.

#### Solution 1B:
1. The above solution is somewhat a naive approach. We can further dive deep into the given data and analyze the profits generated by each store.

2. Once we are able to determine the total profits generated by every store, we can find out the stores which generate the most & the least profits.

3. To do this, we will use the <b>SUMIF</b> function. In order to use the <b>SUMIF</b> function, we will first need to find out a list of unique cities using the inbuilt advance filter.

4. Once done, follow the following formula - <b>{=SUMIF(A$2:A$51291,D3126,B$2:B$51291}</b> *(refer sheet Quest 1B)*
Drag this formula for every unique store location and we will get a list of total profits for every location.

5. Using the sort function we get <b>New York City</b> as the store location which generates profits of *$62036.9837* whereas, <b>Lagos</b> generates the greatest loss of *$-25922.511*.
##### Notice that although Kamina city recorded the least sales, Lagos is the city which actually generated the most loss.
6. Now it is up to the management whether they would want ot invest in a location based on number of sales or on the amount of money earnt or lost

### 2. We want to show our top 10 customers our appreciation by sending them a gift-card that has $500 in-store credit. Which customers should we send it to?
#### Solution 2A:
1. Now in the given dataset, every order has a name associated with it which defines the person who ordered the product.

2. In order to solve this question, we need to find a list of unique customers.
We use Excel’s built-in filter in order to find out a list of unique customers - 
*Data>Advanced>Copy to another location>List Range = $A$2:$A$51291>Copy to = C2>Select the Unique records only>OK*

This gives us a list of all the unique customers & this number turns out to be 796.

3. Moreover, to calculate the number of orders placed by every customer we can use the <b>COUNTIF</b> function.
Use the following formula - <b>=COUNTIF(A$2:A$51291,C2)</b>
This will give us the frequency of the customer name in C2 *(refer sheet Quest 2)*

4. Similarly, drag the formula to all the cells next to the unique customers in order to get a frequency of all the customers and then sort them in descending order.
#### The top 10 customers on this list have placed the most number of orders & thus should be given the $500 gift card.

#### Solution 2B:
1. In this solution, we will follow the same approach as we did in solution 1B.

2. Instead of giving gift cards to those customers who ordered the most number of times, we could give gift cards to those 10 customers whose orders made the most profits for Global Stores.

3. We will follow the same steps as we did in 1B - use the <b>SUMIF</b> function to find out the profits generated by every unique customer.

4. Sort the profits made from each customer in descending order to get a list of top 10 customers who gave Global Stores the most profits.
#### Both the lists differ. Customers who placed the most number of orders did not generate the most profits for Global Superstores.

5. Again, its the decision of the management that to whom they would like to send the gift cards.
### 3. We want to decrease the number of products that we offer. Which profucts should we discontinue?
#### Solution 3A:
1. Following a similar approach as in Solution 2A, we find out the frequency of every sub-category of the product.

2. The steps are exactly as above and instead of sorting the final frequency list in descending order, we sort the list in ascending order this time *(refer sheet Quest 3)*.

3. It turns out that Tables are sold the least number of times - *861*.
#### Thus, Global Superstores can discontinue selling tables as the demand for tables is the least.

#### Solution 3B:
1. In this solution too, we will follow the same approach as we did in solution 1B.

2. Instead of removing the sub-category of products that were ordered the least number of times, we could populate a list of profit/loss generated by each unique sub-category of products and make a decision based on the profits/loss.

3. We will follow the same steps as we did in 1B - use the <b>SUMIF</b> function to find out the profits/loss generated by every unique sub-category.

4. Then sort the profits/loss made from each sub-category in ascending order to get a list of sub-categories along with their profits/loss.

#### Turns out, tables generated losses of around *$64000* and thus, should be discontinued by Global Superstores. 
*This is the final answer for question 3 because in both the solutions 'Tables' turn out to be the least selling items & also incur heavy losses to Global Superstores.*


