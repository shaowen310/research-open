# LLM Reasoning

## Chain of Thought. 2023/01/10. Google Brain

TLDR: Chain of thought unlocked LLM’s reasoning capability.

The authors showed that reasoning abilities emerge in sufficiently large language models via chain-of-thought prompting.

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

The authors explore the ability of language models to perform few-shot prompting for **reasoning tasks.** **They supplied prompts that consist of triples**: \<input, chain of thought, output>.

They show that sufficiently large language models can generate chains of thought **if demonstrations of chain-of-thought reasoning are provided in the exemplars for few-shot prompting**.

The empirical evaluation shows the chain of thought prompting outperforms standard prompting on arithmetic, commonsense, and symbolic reasoning benchmarks.

### Experiments

Datasets

GSM8K: benchmark of math word problems

SVAMP: dataset of math word problems with varying structures

ASDiv: dataset of diverse math word problems

AQuA: dataset of algebraic word problems

MAWPS

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

## Tree of thoughts. 2023/12/03. Google Brain.

TLDR: Tree of Thoughts enables exploration over coherent units of text (thoughts) that serve as intermediate steps toward problem-solving.

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

Motivation:

People search through a combinatorial problem space - a tree where the nodes represent partial solutions, and the branches correspond to operators that modify them. Which branch to take is determined by heuristics that help to navigate the problem-space and guide the problem-solver towards a solution.

Abstraction:

State: a partial solution with the input and the sequence of thoughts so far.

Value: evaluates the progress they make towards solving the problem. A heuristic for the search algorithm to determine which states to keep exploring and in which order.

Action: choosing a state to explore next.

Details:



Example:

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>



