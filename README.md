
Good Old Style SQL for countries, states and cities information. Standard SQL syntax is used. It should work for all relational databases.

# BE CAREFUL WHILE USING!!!!

You have been warned: Although commented out, scripts contain drops table statements. If yıu want to uncomment, have your own responsibility!

# Usage
Run countries.sql, states.sql and cities.sql with your favorite SQL interpreter.

Ex (MySQL command line interpreter): 
```{r, engine='bash', count_lines}
mysql -u USERNAME -pPASSWORD -D DATABASENAME < countries.sql 
mysql -u USERNAME -pPASSWORD -D DATABASENAME < states.sql 
mysql -u USERNAME -pPASSWORD -D DATABASENAME < cities.sql 
```

## Scenario 1

Assume your customer is from Boston.

1. Normally you should show all countries to her to find United states.
```SQL
select *
	from countries;
```

2. From her choice it should be 231 as the country id. And you can bring the states of United States with following SQL:
```SQL
select *
	from states
	where country_id = 231;
```

3. Now, she'll navigate to the state of Massachussets. And you'll show the cities of Massachussets with following SQL:
```SQL
select *
	from cities
	where state_id = 3943;
```

4. And if she choose Boston, you'll have 44918 as your city id. Cheers!

## Scenario 2

Assume your customer is from city Artvin of Turkey.

Normally you should show all countries to her to choose Turkey.
```SQL
select *
	from countries;
```

From her choice it should be 223 as the country id. And you can bring the cities with following SQL:
```SQL
select *
	from states
	where country_id = 223;
```

Now, she'll navigate to the city of Artvin. And you'll show the districts of Artvin with following SQL:
```SQL
select *
	from cities
	where state_id = 3672;
```

The difference between scenario 1 and 2 is, USA has states but Turkey don't. So for Turkey "states" data becomes "cities" and "cities" data become "district". So while labeling, it is better to choose wording accordingly.

# Credit
Initial script source was here: https://github.com/hiiamrohit/Countries-States-Cities-database

# Warranty
These scripts are provided as - is. Use them with your own responsibilities. Under no circumstances the implementer accept any responsibilities!!
