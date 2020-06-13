# State of play

## Current stack:
- Framework: NextJS (front end and SSR/server functions)
- Design system: ThemeUI (built upon emotion.sh)
- CSS: Emotion.sh
- Content management: Sanity.io (headless CMS)
- Large asset storage: AWS S3 (integrated with Sanity.io)
- Hosting: Vercel (formerly called zeit now)
- Testing: React Testing Library + Github Actions
- Continuous deployment: Github/Vercel
- Lambda deployment: Serverless

## Fully Retired/Soon to be retired stuff:
- EC2/Elastic Beanstalk
- Drupal
- MongoDB
- non-Outlook distro lists
- Sparkleshare

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

### Tooling:
- Scaffolding around spinning up Sanity.io deployment with common schemas/layouts for new clients
- Scaffolding around rapidly prototyping NextJS theme for clients

### Client support:
- Set-up shared mailbox for support@ emails

## Open client projects
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
