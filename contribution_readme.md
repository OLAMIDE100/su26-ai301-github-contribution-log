# Contribution 1: Badge request: GitHub Discussions

**Contribution Number:** 1  
**Student:** Adewale Olamide Adesoba  
**Issue:** https://github.com/badges/shields/issues/6047  
**Status:** Phase IV Complete

---

## Why I Chose This Issue


Having used shield.io in the past to make my github profile page colorful and my clear understanding of the issue together with the undelaying technology powering this open source tool like  calling the github api and consuming the response, also the ease of reproducing the issue i hope to confidently add this feature and improve my open source contribution skillset. 

---

## Understanding the Issue

### Problem Description

The solution i will be providing is more of feature enhancement rather than issue, it focuses on adding the answered/unanswered filter variants of the discussions badge to the already existing badges 

### Expected Behavior

Two more discussions badge providing information on answered and unanswered  variants

### Current Behavior

Currently only the total number of discussion of the discussion badge is available

### Affected Components

Discussion badge
https://github.com/badges/shields/tree/master/services/github

---

## Reproduction Process

### Environment Setup

I cloned the master repository, updated my node package manager and ran the required the commands to start the server on my local computer, the only issue was just updating my node package manager as the current version was not compartible with the recommended version from the source repository

Working branch: https://github.com/OLAMIDE100/shields/tree/add-discussion-variants

### Steps to Reproduce

1. git clone master branch
2. update node to 22
3. Run npm ci to install the dependencies.
4. Run npm start to start the badge server and the frontend dev server.
5. Open http://localhost:3000/ to view the frontend.
6. Navigate to others, then click github discussion under 

### Reproduction Evidence

- **Screenshots/logs:** 
![results](images/issue_replication_code_setup.png)

![code-run](images/issues_replication.png)
- **My findings:** The answered and the unanswered variant of the discussion section is not yet available

---

## Solution Approach

### Analysis

From my analysis the last time the section was updated, the api for loading the data for this section was not yet available in github

### Proposed Solution

Add the discussion variants by add codes both for backend and frontend to make this effective

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** The solution will be an extention of the already existing github discussion badge to cover its total answered and unanswered variants.

**Match:** We already have the github discussion badge code for both frontend and backend

**Plan:** 

1. test the api to understand the response and how to properly load them
2. add the frontend and backend code
2. add unit test 


**Implement:** https://github.com/OLAMIDE100/shields/tree/add-discussion-variants

**Review:** Will self-review against project CONTRIBUTING.md and 
commit message conventions before opening PR.

**Evaluate:** check that the github discussion total answered and unanswered variant areseen in my local environment while reproducing and all test associated with them pass successfully

---

## Testing Strategy

### Unit Tests

- Test case 1: test for availability of repo
- Test case 2: test for presence of repo discussion

### Integration Tests

- github api authentication locally


### Manual Testing

check the badge after setup in my local machine

---

## Implementation Notes

### Week 3 Progress

**What I built:**
- Setup the example files in the service folder to foster my practical knowledge on how it works in development environment
- Added 2 services:
  - service 1: get the total count of answered github repository discussion
  - service 2: get the total count of answered github repository discussion
- Added 2 test:
  - Test 1: repo exist
  - Test 2: repo have discussion
- Update the frontend pointing to the documentation
- All existing tests still pass (ran full test suite)

**Challenges faced:**
- Invalid error as no github token was provided locally

**Commits this week:**
- https://github.com/badges/shields/commit/e0251485afd3a470e092022c2c951d635e07fdfb: added both the service and tester for both the answered and unanswered variant of  github discussion



### Week 4 Progress



## Pull Request 

**PR Link:** https://github.com/badges/shields/pull/11951

**PR Description:** 

Add the variant badge of github discussion (answered/unanswered) together with its test and documentation

Closes  https://github.com/badges/shields/issues/6047

## Badge endpoint

`/github/discussions-answered/:user/:repo`
`/github/discussions-unanswered/:user/:repo`

Examples:
- answered discussion: `/github/discussions-answered/vercel/next.js`
- unanswered discussion: `/github/discussions-unanswered/vercel/next.js`


## Implementation

- `services/github/github-discussions-answered.service.js` — fetches the total number of answered discussions for a specific repository
- `services/github/github-discussions-answered.tester.js` — unit tests for URL, transform, and render logic
- `services/github/github-discussions-unanswered.service.js` — fetches the total number of unanswered discussions for a specific repository
- `services/github/github-discussions-unanswered.tester.js` — unit tests for URL, transform, and render logic

## Tests

- `npm run test:services -- --only=GithubTotalDiscussions,GithubAnsweredDiscussions,GithubUnansweredDiscussions` — 6 passing

**Maintainer Feedback:**

- 28/06/2026: Pull request name update to enable automated ci testing


**Status:** Iterating

---

## Learnings & Reflections

In general patience was required to wait for the maintainers updates on the pull request

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]

