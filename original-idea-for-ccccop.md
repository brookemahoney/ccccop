# Context Control Center Contribution Onboarding Process (ccccop)

A new web site.

## Mission

To help individuals and agencies learn how to contribute most effectively to the Drupal AI Context Control Center (CCC) by:
- Creating an online guide for how to contribute
- Creating separate learning paths per persona:
    - Agency
    - Strategist
    - Developer
    - Tester
    - Advocate

## Vision

A place where an interactive guide exists about how to most effectively contribute to CCC.

A place where a Project Lead has modern tools for creating and maintaining a living interactive guide for their stakeholders.

## Values

We follow the Drupal Code of Conduct: https://www.drupal.org/dcoc

## Methods

- AI will be used to interview Brooke, and to help her document, organize, distill, and expand on ideas she has and on ideas that Kristen Pol, the Project Lead, has about the onboarding process.
- Brooke is the project owner for now and is responsible for creating the first draft map.
- When Brooke has questions that she can't answer, she'll use the following skill from `mattpocock/skills` to create a questionnaire for Kristen:
    - `/to-questionnaire`: Turn a decision you can't answer alone into a Markdown questionnaire for the one person who can, filled in async, or together over a meeting. It grills you about the send (who it's for, what you need back), not the subject.

## Tools

The project will use a dedicated docker container:
- Configured using DDEV for generic PHP and/or Node.js, though a static HTML/JS/CSS site is a likely end product.
    - This allows for fast prototyping.
- T3Code runs in the container, acting as an agent orchestrator and providing a UI available in the host OS Browser.
- OpenCode runs in T3Code (other harnesses can be easily added later, ie Claude, Codex, Cursor, Antigravity)
- Matt Pocock's agent skills (mattpocock/skills) are available
- Matt Pocock's `/wayfinder` skill will be used to create a map for research, for prototypes, and for ideation (aka grilling).
- Once all the issues in the map are resolved, which means all the decisions have been made, then if it's decided that the site is a good idea to make, a spec can be made from the map; see Appendix.

Tracked with git, uploaded to a private Github repo that both Brooke and Kristen have access to.
- Can be made public later to utilize the free Github pages feature.
- Contains the full` .ddev` directory, which includes all the planning documentation, the AI-assisted environment, and the implementation of the site.


## Appendix
### Wayfinder Workflow

- Use `/wayfinder (prompt)` to create a map with decision issues.
- Wayfinder will ask you choose a destination: a buildable spec or an actual product.
- After wayfinder has made the initial map, work through issues one at a time using `/wayfinder (ticket number)` until all decisions are made. Sometimes new issues will be created while working on other issues.
- Wayfinder will utilize other skills, such as /grill-with-docs, /prototype, and /research.
    - The map specifies when each of those other skills are to be used
- The map also includes a list of 4 types of decision tickets:
    - research
    - prototype
    - grilling
    - task (things the agent can't quite do itself)
- Once the map is made, then you can use `/to-spec` to turn the map into a spec.
- Then use `/to-tickets` to create implementation tickets from the spec.
- Use `/implement` to implement one ticket at at time
- Use `/implement-spec` to have agents implement the whole spec AFK, using parallel agents
- Use `/code-review` afterward, typically with a different LLM and/or harness.
- Use `/retro` afterward to have the agent document what could have went better in the session.


### Other mattpocock/skills that are helpful

- `/handoff`: Compact the current conversation into a handoff document so another agent can continue the work.
- `/teach`: Teach the user a new skill or concept over multiple sessions, using the current directory as a stateful teaching workspace.
- `/wait-what`: Fire this the moment a message doesn't land.
- `/to-questionnaire`: Turn a decision you can't answer alone into a Markdown questionnaire for the one person who can, filled in async, or together over a meeting. It grills you about the send (who it's for, what you need back), not the subject.


### Notes from Kristen in Slack about contributing and about how the work for the project is usually handled

- "Often there are lots of issues to pick from"
    -  "there are some initiative contributors that tend to pick them up quickly."
- "the initiative works in 2 week sprints."
- "Next week we start sprint 20 but I need to go through and figure out what'll be in it. There are some already tagged."
    - For users with a Drupal Gitlab account, if they are logged in they can see the sprint 20 issues on the following page: https://git.drupalcode.org/project/ai_context/-/work_items/views/95
- "The best way to help is to look at the issues in the sprint list and pick up one that isn't assigned."
    - "There is an expectation that the work is done within a day or two and then unassigned."
- "Another approach is just try testing it and see if you can find bugs or if you have ideas for features or UX improvements."
- "I'm trying to figure out the roadmap for the next 6+ months. Once I have a better handle on that. Things should be more clear."
    - For users with a Drupal Gitlab account, if they are logged in they can see the Gitlab work item "Create CCC roadmap for next two to three quarters (Oct 2026 to June 2027 and later)" on the following page: https://git.drupalcode.org/project/ai_context/-/work_items/3586594

### About the Drupal AI Context Control Center (CCC)

The Context Control Center (CCC) Drupal module "helps Drupal AI use your content, rules, and standards to deliver more accurate, relevant results."

Helpful links:
- Module overview page (agents might be blocked from reading this due to a JS bot challenge), which contains a general description of the features: https://www.drupal.org/project/ai_context .
- Current documentation for contributions: https://ai-context-b13f05.pages.drupalcode.org/contribute/
- Codebase on Gitlab: https://git.drupalcode.org/project/ai_context
- Release Candidate 1 (RC1) was released on October 5th, 2026. A blog post about it can be found here: https://salsa.digital/insights/drupal-ai-context-first-release-candidate-available
- An article from September 16, 2026 "The Context Control Center and your AI Automators" can be found here: https://www.morpht.com/blog/same-rules-every-suggestion-context-control-center-and-your-ai-automators
- An article last updated on October 13, 2026, titled "Context engineering in Drupal: introducing the AI Context Module" can be found here: https://salsa.digital/insights/operationalising-context-engineering-drupal-introducing-ai-context-module/
- An overview of a presentation by Kristen at the AI Learner's Club titled "2026-09-11 — Context Control Center: Teaching Drupal AI Your House Rules" On September 11, 2026 can be found here: https://www.drupal.org/docs/develop/development-tools/ai-coding-tools-for-drupal-development/drupal-ai-learners-club-sessions/2026-09-11-%E2%80%94-context-control-center-teaching-drupal-ai-your-house-rules
- Information about a talk given at DrupalCon Rotterdam on September 30, 2026 can be found here: https://events.drupal.org/rotterdam2026/session/context-control-center-bringing-ai-context-natively-drupal-cms
