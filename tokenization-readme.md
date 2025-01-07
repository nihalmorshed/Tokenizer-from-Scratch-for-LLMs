# Tokenization in LLMs

This Jupyter notebook demonstrates the fundamentals of text tokenization, a crucial preprocessing step in Natural Language Processing (NLP) and Large Language Models (LLMs). The notebook provides a step-by-step implementation of simple tokenizers and explores various text preprocessing techniques.

## Features

- Basic text preprocessing and tokenization
- Implementation of two tokenizer versions (SimpleTokenizerV1 and SimpleTokenizerV2)
- Handling of special tokens for unknown words and document separation
- Demonstration of encoding and decoding processes
- Regular expression-based text splitting
- Vocabulary creation and management

## Requirements

- Python 3.x
- Regular Expressions (re) library
- urllib.request for downloading sample text

## Installation

1. Clone this repository:
```bash
git clone [your-repository-url]
cd tokenization-llm
```

2. Download the required text file:
```python
import urllib.request
url = ("https://raw.githubusercontent.com/rasbt/"
       "LLMs-from-scratch/main/ch02/01_main-chapter-code/"
       "the-verdict.txt")
urllib.request.urlretrieve(url, "the-verdict.txt")
```

## Usage

The notebook contains two main tokenizer implementations:

### SimpleTokenizerV1
Basic tokenizer with encoding and decoding capabilities:

```python
tokenizer = SimpleTokenizerV1(vocab)
text = "Sample text to tokenize"
ids = tokenizer.encode(text)
decoded_text = tokenizer.decode(ids)
```

### SimpleTokenizerV2
Enhanced tokenizer with support for unknown tokens and document separation:

```python
tokenizer = SimpleTokenizerV2(vocab)
text = "Hello, do you like tea? <|endoftext|> Another sentence."
ids = tokenizer.encode(text)
decoded_text = tokenizer.decode(ids)
```

## Key Features Explained

1. **Text Preprocessing**
   - Splits text based on punctuation and whitespace
   - Removes redundant whitespace
   - Handles special characters and punctuation

2. **Vocabulary Management**
   - Creates unique token sets
   - Assigns unique integer IDs to each token
   - Manages special tokens (unknown words, end of text)

3. **Encoding/Decoding**
   - Converts text to token IDs
   - Reconstructs text from token IDs
   - Maintains proper spacing and punctuation

## Output Examples

```python
# Sample tokenization
text = "It's the last he painted, you know, Mrs. Gisburn said."
ids = tokenizer.encode(text)
print(ids)  # [56, 2, 850, 988, 602, 533, 746, 5, 1126, 596, 5, 67, 7]
print(tokenizer.decode(ids))  # "It's the last he painted, you know, Mrs. Gisburn said."
```

## Contributing

Feel free to submit issues, fork the repository, and create pull requests for any improvements.

## License

[Your chosen license]

## Acknowledgments

- Based on the text "The Verdict" from the LLMs-from-scratch repository
- Inspired by tokenization techniques used in modern LLMs
