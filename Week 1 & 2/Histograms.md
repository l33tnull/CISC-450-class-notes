- another way to display the distribution of a quantitative variable
- useful for large [[Data]] sets
- divides the variable values into equal-sized intervals
- can see number of individuals in each interval but not the individual data values
- avoid large bin histograms; they group only in few bins; does not show good variability
- avoid small bin histograms; groups data in lots of bins; does not help see pattern in data
- histograms can also be used to describe the [[Dotplot#Shape of Data|shape]], [[Dotplot#Center of the Distribution|center]], [[Dotplot#Spread of the Distribution|spread]], and [[Dotplot#Outlier of the Distribution|outliers]] of the distribution of quantitative variables
# Making Histograms

- start with a [[Dotplot]]
- divide variable values into equal-sized intervals called bins
- turn each bin into a bar
- the height of the bar indicates the number of individuals in the bin, labeled as count
- for each bin the values at the left-hand endpoint of the bin are included in the bin but those at right-hand endpoint are not
- count is also called frequency
- from counts determine a percentage of individuals with a given interval of variable values
- percentage called a relative frequency
# Analyzing a Histogram using Percentages (Relative Frequencies)

- find total count (sample size)
- divide total by the count of bins pertaining to what you are trying to figure out
- multiply that by 100% to get a percentage
# Creating Histograms in Excel

- select the range of cells

![[../Images/Images/IMG-20260826153244401.png]]

- On the Insert tab, go to the Charts Group and click the Histogram symbol

![[../Images/Images/IMG-20260826153356747.png]]

- Click on Histogram

Result:

![[../Images/Images/IMG-20260826153438619.png]]

To change the bin size and number of bins:

- Right-click on the horizontal axis and click Format Axis

![[../Images/Images/IMG-20260826153522278.png]]

The format axis pane appears. You can edit the bin width and number of bins.

A bin range is a range of values that specifies the limit for each column of the histogram.

![[../Images/Images/IMG-20260826153549685.png]]

Result:

![[../Images/Images/IMG-20260826153608398.png]]
# Creating a Histogram using Data Analysis Toolpak

- Go to the Data tab and click Data Analysis.

![[../Images/Images/IMG-20260826153713561.png]]

- In the Data Analysis dialog box, select Histogram

![[../Images/Images/IMG-20260826153752751.png]]

- In the Histogram dialogue box, select the Input range, Bin range, and Output range. Checkmark the chart output.

![[../Images/Images/IMG-20260826153815615.png]]

- Click OK.

![[../Images/Images/IMG-20260826153837711.png]]

The first bin shows all the values below it. In the above case, 20 shows 0 values, which shows that there are 0 employees that are less than age 20.
# Using Histograms to Compare Distributions

- Use histograms to compare the distribution of a **quantitative variable** across **two groups** (similar to earlier comparisons with dotplots).
- Descriptions focus on the same four elements:
	 **Shape** (skewed left/right, symmetric)
     **Center** (typical values — described with intervals, not exact numbers)
     **Spread** (variability, estimated range)
     **Outliers/deviations** from the overall pattern
- Histograms make it easy to use **percentages (relative frequencies)** to compare intervals.
## Rules for Fair Visual Comparison

- Both histograms must share the **same horizontal scale** and **bin width**.
- Both must share the **same vertical axis scale**.
- Then bar heights can be compared directly.
- Know bin convention: left endpoints are _included_ 
	- Ex: a 1,000 g baby falls in 1,000–1,500
- Caveat: **bin width choice affects shape** and can change our sense of "typical" values — center and spread can only be described approximately, using intervals.
## Example: Smoking & Birth Weight

- Context: 189 new mothers at a Massachusetts hospital in the 1980s; question — does smoking during pregnancy affect birth weight?
- Groups: nonsmokers (n = 115) vs. smokers (n = 74).
### Shape, Center, Spread by Group
|Feature|Nonsmokers (top)|Smokers (bottom)|
|---|---|---|
|Shape|Slightly skewed **left**|Slightly skewed **right**|
|Typical range|~half of babies weigh 3,000–4,000 g (56/115 = 49%)|~half of babies weigh 2,000–3,000 g (38/74 = 51%)|
|Spread|Large variability; weights ~1,000–5,000 g|Large variability; weights ~500–4,500 g|
|Range estimate|~4,000 g|~4,000 g|#
### Key Takeaway Pattern

- Lots of **overlap** between the two distributions.
- Both groups have similar spread, but the **centers differ** — nonsmokers' babies cluster heavier, smokers' babies cluster lighter.
## Using Benchmarks to Compare

A **benchmark** is a fixed cutoff used to compute and compare percentages for each group.
- **Low birth weight** (medical definition: under 2,500 g):
		Nonsmokers: 3 + 8 + 18 = 29 → 29/115 = **25%**
		Smokers: 1 + 1 + 6 + 22 = 30 → 30/74 = **41%**
		Smokers show a much higher incidence of low birth weight.
- **Macrosomia** ("big baby syndrome": 4,000 g or more):
		Nonsmokers: 6 + 2 = 8 → 8/115 = **7%**
		Smokers: 1 → 1/74 = **1%**
		Very few smokers' babies reach the heavy end.
## Writing the Comparison Paragraphs

Structure of the model write-up:

1. **Context first** — who the individuals are (mothers who smoked vs. didn't) and what the variable is (baby birth weight, in grams).
    
2. **Similarities** — both groups show large variability, similar overall range (~4,000 g), and substantial overlap (nonsmokers ~1,000–5,000 g; smokers ~500–4,500 g).
    
3. **Differences** — subtle shift in typical ranges: 49% of nonsmokers' babies are 3,000–4,000 g vs. only 36% of smokers'; 54% of smokers' babies are 2,000–3,000 g vs. only 35% of nonsmokers'.
    
4. **Benchmark evidence** — 41% vs. 25% low birth weight.
    
5. **Conclusion tied to thesis** — smoking is _associated_ with lower birth weights, but high variability suggests other variables also contribute (association ≠ sole cause).
## Tips Checklist

- Develop a **thesis statement** comparing the two groups.
- Make context clear: individuals + variable + units.
- **Synthesize** observations into paragraphs that support the thesis — don't just list facts.
- Incorporate the course vocabulary: shape, center, spread, relative frequencies (percentages), benchmarks.

One-sentence summary: when comparing two histograms, match the scales, describe shape/center/spread for each group, quantify differences with percentages and benchmarks, and write it up as a thesis-driven comparison rather than a list.