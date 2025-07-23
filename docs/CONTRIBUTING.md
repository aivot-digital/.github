# How to contribute 🤝

## Good to know 🤔

  - To get a sense of where the project is heading, or for ideas on where you
    could contribute, take a look at the [roadmap](https://aivot.de/roadmaps) of
    the respective project.
  - We only accept Pull Requests for existing issues. Existing issues have been
    properly discussed and, if not closed, deemed valuable for the project.
  - By contributing your code to a projects GitHub repository, you agree to
    license your contribution in accordance with our
    [Contributor License Agreement](../templates/CONTRIBUTOR_LICENSE_AGREEMENT.md).
    This is necessary in order for us to avoid having licensing problems later
    on. We used the most simple one that exists. It is from
    [Indie Open Source](https://indieopensource.com/forms/cla) which uses plain
    English and is literally only a few lines long.

### Resources 📚

This project contains several resources to help you understand the software
architecture, coding style as well as the development and contribution workflows
(or how we call it: _development view_). Please refer to these documents if you
have any questions regarding these topics and therefore development.

| Resource                                | Description                                                                                                                        |
|-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| [CODE_OF_CONDUCT](./CODE_OF_CONDUCT.md) | Code of conduct for collaboration in this project and when collaborating in general with Aivot and its community                   |
| [CONTRIBUTING](./CONTRIBUTING.md)       | How to contribute to a project (this document 🤯)                                                                                  |
| [SECURITY](./SECURITY.md)               | Patch cycles and how to report vulnerabilities                                                                                     |
| _STYLEGUIDE_                            | Coding styles and the truth about tabs vs. spaces                                                                                  |
| _README_                                | Prerequisites, setup and configuration of the project                                                                              |
| [Docs](https://aivot.de/docs)           | Select the docs for the respective project and have a look at software architecture, APIs and anything else needed for development |

Note: If you have questions regarding the _user view_ (e.g. how to use feature
XY), please refer to our user documentation for the respective project by
choosing the project on our [documentation overview](https://aivot.de/docs).

## General Workflow 🔁

We follow a workflow so that everything always remains under control and optimal
results are achieved. For this, we rely heavily on
[Clickup](https://clickup.com).

| Step | Description                                                                                                                                                                                | Responsibility     | Remarks                                                                                                                                       |
|------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| 1    | A new issue on GitHub is created.                                                                                                                                                          | Contributor        | Contributors must open a GitHub issue first. Aivot works exclusively in ClickUp — every GitHub issue is mirrored there for internal tracking. |
| 2    | A new task on Clickup is created.                                                                                                                                                          | Aivot              |                                                                                                                                               |
| 3    | A new branch is created. All changes are going to be committed to this branch.                                                                                                             | Contributor, Aivot | See [branching](./CONTRIBUTING.md#branching-) for more information about our branching                                                        |
| 4    | A New Pull Request is created. The Pull Request references the solved issue.                                                                                                               | Contributor, Aivot | Use the Pull Request template provided by the repository                                                                                      |
| 5    | Aivot is monitoring for Pull Requests. The newly created Pull Request is reviewed by Aivot. We will either merge the Pull Request, request changes to it, or close it with an explanation. | Aivot              | -                                                                                                                                             |
| 6    | In case the Pull Request is accepted by Aivot: The branch is merged by us.                                                                                                                 | Aivot              | -                                                                                                                                             |

### Company facing vs. community facing

The two systems in use, GitHub Issues and Clickup, each have a very specific
purpose.  
We use GitHub Issues for the community facing part of the workflow and Clickup
for the company facing part of the workflow.

#### Community facing

"Community facing" means making tasks available to the community via
GitHub Issues.  
GitHub Issues includes tasks that are submitted, discussed and implemented by
the community. This makes GitHub Issues the perfect place for people to submit
their ideas.

#### Company facing

"Company facing" means that tasks are handled by us and managed with Clickup
for this purpose. This can include tasks such as a complete feature development
or the task of a code review of a Pull Request from a contributor.
In other words: All tasks that are implemented by us from the beginning, or
that are contributed to by us in the course of their existence, end up in
Clickup (sooner or later this is every task 😅). This allows us a coordinated
internal approach. Clickup is therefore the ideal place for people who want to
see a [roadmap](https://aivot.de/roadmaps) for the project.

#### Behind the scenes of this approach

**Community facing:**  
As a contributor, you create a GitHub issue. From here on there are two ways:

1. If the issue is put up for discussion and therefore not directly assigned to
  you for implementation, we copy the issue as a task to Clickup in the status
  _in technical coordination_. This way we don't lose track of where discussions
  are going on. If we take care of the implementation, the task will be dragged
  through our Clickup board. It will be "company facing" from the moment the
  decision is made that we will develop for this issue.
2. If you as a contributor assign the issue to yourself and work on it, nothing
  happens on our side. Only when you create a Pull Request we get to know about
  it and the issue becomes "company facing". We then create a task in Clickup
  with the status _in review_ in order to be able to give you as a contributor
  feedback as quickly as possible. If the code review is successful, we merge
  your Pull Request and your contribution is included in the project.

**Company facing:**  
When an implementation idea comes from us, we create a task in ClickUp. We
don’t always open a matching GitHub issue. If a GitHub issue does exist, we
assign it to ourselves.
We usually implement these ideas internally. Our internal development also
follows the [contributing guideline](./CONTRIBUTING.md)
(branching, Pull Requests etc.) and is being tracked within Clickup.

## Environment 🌍

Please refer to the _README_ for detailed instructions on setting up this
project as well as developing for it.

## Branching and Workflow 🌳

This section describes our branching model and the step-by-step workflow for
contributing code.

### Branching Model

Our branching strategy is inspired by
[GitFlow](https://nvie.com/posts/a-successful-git-branching-model/) but
streamlined for our workflow.  
Instead of a persistent `development` branch, we use long-lived branches for
upcoming releases (`milestone/*`) and patches (`patch/*`).  
All development happens on temporary `feature/*` and `fix/*` branches.

There are five types of branches:

  - `main`: This branch contains the latest released production code. It is
    protected, and no direct commits are allowed. Changes are only merged from
    `milestone` or `patch` branches.
  - `milestone/X.Y.Z`: Used to aggregate new features for the next major or
    minor release (e.g., `milestone/5.4.0`). It is created from `main`.
  - `patch/X.Y.Z`: Used to aggregate bug fixes for an upcoming patch release
    (e.g., `patch/5.3.1`). It is created from `main`.
  - `feature/<LABEL>[-CU-<TICKET ID>]`: A temporary branch for developing a
    single new feature. It should branch off the current `milestone/*` branch.
  - `fix/<LABEL>[-CU-<TICKET ID>]`: A temporary branch for a single bug fix. It
    should branch off the current `patch/*` branch.

### Contributor Workflow

**1. Contributing a New Feature:**

1. Identify the current `milestone/X.Y.Z` branch for the upcoming release.
2. Create your feature branch from it. The name should follow the pattern
  `feature/<descriptive-label>`. If a corresponding ClickUp ticket exists,
  append it like this: `feature/<descriptive-label>-CU-<ticket-id>`.
3. Do your work on the feature branch. Keep your branch up-to-date by
  periodically merging the latest changes from the `milestone` branch into
  yours.
4. When your feature is complete, open a Pull Request to merge your
  `feature` branch back into the `milestone` branch.

**2. Contributing a Bug Fix:**

1. Identify the current `patch/X.Y.Z` branch for the upcoming patch.
2. Create your fix branch from it. The name should follow the pattern
  `fix/<descriptive-label>`. If a corresponding ClickUp ticket exists, append it
  like this: `fix/<descriptive-label>-CU-<ticket-id>`.
3. Implement the fix on your branch.
4. When the fix is ready, open a Pull Request to merge your `fix` branch back
  into the `patch` branch.

### The Pull Request Process

Once your work is complete and you have opened a Pull Request, the following
process begins:

1. **Prerequisites Check**: Your Pull Request must meet all specified
  requirements. All automated checks (e.g., tests, builds) must pass
  successfully.
2. **Code Review**: The Aivot team will conduct a code review of your
  submission.
3. **Merge**: If the code review is successful and all checks have passed, the
  Aivot team will merge your changes into the target branch.

Please ensure your commit messages follow our formatting guidelines, as this
helps streamline the review process.

## Commit Message Format 💬

This section provides the detailed rules for formatting your commit messages.
We have very precise rules to ensure messages are readable and easy to follow
when looking through the project history.

### General Formatting Rules

  - Separate subject from body with a blank line
  - Capitalize the subject line
  - Do not end the subject line with a period
  - Use the imperative mood in the subject line (e.g. "Add Google SSO")
  - Wrap the body at 80 characters
  - Use the body to explain what and why vs. how (e.g. Add XY because Z vs.
    Added X and did Y)
  - Use the imperative mood in the body

### Commit Message Structure

Each commit message consists of a **header**, a **body**, and a **footer**.
The general structure is as follows:

```text
[TYPE]([SCOPE]): [SUBJECT]
BLANK LINE
[BODY]
BLANK LINE
[FOOTER]
```

A short explanation on the different building blocks of a commit message:

| Building block | Mandatory? | Explanation                                                                                                                                         |
|----------------|------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| **Type**       | yes        | Signals that the change belongs to a defined category. See [Type](./CONTRIBUTING.md#Type) for types used by us.                                     |
| **Scope**      | no         | The name of the core component affected by the change as perceived by the user. See _Scope_ in wiki.                                                |
| **Subject**    | yes        | A succinct description of the change in imperative mood of what is going to be changed by the commit if merged.                                     |
| **Body**       | no         | Explanation of what has been done and why it has been done in imperative mood.                                                                      |
| **Footer**     | no         | Should contain any information about Breaking Changes. If relevant contains a closing reference to a GitHub issue as well as a Clickup task if any. |

Example of a commit message:

```text
feat(auth): Add Google SSO as login option

Add the possibility for users to sign in using Google since many
requested this.

Closes GH-1234
Closes CU-1234

BREAKING CHANGE:
Change auth-endpoint from /auth to /app/auth
```

#### Type

| Type    | Description                                                                                      |
|---------|--------------------------------------------------------------------------------------------------|
| `build` | Changes that affect the build system or external dependencies.                                   |
| `ci`    | Changes to our CI configuration files and scripts.                                               |
| `docs`  | Documentation only changes.                                                                      |
| `feat`  | A new feature.                                                                                   |
| `fix`   | A bug fix.                                                                                       |
| `ref`   | A code change that neither fixes a bug nor adds a feature (refactor).                            |
| `test`  | Adding missing tests or correcting existing tests.                                               |
| `meta`  | Some meta information in the repo changes (example scopes: owner files, editor config, funding). |

#### Revert

If the commit reverts a previous commit, it should begin with `revert:`,
followed by the header of the reverted commit.  
In the body it should say: `This reverts commit [HASH].`, where the [HASH] is
the SHA of the commit being reverted.

## Code Review 🧐

Code review is mandatory at Aivot. This adds overhead to each change, but
ensures that simple, often overlooked problems are more easily avoided.
Code review helps build shared context and collective ownership. It is also an
opportunity to collaborate with others. Finally, code review can identify
several classes of problems before customers are exposed to them.

Code review is managed via GitHub’s Pull Requests. Pull Request templates exist.

### Guidelines for Submitters

#### Try to organize your work in a way that makes it conducive to review

Ideally, a Pull Request is limited to only a single feature or behaviour
change.  
This might feel like more work up-front, but it can make code review faster,
reduce risk by letting you ship in stages, and ultimately end up being quicker.

#### Describe what your PR does in a few sentences in the description field

Explain **why** you’re making these changes. Reference any GitHub Issues or
Clickup tasks that are being addressed.  
If applicable, explain why other approaches were explored but not settled on.  
This gives the reviewer context, and prevents them going down the same rabbit
holes that the submitter may have already explored when creating the code.

#### Annotate specific lines in your PR

If you can, give context to specific lines of code that could use elaboration.

#### Use Draft Pull Requests for Work in Progress

If your Pull Request is not yet ready for a formal review, you must create it
as a Draft Pull Request on GitHub. This is the primary way to set expectations
and signal that your work is still in progress.  
Draft PRs cannot be merged, which prevents accidental merges, but they still
allow all CI checks to run. This is a great opportunity to get early feedback
or to ensure you're on the right path before involving a formal reviewer.

Optionally, you can also add a WIP (Work in Progress) label for extra
visibility, but using GitHub's Draft feature is the required standard.  
Once your work is complete and you are ready for a final review, you can mark
your PR as "Ready for review".

#### Be your own first reviewer

After you’ve put up your Pull Request on GitHub, walk through the code yourself,
before assigning an external reviewer.  
You’ll often catch code mistakes you didn’t see when writing it.  
This is also a good time to leave comments and refresh your memory in order to
write a more helpful description.

#### Assign no more than 1-3 reviewers

It’s tempting to want to involve as many people as possible, but it can often
be distracting, and create a situation where nobody’s clear on who should
actually perform the review.  
Always @mention an appropriate team (or teams) for review instead of individuals
if there is one.  
If your work spans multiple teams (and thus, many reviewers), consider breaking
up your Pull Requests into multiple compatible patches (e.g. a backend change
and a frontend change).

#### Let reviewers know that you’ve made changes

Request review again via the "Reviewers" dropdown (There should be a yellow dot
next to their name again).  
Don’t rely on reviewers mind-reading skills to know that you’re ready to have
them look things over again.  
If you resolve a point of actionable feedback, it's helpful to leave a comment
to let the reviewer know that it was addressed, ideally with a reference to the
commit that addressed it.

### Who reviews code

All engineers should be reviewing code. As you gain more experience and context
on the products we build and technologies we use, you can provide valuable
feedback to other engineers who may be working in areas that are new to them but
familiar to you.

Code review is an opportunity to improve your mentoring and communication
skills. Code review can have the important function of teaching engineers about
the languages, frameworks and technologies we use in a collaborative environment
that is about the changes being made.

Note: This is only relevant for us at Aivot since we are the ones reviewing code
(see [General Workflow](./CONTRIBUTING.md#general-workflow-)).

### Why Pull Requests

Our open source projects are maintained via GitHub and we want to ensure that
the barrier to entry for external contributions is minimal. By using GitHub
features when possible, we make it easy for developers familiar with other
projects on GitHub.

#### GitHub Teams

We currently have no teams defined in GitHub.

### Code Reviews are for

#### 1. Identifying problematic code

Above all, a code review should try to identify potential bugs that could cause
the application to break – either now, or in the future.

  - Uncaught runtime exceptions (e.g. potential for an index to be out of
    bounds)
  - Obvious performance bottlenecks (e.g. O(n^2) where n is unbounded)
  - Code alters behavior elsewhere in an unanticipated way
  - API changes are not backwards compatible (e.g. renaming or removing a key)
  - Complex ORM interactions that may have unexpected query
    generation/performance
  - Security vulnerabilities
  - Missing or incorrect Permissions or Access Control

#### 2. Improving Design

Reviewers should consider if the interactions of the various pieces in the
change make sense together. Do the changes conflict with other requirements or
goals of the project? Could any of the methods being added be promoted to module
level methods? Are methods being passed properties of objects when they could be
passed the entire object?

#### 3. Reducing code complexity

Research shows that Lines of Code are correlated with a higher bug count. If
reviewers see an easy opportunity to significantly reduce the amount of code
that is submitted, they should suggest a different approach.

For example, if a submitter has written a `for` loop to find an item in an
array:

```javascript
for (let i = 0; i < arr.length; i++) {
  if (arr[i] === 'thingiwant') return i;
}
return undefined;
```

It’s fair game to suggest they instead use:

```javascript
return arr.find(x => x === 'thingiwant');
```

This is a mostly objective improvement: there are fewer variables, fewer
statements, and fewer branches, and the method name `find` communicates intent.
Suggesting these types of uncontroversial improvements is encouraged.

Reviewers have to be careful though – it’s easy to go down a rabbit hole of
re-writing code to be as small as possible, and in the end winding up with
something ultimately more complicated. Reviewers have to be pragmatic and strive
to reach a good balance.  
See also: [Code reviews are not for getting it perfect](./CONTRIBUTING.md#3-getting-it-perfect) below.

#### 4. Enforcing coding standards

As much as possible, we use automation to enforce code style and test coverage.
But there are exceptions that cannot necessarily be automated (or perhaps more
accurately, we haven’t automated yet):

  - Variable and file names are sensible, readable, and consistent with existing
    code
  - Migrations have a deployment plan
  - Unused or superfluous code isn’t committed accidentally

#### 5. Making sure requirement covering tests are in existence

Reviewers make sure there are functional tests, integration tests or end-to-end
tests covering the changes. If not they ask for them. We rely on our test suite
to maintain a high quality bar and ship rapidly.

When reviewing tests reviewers double check that the tests cover the
requirements of the project or that the tests cover the defect being fixed.
Tests should avoid branching and looping as much as possible to prevent bugs in
the test code from gaining a foothold.

Functional tests that simulate how a user would call our APIs or use our UX are
key to preventing regressions and avoiding brittle tests that are coupled to the
internals of the products we ship.

Tests are also the ideal place to ensure that the changes have considered
permissions and access control logic.

#### 6. Double-checking expected behaviour

The reviewer should make a genuine attempt to double-check that the goals of the
Pull Request appear to be satisfied by the code submitted. This requires the
submitter to write a good description of the expected behavior, and why.  
See also: [Guidelines for Submitters](./CONTRIBUTING.md#Guidelines-for-Submitters) above.

#### 7. Assessing and approving long-term impact

If you’re making significant architectural, schema, or build changes that will
have long-term ramifications to the software or data, it is necessary to solicit
a senior engineer’s acknowledgment and blessing.

  - Large refactors
  - Database schema changes, like adding or removing columns and tables
  - API changes (including JSON schema changes)
  - Adopting new frameworks, libraries, or tools
  - New product behaviour that may permanently alter performance characteristics
    moving forward

#### 8. Information sharing and professional development

Code reviews are an opportunity for more people to understand forthcoming code
changes, so that they might in turn teach others down the road, and be in a
position to fix something if/when the original author is not available.

Additionally, code reviews are an opportunity to learn about new techniques or
approaches, and be exposed to code you might otherwise not have an opportunity
to browse.

### Code Reviews are not for

#### 1. Passing responsibility onto the reviewer

It is not the responsibility of the reviewer that your code is correct, bug
free, or achieves its goals.  
Reviewers are there to help you, but if something is wrong, it’s your
responsibility to correct it.

#### 2. Boasting about your programming knowledge

As a reviewer, try to stick to objective improvements and make a best-intent
assumption that the submitter has done their homework.

#### 3. Getting it perfect

The goal of code reviews is to reduce risk, not to produce perfect code. It’s
okay to ship code in stages, and to commit to improving something later. If
you’re thinking – if we don’t get it correct up-front, we’ll never come back to
it – consider that if it never needs coming back to, perhaps those changes were
never necessary in the first place.

Code reviews are expensive. Every time you request a change, you’re probably
delaying that Pull Request by 24 hours or more. This can severely inhibit our
ability to move fast. Please be pragmatic, and consider the cost of each
incremental request for changes.

#### 4. Introducing long-term architectural changes for the first time

While code reviews are great for discussion on implementation, they’re not the
place to introduce large, long-term changes for the first time. Before dropping
a Pull Request that implements those changes, you should definitely open an
issue beforehand to start a discussion in general.

### Guidelines for Reviewers

Note: This is only relevant for us at Aivot since we are the ones reviewing code
(see [General Workflow](./CONTRIBUTING.md#general-workflow-)).

#### Be polite and empathetic

Avoid accusatory and/or judgmental comments like: “You should have done X”.

#### Provide actionable feedback

Instead of “This is bad”, try “I feel this could be clearer. What if you renamed
variable X to Y?”

#### Distinguish between “requires changes” and “nitpicks”

Consider marking a Pull Request as approved if the only requested changes are
minor nits, so as not to block the author in another asynchronous review cycle.

#### Respond promptly to code review requests

We’re a community and you need to unblock other developers so that we can all
move forward.  
We recommend checking for open code reviews at the start and end of every day.  
[GitHub's Review Requests tab](https://github.com/pulls/review-requested) can be
a helpful place to keep track of these.

## Dependencies 🔗

We rely on open source projects ourselves for development. In order not to
violate any rights, we pay very close attention to which licenses we allow for
third-party dependencies.  
As a contributor, please be mindful of the licenses of any new dependencies you
introduce. Our policy is as follows:

  - ✅ Permissive Licenses (e.g., MIT, Apache 2.0, BSD): These are generally
    permitted.
  - ⚠️ Weak Copyleft Licenses (e.g., LGPL, MPL 2.0): These must be reviewed and
    approved by our team.
  - ❌ Strong Copyleft Licenses (e.g., GPL, AGPL): These licenses are
    incompatible with our projects and are not permitted.
  - 🚫 Proprietary Licenses: These are not permitted under any circumstances.

To enforce this, an automated license check runs on every Pull Request.
This scan will report whether all licenses are compliant or if further steps are
needed to resolve a conflict.

## Translations 🇩🇪

Currently there is no support for translations. We plan on adding support in the
future.

## Documentation 📝

We at Aivot write any documentation. Be it code documentation or documentation
for the end user. The main reason for this is that documentation is only very
good if it is consistent. In addition, there are sometimes hands-on demos within
the documentation. And we don't expect any external contributor to produce them.

For development documentation as well as end user documentation visit our
[documentation overview](https://aivot.de/docs) and select the respective
project.

--------------------------------------------------------------------------------
Inspired by the great development guideline from the team
[@getsentry](https://github.com/getsentry)
