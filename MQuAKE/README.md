# MQuAKE

paper link [MQuAKE: Assessing Knowledge Editing in Language Models via Multi-Hop Questions](https://arxiv.org/abs/2305.14795).

In this paper, a benchmark for knowledge editing, MQuAKE is introduced, which comprises multi-hop questions that assess whether edited models correctly answer questions where the answer should change as an entailed consequence of edited facts.

Also a simple memory-based approach, MeLLo is introduced, which can scale with LLMs (up to 175B) and outperforms previous model editors by a large margin.


## Datasets

### Overview 
MQuAKE includes a dataset MQuAKE-CF based on counterfactual edits, and another dataset MQuAKE-T of temporal knowledge updates to evaluate model editors on real-world changes.

The datasets are included in `datasets/`. There are three files:
* `MQuAKE-CF-3k.json`: a counterfactual dataset containing 3,000 instances (1,000 for {2,3,4}-hop questions). The results shown in our current paper are based on this dataset (as mentioned in the footnote 2 of the paper).
* `MQuAKE-CF.json`: the full counterfactual dataset containing 9,218 instances.
* `MQuAKE-T.json`: the temporal-based dataset containing 1,825 instances. This is designed to evaluate knowledge editing methods on real-world changes.

### Data format
The dataset is saved as a list of dicts, each of which represents a data instance. An example in `MQuAKE-CF` is shown below.

```
{
  "case_id": 2500,
  "requested_rewrite": [
    {
      "prompt": "{} is a citizen of",
      "relation_id": "P27",
      "target_new": {"str": "Libya", "id": "Q1016"},
      "target_true": {"str": "United States of America", "id": "Q30"},
      "subject": "Vince McMahon",
      "question": "What is the country of citizenship of Vince McMahon?"
    },
    ...
  ],
  "questions": [
    "What city serves as the capital of the country where the CEO of Triple H holds citizenship?",
    "In which city is the capital of the country where the chief executive officer of Triple H is a citizen?",
    "What is the name of the capital city of the country where the CEO of Triple H is a citizen?"
  ],
  "answer": "Washington, D.C.",
  "answer_alias": ["Washington", ...],
  "new_answer": "Franklin",
  "new_answer_alias": ["Franklin, Kentucky", ...],
  "single_hops": [
    {
      "question": "Who is the employer of Triple H?",
      "cloze": "Triple H is employed by",
      "answer": "WWE",
      "answer_alias": ["World Wrestling Federation", ...]
    },
    ...
  ],
  "new_single_hops": [...],
  "orig": {
    "triples": [
      ["Q44567", "P108", "Q35339"],
      ["Q35339", "P169", "Q44430"],
      ["Q44430", "P27", "Q30"],
      ["Q30", "P36", "Q61"]
    ],
    "triples_labeled": [
      ["Triple H", "employer", "WWE"],
      ...,
    ],
    "new_triples": [...,],
    "new_triples_labeled": [...,],
    "edit_triples": [
      ["Q44430", "P27", "Q1016"],
      ["Q1016", "P36", "Q1778943"]
    ]
  }
}
```

For additional details, refer the Original paper

