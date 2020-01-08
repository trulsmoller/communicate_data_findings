# Communicate Data Findings
## by Truls Møller


## Dataset: Prosper Loan Data

The Prosper Loan dataset is a file on 113,937 personal loans that were originated 2006 - 2014, a time range which does include the 2008 Financial Crisis.

EXPLORATION OF THE DATASET

There were initially 114k loan listings and 81 variables of data in the raw dataset. I have added four new columns: 'Year', 'ProsperRating', 'ListingCategory' and 'CreditScore'.

I focus on 14 variables during exploration:

- **LoanOriginationDate** - The start date of the loan
- **Term** - The duration of the loan in months (Three different durations found: 12, 36, 60 months, ie. 1, 3, 5 years)
- **LoanStatus** - The current status of the loan: Cancelled, Chargedoff, Completed, Current, Defaulted, FinalPaymentInProgress, PastDue. The PastDue status will be accompanied by a time range on how long it is past due.
- **ListingCategory** - The category of listing. 20 categories from Debt Consolidation to Wedding Loans denoted with a number in the range 0-20 with description.
- **IncomeRange** -  The income range of the borrower at the time the listing was created.
- **EmploymentStatus** - Whether the borrower is employed, full-time, part-time, retired etc.
- **ProsperRating** - Essentially the same as 'ProsperRating (Alpha)' in the original data only the missing data are populated from CreditGrade. Rating assigned at the time the listing was created, between AA - HR.
- **Year** -  Just the year extracted from the LoanOrigination date.
- **LoanOrginationAmount** - The start amount of the loan.
**BorrowerAPR** - The Borrower’s Annual Percentage Rate for the loan. (Yearly interest rate)
- **CreditScore** The middle of the range between CreditScoreRangeLower and CreditScoreRangeUpper, which describe the borrower's credit score as provided by a consumer credit rating agency. This score is between 400-900 and might be used as a component when Prosper calculate a ProsperRating for the borrower.
- **OnTimeProsperPayments** - Number of past on time payments (less that one month late) at the time of listing.
- **Recommendations** - Number of recommendations the borrower had at the time of listing.
- **IsBorrowerHomeowner** - True / False on whether the Borrower is a home owner.


## Summary of Findings

Time-wise there is a gap in the listing of loans around the 2008 financial crisis. Maybe Prosper was out of business for a while.

The average loan size is about \\$8k and out of 20 categories of loans Debt Consolidation is the most common with 51\\% of the loans. Around half of the borrowers are homeowners.

The (Borrower) APR is our main variable of interest. It tells the yearly interest rate, which is a measure of how expensive a loan is.

The Prosper Rating almost dictates the APR (strong correlation).

The APR depends a lot on the income range.

Homeowners tend to have lower APR than non-homeowners, and also a bit longer term.

There is moderate correlation between APR and Credit Score.
The yearly lower bound for CreditScore is around 500 in 2006-08, while it's around 600 in 2009-14. This means that from 2009 onwards it seems near impossible to get a Prosper loan if your credit rating is less than 600.


## Key Insights for Presentation

The presentation is titled "Improve Your Chances of Getting a Prosper Loan with Low APR", and intends to help a borrower learn what I think is important to keep in mind when seeking a Prosper Loan:

- Having a Credit Score of 650 or more.

And what affects the APR in a good way, so that the interest rate is as low as possible:

- Having as high income as possible
- Being a home owner
