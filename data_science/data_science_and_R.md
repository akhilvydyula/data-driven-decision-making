What is "data science"? A google search of that question generates 460,000,000 hits, and the first page of that search is populated with a variety of inconsistent definitions. So, to add another to the pile, here's some of my thoughts as I try to make sense of this.

Nate Silver created a stir in his address to the Joint Statistical Meetings (JSM) in 2013 when he said "Data scientist is just a sexed up word for statistician." (Earlier in his address he'd said that he's not a statistician. But then again, neither am I, in spite of my job title.)

In 1962, the statistician John Tukey (author of the classic _Exploratory Data Analysis_) wrote that his central interest was in 
> data analysis, which I take to include, among other things: procedures for analyzing data, techniques for interpreting the results of such procedures, ways of planning the gathering of data to make its analysis easier, more precise or more accurate, and all the machinery and results of (mathematical) statistics which apply to analyzing data.

In 1965, Deming wrote about the "Principles of Professional Statistical Practice". What he described is less about the discipline of Statistics and more closely aligned with what we would now call data science (and beware the dated gender-specific language; apparently women didn't do statistics / data science in 1965):

> "Statistical theory is transferable. The specialist in statistical methods may find himself applying the same basic theory in a dozen different fields in a week, rotating through the same projects the next week. Or, he may work day after day primarily in a single substantive field.
> Either way, the statistician requires certain principles of practice for effective use of statistical knowledge. Knowledge of statistical theory is necessary but not sufficient. Statistical theory does not provide a road-map towards effective use of itself.
> ...
> Even though carried off with reasonable conformance to specifications, a study may fail through structural deficiencies in the method of investigation (questionnaire, type of test, technique of interviewing), to provide the information needed. The statistician may reduce the risk of this kind of failure by pointing out to his clinet in the early stages of the study the nature of the contributions that he himself must put into it."
> Deming, W. Edwards. Principles of Professional Statistical Practice. Ann. Math. Statist. 36 (1965), no. 6, 1883--1900. doi:10.1214/aoms/1177699824. http://projecteuclid.org/euclid.aoms/1177699824.


(Alternate from 1979, better written)
> “The data of an experiment consist of much more than a mean and its standard deviation. The user of the results in order to understand them may require not only the original data, but also a description or reference to the method of investigation, the date, place, the duration of the test, a record of the faults discovered during the test, the amount of nonresponse by class, and any side-effects observed.
>
> That Statistiscian has an obligation to help his client to perceive in advance the limitations of any study that is contemplated.
> 
> An important question to ask before the plans for a study go too far is this: What will the results refer to? How do you propose to use them? The answer(s) sometimes can bring forth drastic modification of the plan.”
>
> “Some Contributions to Statistical Inference and Practice”, by W. E Deming, Ch. 20 in Quantitative Techniques for Evaluating the Behavior of Psychiatric Patients. Burdock, 1979



In 1974, Peter Naur published _Concise Survey of Computer Methods_, wherein he uses the term "data science". It took some time, but the term has really caught on lately.

The term as applied to an individual---a "data scientist"---doesn't appear until 2008.

(The above was drawn from Hannah Augur's recent post, ["Beginner's Guide to the History of Data Science"](http://dataconomy.com/beginners-guide-history-data-science/).)

So perhaps it's a good time to look at what's changed.

### The big data deluge

Data science is often spoken in the same breath as "big data". Which is also not a new thing; those gigabytes and megabytes were growing in the background until one day someone realized that we'll soon be dealing in yottabytes, and it wasn't just data anymore, it was "big data".

I think the UPC bar code is a perfect example of this shift. The UPC code was designed in the early 1970s as point-of-sale scanners were being adopted. This computerization was designed to improve business processes---instead of the clerk at the checkout punching in every price, the scanner did that work. Coupled with the increasing power and memory of computers, it also allowed stores to better track sales and inventory.

######![UPC bar code](http://images.all-free-download.com/images/graphiclarge/upca_bar_code_clip_art_16286.jpg)


Since then there has been exponential growth in the volume of data collected as part of business process.  And there have been similar expansions in how that data is used. The UPC codes have revolutionized supply chain management, and are used by stores to understand consumer behaviour. It’s not just “How many boxes of strawberry Pop Tarts are on the shelves?” or “How many boxes of strawberry Pop Tarts do we need to order?” but “What environmental conditions can be used to predict when shoppers will buy strawberry Pop Tarts?” [(Spoiler: hurricanes.)](http://www.nytimes.com/2004/11/14/business/yourmoney/what-walmart-knows-about-customers-habits.html)

And retailers are using information about what we buy to try to sell us more stuff---think of amazon’s “frequently bought together” and “customers who viewed this item also viewed” entires. 

Another thing that has changed is that in many cases data are updated frequently, and made available to analysts on the fly. This means that there is very little lag between the data collection and the analytic output. (Think of the GPS system in your car or on your phone.)

In parallel with big data, public agencies around the world are being more transparent by releasing more and more data, and making it available in formats that can be read by any computer. This supports transparency and accountability, and also provides a public good by allowing outside entities to use publically-collected data and information in other applications.


### The Data Science Process


So what does it take to make sense of all of this data? To collect it, shape it, analyze it, and draw from it intelligence and knowledge?

“Data scientist” is a term increasingly used to describe an individual with a range of skills necessary to make this happen. But what do data scientists _do_?

It turns out that Tukey was prescient. "Data science" as currently understood is a process that is essentially what he'd described over 50 years ago. My own thinking about this is:

1. Defining the research question
2. Collecting data
3. Data carpentry (a.k.a. tidying, munging, hacking)
4. Exploratory data analysis
5. Data modeling
6. Communication
7. bridging #4-6 is a seventh element: Data visualization

Grolemund & Wickham's forthcoming book [_R for Data Science_](http://r4ds.had.co.nz/do-science-with-data.html) has the following diagram:

![A data science project](http://r4ds.had.co.nz/diagrams/data-science.png)

While this diagram is a good place to start thinking about how to approach the data science, it has some shortcomings. They have a) skipped the important first step of collecting data (it has to come from somewhere), b) assumed that the "Understanding" phase won't send you back to the "Tidy" step, and c) looped the "Understanding" phase. I would also argue that visualization is an important tool that applies to exploring, modeling, and communicating...it's not constrained to the "Understanding" phase.

(Note: statistics, as in the academic discipline, is one of the subject areas that a data scientist _absolutely_ needs to know. Knowledge of robust statistical methods supports accurate and informed EDA and modeling. These techniques and tools applied in these two phases of the data science process _are_ statistics, and a good practitioner of data science will benefit from advances in statistics. Contrary to some writers you may encounter, I don't believe that it is a "versus" thing, or that one is better than the other. Statistics makes good data science, and data science is one place that someone trained in statistics can become a practioner.)


### The Role of R in Data Science

R won't help you formulate your hypothesis or collect your data, but in the subsequent steps R is a great tool. Having been designed initially to facilitate exploratory data analysis and statistical modeling (i.e. statistics), packages have subsequently been created that provide the tools to quickly and efficiently undertake data carpentry and data visualization. 

As Roger D. Peng has put it, "The R programming language has become the de facto programming language for data science." (From the book "jacket blurb" for [_R Programming for Data Science_](https://leanpub.com/rprogramming).)

Let's look at each of the five components separately:

#### 1. Defining the research question

Too often overlooked!

#### 2. Collecting data

* Three sources:
+ Pre-packaged
+ Administrative or business data
+ Original (e.g. survey)

Pre-packaged data: whether in the text book or from open data source (Statistics Canada, Data BC)

#### 3. Data carpentry

> Raw data is rarely usable for analysis without significant work. (Peter Mimno, ["Data carpentry"](http://www.mimno.org/articles/carpentry/))

Sometimes called "data hacking", "data wrangling", or "data munging", a better term is "data carpentry". Peter Mimno rightly points out that the other terms either mischaracterize the nature of the work, or are essentially meaningless. He continues:

> the process is more like deciding how to cut into a piece of material, or how much to plane down a surface. It’s not that there’s any real distinction between good and bad, it’s more that some parts are softer or knottier than others. Judgement is critical.

The other key point is that data are often messy. [The Quartz guide to bad data](https://github.com/Quartz/bad-data-guide) provides a rather comprehensive list of all the problems you might encounter on your road to the analysis.

There's a whole sub-topic on tidy vs. non-tidy (different than untidy!) data (see for instance Roger Peng's [blog entry of 2016-02-17](http://simplystatistics.org/2016/02/17/non-tidy-data/). That's a tangent for another day.

R is very good for pulling your data from other sources. There's a wealth of tools for querying SQL databases, importing Excel files (e.g. `readr`).

There are also many tools available for effectively working with dates (date formatting is a favourite pet peeve of mine).

And finally, data carpentry is facilitated with packages such as `dplyr`, which contain straight-forward verb-based syntax (such as `filter`, `group_by` and `summarise`) to create permutations of your existing data. 

I can't say enough good things about `dplyr`. It has become my go-to tool for things I used to do in other software, including completely replacing my use of pivot tables in Excel. And it addressess many of the criticisms that "R is slow"--for one of the 


#### 4. Exploratory data analysis

The ideas of "exploratory data analysis" (EDA) was first presented by Tukey, and he presented a set of tools for EDA in his seminal book (1977). In the book he writes:
> Exploratory data analysis is detective work--numerical detective work--or counting detective work--or graphical detective work. ...the analyst of data needs both tools and understanding." (p.1)

Tukey also emphasizes the importance of data visualization in exploring data; the book is the source of the quote:
> ... pictures based on exploration of data should _force_ their messages upon us. Pictures that emphasize what we already know--"security blankets" to reassure us--are frequently not worth the space they take. Pictures that have to be gone over with a reading glass to see the main point are wasteful of time and inadequate of effect. **The greatest value of a picture** is when it _forces_ us to notice **what we never expected to see.** (p.vi) _[emphasis in original]_

Plenty has been written about using R as a tool for exploratory data analysis; Roger Peng's leanpub book _Exploratory Data Analysis with R_ is a great place to start. Other resources include Eric Cai's [Chemical Statistician blog series](https://chemicalstatistician.wordpress.com/tag/exploratory-data-analysis/).


#### 5. Data modeling

Advanced statistical methods

Where computing power has really changed the game; expanded possibilities of techniques such as K-NN and Monte Carlo

(add machine learning, K-NN etc)


#### 6. Communication

Shiny!

Link to data journalism -- Jonathan Stray, Alberto Cairo


#### 7. Data visualization

An important component of understanding your data at the EDA and modeling stages (#4 and 5), and in how the data's meaning is communicated (#6)

And as the dataviz and web display packages improve (e.g. the recent release of `ggplot2` v.2 was a big leap forward; yes it broke some of my code but the additional functionality is worth the trouble) R will only get better. 

Another sidebar: ggplot2 2.0.0 was released on 2016-01-01 [look up the correct date]. Since then there have been enough additions to warrant a 2.1.0 release; and meanwhile there are new extensions being added in the development version (e.g. [sub-title functionality by Bob Rudis](http://rud.is/b/2016/03/12/ggplot2%E3%81%A7%E5%AD%97%E5%B9%95-subtitles-in-ggplot2/?utm_content=buffer42831&utm_medium=social&utm_source=twitter.com&utm_campaign=buffer).)


Data visualization is also an important component of the last stage of the data science process: communication.


___

### The role of technology

I just want to loop back to technology for a minute.

######![Navvies digging the Manchester Ship Canal](http://www.creativetourist.com/cms/wp-content/uploads/2016/01/PHM-Grafters-Industrial-society-in-image-and-word-@-Peoples-History-Museum.-Navvies-Manchester-Ship-Canal-by-W-E-Birtles-%C2%A9-Chethams-Library-smaller-472x264.jpg)

The people in this picture are “navvies”---the men who dug the canals that criss-cross Britain, which were an important part of the industrial revolution. The idea of canals was an old one, and the use of the steam train to move the dirt was an innovation that helped speed the construction of the [Manchester Ship Canal](http://www.victorianweb.org/history/work/sullivan/13.jpg).

But when it came to building the Panama Canal, human effort was insufficient---and the harnessing of steam power in a new way, with the steam shovel, was the technology that accelerated canal building.

######![Stereo pair of steam shovel digging the Panama Canal](http://cdn.loc.gov/service/pnp/cph/3c10000/3c17000/3c17200/3c17220r.jpg)
(source: [Library of Congress](https://www.loc.gov/item/96520543/))

The same is true with information technology---it can be used to accelerate the use of data, but it is _not_ the solution.

Simultaneous with the increased volume and variety of data that are being collected (and in some cases shared), we have more accessible technology to work with the data. This includes powerful desktop computers with lots of storage, networks and clouds to share the information, and advances in analytic tools.

> "People think this is a technological revolution, but it's really a business revolution enabled by technology." (Stephen Messer, quoted in Barlow, _Learning to Love Data Science_, p.6)

### In closing:

> The scientific method guides data science. Data science solves known problems with the scientific method. (Grolemund & Wickham, [_R for Data Science_](http://r4ds.had.co.nz/do-science-with-data.html), chapter 20)
