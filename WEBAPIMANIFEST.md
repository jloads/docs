## Web App Manifest
https://hackernoon.com/a-beginners-guide-to-progressive-web-apps-the-frontend-web-424b6d697e35

Before we can really say we’ve built a web application (let alone a progressive web app), we need to deal with the manifest.json file, which consists of our application’s name, short_name, icons and a bunch of other properties, providing information about our web application to the client’s browser. Before we get to mess with it, however, we need to get our web application up and running on localhost with the help of npm and React’s tips.

I’m assuming you’re somewhat familiar with the former and that the latter will not give you any trouble, so I will be moving forward with setting up a manifest for our web application. In my experience, you only need to fill in so many fields to create a working web application, so I suggest you head over to the Web App Manifest Generator and fill in the info you want. If you have the time to polish everything up with an icon, you can utilize the Favicon & App Icon Generator to make sure you web application has a nice icon to go with it.

After it’s all said and done, your manifest should look similar to this:
A sample web application manifest

By creating a manifest, we are polishing up our web application and making it behave more like it should. This is only the beginning, though, on or web application’s way to become a progressive web app.

Web Application Manifests are well documented on both MDN and Google Developers. Remember that you can also use the Web App Manifest Generator, if you want to easily and quickly generate a manifest.json for you web application.

https://tomitm.github.io/appmanifest/

https://developer.mozilla.org/en-US/docs/Web/Manifest

https://developers.google.com/web/fundamentals/web-app-manifest/


    {
      "name": "Mockup Progressive Web App",
      "short_name": "Mock PWA",
      "description": "A mock progressive web app built with React and mini.css.",
      "lang": "en-US",
      "start_url": "./index.html",
      "display": "standalone",
      "theme_color": "#1a237e",
      "icons": [
        {
          "src": "\/android-icon-48x48.png",
          "sizes": "48x48",
          "type": "image\/png",
          "density": "1.0"
        },
        {
          "src": "\/android-icon-72x72.png",
          "sizes": "72x72",
          "type": "image\/png",
          "density": "1.5"
        }
      ]
    }
