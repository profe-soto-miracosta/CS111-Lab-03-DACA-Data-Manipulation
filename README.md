# Lab 03 - DACA + Data Manipulation

## Learning Objectives

- Demonstrate an understanding of data manipulation and application to DACA article.

## Program Description

As you saw in this week's article(s), there are a lot of steps and pieces to have been eligible to apply for DACA. The process is expensive and difficult to navigate, so automation can help speed up this process.

You may have noticed that dates are a repeated part of the guidelines, whether it was birthdate, arrival date, start of unlawful immigration status date, date of unbroken US presence, etc. In developing the online application, your team realizes that checking dates is an essential part of determining eligibility.

As the intern on the team, you're tasked with creating a prototype in Java to demonstrate you can accurately calculate the number of days and estimate the number of years between two dates.

**Your job is to output the Julian Day Number for today's date and birthdate, as well as the difference in number of days and the approximate age (whole number years) between the two dates.**

The only direction provided to you was the definition of a _Julian Day Number_ and a website to double-check your work (see definitions below).

## Definitions

- Julian Day Number: https://en.wikipedia.org/wiki/Julian_day
- Check your work with: http://numerical.recipes/julian.html (make sure to select Auto (Julian/Gregorian) calendar option).

Luckily, you made friends with someone from the Quality Assurance (QA) team and they've been mentoring you! You ask for some direction and they point out the formula you should use to calculate the Julian Day Number (JDN) for a date:

$$JDN = day + \dfrac{153m + 2}{5} + 365y + \dfrac{y}{4} - \dfrac{y}{100} + \dfrac{y}{400} - 32045$$

Where:

- **Needed to calculate adjusted month and year:** $a = \dfrac{14-month}{12}$
- **Adjusted month:** $m = month + 12a - 3$
- **Adjusted year:** $y = year + 4800 - a$

For example, Katherine Johnson's birthday is 8/26/1918 ($day = 26$, $month = 8$, and $year = 1918$). Therefore, $JDN = 2421832$. **Note:** When dividing two integers in Java, the result will also be an integer.

## Specifications
Two tests are provided for your code to check it works (besides the "eye-check"):
- JDNs Katherine Johnson: uses Katherine Johnson's birthday 8/26/1918 and the date of her passing 2/24/2020 for the date as test values. It also takes into account the formatting.
- Formatting (spaces+punctuation): tests only that the formatting of expected output matches (down to spaces, spelling, punctuation, format of dates, etc.). Does NOT check actual values of numbers in the output

_TESTING TIP: Note the order of the expected output. If you're having a hard time understanding the test, reach out on our Discord or ask your instructor for some help._

Here is the expected final output, including the proper wording/formatting to pass the test:
```
Julian Day Number for today's date, 2/24/2020, is 2458904

Julian Day Number for birthday, 8/26/1918, is 2421832

The difference in days is 37072, which makes you approximately 101 years old!
```
**Note:** Pay close attention to white-space and line-breaks.

## HACKER CHALLENGE

**Interested in learning more?**

- Time on a computer is usually measured in these kinds of ways, it makes finding differences much easier (simple subtraction)
- Depending on the computer, it'll use different dates and different time measurements
- Java, for example, uses Unix time ([https://en.wikipedia.org/wiki/Unix_time) which starts on January 1st, 1970 and is measured in milliseconds.](https://en.wikipedia.org/wiki/Unix_time)

**Want to improve the precision?**

- After you've submitted the code, upgrade your program to provide the age in years AND days (Ex: 101 years and 64 days)
- Note this upgrade will break both tests.