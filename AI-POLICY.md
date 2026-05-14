# AI Policy

The TorchGeo Organization maintains a number of popular AI libraries. Our users and developers are all AI enthusiasts, thus it should come as no surprise that many contributors would also like to use large language models (LLMs) to contribute to TorchGeo. However, to ensure the quality and maintainability of our software and avoid maintainer burnout, we have to set some boundaries. The following requirements apply to all use of generative AI for contributing to code and documentation via both pull requests and issues:

- [**Responsibility**](#responsibility): You are responsible for your contributions and must understand every line of code you contribute
- [**Copyright**](#copyright): You must hold copyright to your contributions, must verify no copyright infringement
- [**Communication**](#communication): Issue/PR descriptions, replies, and comments must be written by humans, not AI
- [**Conciseness**](#conciseness): Good issues/PRs are concise, multiple contributions should be split into multiple PRs
- [**Disclosure**](#disclosure): You must disclose if and how AI was used, fully autonomous/agentic PRs are rejected
- [**First-Time Contributors**](#first-time-contributors): AI-assisted coding is reserved for existing contributors, cannot use AI for "good first issue"
- [**Guiding Philosophy**](#guiding-philosophy): Ensure that your contributors are faster to review than to rewrite
- [**References**](#references): References to AI policies of our dependencies

Below we provide details and the rationale behind each requirement. Note that this is a rapidly evolving landscape, and we may make frequent updates to this policy in order to keep up with new developments in generative AI.

## Responsibility

Contributors have the opportunity to help us build better software. However, with great power comes great responsibility. Regardless of whether they were written by you or by AI, you are ultimately responsible for your contributions. In particular, you must:

- understand every line of code or documentation that you contribute,
- ensure that you have permission (usually from your employer) to contribute to one of our projects, and
- take responsibility for any bugs you introduce.

Accidents happen, and everyone has introduced one or two security vulnerabilities before ([right? right!?](https://github.com/torchgeo/torchgeo/security/advisories/GHSA-ghq9-vc6f-8qjf)). The important thing is not that your code is perfect, but that you take responsibility for its quality and correctness. This includes apologizing for mistakes, fixing bugs, and reporting vulnerabilities. These are all easy for humans but hard for AI.

## Copyright

AI has raised a number of interesting ethical and legal questions about copyright. While the courts are still out on a number of important considerations, the following are likely to remain true regardless of what the courts decide.

Only humans can hold copyright. This prevents fully autonomous or "agentic" AI contributions, as all code must be contributed under the same copyright. See [Thaler v. Perlmutter](https://media.cadc.uscourts.gov/opinions/docs/2025/03/23-5233.pdf) for more information.

AI is quite good at copying. You as a contributor are responsible for determining whether or not your contributions contain any code that is copied from a project under a different license. If you are not able to confirm whether or not your code is free from copyright issues, please do not open a PR. Instead, open an issue and ask someone else to contribute for you.

## Communication

When you report an issue, we hope that you can describe the issue in your own words. Similarly, when you open a PR, we hope that you can summarize your implementation without AI assistance to guarantee you understand your own contribution. We may ask clarifying questions or suggest improvements to your PR. Please refrain from using AI to automatically respond to maintainer questions. It is fine to use AI for proofreading (typos/grammar) or translation, however.

## Conciseness

One of the biggest reasons for maintainer burnout is the sheer verbosity of most AI contributions. All of a sudden, it is easier than ever to generate a massive feature request that requires scrolling even on desktop or a thousand line PR to implement a complex feature. This has led to not only more PRs, but longer PRs that take exponentially more time and energy to carefully review. Please keep all issues and PRs short and succinct. Avoid combining large refactors and new features in the same PR. While there are no hard requirements for word or line limits, if your PR could reasonably be split into many smaller PRs, we will likely ask you to do just that.

## Disclosure

No one likes guessing whether they are reading something that was written by a human or by AI. To make this easier, we have a handy template you can use to disclose to what extent AI contributed to your PR:

- [ ] 🟢 **No AI usage**: written by humans, for humans
  - For the hard-core programmers who still use vim and emacs
  - "I don't know how to use LLMs and at this point I'm too afraid to ask"
- [ ] 🟡 **AI-assisted**: AI helped with the coding, but I understand every line
  - AI was used to generate the initial boilerplate, but required significant iteration and interaction
  - You understand, manually reviewed, and manually tested every line before opening the PR
- [ ] 🔴 **AI-generated**: AI did everything (may be closed immediately)
  - AI generated all code with little to no interaction beyond the initial prompt
  - You cannot explain the logic behind your implementation without asking the AI

Human-authored code requires significantly more time and effort, resulting in fewer hallucinations that look right but do not actually work. Small human-authored PRs generally only require a single approval before being merge. AI-assisted code can be prone to hallucinations, and often repeats common mistakes from the data it was trained on. AI-assisted PRs require at least two maintainers to approve them before being merged. AI-generated code is not accepted at this time, see [Copyright](#copyright) for more details.

## First-Time Contributors

One of the most rewarding aspects of open source is community building. We routinely train new contributors who may someday be maintainers of the library. However, new contributors are often unfamiliar with the codebase and require time to learn the style of existing code. As such, AI-assisted code is not permitted for new contributors.

Similarly, we routinely mark issues that are well documented and rather straightforward to contribute as "good first issue". These are designed to onboard new contributors and teach them how to contribute to our software. AI-assisted solutions to these issues would defeat the purpose and are thus forbidden.

## Guiding Philosophy

When in doubt, consider the following: is it faster for others to review your PR, or to implement the same feature themselves? Maintainer time is precious, and in order for us to keep up with new PRs, we ask that all PRs are short and easy to review. If you think a maintainer could implement the same thing in the time it takes to review your PR, consider opening an issue instead. The following quote by Nadia Eghbal sums it up best:

> When attention is being appropriated, producers need to weigh the costs and benefits of the transaction. To assess whether the appropriation of attention is net-positive, it's useful to distinguish between _extractive_ and _non-extractive_ contributions. Extractive contributions are those where the marginal cost of reviewing and merging that contribution is greater than the marginal benefit to the project's producers. In the case of a code contribution, it might be a pull request that's too complex or unwieldy to review, given the potential upside.
> — [Working in Public: The Making and Maintenance of Open Source Software](https://press.stripe.com/working-in-public)

Before tackling an issue or opening a PR with the assistance of AI, think about whether you could reasonably solve this problem or implement this feature without the use of AI. If not, it is unlikely that you will fully understand the AI implementation, or at least understanding every line of code it generates.

## References

This AI policy was not developed in a vacuum. While some of the above policy decisions may seem strict, they are quite common among our dependencies:

- [Python](https://devguide.python.org/getting-started/generative-ai/): responsibility, conciseness, copyright
- [pip](https://github.com/pypa/pip/blob/main/AI_POLICY.md): responsibility, copyright, communication, conciseness, guiding philosophy
- [uv/ruff/ty](https://github.com/astral-sh/.github/blob/main/AI_POLICY.md): responsibility, communication, copyright
- [Conda](https://docs.conda.io/projects/conda/en/latest/dev-guide/contributing.html#generative-ai): responsibility, copyright, communication, conciseness
- [NumPy](https://numpy.org/devdocs/dev/ai_policy.html)/[SciPy](https://scipy.github.io/devdocs/dev/conduct/ai_policy.html)/[SymPy](https://docs.sympy.org/dev/contributing/ai-generated-code-policy.html): responsibility, disclosure, copyright, communication, new contributors
- [Matplotlib](https://matplotlib.org/devdocs/devel/contribute.html#generative-ai): responsibility, communication, copyright, guiding philosophy
- [pandas](https://pandas.pydata.org/docs/dev/development/contributing.html#automated-contributions-policy): disclosure, responsibility, verbosity
- [scikit-learn](https://scikit-learn.org/dev/developers/contributing.html#automated-contributions-policy): communication, responsibility, disclosure
- [scikit-image](https://scikit-image.org/docs/dev/development/contribute.html#ai-policy): responsibility, copyright, conciseness, disclosure
- [PyTorch](https://github.com/pytorch/pytorch/blob/main/CONTRIBUTING.md#ai-assisted-development): responsibility, conciseness, new contributors, communication
- [Kornia](https://github.com/kornia/kornia/blob/main/AI_POLICY.md): responsibility, conciseness, communication, disclosure
- [GDAL](https://gdal.org/en/stable/community/ai_tool_policy.html)/[QGIS](https://github.com/qgis/QGIS-Enhancement-Proposals/blob/master/qep-408-ai-tool-policy.md)/[STAC](https://github.com/stac-utils/stac-utils.github.io/blob/main/docs/ai-contribution-policy.md): responsibility, communication, disclosure, copyright, conciseness, guiding philosophy

In particular, our AI policy is most heavily influenced by NumPy and GDAL, with the disclosure template design coming from Kornia!
