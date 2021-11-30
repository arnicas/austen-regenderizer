# austen-regenderizer

This is the skeleton of a start at making Pride & Prejudice gender-choosable, thrown up for #Nanogenmo 2021, although the data labeling took me a year.

The data files were created by hand labeling at the command line using a lightly modified version of David Bamman's [cl-coref-annotator](https://github.com/dbamman/cl-coref-annotator).

The annotations were merged in pandas into the "merged" files in the data directory.

There are various string replacement tools and choices in the notebook.  For this #nanogenmo,
I swapped these characters' genders (m-f and f-m, although the code supports non-binary):

````
name_replacements = {
    0: {"Elizabeth": "Edward", "LIZZY": "EDDIE", "Lizzy": "Eddie", "Eliza": "Ed", "Miss Bennet": "Mr. Bennet", "Elizabeth Bennet": "Edward Bennet", "Miss Eliza": "Mr. Ed", "Miss Elizabeth": "Mr. Edward", "Miss Lizzy": "Mr. Eddie"},
    1: {"Darcy": "Darcy", "Mr. Darcy": "Miss Darcy", "Fitzwilliam Darcy": "Philomena Darcy"},
    2: {"Jane": "John", "Jane Bennet": "John Bennet", "Miss Bennet": "Mr. Bennet"},
    6: {"Bingley": "Bingley", "Charles": "Charlotte", "Mr. Bingley": "Miss Bingley", "Charles Bingley": "Charlotte Bingley"},
    3: {"Mrs. Bennet": "Mr. Bennet"},
    4: {"Mr. Bennet": "Mrs. Bennet"},
    5: {"Lydia": "Luke"},
    18: {"Kitty": "Connie", "Catherine": "Connor"},
    19: {"Mary": "Morris"},
    24: {"daughters": "sons", "girls": "boys", "ladies": "gentlemen", "sisters": "brothers"}
}
````

There are some labeling bugs, a code bug with male possessives and compound nouns, and 
it's confusing to have Miss Bingley both the hero and villain (I should have swapped Caroline too).  Also the text needs formatting to return proper paragraphs, brat (labeling process tool) removed them.

## Issues

There are many!  So many it will be a long blog post.  Gender preference from a marriage standpoint is the least of it.

There's an outstanding code bug related to male possessives right now. "him fears" etc. As well as continued labeling issues to fix.

## Samples

### Chapter 1

It is a truth universally acknowledged, that a single woman in possession of a good fortune, must be in want of a husband.
However little known the feelings or views of such a woman may be on her first entering a neighbourhood, this truth is so well fixed in the minds of the surrounding families, that she is considered the rightful property of some one or other of their sons.

"My dear Mrs. Bennet," said her gentleman to her one day, "have you heard that Netherfield Park is let at last?" Mrs. Bennet replied that she had not.

"But it is," returned he; "for Mrs. Long has just been here, and she told me all about it." Mrs. Bennet made no answer.

"Do you not want to know who has taken it?" cried her husband impatiently.

### Chapter 2


Not all that Mr. Bennet, however, with the assistance of his five sons, could ask on the subject, was sufficient to draw from his wife any satisfactory description of Miss Bingley.
They attacked her in various ways -- with barefaced questions, ingenious suppositions, and distant surmises; but she eluded the skill of them all, and they were at last obliged to accept the second-hand intelligence of their neighbour, Lady Lucas. Her report was highly favourable. Sir William had been delighted with her. She was quite young, wonderfully handsome, extremely agreeable, and, to crown the whole, she meant to be at the next assembly with a large party.

Nothing could be more delightful!
To be fond of dancing was a certain step towards falling in love; and very lively hopes of Miss Bingley's heart were entertained.

"If I can but see one of my sons happily settled at Netherfield," said Mr. Bennet to his wife, "and all the others equally well married, I shall have nothing to wish for."
In a few days Miss Bingley returned Mrs. Bennet's visit, and sat about ten minutes with her in her library. She had entertained hopes of being admitted to a sight of the young gentlemen, of whose beauty she had heard much; but she saw only the mother. The gentlemen were somewhat more fortunate, for they had the advantage of ascertaining from an upper window that she wore a blue coat, and rode a black horse.

An invitation to dinner was soon afterwards dispatched; and already had Mr. Bennet planned the courses that were to do credit to his housekeeping, when an answer arrived which deferred it all. Miss Bingley was obliged to be in town the following day, and, consequently, unable to accept the honour of their invitation, etc.. Mr. Bennet was quite disconcerted. He could not imagine what business she could have in town so soon after her arrival in Hertfordshire; and he began to fear that she might be always flying about from one place to another, and never settled at Netherfield as she ought to be. Lady Lucas quieted him fears a little by starting the idea of her being gone to London only to get a large party for the ball; and a report soon followed that Miss Bingley was to bring twelve ladies and seven gentlemen with her to the assembly. The boys grieved over such a number of ladies, but were comforted the day before the ball by hearing, that instead of twelve she brought only six with her from London -- her five sisters and a cousin.

And when the party entered the assembly room it consisted of only five altogether -- Miss Bingley, her two sisters, the husband of the eldest the eldest, and another young woman. Miss Bingley was good-looking and gentlemanlike; she had a pleasant countenance, and easy, unaffected manners. Her sisters were fine women, with an air of decided fashion. Her brother-in-law, Mr. Hurst, merely looked the gentleman; but her friend soon drew the attention of the room by her fine, tall person, handsome features, noble mien, and the report which was in general circulation within five minutes after her entrance, of her having ten thousand a year. The gentlemen pronounced her to be a fine figure of a woman, the ladies declared she was much handsomer than Miss Bingley, and she was looked at with great admiration for about half the evening, till her manners gave a disgust which turned the tide of her popularity; for she was discovered to be proud; to be above her company, and above being pleased; and not all her large estate in Derbyshire could then save her from having a most forbidding, disagreeable countenance, and being unworthy to be compared with her friend. Miss Bingley had soon made herself acquainted with all the principal people in the room the principal people in the room; she was lively and unreserved, danced every dance, was angry that the ball closed so early, and talked of giving one herself at Netherfield.
Such amiable qualities must speak for themselves.

What a contrast between her and her friend! Miss Darcy danced only once with Mrs. Hurst and once with Miss Bingley, declined being introduced to any other lady, and spent the rest of the evening in walking about the room, speaking occasionally to one of her own party. Her character was decided. She was the proudest, most disagreeable woman in the world, and everybody hoped that she would never come there again.

Amongst the most violent against her was Mr. Bennet, whose dislike of her general behaviour was sharpened into particular resentment by her having slighted one of his sons. Edward Bennet had been obliged, by the scarcity of gentlemen, to sit down for two dances; and during part of that time, Miss Darcy had been standing near enough for him to hear a conversation between her and Miss Bingley, who came from the dance for a few minutes, to press her friend to join it.
"Come, Darcy," said she, "I must have you dance. I hate to see you standing about by yourself  in this stupid manner. You had much better dance."





