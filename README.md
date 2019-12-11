# DATA-512-FINAL
SPL Checkout Data Analysis of Macmillan Publishers. Final Project for UW DATA 512
## Introduction

In October of this year the King County Library System (KCLS) announced that it would [no longer purchase newly released eBooks from Macmillan Publishers](https://kcls.org/news/kcls-boycotts-macmillan-publishers-ebook-embargo/) starting November 1st, 2019. This came in response to [Macmillan Publishers decision to place an embargo on sales of ebooks to US libraries](https://www.publishersweekly.com/binary-data/ARTICLE_ATTACHMENT/file/000/004/4222-1.pdf) due to the effects digital checkouts were having on ebook sales. This decision by Macmillan will also be affecting The Seattle Public Library (SPL) and news of the embargo and its possible effects have motivated me to understand and investigate the impact this may have on Seattle's readers. I urge readers of this report to read NPR's article on the issues at hand, ['You May Have To Wait To Borrow A New E-Book From The Library'](https://www.npr.org/2019/11/01/775150979/you-may-have-to-wait-to-borrow-a-new-e-book-from-the-library).


This notebook is a final project for The University of Washington's Human Centered Data Science course (DATA 512) taught by [Jonathan Morgan](https://jtmorgan.net/). This notebook based report is meant to meet and exceed the [assignment 7 requirements](https://wiki.communitydata.science/Human_Centered_Data_Science_(Fall_2019)/Assignments#A7:_Final_project_report) and was modeled after [Rex Thompson's Report on Paid Street Parking](https://github.com/rexthompson/DATA-512-Final-Project/blob/master/DATA-512-Final-Project.ipynb) per instructor recommendation.

#### Research Question 1: Which type of readers will be affected by Macmillan’s eBook embargo?

#### Research Question 2: What is the possible impact if SPL also boycotts Macmillan?

#### Research Question 2 (Revised): If SPL were to have boycotted Macmillan in 2018, what would the impact have been?

## Reproducibility

This analysis contained in this report is meant to be fully reproducible. The [Checkouts by Title data](https://data.seattle.gov/Community/Checkouts-by-Title/tmmm-ytt6) is publicly available through Seattle governments Open Data Program. However this dataset exceeds Github's current individual file size limit and is therefore if one wishes to reproduce with the full data set please visit the link above and download as csv. If for some reason the link is no longer available please visit https://data.seattle.gov/ and search for "Checkouts by Title" or "Checkouts".

## Data

This analysis relies on the [Checkouts by Title dataset](https://data.seattle.gov/Community/Checkouts-by-Title/tmmm-ytt6) which is publicly available through Seattle governments Open Data Program.

Column | Format | Description |
|-----|------------|----|
UsageClass | Text | Denotes if item is “physical” or “digital” |
CheckoutType | Text | Denotes the vendor tool used to check out the item. |
MaterialType | Text | Describes the type of item checked out (examples: book, song movie, music, magazine) |
CheckoutYear | Number | The 4-digit year of checkout for this record. |
CheckoutMonth | Number | The month of checkout for this record. |
Checkouts | Number | A count of the number of times the title was checked out within the “Checkout Month”. |
Title | Text | The full title and subtitle of an individual item | 
Creator | Text | The author or entity responsible for authoring the item. |
Subjects | Text | The subject of the item as it appears in the catalog |
Publisher | Text | The publisher of the title |
PublicationYear | Text | The year from the catalog record in which the item was published, printed, or copyrighted. |

## Data Limitations

The dataset I found to be surpisingly clean and was able to quantify a lot based on checkouts. I believe the data limitation in this current area is the lack of KCLS checkout data. This is the largest US library system and I was disappointed to not be able to find their checkout data.

## What the Data Does Not Tell You

The data does not have an personal information about anyone checking out these books. It also does not include which branch location data or any location data in general. Because the demographics of the readers of these ebooks was not available it makes it difficult to answer exactly who would be impacted. However, this is greatly to the benefit of the privacy of Seattle's readers!

## References
Seattle Open Data Program Checkouts by Title Dataset: 
KCLS boycott of Macmillan comm: https://kcls.org/news/kcls-boycotts-macmillan-publishers-ebook-embargo/
Stranger Article I took screenshot of: https://www.thestranger.com/slog/2019/10/22/41762476/king-county-public-library-will-boycott-macmillan-ebooks-seattle-public-library-will-not
NPR: https://www.npr.org/2019/11/01/775150979/you-may-have-to-wait-to-borrow-a-new-e-book-from-the-library

## Other Resources

### On R

R Reproducability: https://mran.microsoft.com/documents/rro/reproducibility

R data.table is good: https://eliocamp.github.io/codigo-r/en/2019/07/why-i-love-data-table/
    data.table intro: https://cran.r-project.org/web/packages/data.table/vignettes/datatable-intro.html
    data.table sum one liner with lapply: https://stackoverflow.com/questions/30180590/data-table-sum-and-subset

Cool R guide: https://r4ds.had.co.nz/data-visualisation.html

### On the Embargo and Libraries

https://www.overdrive.com/publishers/st-martins-publishing-group?autoLibrary=t&autoRegion=f&rf-publishDate=2018-12-04&rt-publishDate=2019-09-04&sort=popularity&sd=desc

https://en.wikipedia.org/wiki/Macmillan_Publishers

https://www.owler.com/company/macmillan

KCLS leads ebook checkouts in US: https://kcls.org/news/kcls-tops-overdrive-digital-checkouts-in-2017/

KCLS boycott of Macmillan comm: https://kcls.org/news/kcls-boycotts-macmillan-publishers-ebook-embargo/

SPL Budget: https://www.spl.org/about-us/the-organization/budget-and-operations/budget

TOR Imprint Embargo Statement: https://www.ualibrary.org/mediasrvc/blog/statement-release-regarding-tor-digital-books

TOR Embargo: https://www.publishersweekly.com/pw/by-topic/industry-news/libraries/article/77532-tor-scales-back-library-e-book-lending-as-part-of-test.html

TOR top sellers: https://us.macmillan.com/search?collection=top-sellers&supapress_order=publishdate-desc&page_number=3&format=MEBB&imprint=tor-books

Stranger Article I took screenshot of: https://www.thestranger.com/slog/2019/10/22/41762476/king-county-public-library-will-boycott-macmillan-ebooks-seattle-public-library-will-not

NPR: https://www.npr.org/2019/11/01/775150979/you-may-have-to-wait-to-borrow-a-new-e-book-from-the-library

ALA report: http://www.ala.org/news/sites/ala.org.news/files/content/mediapresscenter/CompetitionDigitalMarkets.pdf

Panorama Project US Library data report: https://static1.squarespace.com/static/5ae8ec5f70e8024a05804e7a/t/5c00229e6d2a73e6ae5478a5/1543512743044/Community+Reading+Event+Impact+Report+v1.pdf

### Similar Research

Jason Sanford doing similar research: https://www.patreon.com/posts/does-library-tor-28075188

Someone's powerbi on the same dataset: https://community.powerbi.com/t5/Data-Stories-Gallery/Readership-in-Seattle-by-Decisive-Data/td-p/224252

### Other datasets (unused)

NY Times Books API: https://developer.nytimes.com/docs/books-product/1/overview
