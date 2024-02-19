# Voyant Text Analysis

## Objective

This lesson will show you how to use a web-based text mining tool to create visualizations with different types of text.

## About Voyant

![Voyant GIF](/assets/voyant-image.png)

Voyant is an application for text / data mining, visualization, and analysis. It was developed by Stéfan Sinclair (McGill University) and Geoffrey Rockwell (University of Alberta). It is user-friendly for beginners to text mining, developing a text corpus, and analyzing texts or qualitative data.

### Access Voyant

It is open source (meaning free to use and be accessed) and offers a Web-based environment (interface), meaning that you do not need to install Voyant Tools to use it. I.E. It may be done through your browser!

Generally speaking, a corpus will remain accessible as long as it **accessed at least once a month**.

### Highlights

1. Voyant includes many interactive features and [guidance for using each feature](https://voyant-tools.org/docs/#!/guide/tools).
2. Data inputs can be through a web url or local files.
3. Supports large size texts and a variety of file formats, including:

   - Text files (txt)
   - web based files (html)
   - XML files
   - PDF files
   - rich text files (rtf)
   - Microsoft Word documents (docx)
   - zip files (zip) for multiple texts collected

4. Visualizations can be downloaded or embedded within web pages.
5. You do not need any knowledge of coding!

## Demo

1. Open your preferred web browser and [go to Voyant Tools](https://voyant-tools.org/).
2. There are currently four ways to upload text to Voyant:
   1. Open one of the practice corpora provided by Voyant
   2. Copy / paste the full text into the box provided
   3. Copy / paste the link(s) (URLs) into the box provided
   4. Add files from your computer using the upload button below the text box
3. ACTIVITY: Each group designate one person to demonstrate (i.e. connect via hdmi to the monitor at your table). Choose and open one of the three practice corpora. Spend ten minutes exploring together.

### "Default Skin"

Default UI presented with opening a new corpus and includes Cirrus, Reader, Trends, Summary, Contexts.

#### Cirrus

**Cirrus** is a word cloud that visualizes the words used most frequently. You can use it for a corpus or individual file. Central location + larger size = most frequently used words. The color of words and their  position are not significant - if you resize the window or reload the page, words may appear in a different location than before.

If you click the **Terms** icon, a table view of common terms across your corpus will appear. A search box will appear at the bottom to search for specific terms as well.

The **Links** icon shows a network graph of frequently used words. Hovering your mouse over words will show their frequency of use in the corpus. If you double-click on a word it will show more results. Keywords are in blue, words in proximity to them are in orange.

Cirrus has a slider near the bottom (with the label "Terms") that allows you to adjust the number of words displayed. The default value is 50.

By default Cirrus shows the top frequency terms for the entire corpus. It's also possible to show top frequency terms for a single document. To do so, select 'scale' and choose the document.

Word clouds can be effective at very quickly drawing attention to high frequency terms. They have also been harshly criticized as being highly reductive and even misleading, as [argued persuasively by Jacob Harris](http://www.niemanlab.org/2011/10/word-clouds-considered-harmful/) and others. However, the reduction of information can also be powerful (as in the [example of comparing stereotyped vocabulary from advertizing for toys](http://crystalsmith.ca/word-cloud-toy-ad-vocabulary-reinforces-gender-stereotypes/)), and Cirrus is perhaps best used in conjunction with other more exploratory and nuanced tools.

![toolbar](/assets/min-toolbar.png)

A toolbar appears above all of the individual graphics.

1. The square with an arrow is a way to export this particular visual. You can export a URL, a way to embed the graphic, or a bibliographic reference.
2. The windows symbol is a way to select a new tool that is not part of the default skin and replace this particular window. If you click the windows icon, this categorized option box will appear to select a different Voyant tool based on what you want to view. Try changing the tool to a different one - what happens?
3. The two circles is a way to customize that tool. If you click the two circles, this option box will appear to adjust settings.
      1. Stopwords lets you add to Voyant Tools auto-common stopwords list that were already removed, such as "an," "and," "or," "but," etc.
      2. White List: you can define a set of allowed words (the opposite of a stopwords list), only terms in this list will be shown in Cirrus (note that the stopwords list is still active, so you may want to choose "None" from the stopwords menu to deactivate it)
      3. Categories lets you categorize frequent words
      4. Font family lets you change the font
      5. Palette lets you change color coding
4. The ? mark is to help explain what that tool does and how to use it.

To reset the tool, select the two-circles icon and then 'reset'.

#### Reader

Reader is where the text is displayed for reading. You can scroll down within the text reader to view more content. Hover over a word to show its frequency in the document. You can click on a word or search for it in the search box to see how often it appears in your corpus.

If you change it to TermsBerry, this visual will display with frequent words. Hover your mouse over a bubble to see how many times that word appears and words that appear next to it in texts will also change color.

#### Prospect Viewer

This shows an overview of the entire corpus, especially useful when there are multiple documents in a corpus. The bars represent each document in the order they appear in the corpus. The relative length of the document is represented both vertically and horizontally (in other words, the taller and wider a document is shown, the longer it is).

There is a thin vertical blue bar that indicates the current position of the Text Reader in the corpus. You can click anywhere along the Prospect Viewer to jump to another location.

#### Trends

Trends (or Term Frequency Chart) provides distribution plots that display the frequencies of word(s) across texts. Each series in the graph is colored according to the word it represents and a color key is displayed. You can click on the words in the key to make them disappear or reappear in chart. An information box will appear by putting your mouse over the dot.

Document Terms shows five columns by default (but you can customize).

- \# is the document number
- Count is the raw frequency of the term in the document
- Relative is the relative frequency of the term in the document
- Trends is a sparkline graph that shows the distribution of the term within the segments of the document
- Significance is a common way of expressing how important a term is in a document relative to the rest of the corpus
- Z-Score (or standard score) is a normalized value for the term's raw frequency compared to other term frequencies in the same document

#### Summary

Summary provides data about the corpus, including:

- Number of files
- How many words are used total in files
- How many unique words are used total in files
- High and low vocabulary counts
- Most frequent words used
- Distinctive words

Documents shows a table of the documents in the corpus and includes functionality for modifying the corpus.

- Words is the number of individual words (tokens) found in the document
- Types is the number of word forms found in the document
- Ratio is the ratio of types to tokens – higher numbers generally mean greater vocabulary diversity
- Words/Sentence is an approximation of the average number of words per sentence
- Author is the document's author (if it can be determined)
- Language is the document's language (if it can be guessed)

Phrases displays phrases that are repeated, how often, and their word length (default shows them in descending order of length).

- Term is the repeating phrase
- Count is the number of times this phrase repeats in the corpus
- Length is the number of words in the listed phrase
- Trends shows the distribution of relative frequencies across documents in the corpus

#### Contexts

Contexts shows textual context of a word, to its left and right.

Correlations compares two words.

- If there is a negative correlation, it means that as the use of term 1 is used more frequently, term 2 is used less frequently.
- If there is a positive correlation, then when term 1 is used term 2 tends to also be used at an increase.

There is also a slider that determines how much context to consider when looking for collocates. The value specifies the number of words to consider on each side of the keyword (so the total window of words is double). By default the context is set to 5 words per side, and the slider can have a minimum of 1 and a maximum of 30.

#### Bubblelines

Bubblelines visualizes the frequency and distribution of terms in a corpus.

Each document in the corpus is represented as a horizontal line and divided into segments of equal length (50 by default).

Each selected word is represented as a bubble with the size of the bubble indicating the word’s frequency in the corresponding segment of text. The larger the bubble the more frequently the word occurs.

### Non-Default-Skin Tools

Voyant currently has [24 options for tools](https://voyant-tools.org/docs/#!/guide/tools).

Try changing 3 of the default skin tools to a different one.

In groups, discuss for 10 minutes:

- What do the different tools reveal?
- How do your results change?
- Which tools do you like best or find confusing to understand?

### Exporting your corpus

#### URLs

Option 1: Bookmark a corpus to return to it later:

- Click Export at the top of the page → select URL for this view
- Voyant indicates that the corpus will be “accessible as long as it accessed at least once a month”

Option 2: Embed a corpus to your webpage:

- Click Export at the top of the page→ select an HTML snippet → click export for the snippet to appear
- Copy and paste the snippet in your page

#### Downloading visualizations

Click the square with an arrow, then click the Export Visualization option, select either the png or svg option.

You can right click on the image and save it to your computer.

#### Exporting your whole corpus

- Hover your mouse over the top right corner
- Export = the square with an arrow
- *NOTE* this is how you can export the full corpus
- Left icon (icon with an A) = how to change the language
- House icon = start over with a new or updated corpus
- Window (four squares) icon = change the tools in your panel
- ? icon = help feature

## Additional Resources

- [Voyant Documentation](https://voyant-tools.org/docs/#!/guide/tools)
- [Voyant github repository](https://github.com/sgsinclair/Voyant)
- [Voyant GoogleSlides Deck from Ruth Carpenter](https://docs.google.com/presentation/d/1PtWn3KSFaYsrJGElWNzmQNvb4hMowViRUehNT4aDXso/edit#slide=id.g129635d4b2e_0_0)
- [Art History Voyant Tutorial](https://psu.mediaspace.kaltura.com/media/Art+History+Voyant+Tutorial/1_tr1f0yai)
- [https://library.villanova.edu/application/files/9815/8739/5480/VoyantToolsParadiseLostTutorial.pdf](https://library.villanova.edu/application/files/9815/8739/5480/VoyantToolsParadiseLostTutorial.pdf)

## Credits

This Voyant lesson is adapted from Ruth Carpenter, Digital Scholarship Librarian at Binghamton University.
