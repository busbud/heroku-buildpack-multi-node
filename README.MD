# Heroku Multi Node buildpack

If you want to go the google route and have a mono repo for all your Node.js apps, but want to deploy to heroku, it will not work as the Node.js buildpack expects package.json to live in the root folder. Enter the multi node buildpack! It allows you to run a specific app in a repository of multiple apps!

It:

1. Looks at `APP_SUBFOLDER` in your env.
1. Copies `root/${APP_SUBFOLDER}/Procfile` to `root/Procfile`
1. Copies `root/${APP_SUBFOLDER}/package.json` to `root/package.json`
1. If present, copies `root/${APP_SUBFOLDER}/yarn.lock` to `root/yarn.lock`

And that's it! Super simple!
