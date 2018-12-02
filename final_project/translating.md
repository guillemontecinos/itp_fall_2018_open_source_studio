# Starting new translations and collaborating with existing p5.js website translations
If you want to contribute with p5.js website translations you are in the right place. Your collaboration can be correcting an already translated content -at the reference, examples or other pages within the website- as well as starting a new language translation. Some topics of this documentation were taken from the README.md file of this repo.


Before starting to contribute there are some important things you have to consider:

### 1. Where to work?
[Fork](https://help.github.com/articles/fork-a-repo/) and [clone](https://help.github.com/articles/cloning-a-repository/) the original repo, and work locally on your machine.

### 2. Check your changes
**Never** open a [Pull Request](https://help.github.com/articles/about-pull-requests/) without have checked before that your changes are correctly working. For that you have to build the website locally following the instructions below.

* What's the file Structure

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
The translation of the p5.js website to languages other than English is part of its internationalization -abbreviated [*i18n*](https://en.wikipedia.org/wiki/Internationalization_and_localization)- process. For that purpose, each website is written in [.hbs](https://www.npmjs.com/package/hbs) format -files created with Handlebars and written using HTML rules- using handlers to access the i18n data of each language and render. Hbs files are stored under `src/template/pages`.

 The i18n data is stored in [.yml](https://en.wikipedia.org/wiki/YAML) files in the `src/data` folder of this repo. For example, under the above mentioned path the .yml files for Ensglish, Spanish and Chinese can be found as follows:

```
en.yml
es.yml
zh-Hans.yml
```

Within the .hbs pages there are tags that replace the actual content and look like this: `{{#i18n "MyKeyword"}}{{/i18n}}`. For example the *Download* tag at the main bar looks like this:

```
<li><a href="{{root}}/download/">{{#i18n "Download"}}{{/i18n}}</a></li>
```

In this example "Download" corresponds to the key-value pair for the translation of that content to other languages. Each key-value can point to a word as well as a phrase. and there must be a key-value for each handler entry in every language, otherwise the website render process can be broken.

Each page contains YAML "front matter" at the top which includes a title and (optional) slug field. The title corresponds to the section in which to place the i18n key-value pairs. (Note: each page has only one title, so for partials within the `partials` folder, place the i18n pairs at the top level). The slug corresponds to the folder in which the page will be placed. This should generally match the folder structure within the `pages` folder.

For nested pages -for example `p5js.org/es/learn/color.html`- the slug of the .hbs document must match the upper folder, in this case `learn`. This is directly related with the way handlers are displayed in the .yml file. For example, all the handlers for the `learn` page are written under its slug with a tab as follows:

```
learn:
  learn-title: "Aprender"
  learn1: "Estos tutoriales proveen una revisión en mayor profundidad o paso a paso sobre temas particulares. Revisa la "
```

But for nested pages it's important not to create a new slug for each page, because it can make the .hbs files not to find the handlers when calling the i18n data. So, for the page color **it is not needed to create a new** `slug: color/` like:

```
color:
  color-title: "Color"
```

Instead of this, the color-related handler must be added to the `learn` list of handlers. For English version, the site will follow the same top-level hierarchy as the original site. When you switch to a different language, the permalink and file structure will include the language abbreviation immediately following the root url. (ex: `https://p5js.org/es/get-started/`)

**Yml files can break the page compilation** process under syntax issues as double quotes within the text. Each YAML handler must be written as `color-rgb-title: "Color RGB"`, which means that the handler `color-rgb-title` has assigned the content `"Color RGB"` in the current language .yml file.

In some cases, the text translated from the original .hbs file (written in HTML) included double quotes used for highlight some idea. In those cases remember to use the scape command `\` before the quotes, otherwise your compiler will interpret it as a syntax error due the handler finished more the one time.

### Translation of Reference
* The reference works a bit differently. The pages are built in English based on the inline documentation in the source code. They are then swapped out using [JS on the front-end](https://github.com/processing/p5.js-website/blob/master/dist/reference/index.html#L130).
* The top level keys in the JSON object correspond to the page headings, menu, footer, etc. You can see all the swaps in [this file](https://github.com/processing/p5.js-website/blob/master/dist/reference/index.html#L130).
* The "p5" key in the JSON object contains individual keys for each reference entry, indexed by variable/function/object name.
* Any entries in the JSON object which are not filled in will be left in English when the page is loaded.
* This is a somewhat hacky solution and not ideal. However, it comes from balancing the desire to have documentation directly in the source code, with the unwieldiness of having multiple languages of documentation inline. It will be our working solution until a better one is found.
* The source content for the reference is handled inline in the [p5.js source code](https://github.com/processing/p5.js). See [Inline documentation](https://github.com/processing/p5.js/blob/master/developer_docs/inline_documentation.md) in the p5.js repo for information on how to contribute.

### Translation of Examples
The examples are handled a bit differently from other pages.
* All examples pages are built from `src/data/examples`.
* Within the examples folder, there is a folder for each of the three languages we currently support: `en/`, `es/`, and `zh-Hans/`. When adding a new example, first add an English version of the file to the `en/` folder, then make sure it is duplicated in the same place in all other languages, then translate for whichever languages you can. If you have created a new folder, add entries to the YAML files with the foldername as the key.
* The folder, file, and numbering structure should match exactly between the different languages. Do not change the filenames. The text for the example name, description, and source code are all in the .js files in the folders.
* Assets for the examples are placed in `src/data/examples/assets`.
* Translations for the topic headers on the example index page are done in the YAML files (`src/data/*.yml`).

## Start a new translation
1. Duplicate `[en.yml]`(https://github.com/processing/p5.js-website/blob/master/src/data/en.yml) in `src/data` and name it `{languageabbreviation}.yml`. For example `es.yml`. See this page for [two-letter language abbreviations](https://www.abbreviations.com/acronyms/LANGUAGES2L).
2. Duplicate `[es.json]`(https://github.com/processing/p5.js-website/blob/master/src/data/reference/es.json) and name it `{languageabbreviation}.json`.
3. Add an entry with the language abbreviation [here](https://github.com/processing/p5.js-website/blob/master/Gruntfile.js#L90).
