# How to InnerSource

Many teams at GovTech have applied the InnerSource collaboration model
to share and deliver more effectively. While the core premise of
Innersourcing is opening up code for collaboration, there are few
considerations to make sure your project is a success.

## Selecting a Project

When deciding if a project is a good candidate for Innersourcing, there
are a few aspects to consider:

* Is the code reusable by other projects and contains relevant shared
  information, such as:
  * Modular components with customizable parameters to allow for
    adaptation and integration into other project software code?
  * Documentation on how to use the software module, how to modify the
    code and how to contribute enhancements back to the InnerSource code
    repository?
* Does the entire project need to be InnerSourced or are smaller
  components more useful?
* Do parts of the project contain classified code that may not be
  appropriate to be shared or reused?

## Preparing your Project for InnerSource

### Onboard to SHIP-HATS

SHIP-HATS is the primary platform for Whole of Government developers to
host their code repositories, track issues and collaboratively share
project documentation.

Developers using the SHIP-HATS code repository platform will be able to
find properly tagged InnerSource code repositories, clone and integrate
the InnerSourced code into their projects, as well as write and
contribute enhancements and modifications back to the InnerSource code
repository.

Please see onboarding and setup information for SHIP-HATS
[here](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation).

### Configuring your Project Repository

Once a project is selected, the team should prepare the code to be made
available internally. The code (and history) in the repository should be
first reviewed for any potentially sensitive project data (including
secrets).

The project repo configuration should be verified to ensure that
protected branches are configured for the trunk branch (typically named
`main` or `master`).

**Merge Requests** are the primary means for contributors to submit
code. The feature should be enabled for the repo and a baseline
configuration established for project team members to review/approve
contributions (for example `CODEOWNERS`).

Once cleaned up and configured, the project repo should be opened up by
setting visibility `'internal'`.

Tagging the repo with the `'innersource'` label and any other relevant
keywords that will aid discovery.

### Issue Tracking

The project issue tracker is a useful way for new contributors to
understand work in progress and any areas they might be able to get
involved.

Although not required, it is recommended to use an Issue tracker that is
easily accessible for the potential contributors. The built-in issue
tracker in the project repo is usually the easiest option for most
projects. If another issue tracker (such as JIRA) is used, ensure that
it is discoverable (eg. linked from from standard documentation) and
openly accessible by new contributors without permission.

To assist new contributors, issue tracking labels are a useful tool to
understand areas to assist or for smaller changes that could be useful
for learning. Standard labels names include `"help wanted"`, `"good
first issue"`.

### Standard Documentation

Potential contributors often are lost when exploring a Innersource
project for the first time. These contributors may have a hard time
figuring out who maintains the project, what to work on, and how to
contribute. Providing documentation in standard files like `README.md`
and `CONTRIBUTING.md` enables a self service process for new
contributors, so that they can find the answers to the most common
questions on their own.

* **A good README**. What does your project do? What need does it
  address? Who inside Government would use it? How do you install it?
* **CONTRIBUTING Guidelines**. How do you want potential contributors to
  approach developing a change or enhancement for your project? An
  initial chat? An empty pull request with a detailed proposal?

Examples of these and other useful standard documents can be found in
the InnerSource template repository in SHIP-HATS.

### Licensing

When two or more agencies within an Government want to share code with
each other, they need an agreement about the terms.

An *InnerSource License* provides a reusable legal framework for the
sharing of source code within the organisation. This opens up new
collaboration options, and makes the rights and obligations of the
involved legal entities explicit. GovTech has developed a permissive
license for sharing code with other agencies (and their vendors) across
the organisation.

The GovTech Public Sector License (GPSL) can be found in the
SHIP-HATS template repository.

### Encouraging External Contributors

Many projects will find themselves in a situation where they
consistently receive feedback, features, and bug-fixes from
contributors. In these situations, project maintainers seek ways to
recognize and reward the work of the contributor above and beyond single
contributions.

It is recommended to establish a team structure to encourage
contributions (such as Maintainers and Trusted Committer roles)

What a Trusted Committer handles is up to each project and its
maintainers. Ensure you document within the project the scope of your
Trusted Committer role. Clear documentation (in the standard
documentation) sets expectations for new community members and
establishes the role for future candidates.

