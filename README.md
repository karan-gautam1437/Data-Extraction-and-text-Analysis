**Data Extraction And Text Analysis Project**

**Explaining how you approached the solution**

**Data Gathering:**

- Read the input.xlsx file to get the list of URLs.
- Analysis of the required libraries will be used for further analysis

**Text Extraction:**

- For each HTML content, identify the section containing the article text. For example tags, class etc.
- By Iterating over two columns in a pandas DataFrame, one containing URL\_IDs and the other containing URLs. The `zip` function pairs each URL\_ID with its corresponding URL, allowing the script to process them together in the loop.
- Used HTML parsing techniques to extract only the article text and title, excluding any website headers, footers, or irrelevant content.
- ` `BeautifulSoup object from the HTML content of the web page, which allows it to parse and navigate the HTML structure. 
- Saved all extracted article text and title into separate text files with the URL\_ID as their file names.

**Text Preprocessing:**

- Text preprocessing by splitting the given text into individual sentences used the `re.split()` function from the `re` module. The regular expression pattern `r'\\. '` matches a period (`.`) followed by a space. The `r` prefix before the pattern string indicates a raw string literal, which treats backslashes as literal characters instead of escape characters.
- After splitting the text into sentences, we create a pandas DataFrame named `b` with a single column named 'abc'. The list of sentences obtained from the previous step is used as the data for this column.
- Storing the sentences in a data frame, we can easily perform further data manipulation, analysis, or preprocessing tasks as needed.
- Tokenize the text into words or sentences.
- Remove stopwords (commonly used words like "and", "the", etc.) to focus on meaningful content.

**Text Analysis:**

- Perform basic text analysis tasks such as:

**Positive Score**: This score is calculated by assigning the value of +1 for each word if found in the Positive Dictionary and then adding up all the values.

**Negative Score:** This score is calculated by assigning the value of -1 for each word if found in the Negative Dictionary and then adding up all the values. We multiply the score with -1 so that the score is a positive number.

**Polarity Score**: This is the score that determines if a given text is positive or negative in nature. It is calculated by using the formula: 

Polarity Score = (Positive Score – Negative Score)/ ((Positive Score + Negative Score) + 0.000001) Range is from -1 to +1

**Subjectivity Score:** This is the score that determines if a given text is objective or subjective. It is calculated by using the formula: 

Subjectivity Score = (Positive Score + Negative Score)/ ((Total Words after cleaning) + 0.000001)

Range is from 0 to +1

1. Analysis of Readability

Analysis of Readability is calculated using the Gunning Fox index formula described below.

**Average Sentence Length** = the number of words / the number of sentences

Percentage of Complex words = the number of complex words / the number of words 

Fog Index = 0.4 \* (Average Sentence Length + Percentage of Complex words)

1. Average Number of Words Per Sentence

The formula for calculating is:

Average Number of Words Per Sentence = the total number of words / the total number of sentences

1. Complex Word Count

Complex words are words in the text that contain more than two syllables.


1. Word Count

We count the total cleaned words present in the text by 

1. removing the stop words (using stopwords class of nltk package).
1. removing any punctuations like ? ! , . from the word before counting.

1. Syllable Count Per Word

We count the number of Syllables in each word of the text by counting the vowels present in each word. We also handle some exceptions like words ending with "es","ed" by not counting them as a syllable.

1. Personal Pronouns

To calculate Personal Pronouns mentioned in the text, we use regex to find the counts of the words - “I,” “we,” “my,” “ours,” and “us”. Special care is taken so that the country name US is not included in the list.

1. Average Word Length

Average Word Length is calculated by the formula:

Sum of the total number of characters in each word/Total number of words




**Output Generation:**

- Create a new Excel file or update the existing one to store the computed variables for each article.
- Include columns for URL\_ID, article title, word count, unique word count, sentiment score, named entity count, and any other relevant variables.

