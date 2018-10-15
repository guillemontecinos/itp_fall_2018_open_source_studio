# Accessibility Assignment
*by Guillermo Montecinos. October 15th, 2018*

A web accessibility audit was committed as an assignment for the Open Source Studio Class, ITP Fall 2018. For this, the website of the [ml5.js](https://ml5js.org) project was chosen.

![](https://github.com/guillemontecinos/itp_fall_2018_open_source_studio/blob/master/week_6/ml5_1.png)

The methodology applied for this task was a complementary use of the [WAVE - Web Accessibility Evaluation Tool](https://wave.webaim.org/extension/) and the Mac screen reader *VoieceOver*.

The WAVE tool analyzes the writing code and the design issues related to the accessibility guidelines defined by the W3C in the [WCAG](https://www.w3.org/WAI/standards-guidelines/wcag/).
The application of WAVE in the initial page of ml5.js shows -in terms of code- just one error, which corresponds to the lack of language defined for the website. This error is shown with a red mark in the upper part of the page. It also displays one alert related to an skipped heading level at the bottom side of the site.

In terms of code the site seems to accomplish the main criteria established in the WCAG.

![](https://github.com/guillemontecinos/itp_fall_2018_open_source_studio/blob/master/week_6/ml5_2.png)

In terms of design, it can be seen that the color contrast of the main text meets the WCAG 2.1 criteria of a 4.5:1 ratio, as can be seen in the next image.

![](https://github.com/guillemontecinos/itp_fall_2018_open_source_studio/blob/master/week_6/ml5_3.png)

This is not accomplished in by the title "Friendly Machine Learning for the Web." of the web which is written in purple color over the same background of the main text, holding a contrast ratio of just 3.8:1.

![](https://github.com/guillemontecinos/itp_fall_2018_open_source_studio/blob/master/week_6/ml5_4.png)

On the other hand, the website was audited by using Mac VoiceOver. Accordingly with WAVE results, the site seems to be well organized, well labeled and easy to navigate with the screen reader. Despite the above, there were two elements of the site that are hard to navigate with screen reader due the labelling used. The first is the righter box with the image classification example which is settled on a frame with no name or label that explains the content of the frame.

![](https://github.com/guillemontecinos/itp_fall_2018_open_source_studio/blob/master/week_6/ml5_5.png)

The second element is the ITP logo at the bottom of the site which is mislabeled with the text "Facebook Open Source" instead of "ITP".

![](https://github.com/guillemontecinos/itp_fall_2018_open_source_studio/blob/master/week_6/ml5_6.png)
