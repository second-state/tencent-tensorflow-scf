[中文](README.md) | [Screencast](https://youtu.be/Thoi7XrIKvE) | [Live demo!](https://sls-website-ap-beijing-7jlzqqj-1302315972.cos-website.ap-beijing.myqcloud.com/) | [Coding tutorial](https://www.secondstate.io/articles/tencent-tensorflow/)

# Quick start

Clone this repo. From the repo's root directory, you can pull our pre-configured dev Docker image and log into it.

```
$ git clone https://github.com/second-state/tencent-tensorflow-scf
$ cd tencent-tensorflow-scf

$ docker pull secondstate/tencent-tensorflow-scf
$ docker run --rm -it -v $(pwd):/app secondstate/tencent-tensorflow-scf
(docker) $
```

> You do not have to use our Docker image. To build on your own computer or container, make sure that you have installed the [Serverless Framework](https://www.serverless.com/framework/docs/providers/tencent/guide/installation/), [Rust](https://www.rust-lang.org/tools/install), and [ssvmup](https://www.secondstate.io/articles/ssvmup/).

Run the following command inside the Docker container to build and deploy the entire application.

```
(docker) $ cd /app
(docker) $ sls deploy
... ...
  website:       https://sls-website-ap-hongkong-kfdilz-1302315972.cos-website.ap-hongkong.myqcloud.com
  vendorMessage: null

63s › tencent-tensorflow-scf › "deploy" ran for 3 apps successfully.
```

Load the website URL in any web browser and start to use this function to identify objects in photos.

> GitHub could be very slow behind the Great Chinese Firewall. Clone from Gitee if you are in mainland China. `git clone https://gitee.com/secondstate/tencent-tensorflow-scf.git`

# Build your own Tensorflow cloud function

Fork this repo and use the `Code | Open with Codespaces` button to launch Github Codespaces IDE in your browser. It may take a few minutes to start the first time. 

## Low code development

Once the Codespaaces IDE starts, you can make simple changes to the source code to customize it for your own applications. [See a coding tutorial](https://www.secondstate.io/articles/tencent-tensorflow/)

* Make changes to the Tensorflow model and data pre-processing and post-processing logic in `src/lib.rs` file. 
* Make changes to the front end UI in the `website/content/index.html` file.

## Build

Open a `Terminal` windon in the Codespaces IDE, and run the following command to build your cloud function.

```
$ rustwasmc build --enable-aot
```

## Deploy

In the `Terminal` window, run the following commands to deploy the Tensorflow cloud function to the Tencent Cloud.

```
$ cp pkg/scf.so scf/

$ sls deploy
... ...
  website:       https://sls-website-ap-hongkong-kfdilz-1302315972.cos-website.ap-hongkong.myqcloud.com
```

Load the deployed URL in any web browser and have fun!

# Develop on your own computer

If you cannot or do not wish to use Github Codespaces, you can install the ssvmup and serverless framework toolchains on your own computer (or Docker image) to build and deploy Tensorflow serverless functions.

[Install the ssvmup tool](https://www.secondstate.io/articles/ssvmup/)

Install the Serverless Framework via the NPM.

```
$ npm install -g serverless
```

That's it. You can now follow the Codespaces' build and deploy instructions above.

