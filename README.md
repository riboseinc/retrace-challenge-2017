# The Retrace Challenge + Rewards

* NEWS: 2017-08-09: We are happy to announce the Retrace Challenge! See below!
* NEWS: 2017-08-21: show [existing submissions](https://github.com/riboseinc/retrace-challenge-2017/blob/master/EXAMPLES.adoc)

See [submissions found on FreeBSD/NetBSD/DragonFlyBSD](https://github.com/riboseinc/retrace-challenge-2017/blob/master/EXAMPLES.adoc)

[retrace](https://github.com/riboseinc/retrace)
is a versatile security vulnerability / bug discovery tool
through monitoring and modifying the behavior of compiled binaries on
Linux, OpenBSD/FreeBSD/NetBSD (shared object) and macOS (dynamic library).

`retrace` can be used to assist reverse engineering / debugging
dynamically-linked ELF (Linux/OpenBSD/FreeBSD/NetBSD) and
Mach-O (macOS) binary executables.


Posted: 2017-08-09

We are happy to announce the Retrace Challenge!

The challenge is composed of three categories:

* Bug Challenge
* Improvement Challenge
* Usage Challenge

Our goal of the challenge is to:

* encourage security researchers to use `retrace` during their vulnerability assessment efforts;
* encourage developers to use `retrace` for code stability efforts; and
* make `retrace` more useful!

The main category is the "Bug Challenge": to find bugs (any bug AND security vulnerabilities)
in well-known software (OSS or proprietary) using `retrace`.


## Important Information

* Participation: anyone can participate
* Organizer: Ribose `retrace` team
* Eligibility period: From 2017-08-09 00:00:00 to 2017-10-10 00:00:00 (GMT) inclusive
* Results:
  * Winners will be announced on 2017-10-16 (GMT) on the same page as this announcement.
  * The selection of prizes will be determined solely by the organizer. We may not select winner(s) in a category if the quality of submissions is below our bottom line.
  * Reward amounts are in USD.
  * Winning challengers will receive their award via Amazon gift cards or PayPal transfer.

Please understand that while we aim to fully implement the spirit of fairness, in the case of any unresolved ambiguity or dispute, the organizer has the sole rights to make all decisions.


## The Bug Challenge

The Bug Challenge encourages finding bugs (any bug AND security vulnerabilities) in
well-known software (OSS / proprietary) using `retrace`.

### Eligibility

* The bug *MUST* be reported to the target software author AND the organizer during the "eligibility period". You must provide evidence to demonstrate this to the organizer (e.g., provide the public / private bug report).
* The bug will be eligible to the reward levels based on its CVE CVSS score.
* There is no absolute definition of "well-known software" -- it will be determined by the organizer -- please contact us to confirm prior to submission.
* Challenge submissions *ARE* allowed to be also submitted to other bounty programs under the condition that those bug reports *ALSO* fulfill our bug report eligibility requirements listed above. If a submission is discovered to be reported to other bounty programs that for example, do not mention `retrace`, it will be disqualified from our challenge.

### Eligibility Of Bug Report

* The bug report *MUST* be confirmed and accepted by the software author to be eligible for this challenge.
* The bug report *MUST*
  * Describe how `retrace` is used to discover / reproduce it
  * Include a link to `https://riboseinc.github.io/retrace/`
  * Mention "This submission is in response to the Ribose Retrace Challenge"

### CVE CVSS Score And Using retrace

* Critical: remote exploitable buffer overflows etc.
  * For example, can be discovered through Socket and File IO fuzzing (work in progress in retrace) or the `stringinject` utility.
* High: local exploitable buffer overflows etc.
  * For example, can be discovered through `getenv` fuzzing or the `stringinject` utility.
* Medium: severe crashes, buffer overflow etc.
  * Easy to discover using various retrace options, `stringinject`.
* Low: your average issues such as memory bugs.
  * Easy to discover using various retrace options, `stringinject`.

### Bug Challenge Rewards

Challenge rewards are given according to the CVE CVSS score of the entry:

* Critical: 1 grand prize of $1,000
* High: 2 prizes of $500
* Medium: 3 prizes of $200
* Low: a public name mention, the journey is the reward!

The `retrace` team will decide among all submissions of the same class (e.g., Medium, High), which discovered bugs would receive what prize, according to criteria derived from the following angles:

* Impact of the target software and impact of the bug in target software. We seek bugs that are more general in impact; rarely occuring bugs in obscure software will be de-prioritized.
* Creativity of retrace usage.

### Submitting To The Bug Challenge

Send an email to retrace@ribose.com with subject "Retrace Bug Challenge Submission" providing the following information:

1. Your particulars
  * Name (Title and Company if any)
  * Email

2. Bug details
  * Description
  * CVE score
  * CVE link and bug report link
  * Evidence of bug report acknowledged and confirmed by software author
  * Evidence of fulfillment of challenge eligibility criteria (e.g., inclusion of `retrace` usage) in the bug report



## The Improvement Challenge

The "improvement challenge" is to improve the actual `retrace` tool in form of code.

The challenger should write code that improves retrace (library or CLI) to do something useful.

### Eligibility

* The improvement *MUST* work on all supported platforms (unless it is a platform-specific improvement)
* The improvement *MUST* be accompanied with code to demonstrate "how the improvement is useful", and the results must be reproducible.
* The PR *MUST* NOT fail our builds on any platforms (Linux, \*BSD)
* Remember that this is an open source project. Your PR may be accepted and included in the `retrace` distribution.
* If the submission is interesting yet the quality of it needs improvement, the retrace team will provide feedback to you.
* Your submission *MUST* be able to be cleanly rebased by the close of submission period.
* Your code *MUST* be free to use by the `retrace` project, such as it does not violate any intellectual property rights (e.g., license agreements or patents) of third parties. Since `retrace` is released under the 2-clause BSD license, the submitted code will also be provided publicly under the 2-clause BSD license.

### Improvement Challenge Rewards

* Best Improvement Winner: 1 grand prize of $1,000
* Runner-Ups: 2 prizes of $500
* Commendable: 3 prizes of $50 each
* Worthy: incorporation into the `retrace` repo with a public name mention.

### Submitting To The Improvement Challenge

Submission is through GitHub Pull Requests to the https://github.com/riboseinc/retrace[`retrace` git repo].

* Your sample code *MUST* be in form of a PR.
* The PR title *MUST* start with "Retrace Improvement Challenge Submission: " with a brief description of improvement following that.
* The PR description must contain the following paragraph:

> I confirm that this submission does not infringe upon any intellectual property rights of any third party, and I have full rights to grant any rights and licenses of this work. I hereby assign the retrace project and its successors, a royalty-free, irrevocable, worldwide, non-exclusive, perpetual right and license to use, distribute, reproduce, modify and prepare derivative works of this submission, to perform and display publicly this submission, and to practice inventions in or associated with this submission, with (for each of the foregoing) full rights to authorize others to do the same.

## The Usage Challenge

The "usage challenge" is to discover creative and interesting ways of using `retrace` in form of code.

The challenger should write code that utilizes and incorporates retrace (lib or CLI) to do something useful AND interesting. The results will be incorporated in the `/examples` directory of the `retrace` repo for public usage, for the benefit of all.

### Eligibility

* Submitted code *MUST* be immediately runnable and results reproducable for the organizer (i.e. include script to install any dependencies, how to run the code and verify usage).
* Submitted code *MUST* be runnable across all supported platforms (unless it is platform-specific).
* The PR must not fail our builds on any platforms (Linux, \*BSD)
* Remember that this is an open source project. Your PR may be accepted and included in the `retrace` distribution.
* If the submission is interesting yet the quality of it needs improvement, the retrace team will provide feedback to you.
* Your code *MUST* be free to use by the `retrace` project, such as it does not violate any intellectual property rights (e.g., license agreements or patents) of third parties. Since `retrace` is released under the 2-clause BSD license, the submitted code will also be provided publicly under the 2-clause BSD license.

### Usage Challenge Rewards

* Best Usage Winner: 1 grand prize of $500
* Runner-Ups: 2 grand prizes of $200
* Commendable: 3 prizes of $50 each
* Worthy: incorporation into the `retrace` repo with a public name mention.

Your submission will be judged on how useful it is to the `retrace` target audience. The term "useful" is defined by its common English definition, with any decisions solely decided by the organizer.

### Submitting To The Usage Challenge

Submission is through GitHub Pull Requests to the [`retrace` git repo](https://github.com/riboseinc/retrace).

* Your sample code must be in form of a PR to the `/examples` directory, with a unique directory path in form of `/examples/{your-github-handle}/{your-entry-name}`.
* The PR title *MUST* start with "Retrace Usage Challenge Submission: " with a brief description of usage following that.
* The PR description must contain this phrase: "I confirm this submission is original work and will not infringe upon any intellectual property rights of any third party, and I have full rights to grant to the retrace project any rights and licenses."


