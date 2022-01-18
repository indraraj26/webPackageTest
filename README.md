# Third party package installation

`npm i javascript-time-ago`

##  Steps to configure
 1. Go to path-mapping.json and add 
   ```
  "javascript-time-ago": {
      "cwd": "node_modules/javascript-time-ago",
      "debug": {
        "src":  ["**"],
        "path": "libs/javascript-time-ago/bundle/javascript-time-ago.js"
      },
      "release": {
        "src":  ["**"],
        "path": "libs/javascript-time-ago/bundle/javascript-time-ago.min.js"
      }
    },
 
   ```
2. Go to main.js and add
  ```
        "customTimeAgo": "libs/javascript-time-ago/bundle/javascript-time-ago.js",
        "timeAgoEn": "libs/javascript-time-ago/locale/en.json",
  ```
3. in dashboard viewModels
  ```
   "customTimeAgo", "timeAgoEn"
  ```
```
 this.connected = () => {
        customTimeAgo.TimeAgo.addDefaultLocale(timeAgoEn)

        // Create formatter (English).
        const timeAgo = new customTimeAgo.TimeAgo('en-US')
        
        timeAgo.format(new Date())
        
        // Implement further logic if needed
      };
```


# Issue
If you go to web folder after the ojet serve then you will find that it is creating one more directory

libs/javascript-time-ago/bundle/bundle/javascript-time-ago.js
I am trying to copy all the javascript-time-ago source to our libs as i have to load locale before trying to use timeAgo constructor.

## Package Path
https://www.npmjs.com/package/javascript-time-ago