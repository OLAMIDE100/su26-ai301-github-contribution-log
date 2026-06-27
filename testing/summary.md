## Summary

Add the variant badge of github discussion (answered/unanswered) together with its test and documentation

feature extension #6047

## Badge endpoint

`/github/discussions-answered/:user/repo`
`/github/discussions-unanswered/:user/repo`

Examples:
- answered discussion: `/github/discussions-answered/vercel/next.js`
- unanswered discussion: `/github/discussions-unanswered/vercel/next.js`

Optional `server` query parameter defaults to `https://copr.fedorainfracloud.org`.

## Implementation

- `services/github/github-discussions-answered.service.js` — fetches total number of answered discussion for a specific repository
- `services/github/github-discussions-answered.tester.js` — unit tests for URL, transform, and render logic
- `services/github/github-discussions-unanswered.service.js` — fetches total number of unanswered discussion for a specific repository
- `services/github/github-discussions-unanswered.tester.js` — unit tests for URL, transform, and render logic

## Tests

- `npm run test:services -- --only=GithubTotalDiscussions,GithubAnsweredDiscussions,GithubUnansweredDiscussions` — 6 passing