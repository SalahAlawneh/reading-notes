# Heroku Deployment
10 10 unread replies. 10 10 replies.

- in order to work with heroku, should installing npm, git, node.js version more than 10
- `heroku ps` => `to check how many dynos are running`
- `npm install`=> `to make it work locally`
- `heroku local web`=> `to run the app locally`
- `Procfile`=> `it's file exist in my local file|text inside it:web: npm start|Procfile will be examine if the app running from the web or locally`
- `npm install`=> `it will used when any change done to to the app before run it`
- to diploy the change the same steps in github was done, we will done here:
  - git add .
  - git commit -m "Add cool face API"
  - git push heroku main
- `heroku addons:create papertrail` add third party cloud services.
- `heroku run bash` => `will make the bash of deno.`