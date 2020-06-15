# State of play

## Current stack:
- Framework: NextJS (front end and SSR/server functions)
  - [Example repo with Static routes, dynamic routes, getInitialProps function, and API routes etc.](https://github.com/NewFrontDoor/stkildapc-nextjs)
- Design system: ThemeUI (built upon emotion.sh)
  - [Example repo with ThemeUI theme files, sx prop, Styled api, ThemeUI components](https://github.com/NewFrontDoor/stkildapc-nextjs)
- CSS: Emotion.sh
  - Used as an escape hatch where the ThemeUI approach impacts code readability or is too inflexible. Used by ThemeUI under the hood, so the syntax is essentially the same. **Prefer use of the sx prop offered by ThemeUI instead, to access theme values**
- Content management: Sanity.io (headless CMS)
  - [A full featured Sanity studio example](https://github.com/NewFrontDoor/crossroadshobart-sanity)
  - [The corresponding NextJS repo with Sanity queries](https://github.com/NewFrontDoor/crossroadshobart.org/blob/master/lib/queries.js) (links directly to queries folder, but just jump up a level to see how the query is utilised)
- Large asset storage: AWS S3 (integrated with Sanity.io)
  - [Sermon upload lamba endpoint](https://github.com/NewFrontDoor/v100it-lambdas/tree/master/functions/sermon-upload) (Likely to be replaced with API routes in NextJS)
  - [Sanity plugin which uses the presigned-post endpoint to upload to S3 from Sanity](https://github.com/NewFrontDoor/crossroadshobart-sanity/blob/master/plugins/s3-upload-widget/index.js)
- Hosting: Vercel (formerly called zeit now)
- Testing: React Testing Library + Github Actions
- Continuous deployment: Github/Vercel
- Lambda deployment: Vercel/Serverless
  - [Our lambda repo, with deployment tooling](https://github.com/NewFrontDoor/v100it-lambdas)

## Fully Retired/Soon to be retired stuff:
- EC2/Elastic Beanstalk
- Drupal
- MongoDB
- non-Outlook distro lists
- Sparkleshare
- Killing cloudfront?

## What needs to be done to complete our transition to the new stack:

### Migrations:
- Ensure all current client sites written in React are running our latest UI components
- Rewrite themes from PHP/other languages/systems onto React/NextJS
- Migrate clients away from Drupal and onto Sanity.io
- Shut down all EC2/EB/Mongo instances

### Libraries/Utilities
- Tightening up of our Presigned URL upload functions to be 1. Sufficiently able to spin up a new function/bucket quickly, 2. Lock it down so it’s safe!
- Nail down our new podcast feed creation (NextJS API routes)
- Complete removal of MineralUI from our ui library, work toward stabilising our components and increasing the number of abstracted components we have (e.g. mobile menus, footers, layout styles matching sanitiy schemas). Once component is stable, write Typescript version

### Projects:
- 'Common footer' project for consistent NFD branding across all client sites
- Entirely rebuilding NFD based on current stack and with new sales focus, including showcase of client sites
- Client onboarding app to automate/streamline the process
- Backup data from Sanity.io

### Tooling:
- Scaffolding around spinning up Sanity.io deployment with common schemas/layouts for new clients
- Scaffolding around rapidly prototyping NextJS theme for clients

### Client support:
- Set-up shared mailbox for support@ emails

## Open client projects
- FOCUS (now v2 - Sanity etc.)
- Soul Church
- Westminster Presbyterian Church
- Vision 100
- Christ Centred Church
- Armadale (final tidy up for new feature)
- Crossroads (final tidy up post-migration)

## Upcoming client projects
- Ministry Development Committee - PCV
- AFES Sunshine Coast
- Mornington Presbyterian Church
- New Front Door

### Outstanding needs
- Any dependency vulnerabilities? Security issues?
- Logs and Monitoring - should we be paying for these from Vercel? Especially around users and payments etc.
- Vercel paid seats
- Backups for sanity data
