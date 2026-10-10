---
permalink: /Assignment-1/
title: "Assignment-1"
---

## Background & Expectations
Before starting, we thought the language of war in 20th-century science fiction would change a lot depending on when the books were written. We expected things like new military technology and the Cold War to shape the words authors used to imagine future wars. We were most interested in the war and space travel tags, because together they bring up two big ideas in sci-fi: how fighting changes on Earth, and the possibility of war spreading beyond it.


Our hypothesis was that war language wouldn’t stay the same across the century. Instead, we thought it would show changing ideas about weapons, political threats and how much damage humans are capable of. This connects to David Seed’s point in Science Fiction: A Very Short Introduction that imagined future wars often carry over the political and technological tensions of the author’s own time. In this case, sci-fi doesn’t just predict the future but also reflects what people were worried about when it was written.


That’s why we were especially interested in the atomic age. Before nuclear weapons, we felt that a lot of science fiction treated technology as a sign of progress or a way to make humans more powerful. Nuclear weapons made that harder to believe, because science could now produce weapons that could destroy on a massive scale. Because of this, we expected sci-fi after World War II to use words like "atomic" and "bomb" more often, along with other words about weapons and destruction. If that happened, it would suggest that authors weren’t just adding new technology to their stories, but were also showing how uneasy they felt about how quickly war was changing and how devastating it could be.


## Computational Insights
With 1000 texts in the corpus, it wouldn't have been possible to read every book cover to cover to figure out these trends. It would have taken a huge amount of time. The notebook let us look at the whole corpus in ways a normal read-through couldn't. It was interesting to explore and play around with, and we feel like the heatmaps, TF-IDF and KWIC worked well together. The heatmaps showed us how often our war words appeared across tags and time periods, TF-IDF showed us what the computer thought was distinctive, and KWIC let us go back to the actual sentences to see what the words meant.


We split the corpus into two time ranges, 1930–1949 and 1950–1969. We picked twenty-year ranges so each one would have enough texts to compare, though this also means we can't see exactly when within a range a change happened. For the heatmaps, we searched for fifteen words we'd expect in anything war-related: war, battle, attack, enemy, enemies, soldier, soldiers, army, fleet, gun, guns, atomic, bomb, bombs and invasion. We had to list plurals separately, because this part of the notebook only matches exact words. The heatmaps show each word as a rate per 1,000 words, so tags with more text don't automatically look bigger.


## Trends & Surprises


Looking back at our hypothesis, we honestly aren't sure whether it was confirmed or not. Some words changed between the two periods and others barely moved, so the picture wasn't as clear as we expected. But we gained a lot of new insight along the way, and some of the most interesting findings were things we never expected to find.


![Heatmap of war words by tag, 1930–1949](/assets/images/heatmap1930-1949.png)
*Figure 1: How often each of our war words appears per 1,000 words in each tag, for books published between 1930 and 1949.*


![Heatmap of war words by tag, 1950–1969](/assets/images/heatmap1950-1969.png)
*Figure 2: The same war words and tags for books published between 1950 and 1969.*


Something that surprised us was how often "gun" shows up across all the tags, not just war. Even though our main focus was the war tag, we thought it was worth looking at the others too. Mars actually had the highest rate of "gun" in both periods (0.30, then 0.33 per 1,000 words). We wouldn't expect that in books about Mars, where we'd assume the writers would use more inventive sci-fi terms. To us this shows how tied sci-fi is to the technology of its time. That said, we didn't check "gun" in KWIC, so some of these could be ray guns and not regular guns.


We expected "atomic" to go up after 1945, but it didn't. It went down in space travel (0.16 to 0.10), society (0.11 to 0.08) and action (0.12 to 0.09), and stayed about the same in war (0.13) and Mars (0.16). "Bomb" did go up a lot in the war tag though (0.07 to 0.18), and so did "bombs" (0.08 to 0.14). We think "atomic" might not always refer to weapons. It could be used for things like atomic energy or science, which would explain why it didn't rise the way we expected. "Bomb" going up in the war tag makes more common sense, since bombs are something you'd naturally expect in war stories. We didn't get to check "atomic" in KWIC, so this is our best guess.


