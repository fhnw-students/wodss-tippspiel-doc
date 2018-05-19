# WODSS Tippspiel

**Workshop project of David Heimgarnter, Gerhard Hirschfeld &amp; Ken Iseli**

---

## Table of Content

- [Contributors](#-contributors)
- [Project Structure](#-project-structure)
- [Database schema](#-database-schema)
- [API](#-api-documentation)
- [UI Wireframes](#-ui-wireframes)

---

## Contributors

In this section are the contributors listed with their developed components.

| Contributor        | Frontend | Backend |
| ------------------ | -------- | ------- |
| [Ken Iseli](https://github.com/orgs/fhnw-students/people/keniseli)          | Rankings | Authentication, Ranking, Translations, Setup |
| [David Heimgartner](https://github.com/orgs/fhnw-students/people/davidheimgartner) | Password-Reset, Profile, Teams | Teams |
| [Gerhard Hirschfeld](https://github.com/orgs/fhnw-students/people/hirsch88) | Login, Registration, Admin, Games, Setup | Admin, Games, Setup |

---

## Project Structure

To manage our project we create a project on GitHub.

[Go to the project board](https://github.com/orgs/fhnw-students/projects/1)

We divided our project into 3 repositories:

- [Documentation](https://github.com/fhnw-students/wodss-tippspiel-doc)
- [Java Spring / REST API](https://github.com/fhnw-students/wodss-tippspiel-api)
- [Vue.JS Frontend Application](https://github.com/fhnw-students/wodss-tippspiel-web)

Every repository is setup with a `README.md` file, which explains how to setup and run the application. Moreover, we used `Travis` as our CI for our frontend and backend project to build and test it. After `Travis` builded the application successfully `heroku` deploys the application in the cloud. Due to the free solution (if the apps are unused they go in a sleep mode) of `heroku` accessing the application could take a while.

- [Deployed frontend application](https://wodss-tippspiel-web.herokuapp.com/)
- [Deployed backend application](https://wodss-tippspiel-api.herokuapp.com/)

---

## Database schema

![ERM](./wodss-erm.png)

### Static data

Static data are the `location`, `nation` and the `game_phase` table. These table will not be changed by the application.

### User

TODO

### Team

TODO

### Games & Tips

The `game` table represents a soccer game like Spain vs Peru. Only an administrator is able to create, update and delete games.

A user can bet an a game and this will be stored in the `tip` table, but he can only alter the score fields and before the game has started. After the admin has enter the score of a game all tips will receive their points.

---

## API documentation

We defined our API with the help of the awesome tool called Swagger. Moreover,  we deployed it on `heroku` to have a live API documentation of our project.

[Go to the Swagger Documentation](https://wodss-tippspiel-swagger.herokuapp.com/)

### How to alter the API documentation

1. Open the [Swagger Editor](https://editor.swagger.io).
2. Copy the [Swagger File](https://raw.githubusercontent.com/fhnw-students/wodss-tippspiel-doc/master/swagger.yml) into the Swagger Editor.
3. Change it
4. Copy the new documentation back into repository
5. Commit your changes.

---

## UI Wireframes

We put the wireframes into a separate document.

[Go to the UI Wireframs](./UI_WIREFRAMES.md).

## Frontend

### Application Structure

The chosen JS-framework Vue.js does not force a specific structure. However, the ecosystem provides some useful tools and libraries to build large scale application.

```
├── public									# static files like index.html & favicon
├── src
│   ├── assets							# Fonts and images
│   ├── components
│		│   ├── Hello.vue				# Vue.JS components
│		│   └── ...
│   ├── config
│		│   └── app.config.ts		# configuration from the .env* files
│   ├── locals
│		│   ├── de.ts						# Translation files
│		│   └── ...
│   ├── models
│   ├── pages								# Page components
│   ├── plugins
│		│   └── **/*.plugin.ts	# Vue.JS plugins
│   ├── routes							# All defined application routes are here
│   ├── services
│		│   ├── api							# All service for making api requests
│		│   └── **/*.service.ts
│   ├── store								# Vuex store
│		│   ├── modules
│		│   └── index.ts
│   ├── styles							# Global styles written in SASS
│   ├── types								# Custom type definitions
│   ├── App.vue							# Main component
│   └── main.ts							# Bootstraps the app
├── .env.development				# App configuration for the development environment
├── .env.production
├── .travis.yml							# CI configuration
├── package.json
├── Procfile								# Defines the run command for heroku
├── README.md								# Documentation
├── server.js								# Small web-server for deploying on heroku
├── static.json							# Defines the root path for heroku
├── tsconfig.json						# TypeScript configuration
├── tslint.json							# TypeScript lint configuration
└── vue.config.js						# Extends the webpack config
```

### Libraries

TODO

### Routing

TODO

### Store Management

TODO

## Backend

TOOD