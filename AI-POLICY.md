# AI Policy

We have now entered a new era of programming where large language models (LLMs) make it easier than ever to write code and contribute to open source. When used correctly, AI has the potential to save time for both contributors and maintainers. However, without a human-in-the-loop carefully iterating with agents and reviewing every line of code, it can quickly devolve into [AI slop](https://en.wikipedia.org/wiki/AI_slop), requiring significantly more time for maintainers than it would for us to simply write the code ourselves. This AI policy is designed to prevent these kind of "extractive contributions",[^1] ensuring the quality and maintainability of our software and avoiding maintainer burnout.

The following policy applies to GitHub, Slack, and Hugging Face. Note that this is a rapidly evolving landscape, and we may make frequent updates to this policy in order to keep up with new developments in generative AI.

[^1]: [Eghbal, 2020, Working in Public: The Making and Maintenance of Open Source Software](https://press.stripe.com/working-in-public)

## Policy

Our policy is simple and can be explained in a single sentence:

> If we can tell something was written by AI just by looking at it, it is not ready.

This applies to all code, documentation, and issue/PR descriptions, hereafter referred to as "contributions". In addition, all communication with maintainers should be written by you, not by your agent.

Telltale signs of AI slop include but are not limited to:

* Overly verbose code or text, often more than double the length it needs to be
* Defensive coding, handling situations that may never occur with complex error handling
* Unnecessary testing, far beyond what is required to test feature behavior or achieve code coverage
* More comments than code, explaining simple and obvious code in a repetitive way

## Enforcement

When maintainers detect contributions in violation of this policy, they will add an "AI-generated" tag. This is a signal to other maintainers that this issue/PR is not yet ready for them to spend their time on.

If you did not use AI during your contribution, please let us know that we made a mistake and we will remove the label. If your contribution is either partially AI-assisted or fully AI-generated, please continue to work on your contribution until it is of higher quality. If the contribution no longer looks like AI slop, you can request a maintainer take another look. If the situation is unchanged, or if a month passes, the contribution will be automatically closed.
