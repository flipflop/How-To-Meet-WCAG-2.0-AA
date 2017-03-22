# How to Meet the Web Content Accessibility Guidelines (WCAG) 2.0 AA

*Authour: Rozario Chivers |
Date: 23/03/2017 |
Version: 0.1*

Conformance Levels: 

- <b>Level A:</b> For Level A conformance (the minimum level of conformance), the Web page satisfies all the Level A Success Criteria, or a conforming alternate version is provided. 

- <b>Level AA:</b> For Level AA conformance, the Web page satisfies all the Level A and Level AA Success Criteria, or a Level AA conforming alternate version is provided. 

- <b>Level AAA:</b> For Level AAA conformance, the Web page satisfies all the Level A, Level AA and Level AAA Success Criteria, or a Level AAA conforming alternate version is provided. 

## Criteria

The criteria for WCAG 2.0 AA compliance includes the following considerations:

- Use Semantic Markup, ensure all tags are well formed and closed correctly, with no duplicate ids. This will reduce parsing errors and increase interoperability with Assistive Technologies (AT). Tip: use a HTML5 validator. To validate a Single Page Application (SPA) copy the Live DOM into the W3C Service from the browser inspector or use an Open Source JavaScript HTML5 Validator library to validate at runtime during development. ```DO NOT: use tables for layout, tables are for tabular data only.```

- Ensure all the correct WAI ARIA attributes, Landmarks and Roles are used appropriately. Note: this is especially important when using tags that are not traditionally input controls like div tags or span. Note: not all Assistive Technologies (AT) interpret or make use of WAI ARIA correctly, for example the JAWS Screen Reader presents a number of compatibility issues in this area.

- Content must be robust enough to be interpreted and used by a wide range of User Agents and Assistive Technologies (AT), i.e. do not test in JAWS only. If possible consider older Assistive Technologies and browser support, for example landmark roles are typically added to ```<header>```, ```<main>``` and ```<footer>``` tags (which are natively accessible in modern browsers) for backwards compatibility specifically for this reason. Example markup:

	```<header role="banner">``` 
	
	```<nav role="navigation">``` 
	
	```<main role="main">``` 
	
	```<article role="article">``` 
	
	```<aside role="complementary">``` 
	
	```<footer role="contentinfo">```
	
	```<form role="search">```

	```Note: this may result in 'redundant' warnings from automated Accessibility validation tools.```

- Clearly define the language of the page programmatically. e.g. ```<html lang="en">```

- All functionality should be operable through a keyboard, in addition to mouse input methods.

- Focus, content should be navigable sequentially and logically related to the content structure. Focus states and operation should be retained for clarity and affordance. Ensure Focus is visible.
	```Tip 1: use tabindex="0" to insert elements into the tab order that are not natively focussable e.g. spans or divs.```
	```Tip 2: use tabindex='-1" to make elements programmatically focussable, without being included in the tab order.```

- Text alternative for non text content (e.g. images, audio or video). For alt attributes avoid: 'picture of', 'image', 'graphic', 'link to' or '*' etc.

- Text should be able to be resized up to 200%. Tip: ensure mobile meta tag settings don't restrict this. Tip: permit zooming on mobile e.g. ```<meta content="width=device-width,user-scalable=YES,minimum-scale=1.0,maximum-scale=2.0" name="viewport">```

- Text should be clear, easy to read and understandable, particularly affecting users with Cognitive Impairment. When authouring content use the "Inverted Pyramid" (used in journalism and writing). Provide important information first.

- Clear hierarchical heading structures within content, making it easier to identify sections and sub sections. Headings are primarily for document structure. ```Tip: use a Document Outlining Tool to reveal heading structure.``` This includes clear section structured page titles to clarify the depth of exploration and context of content within the page. For example for titles front load unique content: ```[page] - [subsection] - [sitename]```

- Headings and Labels should indicate topic or purpose, the correct Semantic Markup must be used for headings and labels i.e. avoid div tags or spans for areas that are clearly headings or labels for form fields.

- Use Semantic Markup to clarify the use of abbreviations, to provide emphasis around content e.g. ```<strong>This important notice will be read with emphasis by a Screen Reader</strong>```

