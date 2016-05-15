# thumby
A simple pure node.js service and server to create, store and serve thumbnail images.


### what does it do?
```
- effectively scales images instead of resizing using width to work out the thumb scales. (so if you have a really tall image it will still use width to generate thumbs, but this should still work well in order to get fixed size thumbs)
- config driven thumb sizes (support lrg, med and sml sizes)
- choose to keep original image or delete it (via config)
- resized images can then be accessed publicly
```

### get started
install it and use it like below

### installation
- clone repo into your server machine
- run `npm install`
- open `src/config.js` and enter your preferred settings
- run `npm run build` to generate the build
- run `npm start` to launch the api server

### api usage
- POST your multipart files to `[http://server-root/thumbs/create]`
- resonse will indicate if its a success. e.g response is `{"ok": 1, "filename": "1462510283123_cool_cat.jpg"}`.
- `ok 1` means its a success and `0` means its a fail
- if its a fail then `error` details are given
- if its a success, then saved image name is given in `filename`

### image server usage
- the uploaded and scaled images and thumbs can be now accessed via the built in image server
- originals from : `[http://server-root/imgs/originals/1462510283123_cool_cat.jpg]`
- large thumbs from : `[http://server-root/imgs/thumbs/lrg/1462510283123_cool_cat.jpg]`
- medium thumbs from : `[http://server-root/imgs/thumbs/med/1462510283123_cool_cat.jpg]`
- sml thumbs from : `[http://server-root/imgs/thumbs/sml/1462510283123_cool_cat.jpg]`

### dev
- update the project to add your own stuff if you want
- `npm run watch` to launch live update dev server (runs tests and lints on each update)

### todo
- add server caching to image server
- add http header caching to image served
- write the dame tests
- add config driven cache headers for serving the images
- provide routes to clean up thumbs (delete)

#### change log
- 1.0.0
  - formalise the first version
- 0.0.3
  - initial working version