For more ideas and examples, see the [Trusted Committer](https://patterns.innersourcecommons.org/p/trusted-committer) pattern.

### Transparent Decision Making

InnerSource projects that want to achieve high participation rates and
make the best possible decisions for everybody involved need to find
ways to create participatory systems throughout the full software
lifecycle.

Publishing internal [Requests for Comments](https://patterns.innersourcecommons.org/p/transparent-cross-team-decision-making-using-rfcs) (RFCs) documents or
[Architecture Decision Records](https://engineering.atspotify.com/2020/04/when-should-i-write-an-architecture-decision-record/) (ADRs) allows for discussions early on in
the design process, and increases the chances to build solutions with a
high degree of commitment from all involved parties.

## FAQ

### What if our team doesn't have time to review all the incoming Merge Requests? <!-- {docsify-ignore} -->

That's up to your team to resolve. But keep this in mind: What is faster,
coding everything from scratch, or reviewing someone else's code?
Approaching these efforts as a collaboration — communicating your goals, plans, risks, etc to the participants looking to contribute can also
save you lots of time. Discussing over 30-60 minutes only takes
30-60 minutes. Clear contributing documentation can save even more time.

### It takes time to get people up to speed with the codebase and go through a couple of Merge Request iterations to get something done. What if we don't have time right now to handle that? <!-- {docsify-ignore} -->

Similar to the previous question, check again and make sure that it will truly take longer to teach
someone about your codebase than to do the work yourself. Also, don't make assumptions about your potential
contributors, especially if they are also following similar proceses: For all you know, they might be able to dive right in and
get the job done quickly. They might even be able to teach you some
things. This approach plays out in the open source world all the time.

### What if we allow a team to go forward with a Merge Request, and the end result is not to our liking? <!-- {docsify-ignore} -->

Try to work with the contributing team early to achieve something you
can all accept. Remember, part of this is on you communicating with the
contributing team what you're hoping they'll produce (in `CONTRIBUTING.md` or one-on-one). Check in with them
to get progress updates. Give them guidance, if needed as this will save
you time, and save frustration for everyone involved.

### What if someone surprises us with a Merge Request we didn't ask for and don't want? <!-- {docsify-ignore} -->

The team is in their right to not accept it. We want people to reach out
(via an Issue/MR/RFC/ADR/etc) to an owning team before making any bug fix
or (especially) more significant change to a repo. If, for example, a
team doesn't do that, and tries to fix one of your bugs or build one of
your requested features without talking to you, then you have the right
to reject their work. That team will most likely learn from the
experience and be sure to talk about their proposed changes before
setting to work. It is recommended to outline your preferred process in
the `CONTRIBUTING.md` document so that there are not too many surprises
and wasted effort on both sides.

### How do I know if a team will accept my proposed Merge Request? <!-- {docsify-ignore} -->

The easiest approach is to check the `CONTRIBUTING.md` and ask the team if
there is anything unclear. We recommend reaching out to their project
team via chat or a raising an Issue (with a 'question' label).

### What about contracted developers who work on InnerSource? <!-- {docsify-ignore} -->

Contractor developers or augmented staff are often not motivated (or
actively disincentivised) to not engage in InnerSource activities. Once
delivered, and even if the code is made visible, their projects are
often less likely to be part of successful InnerSourced engagements. At
the outset of the project, clearly define that the code will be made
`internal` by default or how the project will be transitioned to an
InnerSource project.

### What happens about contributors writing code and not supporting if it has bugs? <!-- {docsify-ignore} -->

When accepting contributions from outside of your own team, there is a
natural aversion to taking responsibility for code not written by your
team. Although not a requirement, one option is to ask for a 30 Day
Warranty that the contributing team consents to provide bug fixes to the
receiving team, which will increase the level of trust between both
teams and makes it more likely that contributions get accepted.


For more ideas and examples, see the [30 Day Warranty](https://patterns.innersourcecommons.org/p/30-day-warranty) pattern.

### What if I need help Innersourcing my project? <!-- {docsify-ignore} -->

Get in touch with the InnerSource Working Group.
and we'll be happy to help.
