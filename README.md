# Quality Assurance with Chai

A project from [freeCodeCamp](https://www.freecodecamp.org/)'s curriculum, forked from their [boilerplate repository](https://github.com/freeCodeCamp/boilerplate-mochachai/) and tweaked for local development.

## Overview

As part of completing the freeCodeCamp [Quality Assurance with Chai](https://www.freecodecamp.org/learn/quality-assurance/quality-assurance-and-testing-with-chai) certification a number of self-study projects need to be completed, and this is the repo/app that is supplied to pass the accreditation.

The curriculum is undergoing a major update so these projects are likely to change, but at the time of writing (August 2020) the information herein is correct.

## Local Development

Although I managed to get all the tests passing locally, I couldn't get the server to run/respond properly on REPL.it after updating packages and deploying it there. The boilerplate version provided by freeCodeCamp _did_ run OK, so I just copied the test files there to pass the accreditation. The actual solutions are identical in this repo, I just couldn't solve the deployment issue.

## `.env`

If you're interested in cloning this repository, you'll need to set a few things in your `.env` file, both in your local environment and the target. In order to have my `.env` file read locally at run-time, rather than having to set them _literally_, I use the following command in my `dev` script in `package.json` and then run `npm run dev` during local development:

~~~sh
export $(cat .env | xargs) && nodemon server.js
~~~

## Git to REPL Deployment

I have deployed the final app to [REPL.it](https://repl.it/) because the freeCodeCamp tests need something to run against and provide a pass/fail result. I borrowed and incorporated the design of a [Github-usable webhook](https://github.com/nmcardoso/glitch-github-sync/) that'll run various Git commands on the target server and update it every time I push to Github. That's obviously not necessary for local development or deployment on other infrastructure, but it's handy for Glitch and other REPLs.

The webhook is located at `/git`.
