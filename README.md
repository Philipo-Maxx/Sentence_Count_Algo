# Sentence Analyzer Algorithm

This project provides an algorithm and its JavaScript implementation to analyze a sentence. The goal is to compute and display:

- The length of the sentence.
- The number of words in the sentence.
- The number of vowels in the sentence.

## Algorithm Overview

### Algorithm: `read_a_sentence`

**Variables:**

- `sentence`: A string input containing the sentence to analyze.
- `sentence_length`: An integer to store the length of the sentence.
- `spaces_count`: An integer to count the number of spaces in the sentence.
- `word_count`: An integer to calculate the number of words in the sentence.
- `vowel_count`: An integer to count the number of vowels in the sentence.

**Steps:**

1. **Read Input:**

   - Read the `sentence` from user input.
   - Calculate the length of the sentence and store it in `sentence_length`.

2. **Count Words:**

   - Iterate over each character in the sentence.
   - Count the number of spaces (`spaces_count`).
   - Calculate the number of words as `spaces_count + 1` and store in the `word_count` variable.

3. **Count Vowels:**

   - Iterate over each character in the sentence.
   - Count the vowels (`a`, `e`, `i`, `o`, `u`) and store in the `vowel_count` variable.

4. **Output Results:**
   - Print the `sentence_length`, `word_count`, and `vowel_count`.

## JavaScript Implementation

The following JavaScript code implements the above algorithm:

```javascript
function analyzeSentence(sentence) {
  // Convert the sentence to lowercase to handle case insensitivity
  sentence = sentence.toLowerCase();

  // Get the length of the sentence
  const sentenceLength = sentence.length;

  // Initialize counts
  let spacesCount = 0;
  let wordCount = 0;
  let vowelCount = 0;

  // Edge case: if sentence is empty
  if (sentenceLength === 0) {
    console.log("Sentence Length: 0");
    console.log("Word Count: 0");
    console.log("Vowel Count: 0");
    return;
  }

  // Count spaces and vowels
  for (let i = 0; i < sentenceLength; i++) {
    if (sentence[i] === " ") {
      spacesCount++;
    } else if ("aeiou".includes(sentence[i])) {
      vowelCount++;
    }
  }

  // Calculate word count
  wordCount = spacesCount + 1;

  // Output results
  console.log("Sentence Length:", sentenceLength);
  console.log("Word Count:", wordCount);
  console.log("Vowel Count:", vowelCount);
}

// Example usage
analyzeSentence("Hello world!");
```