- Link Purpose (In Context), the content of a link should clearly describe it's purpose, what information it relates to and where the link may direct the user to. If a link can not be understood outside the context of the page consider rewriting it. (i.e. take all links from a visual design and place them in a list on a blank piece of paper - can the links be understood).
	```DO NOT: use "Click here" or "More info" links.```

- Interactive components should not solely rely on sensory characteristics, e.g. shape, size, visual location, orientation or sound.
 
- Colour should not be the only method for conveying information e.g. red text for errors (an icon, border or background can be used as visual cues). Note: Many users are colour blind. Rule: never indicate information or a state change to the user with colour alone. Typical examples are error message areas that contain red text with a border and background for clarity.

- Colour contrast should be within the recommended ratios for content and images

- Audio, video and long running animations should provide options for control, in particular pausing and stopping. Provide audio and video transcriptions where appropriate (this will also help with SEO). For Accessibility consider [Web Video Text Tracks Format (WebVTT)](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API), which has good modern (Standards Compliant) [browser support](http://caniuse.com/webvtt/embed/), including mobile devices.

- Timing should be adjustable e.g. Session timeouts should provide options for extension. Animations and auto updating content should provide options for pausing, stopping or hiding.

- Avoid content or animations that flicker or flash more than 3 times per second.

- Navigable, provide mechanisms to find content and allow users to understand where they are. Apply consistently and predictably.

- Interaction and Input, ensure interactive components do not immediately change content and display without preparing the user for the change in context. For example: avoid 'Jump To' page scrolling and ensure Tabs use CSS animation to indicate a change of context when each tab is interacted with via click, tap or focus. Changes of context should only be initiated only by user request.

- Provide multiple pathways to content, does the user have more than one method for locating web pages within a set of web pages? (excluding steps within a process flow).

- Allow users to be able to bypass areas of repeated content across pages e.g. Skip Links.

- Forms, help users to identify and recover from errors. Tip: Screen Reader only (hidden from display) error summaries will help users identify lists of errors and to select and rectify the appropriate error via links). 

- Provide clear instructions where necessary, but do not overload with too much text as this adds to Cognitive Load for all users. Make suggestions available to aid error recovery of valid input types (only if this requirement is not in conflict with security considerations i.e. providing too much information to hackers). 

- Clearly indicate required or mandatory fields to the user. 

- Always associate labels with form fields unless labels are used to wrap form elements.
```DO NOT: use placeholder text instead of labels.``` Also reconsider the [User Experience benefit of placeholder text](https://www.nngroup.com/articles/form-design-placeholders/).

- Ensure that changing the setting of any form control or field does not automatically cause a change of context. If conditional display is required ensure the correct notification of change is made, prior to and during the interaction. 

## Resources

- [Web Accessibility Checklist](http://a11yproject.com/checklist.html)
- [Accessible HTML5 Video Player](https://github.com/paypal/accessible-html5-video-player)
- [The little-known iPhone feature that lets blind people see with their fingers](http://finance.yahoo.com/news/david-pogue-on-iphone-voiceover-163733668.html)
- [Using the tabindex attribute](https://www.paciellogroup.com/blog/2014/08/using-the-tabindex-attribute/0)
- [Chrome Accessibility Tools](https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb)
- [JavaScript Readability Score Bookmarklet](https://accessibility.oit.ncsu.edu/tools/readability/)
- [Colour Contrast Analyser](https://www.paciellogroup.com/resources/contrastanalyser/)
- [How to design (in Sketch, Photoshop and Web) for color blind users](https://medium.com/sketch-app-sources/how-to-design-in-sketch-for-color-blind-users-2b189c0d58fe#.j11r6n14k)
- [Start Building Accessible Web Applications Today](https://egghead.io/lessons/html5-accessible-button-events)
- [A11ycasts #02](https://www.youtube.com/watch?v=fGLp_gfMMGU)
- [Accessibility Wins](https://a11ywins.tumblr.com/)

## Further Reading

- [Screen Readers on Touchscreen Devices](https://www.nngroup.com/articles/touchscreen-screen-readers/)
