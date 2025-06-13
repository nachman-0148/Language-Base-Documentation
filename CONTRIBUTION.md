
# Contributing to Singularity

We're thrilled you're interested in contributing to Singularity, the Language Base! Your contributions help us make Singularity more powerful, user-friendly, and robust.

---

## How to Contribute

There are many ways to contribute, not just by writing code:

* **Reporting Bugs:** If you find a bug, please open an issue on our GitHub repository. Provide a clear and concise description of the bug, steps to reproduce it, and your environment details.
* **Suggesting Enhancements:** Have an idea for a new feature or an improvement to an existing one? We'd love to hear it! Open an issue to discuss your proposal.
* **Writing Documentation:** Clear and comprehensive documentation is crucial. You can help by improving existing docs, adding examples, or writing new guides.
* **Submitting Pull Requests (PRs):** If you've fixed a bug, implemented a new feature, or made an improvement, submit a pull request!

---

## Submitting Pull Requests

If you're planning to contribute code, please follow these guidelines:

1.  **Fork the Repository:** Start by forking the main Singularity repository to your GitHub account.
2.  **Clone Your Fork:** Clone your forked repository to your local machine:
    ```bash
    git clone [https://github.com/your-username/singularity.git](https://github.com/your-username/singularity.git)
    cd singularity
    ```
3.  **Create a New Branch:** Always create a new branch for your changes. This keeps your work organized and makes PRs easier to review.
    ```bash
    git checkout -b feature/your-feature-name-or-bugfix/your-bug-id
    ```
    (e.g., `feature/add-loop-construct` or `bugfix/fix-transpiler-error-123`)
4.  **Make Your Changes:** Implement your bug fix, feature, or enhancement.
5.  **Write Tests:** For code contributions, please write (or update) relevant tests to ensure your changes work as expected and prevent regressions.
6.  **Run Tests:** Before committing, make sure all existing tests pass, and your new tests pass.
7.  **Commit Your Changes:** Write clear, concise commit messages. A good commit message explains *what* you changed and *why*.
    ```bash
    git commit -m "feat: Add support for inline comments"
    git commit -m "fix: Resolve issue where parameters were not parsed correctly"
    ```
    (We generally follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) for commit messages.)
8.  **Push to Your Fork:** Push your new branch to your forked repository on GitHub.
    ```bash
    git push origin feature/your-feature-name
    ```
9.  **Open a Pull Request:** Go to the original Singularity repository on GitHub and open a new pull request from your branch.
    * **Reference Issues:** Link your PR to any relevant issues by including `Closes #XYZ` or `Fixes #XYZ` in your PR description.
    * **Describe Your Changes:** Clearly describe the purpose of your PR, the changes you've made, and any potential impacts.
    * **Screenshots/Examples:** If applicable, include screenshots or usage examples that demonstrate your changes.

---

## Code of Conduct

Please note that this project is released with a [Contributor Code of Conduct](CODE_OF_CONDUCT.md). By participating in this project, you agree to abide by its terms.

---

Thank you for helping us build Singularity!
