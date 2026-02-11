---
id: n-gram fuzzy search
aliases: []
tags: []
---
# N-gram fuzzy search

The **n-gram fuzzy search** is an algorithm for fuzzy searching string

## Logic

To achieve this it break the string into overlapping chunks of N characters then
compare how many chuncks overlap between two strings. It then assign a score to
it

## Process

### Generating n-grams

First we need to generate an **n-grams** the most common approach is to split
into chuncks of three characters

We start by adding padding at the start and end of the string

```
"batman" → "  batman "

Trigrams:
  "  b"  (positions 0-2)
  " ba"  (positions 1-3)
  "bat"  (positions 2-4)
  "atm"  (positions 3-5)
  "tma"  (positions 4-6)
  "man"  (positions 5-7)
  "an "  (positions 6-8)
```

The added padding ensured that the start and end of words are distinctive. For
example "bat" and "combat" will have different edge trigrams

### Comparing the sets of n-grams

To compare the set of n-grams there is two approaches 

#### Jaccard Similarity 

The **jaccard similarity** also call the **symmetric approach** compare the
length of the intersection of the two trigrams to the length of the union

```
score = |A ∩ B| / |A ∪ B|
```

This approach has the following benefits/disadvantage
- good when strings are similar length
- penalizes heavily when one string is much longer

It is use when the strings have similar length

#### Asymmetric Similarity

The **asymmetric similarity** compare the length of the intersection of the two trigrams to
the length of the trigram

```
score = |A ∩ B| / |A| (where A = query trigrams)
```
This approach works well for short query vs long target and it's mainly use for
search where users type partial names


### Definition the threshold

With the score we must define a threshold so that each comparison that has a
score less than it are not kept

We typically use this one depending of the purpose
- 0.3 : permissive, catches more typos but more false positive
- 0.4 : balances
- 0.5 : strict but might miss valid matches

## Implementation

```rust
use std::collections::HashSet;

pub fn trigrams(s: &str) -> HashSet<String> {
    let s_with_spaces = format!("  {} ", s.to_ascii_lowercase());
    let mut set = HashSet::new();

    for i in 0..s_with_spaces.len().saturating_sub(2) {
        set.insert(s_with_spaces[i..i + 3].to_string());
    }

    set
}

/// Jaccard similarity (symmetric)
/// Good for comparing strings of similar length
/// score = |A ∩ B| / |A ∪ B|
pub fn similarity_symmetric(a: &str, b: &str) -> f64 {
    let tri_a = trigrams(a);
    let tri_b = trigrams(b);

    let intersection = tri_a.intersection(&tri_b).count() as f64;
    let union = tri_a.union(&tri_b).count() as f64;

    if union == 0.0 {
        return 0.0;
    }

    intersection / union
}

/// Asymmetric similarity
/// Good for short query vs long target (search boxes)
/// score = |A ∩ B| / |query|
pub fn similarity_asymmetric(query: &str, target: &str) -> f64 {
    let tri_query = trigrams(query);
    let tri_target = trigrams(target);

    if tri_query.is_empty() {
        return 0.0;
    }

    let intersection = tri_query.intersection(&tri_target).count() as f64;

    intersection / tri_query.len() as f64
}
```

## Complexity

The complexity of this algorithm is $O(n+m)$ where $n$ is the length of the
query and $m$ the length of the target

The complexity emerge from the creation of the n-grams because in the worst case
we create an n-gram of 1 so we must loop over all the string length

## Advantages / disadvantage

### Advantages

- Handles typos well: "batmn" vs "batman" shares most trigrams
- Handles transpositions: "bamtan" still shares many trigrams
- Language agnostic — no dictionary needed
- Fast with proper indexing (PostgreSQL GIN/GiST, inverted index)

### Disadvantage

- Poor with missing characters: "btmn" vs "batman" fails (few trigrams overlap)
- Length sensitive with Jaccard: "zelda" vs "The Legend of Zelda" scores low
- No semantic understanding: "car" vs "automobile" scores 0
