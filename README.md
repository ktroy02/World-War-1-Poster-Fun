# WW1 Poster Fun
### The war ended. The data didn't.

---

## Introduction

World War One is remembered as one of the most violent wars in modern history, thanks to its unique timing at the start of the 20th century that coincided with technological leaps. Technology for war had steadily been improving (or getting more deadly) since the end of the Fraco-Prussian war that occurred 30 years prior, meaning that the generation of people that witnessed the First World War hadn't seen such a vast scale of destruction in multiple decades. While guns, planes and hand grenades made their debut in the War to End All Wars, a different battle was being waged through paint, ink and canvas. The financial realities of war halted the economic machines of the modern world, as men and women left their homes and jobs to support the war effort. Those who were left at home were met with a variety of images that detailed their mission: ration, donate and survive through the tightened grip of the Great War. The era that produced this rich archive of images represents the larger culture of war shared by countries separated by politics, borders, and oceans.

This project utilizes methods from the field of Digital Humanities to analyze a collection of over 1,400 WW1 posters pulled from the Library of Congress digital archive. Instead of focusing solely on the visual data, using computational sentiment analysis allows us to measure the emotional undertone embedded within the poster’s summaries. Moving beyond a traditional close reading approach allows us to ask broader questions: how does sentiment vary across the posters from different nations? How does the content and purpose of these posters change from culture to culture, if it does at all?
By combining natural language processing with archival research, this project bridges the gap between traditional humanities scholarship and computational methods. Resulting in an  interactive, data driven visual essay that invites readers to explore the emotional landscape of WWI propaganda in a modern way. 


## Methods

This project was built using a combination of Python, NLTK, and Plotly, applied to a dataset of WWI poster descriptions sourced from the Library of Congress digital archive. The dataset  contains 1,470 posters with usable textual summaries, each describing the visual content and purpose of an individual poster.


### Data Collection

The poster metadata (including titles, summaries, Library of Congress IDs, and dates) was scraped from the Library of Congress digital collections and compiled into a CSV file containing 1,618 rows. After cleaning the empty rows resulting from an error, 1,470 rows with complete summary text were retained for analysis.

### Sentiment Analysis

Sentiment analysis was performed using VADER (Valence Aware Dictionary and sEntiment Reasoner), a language-based sentiment analysis tool developed specifically for short, emotional texts. VADER assigns each text a compound sentiment score ranging from -1 (most negative) to +1 (most positive), with scores above 0.05 classified as positive, below -0.05 as negative, and between the two as neutral.

VADER was chosen for this project because it is well-suited to short descriptive texts and does not require large training datasets. Each poster summary was passed through the VADER coding tool and assigned a compound score, which was then added to the dataset as a new column.

### Visualization

Results were visualized using Plotly, an interactive Python graphing tool. The final scatter plot displays all 1,470 posters sorted from most negative to most positive sentiment, with each point color-coded on a red-yellow-green scale. Hovering over any point reveals the poster's title, LCCN (ID), date, sentiment score, and a brief summary explaining the message of the poster.

.ve-iframe https://ktroy02.github.io/World-War-1-Poster-Fun/sentiment_graph.html

---

## Findings

The overall average sentiment score across all 1,470 posters was **-0.0431**, placing the dataset is just barely in the negative territory by VADER's standard thresholds. This finding, while not consisting of all posters on the LOC website, is still meaningful in context: the dominant emotional tone of WWI propaganda, as captured in archival summaries, skews slightly negative.

This result may seem counterintuitive because propaganda is often associated with stimulating, optimistic messaging designed to inspire action. A closer look at the data reveals that a large portion of the posters in this collection deal with themes of sacrifice, loss, injury, disability, and financial obligation. War bond posters frequently invoke the suffering of soldiers to motivate civilians to contribute financially while not actively fighting. Recruitment posters appeal to the emotions of guilt and duty rather than excitement. Posters that have candid depictions of the war frequently include injured or disabled soldiers, skewing the dataset towards a more somber sentiment overall. 

The distribution of scores is wide, ranging from **-0.9643** (most negative) to **+0.9432** (most positive), suggesting that while the average is slightly negative, individual posters vary enormously in their emotional register. Some posters are strikingly hopeful, celebrating allied unity and the promise of peace. Others are deeply mournful, depicting the human cost of war with unflinching directness.

The table below is color-coded according to the sentiment score of the individual poster. Red: Negative, Yellow: Neutral, Green: Positive

The descriptive statistics below for the 1,470 WWI poster summaries reveal a dataset with high variability in emotional tone. The mean sentiment score of -0.0431 places the collection just slightly in negative territory, suggesting that on average, the posters leaned toward depressing or somber messaging, however slight it may be. The median score of 0.0000 indicates that exactly half of the posters fell on either side of neutral, meaning the negative pull comes largely from a smaller group of highly negative outliers rather than a broad negative trend. The standard deviation of 0.3775 and wide range of 1.9075 confirm that poster sentiment wasn’t organized in terms of emotion, spanning from deeply negative depictions of suffering and enemy threat to strongly positive calls for patriotism and victory. This spread reflects the diverse propaganda strategies employed cross-culturally during the war. The table below is color-coded according to the sentiment score of the individual poster. Red: Negative, Yellow: Neutral, Green: Positive

