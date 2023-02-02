# Basic Injection

**See if you can leak the whole database using what you know about SQL Injections. [LINK](https://web.ctflearn.com/web4/)**

**Don't know where to begin? Check out CTFlearn's [SQL Injection Lab](https://ctflearn.com/lab/sql-injection-part-1)**

---

We are greeted with a webpage that takes an input, presumably an SQL query. 

![bilde](https://user-images.githubusercontent.com/70077872/216270169-4a64177b-551f-4a34-a28c-520754c9fa4c.png)

As an SQL query is typically `SELECT [*] FROM [table] WHERE [condition] [operator] [value];` (for example: SELECT * FROM employees WHERE name == "Mathias";). We want to break that syntax and get the whole database without actually knowing the names of the tables and the values. The key here is to inject code that is not meant to be injected.

A quick Google search may find us the answer, but one can also do it manually or with automated tools like SQLmap. Ultimately, the query which works is `' or 1=1#`. This might seem weird at first but I'll break it down. The `'` is used to end the previous SQL query statement and allow us to enter our own. `or 1=1` is an operator which says that only one of the statements have to be true. Since the previous statement most likely is **not** true, but 1=1 is true, it favours this statement. Lastly, `#` is used as a comment to comment out the rest of the query. The injected query basically states that the query is true, which tells the database to output what it has:

![bilde](https://user-images.githubusercontent.com/70077872/216272374-1e2f8fc2-b136-4a7c-a426-8fa08a537968.png)

And we can collect our flag.

Flag: `CTFlearn{th4t_is_why_you_n33d_to_sanitiz3_inputs}`



