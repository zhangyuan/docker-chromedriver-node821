# docker-chromedriver-node821

[![Build Status](https://travis-ci.org/zhangyuan/docker-chromedriver-node821.svg?branch=master)](https://travis-ci.org/zhangyuan/docker-chromedriver-node821)

Docker image for autumated testing with Chrome and NodeJS.

## Usage

### Docker Pull Command

```
docker pull zhangyuan/docker-chromedriver-node821
```

### NVM and NodeJS

NVM is not actived by default, load it by running the following command:

```shell
export NVM_DIR="$HOME/.nvm" && [ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh"
```

### Xvfb

In order to run tests with Chrome, use `xvfb-run` to run your own command. For example:

```
xvfb-run npm run test
```

### Chromedriver

If you are using `selenium-webdriver`, be sure to pass `--headless` and `--no-sandbox` to driver:

```es6
const webdriver = require('selenium-webdriver')
const chrome = require('selenium-webdriver/chrome')

const options = new chrome.Options()
options.addArguments(["--headless", "--window-size=1200,600", "--no-sandbox", "--disable-gpu"])
var driver = new webdriver.Builder()
    .forBrowser('chrome')
    .setChromeOptions(options)
    .build()

```
