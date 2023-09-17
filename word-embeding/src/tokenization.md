# Tokenization

Most NLP task do not operate directly on character as that would often be inefficient or, depending on the task, would not produce meaningful result.

Instead it divide the text into word, or more accurately token. The important part is that it does not see character has compose the token.
Token are threated as atomic unit that cannot be farther divided.

Depending on which NLP task you whish to perform, the constraint the tokenization system must meet change.

In the case of this programme, the only NLP task we run is clustering the embedding vector of the token.
This essentially mean that we create group of word that are syntactically and semantically similar.

For this task we would like token to acutely be word, which is not a propriety all approach give us.

In your case, we do not need the tokenizer to be exhaustive. Some word that were not encounter when the vocabulary was created
can not be tokenize and are silently ignore. While this is not a deal breaker for this program, this behavior would not
be acceptable for a LLM.

It work noting that exact definition of a word is ambiguous and that even the best approach have edge case.

The most rebuste aproche I could use would be the one outline in the "Default Word Boundary Specification" section of the
Unicode Standard Annex #29 (it can be found [here](https://www.unicode.org/reports/tr29/#Default_Word_Boundaries))

I did create a prototype that implemented part of this method, however it was to slow for my likeing.

Instead I fell back to the word boundary of the regex create. The regex create implementation is a based on the
"Simple Word Boundaries" which is spacify in a [other](https://unicode.org/reports/tr18/#Simple_Word_Boundaries) unicode document.
It is wort noting that the regex implementation differ a bit from say specification.

this aproche, while far from perfect word well enophe.