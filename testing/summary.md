## What does this PR do?

This PR adds answered and unanswered variants to the GitHub Discussions badge in shields.io. It extends `github-discussions.service.js` to support `/answered` and `/unanswered` path variants alongside the existing total count, and adds unit tests in `github-discussions.tester.js` for URL construction, transform, and render logic. Frontend documentation is updated so users can discover and use the new badge variants.

Examples:
- Total: `/github/discussions/vercel/next.js`
- Answered: `/github/discussions/vercel/next.js/answered`
- Unanswered: `/github/discussions/vercel/next.js/unanswered`

## Why was this PR needed?

Issue #6047 requested answered and unanswered filter variants for the existing GitHub Discussions badge. Previously, only the total discussion count was available. Since the GitHub API now supports filtering discussions by answered status, extending the existing service with path variants — rather than adding separate endpoints — matches how other GitHub badges in the codebase handle similar cases and keeps the API consistent for users.

## What are the relevant issue numbers?

Closes #6047

## Does this PR meet the acceptance criteria?

- [x] Well Written Title and Summary of the PR
- [x] Tests added for new/changed behavior
- [x] All tests passing (`npm run test:services -- --only=GithubDiscussions` — 9/9 passing)
- [x] Follows project service patterns (extends existing `github-discussions` badge)
- [x] No breaking changes introduced

## Screenshots

All three badge variants running locally against `vercel/next.js`:

![GitHub discussions badges — total, answered, and unanswered](../images/Screenshot%202026-07-03%20at%2017.42.33.png)



## File changes

| File | Change |
|------|--------|
| `services/github/github-discussions.service.js` | Extended to support `/answered` and `/unanswered` path variants; fetches filtered counts from the GitHub API |
| `services/github/github-discussions.tester.js` | Added unit tests for URL construction, transform, and render logic for the new variants |
| Frontend documentation | Updated badge listing and examples so users can discover the answered and unanswered variants |
