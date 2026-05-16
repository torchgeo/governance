# AI Policy

The TorchGeo Organization maintains a number of popular AI libraries. Our users and developers are all AI enthusiasts, thus it should come as no surprise that many contributors would also like to use large language models (LLMs) to contribute to TorchGeo. However, to ensure the quality and maintainability of our software and avoid maintainer burnout, we have to set some boundaries.

Note that this is a rapidly evolving landscape, and we may make frequent updates to this policy in order to keep up with new developments in generative AI.

## Motivation

LLMs are an exciting new technology that introduces many possibilities, but also a number of serious concerns:

### Ethical Concerns

LLMs are trained on massive amounts of copyrighted material without the consent of copyright holders.[^1] This includes open source software such as the libraries we maintain. While this has been extremely lucrative for a small number of large companies, these financial incentives have not transferred to open source maintainers. Instead, many programmers have lost their jobs, with an estimated 85 million jobs already displaced by AI and 41% of employers planning to further reduce their workforce due to AI automation in the next five years.[^2]

[^1]: [Gervais et al., 2024, The Heart of the Matter: Copyright, AI Training, and LLMs](https://dx.doi.org/10.2139/ssrn.4963711)
[^2]: [Nartey, 2025, AI Job Displacement Analysis (2025-2030)](https://dx.doi.org/10.2139/ssrn.5316265)

### Legal Concerns

LLMs have been shown to be capable of reproducing entire copyrighted works.[^3][^4] When using LLMs, it can be difficult if not impossible to know whether the code they produce contains copyrighted material from the training dataset. Unfortunately, if you use LLMs and unintentionally introduce copyright violations into our software, you are not the person who will be sued, we are. While the courts are still undecided on whether the use of LLMs constitutes copyright infringement, US courts have ruled that AI cannot hold copyright.[^5] Since all contributions to our software must be contributed under an open source license, you must hold copyright over the code you would like to contribute. This prevents fully autonomous or "agentic" AI from contributing to our libraries.

[^3]: [Mueller et al., 2024, LLMs and Memorization: On Quality and Specificity of Copyright Compliance](https://doi.org/10.1609/aies.v7i1.31697)
[^4]: [Ahmed et al., 2026, Extracting books from production language models](https://doi.org/10.48550/arXiv.2601.02671)
[^5]: [Thaler v. Perlmutter, 2025](https://media.cadc.uscourts.gov/opinions/docs/2025/03/23-5233.pdf)

### Environmental Concerns

LLM training and deployment require a substantial amount of energy and water, with data centers contributing to urban heat islands and climate change.[^6] Studies have shown that models like GPT-4 emit 5–19 times more CO<sub>2</sub> than human programmers to generate code of similar quality.[^7] As a software ecosystem centered around environmental and climate research, we also strive to minimize our carbon footprint in software development.

[^6]: [Singh et al., 2025, A Survey of Sustainability in Large Language Models: Applications, Economics, and Challenges](https://doi.org/10.1109/CCWC62904.2025.10903774)
[^7]: [Woo, 2025, A comparative study of AI and human programming on environmental sustainability](https://doi.org/10.1038/s41598-025-24658-5)

### Logistical Concerns

We have seen a significant increase in PRs lately thanks to LLMs. However, this has also resulted in our maintainers being stretched thin. [AI slop](https://en.wikipedia.org/wiki/AI_slop) and unnecessarily verbose code has resulted in PRs that are double the typical length.[^8] While it is easier than ever to generate large PRs, it takes humans exponentially longer to review these PRs. This has led to _extractive_ contributions that take more out of the project than they add:[^9]

> When attention is being appropriated, producers need to weigh the costs and benefits of the transaction. To assess whether the appropriation of attention is net-positive, it's useful to distinguish between _extractive_ and _non-extractive_ contributions. Extractive contributions are those where the marginal cost of reviewing and merging that contribution is greater than the marginal benefit to the project's producers. In the case of a code contribution, it might be a pull request that's too complex or unwieldy to review, given the potential upside.

[^8]: [Baltes et al., 2026, "An Endless Stream of AI Slop": The Growing Burden of AI-Assisted Software Development](https://doi.org/10.48550/arXiv.2603.27249)
[^9]: [Eghbal, 2020, Working in Public: The Making and Maintenance of Open Source Software](https://press.stripe.com/working-in-public)

### Educational Concerns

Open source software is sustained by its contributors, and teaching new contributors to become future maintainers can be even more important than the code being contributed. Research by Anthropic has found that "AI use impairs conceptual understanding, code reading, and debugging abilities, without delivering significant efficiency gains on average."[^10] However, certain uses of AI are more detrimental than others. While the use of AI to explain existing code can help, the use of AI to automate tasks like code writing results in poorer understanding of the code and review process.

[^10]: [Shen and Tamkin, 2026, How AI Impacts Skill Formation](https://doi.org/10.48550/arXiv.2601.20245)

## Policy

The following requirements apply to all use of generative AI for contributing to code and documentation via both pull requests and issues.

### Responsibility

Regardless of whether they were written by you or by AI, you are ultimately responsible for your contributions. In particular, you must:

- understand every line of code or documentation that you contribute,
- ensure that you have permission (usually from your employer) to contribute to one of our projects, and
- take responsibility for any bugs you introduce.

Accidents happen, and everyone has introduced one or two security vulnerabilities before ([right? right!?](https://github.com/torchgeo/torchgeo/security/advisories/GHSA-ghq9-vc6f-8qjf)). The important thing is not that your code is perfect, but that you take responsibility for its quality and correctness. This includes apologizing for mistakes, fixing bugs, and reporting vulnerabilities.

Before tackling an issue or opening a PR with the assistance of AI, think about whether you could reasonably solve this problem or implement this feature without the use of AI. If not, it is unlikely that you will be able to fully understand the AI implementation.

### Copyright

Fully autonomous or "agentic" AI contributions are not accepted as AI cannot hold copyright. You as a contributor are responsible for determining whether or not your contributions contain any code that is copied from a project under a different license. If you are not able to confirm whether or not your code is free from copyright issues, please do not open a PR. Instead, open an issue and ask someone else to contribute for you.

### Communication

When you report an issue, we hope that you can describe the issue in your own words. Similarly, when you open a PR, we hope that you can summarize your implementation without AI assistance to guarantee you understand your own contribution. We may ask clarifying questions or suggest improvements to your PR. Please refrain from using AI to automatically respond to maintainer questions. It is fine to use AI for proofreading (typos/grammar) or translation, however.

### Conciseness

Please keep all issues and PRs short and succinct. Avoid combining large refactors and new features in the same PR. While there are no hard requirements for word or line limits, if your PR could reasonably be split into many smaller PRs, we will likely ask you to do just that.

### Disclosure

All PRs must disclose to what extent AI was involved in writing the code using the following template:

- [ ] 🟢 **No AI usage**: written by humans, for humans
  - You wrote all code yourself without AI assistance, great job!
  - These PRs require at least one maintainer to approve before they can be merged
- [ ] 🟡 **AI-assisted**: AI helped with the coding, but I understand every line
  - AI was used to generate the initial boilerplate, but required significant iteration and interaction
  - You understand, manually reviewed, and manually tested every line before opening the PR
  - These PRs require at least two maintainers to approve before they can be merged
- [ ] 🔴 **AI-generated**: AI did everything (will be closed immediately)
  - AI generated all code with little to no interaction beyond the initial prompt
  - You cannot explain the logic behind your implementation without asking the AI
  - These PRs will be closed immediately, as AI cannot hold copyright

### First-Time Contributors

AI-assisted code is not permitted for first-time contributors. Instead, your first PR must be written by hand to ensure you understand the style and design of the library. We routinely mark issues that are well documented and rather straightforward to contribute as "good first issue". These are designed to onboard new contributors and teach them how to contribute to our software. AI-assisted solutions to these issues would defeat the purpose and are thus forbidden.

## Enforcement

The above policy will be enforced more strictly depending on how many times a contributor violates the policy, not based on the severity of the violation. In all cases, a maintainer will point out exactly which part of the AI policy has been violated so that contributors can learn from their mistakes.

1. First-time offense: ask the contributor to make corrections.
2. Second-time offense: immediately close the issue/PR.
3. Third-time offense: a temporary ban on all contributions.
4. Fourth-time offense: a permanent ban on all contributions.

These penalties do not apply to contributions made before this policy was adopted, and do not stack for multiple contributions made at the same time.

## References

This AI policy was not developed in a vacuum. While some of the above policies may seem strict, they are quite common among our dependencies:

- [Python](https://devguide.python.org/getting-started/generative-ai/): responsibility, conciseness, copyright
- [pip](https://github.com/pypa/pip/blob/main/AI_POLICY.md): responsibility, copyright, communication, conciseness
- [uv/ruff/ty](https://github.com/astral-sh/.github/blob/main/AI_POLICY.md): responsibility, communication, copyright
- [Conda](https://docs.conda.io/projects/conda/en/latest/dev-guide/contributing.html#generative-ai): responsibility, copyright, communication, conciseness
- [NumPy](https://numpy.org/devdocs/dev/ai_policy.html)/[SciPy](https://scipy.github.io/devdocs/dev/conduct/ai_policy.html)/[SymPy](https://docs.sympy.org/dev/contributing/ai-generated-code-policy.html): responsibility, disclosure, copyright, communication, first-time contributors
- [Matplotlib](https://matplotlib.org/devdocs/devel/contribute.html#generative-ai): responsibility, communication, copyright
- [pandas](https://pandas.pydata.org/docs/dev/development/contributing.html#automated-contributions-policy): disclosure, responsibility, verbosity
- [scikit-learn](https://scikit-learn.org/dev/developers/contributing.html#automated-contributions-policy): communication, responsibility, disclosure
- [scikit-image](https://scikit-image.org/docs/dev/development/contribute.html#ai-policy): responsibility, copyright, conciseness, disclosure
- [PyTorch](https://github.com/pytorch/pytorch/blob/main/CONTRIBUTING.md#ai-assisted-development): responsibility, conciseness, first-time contributors, communication
- [Kornia](https://github.com/kornia/kornia/blob/main/AI_POLICY.md): responsibility, conciseness, communication, disclosure
- [GDAL](https://gdal.org/en/stable/community/ai_tool_policy.html)/[QGIS](https://github.com/qgis/QGIS-Enhancement-Proposals/blob/master/qep-408-ai-tool-policy.md)/[STAC](https://github.com/stac-utils/stac-utils.github.io/blob/main/docs/ai-contribution-policy.md): responsibility, communication, disclosure, copyright, conciseness

In particular, our AI policy is most heavily influenced by NumPy and GDAL, with the disclosure template design coming from Kornia!
