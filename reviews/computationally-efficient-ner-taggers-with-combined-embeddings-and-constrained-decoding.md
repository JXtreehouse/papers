
## Computationally Efficient NER Taggers with Combined Embeddings and Constrained Decoding

Brian Lester, Daniel Pressel, Amy Hemmeter, and Sagnik Ray Choudhury, Arxiv, 2020
 

## Summary
- concatenation of multiple pre-trained word embeddings instead of using single embedding
- model: constrained decoding by having large negative values for illegal transitions such as I- of one class cannot follow B- of another.
- experiments: tasks - NER, Slot filling and POS tagging
- framework: [Baseline](https://github.com/dpressel/mead-baseline)
- best complementary embeddings: dissimilar with the base embedding + great coverage (attestation) w/ the dataset.
- constrained decoder works when there is a large proportion of "strictly dominated tokens" - ambiguous (token-tag correlation is low) tokens that can only take a single tag value because of the previous tag    

## Strengths
- impressive results/claims across multiple tasks. 
- seemingly simple idea, which pays dividends.
- strong analysis section 

## Weaknesses 
- Didn't see a *Models* section which goes into details on the implementation details of constrained decoding over the crf layer 

## Notes
- IOBES performs better than BIO, *Ratinov and Roth (2009)*
- CRF forward algorithm is *O(NT<sup>2</sup>)* where N is the length of the sentence and T is the number of possible tags
- Cross Entropy Loss - *O(N)* for sparse labels