# Lab 05 — Conclusion

<!--
Read this before you write.

This file is graded by your instructor, by hand, and it is worth 6 of the 15 points.

- Type it yourself. Do not use a chatbot, an AI assistant, an AI autocomplete or a "rewrite my
  text" tool for any part of it, not even for grammar. English that is plain and a little
  clumsy but yours is better than polished text that is not.
- Use your own numbers. Every number you quote must be one your own notebook printed. Copy
  the number exactly as it appeared. A number your notebook did not print is marked as wrong.
- Answer in your own words, about 80-200 words per question. A short answer that uses your
  numbers beats a long answer that could have been written by anyone.
- Delete these comment lines if you like. Keep the three headings and the last line.
-->

## 1. Which layer changed your results the most?

Give the numbers before -> after for that layer (correct / wrong / no answer, out of 20) and say
whether it changed what the agent *can do* or only what it *admits*. If no layer changed the
number of correct answers, say so and explain what the layers did change instead.

(Layer 1 had the most significant impact on the result: 16 / 4 / 4 to 18 / 6 / 0 . The number of correct answers increased, but so did the number of errors—the ability to continue after a tool-related error does not guarantee a correct answer.)


## 2. One failure the full harness did not fix

Pick one question that the full harness (layer 3) still gets wrong or refuses. Give its id
(q01 ... q20). Open its trace in the notebook: at which step did it go wrong, and what did
the model do instead? Name one thing you would add to the harness, and what it would cost
(extra model calls, tokens, time, or a new way to fail).

(In Q18, the model formulated the calculation incorrectly it divided the difference by 100 which is unnecessary when dealing with percentage points. The calculator returned 0.055 and the model output 0.55. The answer was rejected and marked as UNVERIFIED. I would suggest adding a formula-validation step prior to the actual calculation. This would require additional code and a retry would consume more tokens and time)

## 3. Workflow or agent for the monthly ranking?

Dala Insight wants to publish, every month, "which region is highest and which is lowest on one
indicator in one year". Would you ship the fixed workflow or the agent? Use the accuracy, the
number of model calls, the tokens and the time you measured in Part 1. Then say in one sentence
what kind of question would make you choose the other one.

(I would choose the fixed workflow because monthly rankings follow the same steps. I would choose an agent for questions needing several tools and calculations. To compare accuracy, calls, tokens and time, I still need your Part 1 results for the 15 fixed questions.)

---

I wrote this file myself, without any AI tool.
