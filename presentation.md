# The Wrong Way to Use AI Agents with Git and GitHub

## An Educational Demonstration

* **Topic:** AI agents, Git, GitHub and software development workflows
* **Main message:** Never let an AI agent develop, approve and merge its own code without independent human oversight.

---

## Slide 1 — Introduction

### What happens when an AI agent has too much autonomy?

This demonstration uses Claude Code to:
* Build a simple HTML/CSS webpage.
* Create one commit.
* Push to a GitHub branch.
* Open a Pull Request to `main`.
* Attempt to approve and merge its own Pull Request.

**Objective:** Show what to avoid when integrating AI agents into collaborative development.

---

## Slide 2 — The Workflow We Should Avoid

### One agent, too many responsibilities

The agent:
1. Writes the code.
2. Reviews its own changes.
3. Commits and pushes the code.
4. Opens the Pull Request.
5. Approves and merges it into `main`.

### Why is this dangerous?

The same agent creates and authorises the change. Without independent review, defects, vulnerabilities and poor design decisions may go undetected.

---

## Slide 3 — Git Branches

### The development workflow

```text
             agent
                |
                v
        Develop HTML and CSS
                |
                v
          Create commit
                |
                v
        Push to GitHub
                |
                v
         Create Pull Request
                |
                v
              main
```

Changes move from `agent` to `main` through a Pull Request.

**The issue is not AI-assisted coding. It is allowing one agent to control the entire process without independent checks.**

---

## Slide 4 — The Single-Commit Problem

### Why avoid one commit for every change?

A single commit can make it harder to:
* Understand individual changes.
* Find the source of defects.
* Review implementation steps.
* Revert one logical change.
* Trace development history.

### Best practice

Use small, atomic commits. Each commit should represent one logical change.

---

## Slide 5 — The Pull Request Problem

### A Pull Request is not just a formality

A Pull Request should enable teams to:
* Review code and design decisions.
* Find defects and security issues.
* Run automated tests.
* Confirm project requirements are met.

If the agent writes and approves the code, review is no longer independent.

**Use Pull Requests for quality control, not merely automation.**

---

## Slide 6 — The Approval Problem

### Can an AI agent approve its own Pull Request?

This depends on repository settings, the authenticated account and GitHub review rules. GitHub may block self-approval or require another authorised reviewer.

**Never bypass branch protection or required reviews to make automation succeed.**

A blocked approval demonstrates the value of independent controls.

---

## Slide 7 — What Can Go Wrong?

### Potential risks

* Defective code reaches production.
* Security vulnerabilities go undetected.
* Tests are skipped.
* Poor design enters `main`.
* Git history becomes unclear.
* Excessive permissions enable unintended changes.
* Changes merge without meaningful human review.

These risks increase when one agent can modify, approve and merge code without independent oversight.

---

## Slide 8 — The Recommended Workflow

### Human oversight and automated checks

```text
        AI Agent
            |
            v
     Develop the code
            |
            v
      Create atomic commits
            |
            v
      Push feature branch
            |
            v
      Open Pull Request
            |
            v
    Automated CI/CD checks
            |
            v
 Independent human review
            |
            v
      Approve and merge
            |
            v
           main
```

### Recommended controls

* Protect the `main` branch.
* Require independent reviews.
* Run tests and security checks.
* Apply least-privilege access.
* Separate development, review and approval.
* Maintain an auditable Git history.

---

## Slide 9 — Key Takeaways

1. AI agents can automate much of software development.
2. Automation does not replace independent review.
3. Large, unrelated commits reduce traceability.
4. Pull Requests should provide meaningful quality control.
5. Branch protection and permissions are essential safeguards.
6. Human oversight should match the risk of the change.

**The goal is controlled autonomy, not unrestricted automation.**

---

## Slide 10 — Discussion

### Questions for the audience

* Should an AI agent merge its own code into `main`?
* What permissions should it have?
* Which checks should be mandatory?
* When does useful automation become excessive autonomy?
* What if the agent introduces a critical vulnerability?

### Final message

**Let AI agents accelerate development, but do not confuse automation with accountability.**

The strongest workflow combines AI productivity, independent verification and controlled access.

---

## References

* [Git documentation](https://git-scm.com/doc)
* [GitHub Pull Request reviews](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests)
* [GitHub protected branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches)
* [GitHub Actions documentation](https://docs.github.com/en/actions)
* [Claude Code documentation](https://code.claude.com/docs/en/overview)
