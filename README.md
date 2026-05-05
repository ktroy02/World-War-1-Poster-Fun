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

.ve-iframe https://raw.githubusercontent.com/ktroy02/World-War-1-Poster-Fun/main/sentiment_graph.html 

---

## Findings

The overall average sentiment score across all 1,470 posters was **-0.0516**, placing the dataset is just barely in the negative territory by VADER's standard thresholds. This finding, while not consisting of all posters on the LOC website, is still meaningful in context: the dominant emotional tone of WWI propaganda, as captured in archival summaries, skews slightly negative.

This result may seem counterintuitive because propaganda is often associated with stimulating, optimistic messaging designed to inspire action. A closer look at the data reveals that a large portion of the posters in this collection deal with themes of sacrifice, loss, injury, disability, and financial obligation. War bond posters frequently invoke the suffering of soldiers to motivate civilians to contribute financially while not actively fighting. Recruitment posters appeal to the emotions of guilt and duty rather than excitement. Posters that have candid depictions of the war frequently include injured or disabled soldiers, skewing the dataset towards a more somber sentiment overall. 

The distribution of scores is wide, ranging from **-0.9643** (most negative) to **+0.9432** (most positive), suggesting that while the average is slightly negative, individual posters vary enormously in their emotional register. Some posters are strikingly hopeful, celebrating allied unity and the promise of peace. Others are deeply mournful, depicting the human cost of war with unflinching directness.
