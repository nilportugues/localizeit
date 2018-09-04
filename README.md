# LocalizeIt

> [ex-Translectra] Open-source Translation Management System in NodeJS.

[![The MIT License](https://img.shields.io/badge/license-MIT-orange.svg?style=flat-square)](http://opensource.org/licenses/MIT)
[![Travis](https://img.shields.io/travis/ivangabriele/localizeit.svg?style=flat-square)](https://travis-ci.org/ivangabriele/localizeit)
[![David](https://img.shields.io/david/ivangabriele/localizeit.svg?style=flat-square)](https://david-dm.org/ivangabriele/localizeit)
[![David](https://img.shields.io/david/dev/ivangabriele/localizeit.svg?style=flat-square)](https://david-dm.org/ivangabriele/localizeit)

[![NSP Status](https://nodesecurity.io/orgs/ivan-gabriele/projects/5b1b111f-60f8-4fe2-859e-7c5792b1eabd/badge)](https://nodesecurity.io/orgs/ivan-gabriele/projects/5b1b111f-60f8-4fe2-859e-7c5792b1eabd)

## Introduction

This TMS is highly inspired from [Attlassian Translations](https://translations.atlassian.com/) which is unfortunately not open-sourced. We all know how translations management can be laborious and we tried to create a tool that can fit multiple kind of projects: software development, documentation, marketing, etc.

We have started implementing a full versionning system (for both translation keys and projects).

## Features

- Ready to deploy: can be automatically integrated with a CI host (Heroku, AWS, Azure, etc)
- Cross-projects translation keys
- Multiple submissions management for each key (per language)
- Voting and approval system for submitted translations
- Keys versionning
- Markdown support

## Roadmap

- Projects versionning (in progress)
- Default language setting
- XLIFF and Gettext PO exports
- JSON, XLIFF and Gettext PO imports
- Comment translation submissions
- Edit translation submissions
- User dashboard

## Demo

https://localizeit.herokuapp.com

## Deploy

LocalizeIt is quite easy to deploy and just require environment variables and a Google developer account to be set in order to work There is no need to touch the code at all if you use modern CI environments like Heroku.

### Setup Google signup/login

Since LocalizeIt is dedicated to crowdsourced translations, we found that the most universal and easiest way to manage the authentication process was only support the signup/login via Google accounts, at least for the current major version.

You thus need to setup a [Google Developer account](https://console.developers.google.com) if you don't already have one.

Once it's done, you'll need to setup your credentials, with `https://www.example.com/auth/callback` as authorized redirect URIs. You can add `https://localhost/auth/callback` if you want to run it locally.

You will also need to enable the **Google+ API**.

### Mandatory environment variables

- **GOOGLE_API_KEY**: your Google API credentials `client_id`.
- **GOOGLE_API_SECRET**: your Google API credentials `client_secret`.
- **MONGODB_URL**: your full MongoDB url.
- **SESSION_SECRET**: a randomly generated, long and complex passphrase.
- **WEBSITE_NAME**: your translation website name.
- **WEBSITE_URL**: your translation website url _(**without** slash at the end)_.

### Heroku

1. Create your heroku app in the dashboard or via the Heroku Toolbelt.
2. Add a MongoDB add-on, **mLab MongoDB** for example.
3. Set up the [mandatory environment variables](#mandatory-environment-variables) in your app settings.
4. Clone the project locally:<br>
   `git clone https://github.com/ivangabriele/localizeit.git`
5. Enter the directory:<br>
   `cd localizeit`
6. Link your Heroku app:<br>
  `heroku git:remote -a localizeit` _(Replace "localizeit" by the name of your Heroku app)_
7. Push the project to Heroku:<br>
   `git push heroku master`

That's it ! It should automatically build and deploy now ;)

## Contribute

### Getting Started

    git clone https://github.com/ivangabriele/localizeit.git
    cd localizeit
    npm i

### Start developing

Once you're all set up, you can start coding:

    npm run start:dev

will automatically start a "live" watch compiling the backend & frontend JS code (in `build` folder) on file changes.
