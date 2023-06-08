# Shopify App Template - Next.js App Router

This is a template for building a [Shopify app](https://shopify.dev/apps/getting-started) using Next.js and Typescript. It contains the basics for building a Shopify app. This template was modified from the original example node app to use a single Next.js native application.

Rather than cloning this repo, you can use your preferred package manager and the Shopify CLI with [these steps](#installing-the-template).

## Next.js and Shopify Embedded Apps

This repository contains a boilerplate codebase for developing Shopify apps using Next.js, a popular React framework, and an app router for easy navigation. It includes essential setup and configuration for Shopify app authentication and provides a starting point for building powerful Shopify apps. Use this repository as a template to kickstart your Shopify app development projects. There a couple key points to be aware of when diving into the project:

### Environment Variables

There are a couple environment variables you need to set up in order for the app to run. Create a file called `.env.local` in the `/web` directory (or the root of your Next.js app) and add the following lines;

```bash
NEXT_PUBLIC_HOST=$HOST
NEXT_PUBLIC_SHOPIFY_API_KEY=$SHOPIFY_API_KEY
MONGODB_URI= # mongoDB Cluster URI
```

The first two variables are automatically populated by the Shopify CLI.

## Todo

- ✅ Update project to use the new `/apps` directory from Next.js

## Errors

- ❗Need some improvements on NEXT Router Error

## Benefits

Shopify apps are built on a variety of Shopify tools to create a great merchant experience. The [create an app](https://shopify.dev/apps/getting-started/create) tutorial in our developer documentation will guide you through creating a Shopify app using this template.

The Node app template comes with the following out-of-the-box functionality:

- OAuth: Installing the app and granting permissions
- GraphQL Admin API: Querying or mutating Shopify admin data
- REST Admin API: Resource classes to interact with the API
- Shopify-specific tooling:
  - AppBridge
  - Polaris
  - Webhooks

## Tech Stack

This template combines a number of third party open-source tools:

- [Next.js](https://nextjs.org/) builds the [React](https://reactjs.org/) frontend.

The following Shopify tools complement these third-party tools to ease app development:

- [Shopify API library](https://github.com/Shopify/shopify-node-api) adds OAuth to the Express backend. This lets users install the app and grant scope permissions.
- [App Bridge React](https://shopify.dev/apps/tools/app-bridge/getting-started/using-react) adds authentication to API requests in the frontend and renders components outside of the App’s iFrame.
- [Axios](https://axios-http.com/) for simple http requests for interacting with the API (Shopify or Custom API routes through Next API Pages).
- [Apollo](https://www.apollographql.com/) for interacting with the Shopify GraphQL API.
- [Polaris React](https://polaris.shopify.com/) is a powerful design system and component library that helps developers build high quality, consistent experiences for Shopify merchants.
- [Custom hooks](https://github.com/Shopify/shopify-frontend-template-react/tree/main/hooks) make authenticated requests to the Admin API.

## Getting started

### Requirements

1. You must [download and install Node.js](https://nodejs.org/en/download/) if you don't already have it.
1. You must [create a Shopify partner account](https://partners.shopify.com/signup) if you don’t have one.
1. You must [create a development store](https://help.shopify.com/en/partners/dashboard/development-stores#create-a-development-store) if you don’t have one.

### Installing the template

This template can be installed using your preferred package manager:

Using pnpm:

```shell
pnpm create @shopify/app --template https://github.com/AppifyTeck/shopify-app-next.git
```

Using npx:

```shell
npx @shopify/create-app@latest --template https://github.com/AppifyTeck/shopify-app-next.git
```

This will clone the template and install the required dependencies.

#### Local Development

[The Shopify CLI](https://shopify.dev/apps/tools/cli) connects to an app in your Partners dashboard. It provides environment variables, runs commands in parallel, and updates application URLs for easier development.

You can develop locally using your preferred package manager. Run one of the following commands from the root of your app.

Using pnpm:

```shell
pnpm run dev
```

Using yarn:

```shell
yarn dev
```

Using npm:

```shell
npm run dev
```

Open the URL generated in your console. Once you grant permission to the app, you can start development.

## Deployment

### Application Storage

This template uses MongoDB for accessing and managing sessions. It uses a custom written solution to handle connections to the MongoDB database in the Next.js development and production environment.

### Build

The frontend is a single page app. It requires the `SHOPIFY_API_KEY`, which you can find on the page for your app in your partners dashboard. Paste your app’s key in the command for the package manager of your choice:

Using pnpm:

```shell
cd web/frontend/ && SHOPIFY_API_KEY=REPLACE_ME pnpm run build
```

Using yarn:

```shell
cd web/frontend/ && SHOPIFY_API_KEY=REPLACE_ME yarn build
```

Using npm:

```shell
cd web/frontend/ && SHOPIFY_API_KEY=REPLACE_ME npm run build
```
