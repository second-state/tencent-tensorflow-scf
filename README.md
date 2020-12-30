
## Prerequisite

[Install the ssvmup tool](https://www.secondstate.io/articles/ssvmup/)

Install the Serverless Framework via the NPM.

```
$ npm install -g serverless
```

## Build

```
$ ssvmup build --enable-aot
```

## Deploy

```
$ cp pkg/scf.so scf/
$ sls deploy
```

Load the deployed URL in your browser and have fun! Exmample: https://sls-website-ap-hongkong-wlzo13p-1302315972.cos-website.ap-hongkong.myqcloud.com/

## Developers

Make changes to the Tensorflow model and data pre-processing and post-processing logic in `src/lib.rs` file.

Make changes to the front end UI in the `website/content/index.html` file.



