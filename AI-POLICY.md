# AI Policy

The TorchGeo Organization maintains a number of popular ML libraries. Our users and developers are all ML enthusiasts, thus it should come as no surprise that many contributors would also like to use large language models (LLMs) to contribute to TorchGeo. However, to ensure the quality and maintainability of our software and avoid maintainer burnout, we have to set some boundaries.

Note that this is a rapidly evolving landscape, and we may make frequent updates to this policy in order to keep up with new developments in generative AI.

## Policy

The following requirements apply to all interactions on GitHub, including discussions, issues, pull requests, code, documentation, and comments. While many of these requirements are designed with generative AI in mind, they also apply to human-authored contributions as well.

### Responsibility

You are ultimately responsible for your contributions. In particular, you must:

- understand every line of code or documentation that you contribute,
- ensure that you have permission (usually from your employer) to contribute, and
- take responsibility for any bugs you introduce.

Accidents happen, and everyone has introduced one or two security vulnerabilities before (right? right!?[^1]). The important thing is not that your code is perfect, but that you take responsibility for its quality and correctness. This includes apologizing for mistakes, fixing bugs, and reporting vulnerabilities.

Before tackling an issue or opening a PR with the assistance of AI, think about whether you could reasonably solve this problem or implement this feature without the use of AI. If not, it is unlikely that you will be able to fully grasp the AI implementation.

[^1]: [TorchGeo Security Vulnerability](https://github.com/torchgeo/torchgeo/security/advisories/GHSA-ghq9-vc6f-8qjf)

### Copyright

Fully autonomous or "agentic" AI contributions are not accepted as AI cannot hold copyright.[^2] You as a contributor are responsible for determining whether or not your contributions contain any code that is copied from a project under a different license. If you are not able to confirm whether or not your code is free from copyright issues, please do not open a PR. Instead, open an issue and ask someone else to contribute for you.

[^2]: [Thaler v. Perlmutter, 2025](https://media.cadc.uscourts.gov/opinions/docs/2025/03/23-5233.pdf)

### Communication

All communication with maintainers, including descriptions and comments on issues and PRs, should be made by humans. When you report an issue, we want to see you describe the issue in your own words to ensure you spent time debugging it. Similarly, when you open a PR, we want to see you summarize your implementation without AI assistance to guarantee you understand your own contribution. We may ask clarifying questions or suggest improvements to your PR. Please refrain from using AI to automatically respond to maintainer questions. It is fine to use AI for proofreading (typos/grammar) or translation, however.

### Conciseness

AI makes it easier than ever to quickly open a PR with minimal effort. However, without careful involvement of a human-in-the-loop, this can result in overly verbose PRs containing defensive coding and unnecessary testing. While this may save you time, human maintainers still have to review every line of code, unfairly shifting the burden and leading to "extractive contributions".[^3] Please keep all issues and PRs short and succinct. Avoid combining large refactors and new features in the same PR. While there are no hard requirements for word or line limits, if your PR could reasonably be split into many smaller PRs, we will likely ask you to do just that.

[^3]: [Eghbal, 2020, Working in Public: The Making and Maintenance of Open Source Software](https://press.stripe.com/working-in-public)

### Disclosure

All PRs must disclose to what extent AI was involved in writing the code using the following template:

- [ ] 🟢 **No AI usage**: written by humans, for humans
  - You wrote all code yourself without AI assistance, great job!
- [ ] 🟡 **AI-assisted**: AI helped with the coding, but I understand every line
  - AI was used to generate the initial boilerplate, but required significant iteration and interaction
  - You understand, manually reviewed, and manually tested every line before opening the PR
- [ ] 🔴 **AI-generated**: AI did everything, review with caution
  - AI generated all code with little to no interaction beyond the initial prompt
  - You cannot explain the logic behind your implementation without asking the AI
  - These PRs will be closed immediately, as AI cannot hold copyright
