<p align="center">
  <a style="padding-right: 16px;" href="https://forestry.io">
    <img src="https://app.forestry.io/assets/forestry-logotype-pos-c71a6bd237d9199d0457ba2811553997ff5bab0d2cd0e740686ab26c00d9c240.svg" width="112" height="28">
  </a>
  &nbsp;
  <a href="https://nuxtjs.org/">
    <img src="/static/nuxtjs-typo.svg" width="100" height="28">
  </a>
</p>
<h1 align="center">
  Brevifolia
</h1>

## About

[![Netlify Status](https://api.netlify.com/api/v1/badges/97aa0f61-0fe8-4859-a1b7-d7bcaabc0e5f/deploy-status)](https://app.netlify.com/sites/brevifolia-nuxt-forestry/deploys)

Brevifolia is minimalist blog starter to get you going using [Forestry](https://forestry.io/) with [Nuxt](https://nuxtjs.org/). Check out the demo [here](https://brevifolia-nuxt-forestry.netlify.com/)

This blog is statically generated by Nuxt, a rendered combination of Vue components and markdown files. It is preconfigured to work with Forestry as a way to manage your content. Forestry makes changes by editing markdown or data files, uploading media to the correct directory and committing these updates to your repo directly.

The styles were coded & designed by yours truly, using [scss](https://sass-lang.com/). The font used is [Work Sans](https://fonts.google.com/specimen/Work+Sans). 

##  Quick Setup

#### *Import Directly to Forestry*

<a href="https://app.forestry.io/quick-start?repo=kendallstrautman/brevifolia-nuxt-forestry&engine=other">
    <img alt="Import this project into Forestry" src="https://assets.forestry.io/import-to-forestryK.svg" />
</a>

#### *Set-up Locally*
In your terminal, navigate to where you would like this blog to live, then run 
```bash
#clone the repo
git clone git@github.com:kendallstrautman/brevifolia-nuxt-forestry.git

#navigate to the directory
cd brevifolia-nuxt-forestry

#install dependencies & run dev server with yarn 
yarn install
yarn dev

#or with npm 
npm install
npm run dev
```
You should then be able to navigate to localhost:3000 in your web browser

## Project Structure 

- Site-level configuration is stored in `content/data/config.json`. This data is loaded into `nuxt.config.js` to provide default site metadata. 
- Add and access webpack and Nuxt config options via `gridsome.config.js`. Global styles are loaded here. This is also where all the dynamic routes are generated for static export. [This blog](https://regenrek.com/posts/create-a-frontmatter-markdown-powered-blog-with-nuxt-js-in-2019/) and [this template](https://github.com/jake-101/bael-template) were a big help in figuring out how to approach dynamic routing with Nuxt.
- Edit global & reset styles via `assets/styles/...`. All component and page scss files are imported in the `global.scss` file.
- `content/...`contains all your markdown blog posts & data files (e.g. authors list, info page data). These are all editable by Forestry. 
- Images live and are uploaded in `static/`
- The `pages/` directory is a very important and required directory for Nuxt. This is where all your pages for the site live and routes for each page are built automatically based on filename.
- Blog posts are built from a template that can be accessed at `pages/blog/_slug.vue`. The markdown is parsed by [frontmatter-markdown-loader](https://www.npmjs.com/package/frontmatter-markdown-loader). This is a [dynamic template](https://nuxtjs.org/guide/routing#dynamic-routes) that gets passed a slug value as a parameter through the route. 
- The pages & blog template are comprised of components from the `components/...` directory.

## Using Forestry as your CMS

The `.forestry` directory contains all the settings information and frontmatter configuration to allow Forestry to setup the sidebar structure and editing capacity for this blog. After importing this blog into forestry, you can [access and edit](https://forestry.io/docs/editing/) all of the content via the sidebar. 

You can add new blog posts, [data files](https://forestry.io/docs/editing/data-files/), or entire pages and sections to fit your needs. You can also [customize how media](https://forestry.io/docs/media/) is handled, by configurating gitLFS, Cloudinary, S3, or Netlify Large Media.

You can set up a [remote admin](https://forestry.io/docs/editing/remote-admin/) for content editors to log in directly to yoururl.com/admin to make content updates.

### Instant Previews

The [instant preview](https://forestry.io/docs/previews/instant-previews/) method spins up the Nuxt development server for a long-lived preview that can quickly respond to content updates. When using instant previews, your preview command should be the develop command. The development server spawned by this command should be available over port 8080, and bind to 0.0.0.0. The forestry:preview command in this project's package.json will launch a dev server compatible with Forestry's instant previews.

## Deploy Options

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/kendallstrautman/brevifolia-nuxt-forestry)

[Netlify](https://www.netlify.com/blog/2016/09/29/a-step-by-step-guide-deploying-on-netlify/) is a great way to easily deploy sites. There's no special setup you need to do with Forestry to deploy with Netlify. When Forestry makes commits to your repo, Netlify will auto-trigger a rebuild / deploy when new commits are made.
