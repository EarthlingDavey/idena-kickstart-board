# Davey's Proposal Technical Details

This document is an outline of how I would develop the site and why I think it is important and relevant to the kickstarter project & Idena.

In the interest of transparency I am asking for my freelance rate of \$250 / day. And I estimate that the build, adding content and quality testing will take around 9 days.

My rough maths say this project would meet the target if a fraction of people send only a fraction of their daily mining reward.

I understand this is not the usual way crypto developers approach funding. Most times they ask for less than their salary, but please read the details and understand that I like Idena, so I want it to succeed.

Please hold off picking me as the developer and wait for other offers of developers. Compare the technical details of each, and then make a decision.

## Frontend technology

Use React and the react framework [next.js](https://nextjs.org/).

Benefits for this project:

- Pre-Rendering, which means that the website is rendered on the server. Compared to react this has seo advantages.
- Components. This means that each part of the website can be built once and shared across multiple react websites. For example we can re-use the header from [idena-apps.org](https://idena-apps.org)
- CSS-in-JS. Helps us write maintainable css that is easy for new developers to start with. With one big css file or badly managed scss - coding styles can get very messy and time consuming.
- React is a single page app. So no loading between page changes. Gives a quick feel when browsing.
- React is a popular library. And react developers should be able to learn next.js easily. Good for having multiple contributors.
- Next.js is one of the technologies used for the Idena desktop wallet. If we attract next.js and react developers to the community then they can contribute to both and/or new projects.

### Other frontend considerations

- schema.org markup to describe the pages content in an easy to digest way for seo bots
- social meta tags mean social shares from the site have images and description
- development with multi language support in mind. This may be added in the future.

## API between front and backend

Graphql is an alternative to REST api.

Benefits for this project:

- Frontend code can be written quickly.
- Whereas multiple consecutive rest api calls would have been needed in the past. A single graphql one can be made now. Quicker coding and loading.
- Becoming a new industry standard. Could attract new developers to the community if they see we are sing new tech.
- GitLab ( and other git hosts ) provides a graphql API. So we can get project information directly from there into the browser.

## Data storage

A git host like GitLab for data that should be publicly viewable.

Benefits for this project:

- An audit trail of sort. So that all proposals and changes are publicly visible.
- An account and permissions system. So the website does not need it's own login/account area.
- The voting/donation address will load directly into the browser from GitLab, minimising risk of a hack.

A sql like database will be used on the backend

Needed for the project.

- Track donations
- Cache the proposals from the GitLab repo
- Store other info like people who write proposal

The official Idena API will be used (to start with) to get data regarding votes/donations

I will also use the backup .org domain as a fallback in case idena.io domain is down.

There is also potential to add a 3rd party fallback.

## Backend

A node.js backend

- Can read the db and serve up a graphql API. It is self documenting, making it easy for new developers.
- Webhooks endpoints, so that if a git repository is updated, it can take appropriate action. Like syncing.
- Uses sequelise an orm so we can start with sqllite and scale to mysql if necessary.
- Possibility for using web-sockets easily. For example realtime updates on screen as donations are confirmed on the network.

## Developer experience

Using docker during development. Development is the same across Win/OSX/Linux

Fully documented code. Easy to maintain.

Using separate git repositories for frontend, backend, proposals. To keep things organised.