The biggest surprise came from KWIC. "Yankees" was one of the top distinctive words for the war tag in 1950–1969, so we checked it in context.


Here are some example KWIC results for "yankees":


> **Bond:** "...decent treatment the nazi shook his head disdainfully, ach, you **yankees**, always the dreamers, warfare is no silly child's game..."
>
> **Norton:** "...don't give me any nonsense about goin to kill **yankees** because they killed him, when a man goes to war..."
>
> **Norton:** "...that for yourself today an there's guerrillas to give the **yankees** trouble, they hole up in the brelsford caves..."


We only looked at a few examples, so we can’t say much about the books themselves. Even so, the word shows up in different books and kinds of sentences. In the first one, from a book by Bond, it appears in the same line as “nazi,” next to a line about warfare. In the other two, from a book by Norton, it’s used around words like “kill,” “war” and “guerrillas.”


## Methodological Questions


We made heatmaps for our two time ranges to see if the words used changed between the two periods. We also ran TF-IDF on the war and space travel tags for both periods, to see what the computer would pick out as distinctive instead of only the words we chose ourselves. But with only two tags to compare, it mainly gave us character names.


![TF-IDF, 1930–1949, first round](/daah/assets/images/1-tf-idf-1930-1949.png)
*Figure 3: The most distinctive words for the space travel and war tags in 1930–1949, according to TF-IDF. Almost all of them are character names rather than war vocabulary.*


![TF-IDF, 1950–1969, first round](/daah/assets/images/1-tf-idf-1950-1969.png)
*Figure 4: The most distinctive words for the space travel and war tags in 1950–1969, according to TF-IDF. Names like kirby, rennie and boyd take up the top spots for the war tag.*


Because the results were mostly names, we added them as stopwords and ran the TF-IDF chunk again:


![TF-IDF, 1930–1949, second round](/daah/assets/images/2-tf-idf-1930-1949.png)
*Figure 5: The most distinctive words for 1930–1949 after removing the first round of names. New names replaced the old ones at the top.*


![TF-IDF, 1950–1969, second round](/daah/assets/images/2-tf-idf-1950-1969.png)
*Figure 6: The most distinctive words for 1950–1969 after removing the first round of names. Again, new names appeared, along with a few words like "yankees," which led us to check it in KWIC.*


This showed us a big limitation. Even after we removed the first round of names, new ones kept appearing at the top, so the chart wasn’t really showing us war vocabulary at all. That’s why we turned to KWIC, to look at one of the remaining words in its actual sentences.


We also ran into limits with the tools themselves. We wanted to check more words in KWIC, but posit.cloud kept warning us about a session limit and each search was taking too long to run, so we only got to look at “yankees” in context.


Even so, we feel like the heatmaps, TF-IDF and KWIC worked well together to help us move towards a conclusion. Each one showed us something the others couldn’t: the heatmaps tracked the words we picked, TF-IDF showed what the computer picked, and KWIC let us see how a word was actually used.


## Scope & Scale
Having 1000 texts meant we could see patterns across decades that we'd never find just by reading. But it also made it easy to miss that a couple of books could take over the results. We wanted to run KWIC on more words, but we decided we had enough to go off and just worked with what we had. We feel like sci-fi was a good genre to do this with, but we'd also like to try the same kind of analysis on fantasy, since there are a lot of metaphors to be made there and it would be interesting to see how its language changes over time.


## Transferability


This project showed us that distant reading can be useful outside of this class. When researching a topic, authors often reference each other, and being able to analyze which ones are cited most could help build a more credible argument and a better bibliography. In art history, distant reading could help identify trends in the language critics, historians and artists themselves used in reviews, catalogues and artist statements, and show which movements and themes people were most interested in at a certain point in time.


## Moving Beyond the Notebook
If we had more coding skills, we would try to computationally create a visual timeline showing how words evolve over time. In particular, we'd want to track words that mean the same thing but were said differently in different periods, so you could see one word fade out as another one takes its place.




## Contributions
We both contributed to every part of this project. We sat in work sessions together and worked on the notebook, the analysis, and the writing at the same time.


## AI Disclosure
We used Claude to help decide/brainstorm war-related words to search for, and to debug errors when we could not figure it out ourselves after trying.

[Ready for grading]