.ve-iframe https://ktroy02.github.io/World-War-1-Poster-Fun/sentiment_stats.html height=350

## Poster Score Examples

The following three posters represent the emotional extremes and the midpoint of the dataset. Each was selected based on its VADER sentiment score. 

### Most Positive Poster Score: 0.9432
**Per la libertà e la civiltà del mondo**
*Italy · [1917] · LCCN: 2004666223*

![Most Positive Poster](https://tile.loc.gov/storage-services/service/pnp/cph/3g10000/3g12000/3g12200/3g12256v.jpg)

Translated as "For the liberty and civilization of the world," this Italian poster earns the 
highest sentiment score in the dataset at 0.9432. The image  depicts soldiers from Italy, Great Britain, France, and the United States 
standing together beneath their respective national flags. Its text calls on citizens to 
subscribe to the National Loan for the liberty of the civilized world. The imagery of allied 
unity and the language of liberation and civilization combine to produce one of the most 
positive sentiment scores in the entire dataset. Rather than invoking sacrifice or suffering, 
this poster frames the war as a collective, noble fight for freedom shared 
across nations. It is a rare example of unambiguously optimistic WWI propaganda.

🔗 [View on Library of Congress](https://www.loc.gov/item/2004666223)

---

### Neutral Poster: Score: 0.0000
**Motherless, fatherless, starving--How much to save these little lives?**
*United States · [1918] · LCCN: 2002722700*

![Neutral Poster](https://tile.loc.gov/storage-services/service/pnp/cph/3g00000/3g09000/3g09800/3g09861v.jpg)

Despite its emotionally charged title, this American Red Cross poster scores exactly 0.0000, which is perfectly neutral by VADER's measure. This is a good example of how VADER analyzes language literally: words like "motherless," "fatherless," and "starving" carry negative connotations in everyday speech, but VADER may balance these against the implied positive appeal to charity and saving lives. The score of zero does not mean the poster is emotionally empty; instead, it reflects the tension between the careful neutrality needed in order to be approved for political use, and the human cost war takes. This poster reminds us that sentiment analysis has limits when applied to persuasive historical texts where emotional complexity is the point.

🔗 [View on Library of Congress](https://www.loc.gov/item/2002722700)

---

### Most Negative Poster — Score: -0.9643
**Kriegsgefangenenheimkehr. Auskunft! Rat! Hilfe!**
*Germany · [1919] · LCCN: 2004665987*

![Most Negative Poster](https://tile.loc.gov/storage-services/service/pnp/cph/3g10000/3g11000/3g11700/3g11709v.jpg)

This German poster, produced just after the war's end in 1919, shows a returning prisoner 
of war clutching his belongings and looking bewildered, with other returning prisoners 
visible in the background. The text announces information, advice, and help for returning 
POWs. The score of -0.9643 makes it the most negative poster in the dataset, textually 
speaking — a fitting reflection. Where other posters asked civilians to give money or enlist, 
this one confronts the aftermath: broken men returning to a broken country, in need of basic 
guidance just to navigate civilian life again.

🔗 [View on Library of Congress](https://www.loc.gov/item/2004665987)

---

## Conclusion

This project set out to ask how emotions were marketed during a period of war and arrived at a nuanced answer. The data suggests that the dominant tone of this poster collection is slightly negative, driven by the weight of themes such as sacrifice, suffering, disability, and obligation that pervade the visual culture of the early 20th century. The range is enormous: from jubilant celebrations of allied unity to quiet portraits of the vulnerable that were left behind, the posters in this dataset tell a far more complex emotional story than any single narrative of heroism or tragedy could capture.

Sentiment analysis is not a perfect tool for reading propaganda. VADER was designed for 
modern English text and performs less reliably on translated summaries, archival 
descriptions, and images themselves. The scores reflect the language of the poster descriptions, not the posters themselves, a limitation worth acknowledging given the intensely visual nature of this archive. Nevertheless, as a method for exploring large collections of cultural artifacts, sentiment analysis opens up patterns that would be invisible to a single reader working through the archive manually. There are some things where close reading does not make sense, and technology can work to fill in the gaps on our behalf. 

Digital humanities projects like this one argue that data and interpretation are not opposites. 
Numbers do not replace close reading, they work in tandem to give us a more comprehensive and fulfilling picture of the past. The most negative poster in this dataset is not just a data point. It reflects a very real, unheard voice in history, of people that came home to find their lives completely upended by the chaos and cruelty of war. That is, if one could come back home at all, or find an untimely death in the muddy trenches of central Europe. The data has revealed their stories, giving us an unflinching glimpse of a world at war. the edge of a war that has already ended, clutching his belongings, looking for help. The data pointed us in the right direction, and the rest is history.

---

*WW1 Poster Fun · Sentiment Analysis Archive · The war ended. The data didn't.*

