# Quick start

Make sure that you have the Serverless Framework installed. Clone this repo, and do the following.

```
$ sls deploy
... ...
  website:       https://sls-website-ap-hongkong-kfdilz-1302315972.cos-website.ap-hongkong.myqcloud.com
  vendorMessage: null

63s › tencent-tensorflow-scf › "deploy" ran for 3 apps successfully.
```

Load the website URL in any browser and start to use this function to identify objects in photos.

# Build your own Tensorflow function

## Prerequisite

[Install the ssvmup tool](https://www.secondstate.io/articles/ssvmup/)

Install the Serverless Framework via the NPM.

```
$ npm install -g serverless
```

## Low code

Make changes to the Tensorflow model and data pre-processing and post-processing logic in `src/lib.rs` file.

Make changes to the front end UI in the `website/content/index.html` file.


## Build

```
$ ssvmup build --enable-aot
```

## Deploy

```
$ cp pkg/scf.so scf/
$ sls deploy
... ...
  website:       https://sls-website-ap-hongkong-kfdilz-1302315972.cos-website.ap-hongkong.myqcloud.com
```

Load the deployed URL in your browser and have fun!




