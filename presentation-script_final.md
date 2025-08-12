# Sparse Distributed Memory Model Presentation

## Slide 1: Configuring the model

**Process Flow:**
MNIST digit (28×28 pixels) → Binary thresholding → Bipolar representation (+1/-1) → Projection to 2000-dimensional space → Sparse activation (500 of 100,000 locations) → Pattern retrieval

The process transforms a 784-pixel MNIST image into a hyperdimensional representation:

1. Start with raw image data (28×28 = 784 pixels)
2. Apply threshold to create binary values (0/1)
3. Convert to bipolar values (+1/-1) for mathematical operations
4. Project into 2000D space via multiplication with BASIS_VECTORS matrix
5. For each HD vector, compute similarity to 100,000 address vectors
6. Activate only 500 closest locations (p=0.005 of total memory)

**Key point:** This sparse activation is key to the model's efficiency - using just 0.5% of memory locations per pattern while maintaining robust and specific retrieval capabilities.

## Slide 2: Performance Under Noise

**LEFT – Recall accuracy gradually decreases with increasing noise**
- Progressive noise (0%-90%) applied to digit "4"
- Key limitation: SDM cannot identify inverse patterns despite preserved structure
 
**RIGHT – Performance: recall accuracy gradually decreases with increasing noise**
- 70.9% accuracy on clean images
- Overall pattern demonstrates predictable, graceful degradation

**BOTTOM – Noise impact: initial steep increase followed by gradual effects of additional noise**
- Shows vector difference between clean and noisy representations
- Vector similarity preserved even at extreme noise levels

## Slide 3: SDM Capacity

- Maintains ~70% accuracy from hundreds to 25,000 patterns, with a brief performance dip around 1,000 patterns before restabilizing
- Demonstrates efficient storage capacity for large datasets

## Slide 4: Model characteristics and memory recall

**Key strengths and limitations:**
- Key strength of SDM: Gradual performance decline vs. Hopfield's all-or-nothing retrieval 
- Key limitation: Failure to recognize inverse representations despite preserved structure

**Memory recall concepts:**
- Memory recall: the mental process of retrieving information from the past
- Cued recall: retrieving memories when provided with a specific prompt or cue

**Kanerva's SDM is fundamentally a cued recall system:**
- Input as Cue: The system takes an input pattern (like a digit image) as its cue
- Associative Activation: This cue activates memory locations that are most similar to it
- Retrieval Process: The cue doesn't need to be perfect - just similar enough to activate the right memory locations
- Pattern Completion: From partial or noisy information, the system can retrieve the complete stored pattern

## Slide 5: Memory Principles Quote

> 'The brain works with memory based on two contradictory principles. Parts of the brain try to make as much of the information as possible into something that is similar and categorizable to save space, while the hippocampus fights to preserve the uniqueness of events.'
> — Anders Fjell

It highlights the tension between generalization and specificity:

- **Hopfield networks** 'categorize to save space.' They compress information into a limited number of stable patterns, merging similar patterns and losing specificity. This is more like how our semantic memory works – creating general concepts rather than preserving every detail.

- **Kanerva's SDM**, on the other hand, resembles more the hippocampus approach - it 'fights to preserve uniqueness.' By distributing patterns across many specific memory locations, it maintains the distinct features of individual patterns while still allowing for similarity-based retrieval. More closely mirroring our episodic memory that preserves specific experiences.

These models offer valuable insights into memory function, with Hopfield networks strong in learning general patterns and pattern completion, and SDM demonstrating how distributed representations can address capacity limitations while remaining robust against noise - together they show different aspects of the brain's memory systems.