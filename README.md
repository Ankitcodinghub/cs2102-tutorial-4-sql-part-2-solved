# cs2102-tutorial-4-sql-part-2-solved
**TO GET THIS SOLUTION VISIT:** [CS2102 Tutorial #4-SQL (Part 2)  Solved](https://www.ankitcodinghub.com/product/cs2102-solved-7/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;117761&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS2102 Tutorial #4-SQL (Part 2)&nbsp;  Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
1 Discussions

The following questions are to be discussed during tutorial. All answers will be released with explanation.

This tutorial discussion questions are based on the following pizza database schema. The ER diagram is shown below.

The ER diagram produces the following schemas:

Relation Description

All the pizzas of interest.

The name and location of each customer.

The name and location of each restaurant.

The ingredients used in each pizza.

Pizzas sold by restaurants and the prices.

Likes(cname,pizza) Pizzas that customers like.

1

Additionally, we have the following foreign key constraints on the database schema:

• (Recipes.pizza) (Pizzas.pizza)

• (Sells.rname) (Restaurants.rname)

• (Sells.pizza) (Pizzas.pizza)

• (Likes.cname) (Customers.cname)

• (Likes.pizza) (Pizzas.pizza)

SELECT DISTINCT cname

FROM Likes L

WHERE EXISTS (

SELECT 1

FROM Sells S

WHERE S.rname = ‘Corleone Corner’

AND S.pizza = L.pizza

);

1. (Simple Query) For each of the following queries, write an equivalent SQL query that does not use any subquery. Note that we do not consider set operation (e.g., in Q1 UNION Q2, neither Q1 nor Q2 are considered subqueries).

(a) Query A

1

2

3

4

5

6

7

8

(b) Query B

SELECT cname

FROM Customers C

WHERE NOT EXISTS (

SELECT 1

FROM Likes L, Sells S

WHERE S.rname = ‘Corleone Corner’

AND S.pizza = L.pizza

AND C.cname = L.cname

);

SELECT rname, pizza, price

FROM Sells S

WHERE price &gt;= ALL (

SELECT S2.price

FROM Sells S2

WHERE S2.rname = S.rname

AND S2.price IS NOT NULL

);

11

22

33

44

55

66

77

88

9

2. (SQL Query) Write an SQL query to answer each of the following questions on the pizza database without using aggregate functions. Remove duplicate records from all query results.

(a) Find pizzas that Moe likes but is not liked by Lisa.

(b) Find pizzas that are sold by at most one restaurant in each area; exclude pizzas that are not sold by any restaurant.

(c) Find all tuples (A,P,Pmin) where P is a pizza that is available in area A (i.e., there is some restaurant in area A selling pizza P) and Pmin is the lowest price of P in area A.

3. (Equivalence) Consider the query to find distinct restaurants that are located in the East area. The following are two possible SQL answers (denoted by Q1 and Q2) for this query.

Q1 Query 1

SELECT DISTINCT S.rname

FROM Sells S JOIN Restaurants R

ON S.rname = R.rname AND R.area = ‘East’;

1

2

3

Q2 Query 2

SELECT DISTINCT S.rname

FROM Sells S, Restaurants R

WHERE S.rname = R.rname

AND R.area = ‘East’;

1

2

3

4

The semantics of these two SQL queries are defined by the relational algebra expressions shown below. Discuss whether Q1 and Q2 are equivalent queries.

(a) Q1 (b) Q2

4. (Equivalence) Consider the query to find distinct restaurants that are located in the East area or restaurants that sell some pizza that Lisa likes, where the restaurants that do not sell any pizza are to be excluded. The following are two possible SQL answers (denoted by Q1 and Q2) for this

query.

Q1 Query 1

SELECT DISTINCT S.rname

FROM Sells S JOIN Restaurants R

ON S.rname = R.rname AND R.area = ‘East’

UNION

SELECT DISTINCT S.rname

FROM Sells S JOIN Likes L

ON S.pizza = L.pizza AND L.cname = ‘Lisa’;

1

2

3

4

5

6

7

Q2 Query 2

SELECT DISTINCT S.rname

FROM Sells S, Restaurants R, Likes L

WHERE (S.rname = R.rname AND R.area = ‘East’)

OR (S.pizza = L.pizza AND L.cname = ‘Lisa’);

1

2

3

4

The semantics of these two SQL queries are defined by the relational algebra expressions shown below. Discuss whether Q1 and Q2 are equivalent queries.

(a) Q1

(b) Q2

2 Challenge

The answers to the following questions is given without explanation. Please discuss them on Canvas.

1. (SQL Query) Write an SQL query to answer each of the following questions on the pizza database without using aggregate functions. Remove duplicate records from all query results.

(a) Find all tuples (A,P,Pmin,Pmax) where P is a pizza that is available in area A (i.e., there is some restaurant in area A selling pizza P), Pmin is the lowest price of P in area A and Pmax is the highest price of P in area A.

2. (Update) Consider again the following relational schema discussed in Tutorial 2 Question 2 (Discussions).

CREATE TABLE Offices ( office_id INTEGER, building TEXT NOT NULL, level INTEGER NOT NULL, room_number INTEGER NOT NULL, area INTEGER,

PRIMARY KEY (office_id),

UNIQUE (building, level, room_number)

);

CREATE TABLE Employees ( emp_id INTEGER,

name TEXT NOT NULL,

office_id INTEGER NOT NULL,

manager_id INTEGER,

PRIMARY KEY (emp_id),

FOREIGN KEY (office_id) REFERENCES Offices (office_id) ON UPDATE CASCADE,

FOREIGN KEY (manager_id) REFERENCES Employees (emp_id) ON UPDATE CASCADE );

1

2

3

4

5

6

7

8

9 10

11

12

13

14

15

16

17

18

19

20

21

Suppose that the o ce with office id = 123 needs to be renovated. Write an SQL statement to reassign the employees located in this o ce to another temporary o ce located at room number 11 on level 5 at the building named Tower1.

Hint: You can use subquery in an update statement.

3. (Backward Reasoning) You are given the following schema:

• Students(matric, sname)

• Workings(pid, matric, since)

• Projects(pid, pname)

• Categories(pid, cname)

You are also given the following foreign key:

• (Workings.matric) (Students.matric)

• (Workings.pid) (Projects.pid)

• (Categories.pid) (Projects.pid)

Consider the following SQL query:

SELECT *

FROM Students NATURAL JOIN Workings NATURAL JOIN Projects

NATURAL JOIN Categories;

1

2

3

4

Say it produces the following result:

matric sname pid since cname

A0001 AA P01 2002 CA

A0001 AA P01 2002 CB

A0001 AA P02 2004 CB

A0002 BB P01 2003 CA

A0002 BB P01 2003 CB

A0003 CC P03 2004 CA

A0003 CC P03 2004 CC

A0003 CC P03 2004 CD

A0004 AA P03 2004 CA

A0004 AA P03 2004 CC

A0004 AA P03 2004 CD

Now consider another the query to find all pair of distinct projects’ pid (i.e., (p1, p2)) such that the two projects have exactly the same set of categories . It produces the following result:

pid pid

P01 P04

P04 P01

P03 P05

P05 P03

Simply note that P01 and P04 have exactly the same set of categories. Similarly, P03 and P05 have exactly the same set of categories. What is a possible result of the following SQL query? Show your answer using only P01, P03, P04, and P05?

SELECT pid FROM Categories

EXCEPT ALL

SELECT DISTINCT pid FROM Categories WHERE cname &lt;&gt; ‘CA’;

1

2

3
