![GettyImages-1210455332](https://user-images.githubusercontent.com/109621999/184076374-8a61675b-969b-4ce7-8578-f41123e87bfc.jpeg)


### Covid-Data

So, I have been struggling finding a job and I got a lot of advise from my peers, I worked on revamping my resume and some people suggested I add more to my Github portfolio. 
The goal is to add all the queries I write as practice tasks to my Github profile, at least 3 times every week. Having said that, these might not always be pretty or very well put together.

This is a dataset I downloaded from Kaggle **Worldwide Covid Cases & Vaccination Data Combined (https://www.kaggle.com/datasets/kunwarakash/covid-cases-and-vaccination-data)**

Here are some of the questions I tried to answer based on the dataset:
1. Which are the top 5 countries with the highest number of fully vaccinated people?
``` 
SELECT country, SUM(fully_vaccinated) AS vaccine_totals
FROM covid
GROUP BY country
ORDER BY vaccine_totals DESC
LIMIT 5;
```
![Screenshot 2022-08-11 at 2 40 30 AM](https://user-images.githubusercontent.com/109621999/184077689-e6e797b6-05e9-4a6f-ba49-4e5669fac98e.png)


2. What are the average total reported deaths from Covid-19 per country?
```
SELECT country, AVG(total_deaths) as death_avg
FROM covid
GROUP BY country
ORDER BY country;
```
![Screenshot 2022-08-11 at 2 43 28 AM](https://user-images.githubusercontent.com/109621999/184078005-463a627f-4250-4c52-8b75-a4debfb560b1.png)

3. What are the totals of reported Covid-19 cases and Covid-19 deaths in every country?
```
SELECT country, SUM(total_cases) AS cases, SUM(total_deaths) AS deaths
FROM covid
GROUP BY country;
```
![Screenshot 2022-08-11 at 2 48 38 AM](https://user-images.githubusercontent.com/109621999/184078697-55d52713-ff0a-4c2c-9ad1-500a768cca42.png)

4. How many covid cases and covid deaths were reported between 01-22-2020 and 02-22-2020 per country?

```
SELECT distinct(country), date, daily_deaths, daily_cases
FROM covid
WHERE date between '2020-01-22' AND '2020-02-22'
AND daily_deaths > 0
ORDER BY date ASC;
```
![Screenshot 2022-08-11 at 2 45 35 AM](https://user-images.githubusercontent.com/109621999/184078286-3e46923b-43c5-4539-bacc-84cb5246a19c.png)

5. When was the first Covid-19 case reported in Suriname?   
```
SELECT country, date, daily_cases
FROM covid
WHERE country = 'suriname'
AND daily_cases >0 
ORDER BY date
```
![Screenshot 2022-08-11 at 2 50 15 AM](https://user-images.githubusercontent.com/109621999/184078887-7fedff31-62c7-46fb-9ad5-3afc576ba3d9.png)

## Also played around with the dataset in **Tableau**, below some simple visuals:
![Screenshot 2022-08-11 at 3 55 55 AM](https://user-images.githubusercontent.com/109621999/184088969-0e080b12-8c19-4fcb-8f1c-64e4d522c94a.png)
![Screenshot 2022-08-11 at 3 44 19 AM](https://user-images.githubusercontent.com/109621999/184087056-6cc5db75-0469-4fbf-9a67-854bda06ba42.png)
![Screenshot 2022-08-11 at 3 54 30 AM](https://user-images.githubusercontent.com/109621999/184088715-603b028c-f256-4bb7-8780-ad9dc6b17b8f.png)


#### To see more of my visuals and/ or dashboards: _https://public.tableau.com/app/profile/varshni3490#!/_

#### For those of you who find yourself on this page, feel free to follow me and give your feedback :)

#### LinkedIn: _https://www.linkedin.com/in/varshnir/_

#### E-mail: _varshniramdhani@gmail.com_

