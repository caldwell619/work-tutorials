# Running on Your Machine

[Table of Contents](../README.md)

## Disclaimer

Some developers choose to use Docker to run the project. That's the goal, but we're not all there yet.

## Checklist so far

- [ ] All programs from [the installation page] at installed(./requirements.md)
- [ ] You have the project cloned locally
- [ ] You have created a `.env.local` with the applicable information

## Configuring npm

SWBC uses a Verdaccio local npm registry. It's hosted locally, so we need to tell npm where to look for certain packages.

To configure npm, run the following while on the local network ( VPN or in office ):

```bash
npm set registry https://registry.npmjs.org \
npm config set @swbc:registry http://d-appadi1:4873 \
npm config set @tuplelabs:registry http://d-appadi1:4873
```

## Second Disclaimer / Docker

This is important. **Pay Attention**. Yeah, you. The one barely reading this!

If you install dependencies on `Node v10.x`, you cannot switch to Node `v8.10` and run this application.

This project uses Sass, and compiles the styles using a specific Node version. This is why we [use Docker](./docker.md)

## Commands

Getting started isn't too hard, if explained even mildly well.

### Cors Proxy

Open a new tab in the terminal, and run `corsproxy`. This will start a process that **MUST** be running while developing. Don't worry too much about those specifics right now.

### Installing Dependencies

In a new tab, navigate to the web root, `BuyNow/source/web/`

If using Node `v10,x`, run `npm ci`

`ci` installs off of `package-lock.json` rather than `package.json`. The reason this is preferred is because `npm i` can, and often will overwrite `package-lock.json` causing lots of problems.

### Running Locally

Theres 2 commands for starting the development server. This page assumes you're not using Docker.

After the dependencies have finished installing, run `npm run serve`.

#### Part One

This command [sources](https://ss64.com/bash/source.html) the `.env.local` file, injecting the variables defined inside of it, as consumable `process.env.VAR_NAME` inside of the JavaScript code.

#### Part Two

This command also runs the development server to show the code on the interwebs, with the local environment variables injected inside of the code.

## Next Steps

Yay! Stuff is on the screen. 

Let's talk about [contributing](./contributing.md)
