# Final Project Documentation Template (WIP)

All the documentation of this project can be found [here](https://github.com/guillemontecinos/itp_fall_2018_open_source_studio/blob/master/final_project/documentation.md).

## Project Title

**Tracking of p5.js Spanish website translation and development of a translation guide (for any language)**

*This project consist in a collaboration with the internationalization (i18n) of the p5.js website. It consisted in the translation of content to Spanish and the develop of a documentation document that will gather all the information needed for future collaborations on website translation, focused on first-time contributors and non-English speakers.*

## Team Members

* [Guillermo Montecinos](https://github.com/guillemontecinos)

## Deliverables / Work Product

* [Color page translation to Spanish](https://p5js.org/es/learn/color.html). Merged under [#297](https://github.com/processing/p5.js-website/pull/297).
* [Coordinate System page translation to Spanish](https://p5js.org/es/learn/coordinate-system-and-shapes.html). Merged under [#297](https://github.com/processing/p5.js-website/pull/297).
* [Contributing to p5.js website internationalization (i18n) documentation](https://github.com/guillemontecinos/itp_fall_2018_open_source_studio/blob/master/final_project/i18n_contribution.md)

## Define the problem you addressed and greater landscape

This project attempted to address the problem of creating and maintaining translations to new languages other than English of the p5.js website. As an open-source and community-led project p5.js doesn't count with the resources to maintain and incorporate multiple languages automatically or by contributors.

This project goals were: 1) to review existing Spanish translations of the website and translate pages that haven been translated yet, and 2) develop a documentation document that could facilitate new contributions. Before this project the only resource and guidelines to learn how to contribute in new or existing translations was the repository's [README](https://github.com/processing/p5.js-website) file which -even it contains essential information- is brief and leaves too many points without explanation.

This idea came after a collaboration I did last year with Aarón Montoya-Moraga when he translated both the website and the book to Spanish.

## Implementation
1. _What themes, readings, and discussion from [the first half of this course](https://github.com/Open-Source-Studio-at-ITP/Syllabus) were most relevant to your work on this project? Version Control, Community / Code of Conduct, Unit Testing, Documentation and Accessibility, Software Licensing, Project Funding_

Due to this collaboration was a pure open-source contribution -because discussions were held with other community members- the entire first part of the course was very useful. In one hand soft skills in open-source that were learned led me to kindly deal with discussions with other contributors. On the other hand, technical skills as the use of git and GitHub made this process very easy. Examples of this were the assignments in which we had to fork a repository, commit changes from a local branch and then submit a Pull Request. That was incredibly useful for this project.
2. _Describe the technical details about your implementation and development process._

The technical implementation of this project consisted in:
* Understand how the website works, which means learn the files structure, learn the setup process and the procedure before each commit, and learn which files must be modified and how.
* Fork and clone the original repo
* Install `npm` dependencies and run website building process
* Modify proper files
* Commit changes to my fork
* Pull request my changes to the base repository

3. _What challenges, stumbling blocks, difficulties did you encounter along the way._

One great challenge of this project was to understand how the p5.js website work and how its files are organized, because even there is a documentation section in the README file, it is so brief and there are subtle relations between files that just can be understood by putting your hands on the code.

Other key issue I had to face was to understand how the website building process was and how it should be carried out. It was important because as during this project important modifications were carried out and the building process got broken many times.

Finally and due to breaking the building process key, submitting my Pull Request was quite complicated because in one occasion I submitted a broken version of the website, which couldn't be fixed. That experience was a great source of learning because I had to deal with solving issues -I was strongly supported by Aarón- at the same time I tried to do it as fast as possible because other commits were not able to be built due to my broken changes.

4. _How did your final development line up with your proposal timeline._

The final outcome of this project matched the original plan in terms of working in the tutorial for translation contributing. It's important to say that it was mainly pushed by Dan because otherwise I'd have kept translating content from English to Spanish. In terms of the first kind of deliverables I just translated Color and Coordinate System pages, whilst in terms of documenting I completed the task.

5. _What was your biggest success? What was your biggest failure?_

My biggest success was to understand the logic that underlies the website's framework and to be able to apply the git/GitHub functionalities learned during the class to the collaboration itself.

On the other hand my biggest failure was to break the website after submitting a Pull Request without checking before if the page building process worked properly. Despite of this, it was a huge opportunity to improve my collaboration.

## Accessibility

_What challenges did you encounter in terms of Web Content Accessibility Requirements: [see the Accessibility assignment as a reference](https://github.com/Open-Source-Studio-at-ITP/Syllabus/blob/source/accessibility-assignment.md#instructions)._

## Mentoring

This project was mentored by [Aarón Montoya-Moraga](https://github.com/montoyamoraga), graduated from NYU ITP on 2017, former Resident at the school and contributor at the Processing Foundation.

Aarón has experience on p5.js internationalization since he translated to Spanish both the website and the book. We had at least one meeting per week in which we discussed the week progress and the goals for the next one. His advice was particularly useful when organizing and defining the goals of the translation documentation.

## Longer-Term Goals

_What do you see as the longer term plan for this project and your project involvement?_

I see this project in the long term as a useful tool for future i18n contributions. The documentation elaborated within this project will be published in the p5.js-website repository -most probably- as wiki page. Apart from that I expect to apply to a Processing Foundation Fellowship to work in the p5.js website translation tracking system, area of the site in which I didn't work but is an opportunity to improve the automation of the page maintenance.
