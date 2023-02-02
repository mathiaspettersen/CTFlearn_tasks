# Basic Injection

**See if you can leak the whole database using what you know about SQL Injections. [LINK](https://web.ctflearn.com/web4/)**

**Don't know where to begin? Check out CTFlearn's [SQL Injection Lab](https://ctflearn.com/lab/sql-injection-part-1)**

---

We are greeted with a webpage that takes an input, presumably an SQL query. 

![bilde](https://user-images.githubusercontent.com/70077872/216270169-4a64177b-551f-4a34-a28c-520754c9fa4c.png)

As an SQL query is typically `SELECT [*] FROM [table] WHERE [condition] [operator] [value]`. We want to break that syntax and get the whole database without actually knowing the names of the tables and the values. 



