# SingleFile (Command Line Interface)

## Introduction

SingleFile can be launched from the command line by running it into a (headless) browser. It runs through Node.js as a standalone script injected into the web page instead of being embedded into a WebExtension. To connect to the browser, it can use [Puppeteer](https://github.com/GoogleChrome/puppeteer) or [Selenium WebDriver](https://www.npmjs.com/package/selenium-webdriver). Alternatively, it can also emulate a browser with JavaScript disabled by using [jsdom](https://github.com/jsdom/jsdom).

## Install

- Make sure Chrome or Firefox is installed and the executable can be found through the `PATH` environment variable. Otherwise you will need to set the `--browser-executable-path` option to help SingleFile locating it. As an alternative to Chrome and Firefox, you can use jsdom by setting the `--back-end` option to `jsdom`.

- Install [Node.js](https://nodejs.org)

- Unzip the [master archive](https://github.com/gildas-lormeau/SingleFile/archive/master.zip) somewhere on your disk in an empty folder and go into the `SingleFile-master/cli` directory.

  `unzip master.zip .`
  
  `cd SingleFile-master`
  
  `cd cli`
  
- As an alternative to decompressing the master archive, you can clone the repository if `git` is installed on your machine and go into the `SingleFile/cli` directory.

  `git clone https://github.com/gildas-lormeau/SingleFile.git`
  
  `cd SingleFile`
  
  `cd cli`

- Install dependencies with npm (installed with Node.js).

  `npm install`
  
- Make `single-file` executable (Linux/Unix/BSD etc.).

  `chmod +x single-file`

- To use Firefox instead of Chrome, you must download the [Selenium WebDriver](https://www.npmjs.com/package/selenium-webdriver) component (i.e. `geckodriver` for Firefox).  Make sure it can be found through the `PATH` environment variable or the `cli` folder. Otherwise you will need to set the `--web-driver-executable-path` option to help WebDriver locating the executable.

## Run

- Syntax
 
  `single-file <url> [output] [options ...]`

- Display help

  `single-file --help`

- Examples

  - Dump the processed content of https://www.wikipedia.org into the console

  `single-file https://www.wikipedia.org`

  - Save https://www.wikipedia.org into `wikipedia.html`

  `single-file https://www.wikipedia.org wikipedia.html`

  - Save https://www.wikipedia.org into `wikipedia.html` with Firefox instead of Chrome

  `single-file https://www.wikipedia.org wikipedia.html --back-end=webdriver-gecko`
  
## Docker

- Build

  `docker build -t singlefile .`
  
- Run

  `docker run singlefile "https://www.wikipedia.org"`
  
- Run and pipe the result into a file

  `docker run singlefile "https://www.wikipedia.org" > wikipedia.html`

## License

SingleFile is licensed under AGPL. Code derived from third-party projects is licensed under MIT. Please contact me at gildas.lormeau &lt;at&gt; gmail.com if you are interested in licensing the SingleFile code for a commercial service or product.
