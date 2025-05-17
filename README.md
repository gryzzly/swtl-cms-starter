# STWL CMS Starter

To start using SWTL CMS, the simplest is to use the swtl-cms-starter template. 

Create a new repository using this template – https://github.com/new?template_name=swtl-cms-starter&template_owner=gryzzly 

Go to [Netlify](https://www.netlify.com/) and create a new site. After signing up/in, the easiest way to do that is to “browse-to-upload” a folder with empty index.html in it. You can run the following 

```
mkdir new-netlify-site  && touch new-netlify-site/index.html
```

and then select the created folder at https://app.netlify.com/drop 

After the new project is created on Netlify, you’ll need to set two values as "Repository secrets" in Github repo settings (so that we can deploy to Netlify). Go to /settings/secrets/actions in your repo and under “new repository secret” set:  

- `NETLIFY_AUTH_TOKEN` – the token is specific to the user, and you can create a new one in https://app.netlify.com/user/applications#oauth under “Personal access tokens”
- ` NETLIFY_SITE_ID` – you can find it in “project configuration” in your newly crated Netlify site under “Project ID” in Project Information.

You can inspect how these secrets are used in `.github/workflows/build.yml` in your new repository. 

Nice, we are ready to deploy the site – let’s re-run initial commit’s build action to see if this has worked. Go to your repo’s Actions, select “Initial commit” and select “Re-run all jobs” and confirm. After build is complete, we can try visiting the website (You can find the URL in the new Project overview on Netlify. 

If the deployment was successful, we should have a “Hello world” rendered in the browser when visiting our new site. 

Navigating to /admin should present an “authorise” button that will sign you in to the admin UI. 

Congrats, you can create and edit pages. You can use `build.mjs` as a starting point – import the content JSON and use it for building your website. 

You can configure the CMS (create new data models with custom fields) in `swtl-sms-config.json` file. To learn more about the configuration and custom fields, head to [stwl-cms](https://github.com/gryzzly/swtl-cms). 


