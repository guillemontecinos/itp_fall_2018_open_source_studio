# Final Project Documentation
This is the documentation of the project [**Tracking of p5.js Spanish website translation and development of a translation guide (for any language)**](https://github.com/guillemontecinos/itp_fall_2018_open_source_studio/blob/master/final_project/proposal.md), developed for the class [**Open Source Studio**](https://github.com/Open-Source-Studio-at-ITP/) @ NYU ITP, Fall 2018.

## Week 1
### Week 1 Goals
* Track, translation and correction of Spanish p5.js website
* Track, translation and correction of Spanish p5.js reference (1/2)

### Advances
#### [Forking p5.js website repo](https://github.com/guillemontecinos/p5.js-website) to my GitHub account
The [original repo](https://github.com/processing/p5.js-website) was forked to my account and cloned into my local.

#### Translation Check
Translation check by page and handlers. Not mentioned handlers con be considered as ok.
##### Inicio: *p5js.org/es/*
* p1x2: modified
##### Descargar *p5js.org/es/download*
* editor-includes: translation is ok @ [es.yml](https://github.com/processing/p5.js-website/src/data/es.yml) but is not being shown in rendering process. Submitted in the following [Issue](https://github.com/processing/p5.js-website/issues/287)
##### Empezar *p5js.org/es/get-started/*
* download4: the word *miniaturizada* was changed for *reducida* due to the first one is not as common for this purpose.
* envirnoment9: modified
* envirnoment11: modified
* your-first-sketch2: modified
* **[Using p5 with a screen reader](https://p5js.org/es/learn/p5-screen-reader.html) page is not translated yet.**
* your-first-sketch9: modified
* your-first-sketch10: modified
* your-first-sketch12: modified

#### [Commit November 12th, 2018](https://github.com/guillemontecinos/p5.js-website/commit/c01572279342265c4f03fcfd9894f710fb86672f)
The above [Translations Check](https://github.com/guillemontecinos/itp_fall_2018_open_source_studio/blob/master/final_project/documentation.md#translation-check) were committed to my repo's fork and pulled to the Processing repo by the [Pull Request](https://github.com/processing/p5.js-website/pull/288).

##### Bibliotecas *https://p5js.org/es/libraries/*

* **[Link to p5.dom library](https://p5js.org/es/reference/#/libraries/p5.dom) is not translated yet.**
* **[Link to p5.sound library](https://p5js.org/es/reference/#/libraries/p5.sound) is not translated yet.**
* **[Link to p5.accessibility](https://github.com/processing/p5.accessibility) goes to a github .md file in English.**
* Note: Contributed libraries links were not reviewed.
* using-a-library1: modified
* using-a-library2: modified
* create-your-own1: modified

##### Aprender *https://p5js.org/es/learn/*
* learn1: modified
* **[Link to p5.js overview](https://github.com/processing/p5.js/wiki/p5.js-overview) goes to p5.js wiki @ Github. Not translated yet.**
* **[Link to Processing transition](https://github.com/processing/p5.js/wiki/Processing-transition) goes to p5.js wiki @ Github. Not translated yet.**
* **[Link to Local Server](https://github.com/processing/p5.js/wiki/Local-server) goes to p5.js wiki @ Github. Not translated yet.**
* **[Link to Using p5 with a screen reader](https://p5js.org/es/learn/p5-screen-reader.html) page is not translated yet.**
* **[Link to node.js and socket.io](https://github.com/processing/p5.js/wiki/p5.js,-node.js,-socket.io) goes to p5.js wiki @ Github. Not translated yet.**
* **[Link to Beyond the canvas](https://github.com/processing/p5.js/wiki/Beyond-the-canvas) goes to p5.js wiki @ Github. Not translated yet.**
* **[Link to Getting started with WebGL in p5](https://github.com/processing/p5.js/wiki/Getting-started-with-WebGL-in-p5) goes to p5.js wiki @ Github. Not translated yet.**

###### Color *https://p5js.org/es/learn/color.html*
Sub-page Color was modified.
* On [src/templates/pages/learn/color.hbs](https://github.com/guillemontecinos/p5.js-website/blob/master/src/templates/pages/learn/color.hbs) title and slug were modified from *learn* to *color*.
* On [es.yml](https://github.com/guillemontecinos/p5.js-website/src/data/es.yml) and [en.yml](https://github.com/guillemontecinos/p5.js-website/src/data/en.yml) a class for color and handlers were added at line 430.
* TODO: I'm changing color.hbs text to handlers. First I create them in the en.yml and then I copy them to es.yml and then translate. I'm at color-p2x4.

## Week 2
### Week 2 Goals
* Track, translation and correction of Spanish p5.js reference (2/2)
### Advances - Translation
###### Color *https://p5js.org/es/learn/color.html*
* Handlers in color.hbs were created and moved to the files en.yml, es.yml and zh-Hans.yml.
* Every handler at the es.yml were translated to Spanish.
###### Coordinate System and Shapes *https://p5js.org/es/learn/coordinate-system-and-shapes.html*
* Handlers in coordinate-system-and-shapes.hbs were created and moved to the files en.yml, es.yml and zh-Hans.yml.
* Every handler at the es.yml were translated to Spanish.

#### [Commit November 20th, 2018](https://github.com/guillemontecinos/p5.js-website/commit/3272d0c4de19af18339f0397989ed9cf22d9f135)
The above was committed to the source branch through the following [PR](https://github.com/processing/p5.js-website/pull/293).

## Week 3
### Week 3 Goals
* Track, translation and correction of Spanish p5.js examples (1/2)
### Advances - Fixing problems
Due to the PR [#293](https://github.com/processing/p5.js-website/pull/293) a bunch of problems were introduced to the website, because after that it couldn't be [compiled](https://github.com/processing/p5.js-website/commit/733e64f50cd196c2c41903617a1392faaf5f78bc#r31435805) again.

The errors introduced had two origins:

#### 1. YAML files can break compilation
The `.yml` files can break the page compilation process under syntax issues as double quotes within the text. Each YAML handler must be written as `color-rgb-title: "Color RGB"`, which means that the handler `color-rgb-title` has assigned the content `"Color RGB"` in the current language `.yml` file.

In some cases, the text translated from the original `.hbs` file (written in HTML) included double quotes used for highlight some idea. In those cases I didn't use the scape command `\` before the quotes, which was interpreted by the compiler as there was a syntax error due the handler finished more the one time.

#### 2. Handlers managing and new slugs creation at hbs files
The structure of `.hbs` files contains at the head a slot for declaring the folder where the page will be placed when compiled.

```
---
title: learn
slug: learn/
---
```

For nested pages -for example `p5js.org/es/learn/color.html`- the slug of the `.hbs` document must match the upper folder, in this case `learn`. This is directly related with the way handlers are displayed in the `.yml` file. For example, all the handlers for the `learn` page are written under its slug with a tab as follows:

```
learn:
  learn-title: "Aprender"
  learn1: "Estos tutoriales proveen una revisión en mayor profundidad o paso a paso sobre temas particulares. Revisa la "
```

For the case of nested pages it's important to not create a new slug for each page, because it can make the `.hbs` files not to find the handlers when calling the `i18n` data. So for the page color **it is not needed to create a new** `slug: color/` like:

```
color:
  color-title: "Color"
```

Instead of this, the color-related handler must be added to the `learn` list of handlers, as done in the PR [#297](https://github.com/processing/p5.js-website/pull/297).

### Results
* After the above the page can be created successfully.
* Creation of [translating.md](https://github.com/guillemontecinos/itp_fall_2018_open_source_studio/blob/master/final_project/translating.md).

## Week 4
### Week 4 Goals
* Track, translation and correction of Spanish p5.js examples (2/2)
* Write TRANSLATION.md (1/2)

### Advances

#### Mentoring Meeting
A meeting was held with @montoyamoraga in which the work carried out thus far was discussed. The main conclusion was to make the documentation file an accessible and well explained resource, that could be followed even for people with low experience using GitHub. That meeting notes and summary were documented in this [issue](https://github.com/guillemontecinos/itp_fall_2018_open_source_studio/issues/4), but the main points are as follow:

- change title to contributing or i18n or related
- add instructions for when you make a mistake, start over again, as in, delete your fork, fork again, etc.
- add screenshots
- add https://help.github.com/articles/syncing-a-fork/ instructions of setting up your fetch upstream.
be very explicit on making new pull requests only include src/ files, nothing else.
- be very explicit on making the difference between setup that only happens once on your machine or fork, and things that happen all the time
- Some structure:
1. Intro: how the website works
2. section 0: setup that only happens once
3. section 1: everytime you do a pull request you do X
- remind that issues are welcome, and that pull request is a lot to ask maybe
- be encouraging and use "you", second person, paraphrase from p5.js community statement
- explain how i18n works for pages in general and for reference
- talk about i18n handlers and placeholders

Most of the changes proposed during the meeting were included in the final version of this project.

#### User test
A user testing session was carried out during the last meeting of the class. In that opportunity the documentation file was followed and reviewed by @nicolaspe and @camilleweins, according to the directions opened in this [issue](https://github.com/guillemontecinos/itp_fall_2018_open_source_studio/issues/5):

Thanks for your collaboration! 😄

**Directions**
1. Follow this [tutorial](https://github.com/guillemontecinos/itp_fall_2018_open_source_studio/blob/master/final_project/i18n_contribution.md) to set up the repo. Fork [my fork](https://github.com/guillemontecinos/p5.js-website) of the base repo.
2. go to `src/data/es.yml` and make the following modifications (further information [here](https://github.com/guillemontecinos/itp_fall_2018_open_source_studio/blob/master/final_project/i18n_contribution.md#translation-of-all-pages-except-reference-and-examples)):
* Change the content of the `interactivity-title` from "Interactivity" to "Interacción"
* Change the content of the `interactivity`handler from "Introduction to interactivity with the mouse and keyboard." to "Introducción a la interacción usando el ratón y el teclado."
3. Commit your changes to your repo
4. Submit a Pull Request to my fork.

**Evaluation**
If you detect any need of improvement or advice please open an Issue under this repo.

## Week 5
### Week 5 Goals
* Write TRANSLATION.md (2/2)
* Final documentation

### Advances
