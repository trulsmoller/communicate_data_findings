# Communicate Data Findings
## by Truls Møller


## Dataset: Prosper Loan Data

The Prosper Loan dataset is a file on 113,937 personal loans that were originated 2006 - 2014, a time range which does include the 2008 Financial Crisis.

My analysis will focus on:
- **High-level overview** of the data.
- **Variables that seem (at least to me) relevant to decisions by the Lender _at the time a new loan gets originated_**, with the help of univariate plots to answer any questions that may arise.
- **Interaction between the variables** with the help of bivariate and multivariate plots to answer any questions that may arise on the interactions.

Here is a breakdown of the relevant variables in three categories.

1) BASIC LOAN DATA
- ListingCategory (numeric) : The category of listing. 20 categories from Debt Consolidation to Wedding Loans denoted with a number in the range 0-20 without any description.
- **ListingCategory** The category of listing. 20 categories from Debt Consolidation to Wedding Loans denoted with a number in the range 0-20 _with_ description.
- **LoanOriginationDate**: The date the loan was originated.
- **Year**: Just the year extracted from the LoanOrigination date
- **LoanOriginalAmount** : The origination amount of the loan.
- **BorrowerAPR**: The Borrower’s Annual Percentage Rate for the loan. (Yearly interest rate)
- **Term**: The duration of the loan in months (Three different durations found: 12, 36, 60 months, ie. 1, 3, 5 years)
- **Loan Status**: The current status of the loan: Cancelled, Chargedoff, Completed, Current, Defaulted, FinalPaymentInProgress, PastDue. The PastDue status will be accompanied by a time range on how long it is past due.

2) CREDIT GRADES / PROSPER RATINGS DATA
- CreditGrade : The Credit rating that was assigned at the time the listing went live. Used for listings pre-2009 only.
- ProsperRating (Alpha) : The Prosper Rating assigned at the time the listing was created, between AA - HR. Used for listings post-2008 only, hence complementary to CreditGrade.
- **ProsperRating** : Added column. It is the same as 'ProsperRating (Alpha)' only the missing data are populated from CreditGrade. This provides a nice continuity over time.
- **CreditScore** is the middle of the range between CreditScoreRangeLower and CreditScoreRangeUpper, which describe the borrower's credit score as provided by a consumer credit rating agency. This score might be used as a component when Prosper calculate a ProsperRating for the borrower.

3) DATA THAT MIGHT HAVE AFFECTED PROSPER RATINGS
- **EmploymentStatus** Whether the borrower is employed, full-time, part-time, retired etc.
- **IncomeRange** : The income range of the borrower at the time the listing was created.
- **Borrower State** Two letter abbreviation of the state of the address of the borrower at the time of listing.
- **IsBorrowerHomeowner** True or False.
- **OnTimeProsperPayments** : Number of past on time payments (less that one month late) at the time of listing. Null if there are no prior loan history.
- **Recommendations** : Number of recommendations the borrower had at the time of listing.

All these variables will be used in our analysis, but only the ones in **bold** will be used explicitly.

## Summary of Findings

ListingCategory - Out of 20 categories Debt Consolidation is the most frequent loan type with 51 percent of all Prosper loans. A log transformation on the axis with the counts was necessary in order to compare the listing categories with low frequency.

LoanOriginationDate - Just plotting all the loans per date revealed a gap in new business around the financial crisis. Then the volumes of loans originated skyrocketed the last one year 2013-14 and more than doubled. A multivariate plot revealed that Prosper added lots of new listing categories (types of loans) in 2011-13, which contributed to the mentioned "skyrocketing" in the volume of loans.

LoanOrginalAmount - common loan sizes at round numbers like 4k, 10k and 15k dollars leads to many peaks, but the average is just above USD 8,000.

ProsperRating - nice unimodal and symmetric distribution

CreditScoreAvg - nice unimodal, quite normal and symmetric distribution, and it's discrete

IncomeRange - good amount of data points in each range, unimodal with a peak around 50k dollars

IsBorrowerHomeowner - Almost 50/50

OnTimeProsperPayments - maybe not that useful, since it say anything about the proportion of on time payments.

Recommendations (log transform) - 96.2 percent of loans, the borrower does not have recommendations


## Key Insights for Presentation

> Select one or two main threads from your exploration to polish up for your presentation. Note any changes in design from your exploration step here.
