# Deploy to Github Pages

You can deploy to github pages with a couple minor changes to Polymer Starter Kit:

1. Uncomment this line  `// app.baseUrl = '/polymer-starter-kit/';` in app.js `app.getUrl function:`
```
app.getUrl = function(suffix) {
  app.baseUrl = '/';
  if (window.location.port === '') {  // if production
    // Set app.baseURL to '/your-pathname/' if running from folder in production
    // app.baseUrl = '/polymer-starter-kit/';
  }
  console.log('getUrl: app.baseUrl ',app.baseUrl );
  return app.baseUrl.replace(/\/$/, '') + suffix;
};
```
2. Change `app.baseUrl = '/polymer-starter-kit/';` to `app.baseUrl = '/your-pathname/';`
3. Run `gulp build-deploy-gh-pages` from command line
4. To see changes wait 1-2 minutes then load Github pages for your app (ex: http://polymerelements.github.io/polymer-starter-kit)

### Notes

* When deploying to Github Pages we recommend using hashbangs which is Polymer Starter Kit default.
* This method should work for most hosting providers when using a subfolder.
