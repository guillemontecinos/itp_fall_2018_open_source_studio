# Starting new translations and collaborating with existing p5.js website translations
*Some topics of this documentation were taken from the README.md file of this repo.*


## File Structure
* __See note about what to include in pull requests [here](https://github.com/processing/p5.js-website/wiki/Pull-requests).__
* `src/` – All the pieces for generating the built site. __Edits should be made here.__
  * `assets/` – All static files (imgs, css, fonts, js, p5_featured homepage sketches)
    * Note: if you make edits here you must restart the server to see your changes. To see changes immediately, you can edit the assets files in the dist directory, but need to copy and paste your updated work here for it to be saved.
  * `data/` – translation files
  * `templates/`
    * `layouts/` – default.hbs is main page template
    * `pages/` – Contains each of the pages of the p5 site, these get inserted in `{{> body }}` tag of default layout.
    * `partials/` – These are reusable pieces that can get added to any page or layout, they correspond to other `{{> filename }}` tags in the pages or default layout.
* `dist/` – Where the rendered files are stored, this can be placed directly online.
* `Gruntfile.js` – This file contains all the tasks for using assemble and YAML to generate the final, static site. It uses the taskrunner [grunt](http://gruntjs.com/).


## Building Process
Each time you make changes in any file of the website it's needed to build it again. For that, follow the next directions:

0. Install [node.js](https://nodejs.org/en/download/).
1. Download this zip file or [clone this repository](https://help.github.com/articles/cloning-a-repository/) and navigate to the directory in the terminal.
2. In the repo directory type `npm install` for installing all the dependencies.
3. Type `npm run watch` to run.
4. This should open a window in your browser with the site running at http://localhost:9000.

## Working on existing translations

### Translation of all pages except Reference and Examples
### Translation of Reference
### Translation of Examples

## Start a new translation
