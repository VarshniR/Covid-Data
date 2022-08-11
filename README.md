![GettyImages-1210455332](https://user-images.githubusercontent.com/109621999/184076374-8a61675b-969b-4ce7-8578-f41123e87bfc.jpeg)


### Covid-Data

So, I have been struggling finding a job and I got a lot of advise from my peers, I worked on revamping my resume and some people suggested I add more to my Github portfolio. 
The goal is to add all the queries I write as practice tasks to my Github profile, at least 3 times every week. Having said that, these might not always be pretty or very well put together.

This is a dataset I downloaded from Kaggle **Worldwide Covid Cases & Vaccination Data Combined (https://www.kaggle.com/datasets/kunwarakash/covid-cases-and-vaccination-data)**

Here are some of the questions I tried to answer based on the dataset:
1. Which are the top 5 countries with the highest number of fully vaccinated people?
2. What are the average total deaths from Covid per country?
3. What are the totals of covid cases and covid deaths in every country?
4. How many covid cases and covid deaths were reported between 01-22-2020 and 02-22-2020 per country?
5. When was the first Covid-19 case reported in Suriname?   


``` 
SELECT country, SUM(fully_vaccinated) AS vaccine_totals
FROM covid
GROUP BY country
ORDER BY vaccine_totals DESC
LIMIT 5;
```

```
SELECT country, AVG(total_deaths) as death_avg
FROM covid
GROUP BY country
ORDER BY country;
```

```
SELECT country, SUM(total_cases) AS cases, SUM(total_deaths) AS deaths
FROM covid
GROUP BY country;
```

```
SELECT distinct(country), date, daily_deaths, daily_cases
FROM covid
WHERE date between '2020-01-22' AND '2020-02-22'
AND daily_deaths > 0
ORDER BY date ASC;
```
```
SELECT country, date, daily_cases
FROM covid
WHERE country = 'suriname'
AND daily_cases >0 
ORDER BY date
```

## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/VarshniR/Covid-Data/edit/main/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/VarshniR/Covid-Data/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
