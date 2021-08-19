### webpack-module-federation-example

# Lerna + NPM v7

In this case, NPM v7 workspaces feature are been used so all dependencies are hoisted to root node_modules and all packages has access to them and use Lerna to execute a command on all monorepo packages

# i18n

This example also contains i18n (using i18next and react-i18next) to show that even with remote microfrontends managed by Module Federation, we are able to share the same i18next instance (and thus a change in the language in one page will be send to all pages/MFEs using it) and even overwrite translations of a MFE from another one.

# Authentication (React Context API)

This example includes a very simple authentication feature just to show that it is also possible to use React Context API with remote MFEs. When user logins at the home page, a token is generated and stored in the Context and later retrieved in another MFE to be able to check if user is still logged and show some information get from authentication fake system.

## Cons & Pros

### Pros

- It is was not generated using create-react-app we have access to Webpack configuration.
- All apps are in a Monorepo that can also contain libraries (like a design system or shared components)
- Module federation works as expected

### Cons

- New apps needs to be generated manually or via a custom CLI as we can't use CRA.

# Steps

Execute `npm install` to install all dependencies

To start the MFEs in development mode, just execute:

`npm run develop`

To build for production execute the command:

`npm run build`

Once the build is finished, you can start a simple local web server with:

`npm run start`