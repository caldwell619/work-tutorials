# Cloning the Project onto Your Machine

[Table of Contents](../README.md)

## Setup

It doesn't matter which folder you keep the project in, just make sure it's **not** a git repository.

Find that special one, and run ` git clone `.

## Necessary Local Files

In the project root of `web` ( `BuyNow/source/web/` ), create a `.env.local` file.

Copy the `.env.development` file's contents into this file, and change a couple things.

### Original

`VueAppPUBLIC_KEY= `
`VueAppAPI_URL= `

### Local

`VueAppPUBLIC_KEY= ASK_ONE_OF_US`
`VueAppAPI_URL= http://localhost:1337/ `

The public key for the reCaptcha is stored in TFS for the non-local environments.

The API URL needs to first run through the locally `cors proxy` for it to work. We will work on set up of that later, for now just make sure the url changes.

## Next Steps

This one was pretty straight forward.

Onto [running the project locally](./running.md)