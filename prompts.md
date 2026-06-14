# Prompts & Bake-off Notes

Record the exact prompts you used and your verdict here. This file is graded.

## Task 2 — Prompt-pattern bake-off

### Zero-shot prompt

```text
Classify the following support ticket into exactly one label:

Labels:
- billing
- bug
- feature_request
- other

Return ONLY the label.

Ticket:
{text}
```

### Few-shot prompt

```text
Classify support tickets into one label.

Examples:

Ticket: "I was charged twice for my subscription."
Label: billing

Ticket: "The app crashes whenever I upload a photo."
Label: bug

Ticket: "Please add dark mode."
Label: feature_request

Ticket: "How do I change my profile picture?"
Label: other

Now classify this ticket.

Ticket:
{text}

Return ONLY the label.
```

### Chain-of-thought / decomposition prompt

```text
You are classifying customer support tickets.

Think step by step about what category best fits the ticket.

Then return ONLY one of these labels:

billing
bug
feature_request
other

Ticket:
{text}
```

### Verdict (3–4 sentences)

> All three prompting patterns correctly classified the provided support tickets. Zero-shot prompting was sufficient for this task because the categories were simple and clearly defined. Few-shot prompting was slightly more consistent by providing examples for each category. Chain-of-thought did not improve the final classifications and likely used more tokens, making it less efficient for this straightforward classification task.

## Task 3 — Structured output notes

> Both Gemini and the local Ollama model reliably returned valid JSON after enabling structured output and using a low temperature. Gemini classified all tickets correctly, while Ollama misclassified a few tickets and produced less consistent confidence scores, but its JSON format remained valid throughout the test.
