# Getting Started

The steps for running the project locally are pretty straight forward.

- Clone the repository
  - `git clone http://p-apptfsalm1:8080/tfs/AppDevScrum/Marketplace/_git/mkt-web-ui`
- Navigate to the project
  - `cd mkt-web-ui/`
- Install the necessary dependencies
  - `npm install`
- With `vue-cli-service` globally installed, start the local enviornment server. By default, it runs on port 8080.
  - `npm run serve`
- In the browser, navigate to `localhost:8080/:institutionId/splash` to see the home page.
  - Substitute `institutionId` with a real one, obviously

This build uses a hot reload, so any changes made to the code will be reflected in the browser without you having to refresh, or save the file. It is buggy sometimes, so a refresh can be necessary on rare occasions
