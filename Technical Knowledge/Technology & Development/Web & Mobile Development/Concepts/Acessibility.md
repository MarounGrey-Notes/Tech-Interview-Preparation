# Accessibility Standards Interview Questions

WCAG 2.1 guidelines categorize accessibility criteria into 3 levels to allow for prioritization and staged compliance:

**A (lowest)**: 
Must satisfy to remove barriers preventing access. Includes things like:
- Providing text alternatives 
- Making functionality keyboard accessible
- Supporting OS/browser accessibility features 

**AA**: 
Should satisfy to remove significant barriers. More stringent level that includes: 
- Higher color contrast requirements  
- All functionality available from keyboard 
- Allowing time limits to be turned off or adjusted
- Not relying on sensory characteristics alone 

**AAA (highest)**: 
May satisfy to improve accessibility. Most stringent requirements enhancing experiences such as:
- Media alternatives like captions, transcripts, audio descriptions
- Identifying language changes
- Offering pronunciation guidance for unfamiliar words
- Warning of flashing content

Most organizations aim for AA compliance to balance meaningful access with level of effort. AAA targets enhanced experiences via going the extra mile wherever possible.

![WCAG 2.0 Infographics](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fhurix.com%2Fwp-content%2Fuploads%2F2017%2F07%2FWCAG_Standards-at-a-glance_Infographic-1-1024x465.jpg&f=1&nofb=1&ipt=ebce42e867e4ccb60caf8ed4772a338afef04ba2db3b04b020b64c9d78cf8b88&ipo=images)

## Explain what WCAG and ADA compliance means and why it is important?
WCAG refers to the Web Content Accessibility Guidelines that provide recommendations for making web content accessible to a wide range of users with disabilities. ADA refers to the Americans with Disabilities Act which legally mandates accessibility standards in the US.
Following these standards ensures we don't exclude users with limitations and our sites/apps remain usable for as many people as possible. Accessibility is not only the right thing to do but also expands the userbase.

## What are some key things you keep in mind when designing interfaces to support screen reader and keyboard navigation?
Some key things include:

- Using proper semantic HTML elements like nav, main, h1-h6 tags etc.
- Providing textual equivalents for non-text elements.
- Maintaining logical focus order and outlining focus with CSS.
- Confirming color contrast ratios meet minimum requirements.
- Testing the site works fine when accessed fully via keyboard.

## What specific accessibility standards like color contrast ratios, skip to main content links etc have you implemented?
For example - I recently implemented a portal-wide 4.5:1 color contrast standard for all text against background colors. This helps readers with low vision better perceive the content rather than getting obscured by lack of sufficient contrast ratios.

## How have you implemented or validated accessibility in your past projects or experience?
In a recent project building a web application for course selections, accessibility was a key requirement. Here is how I ensured it was woven into the entire product:

**Implementation**

- Used HTML semantic elements like main, nav, section to allow native reader understanding

- Confirmed color contrast ratios by using Lighthouse in dev tools to catch issues early

- Implemented keyboard navigation so all actions can be triggered without a mouse

- Used aria-label attributes for custom components to provide screen readers extra context

- Programmatically managed focus states relying on CSS outline rather than color

**Validation**

- Did manual testing by turning off CSS and relying on keyboard alone to confirm logical flow

- Used JAWS screen reader to ensure semantic HTML is read properly and ARIA labels are effective

- Added badges displaying text alternatives for all icons to clarify meaning

- Used axe extension to audit and catch any flagged violations that need addressing

- Tested on mobile to ensure elements have proper tap targets and touch support

By considering these throughout designing, developing, testing - I was able to meet all AA level criteria for WCAG compliance.

## How do you test that your web pages, components and interactions are screen reader friendly?
**Manual Testing**

- Turn off CSS and rely on keyboard alone to click through every action and content piece to confirm things remain navigable and understandable.
- Use a screen reader like NVDA or JAWS to browse through page content and interactions. Check if reading order is logical.
- Verify custom interactive components are understandable and usable with voiceover descriptions using aria-labels.

**Automated Audits**

- Use axe or WAVE browser extensions to audit for violations and missing attributes like alt text.
- Validate content is readable with Natural Language Processing API tools.
- Lighthouse accessibility checks for color contrast, focus management etc.

**Real User Testing**

- Conduct moderated sessions directly with blind users to uncover usability issues.
- Ask the users to verbalize what they understand about the current screen as they navigate through. Identify interpretation gaps.

## Do you have experience building Single Page Apps or web sites optimized for low vision users?
Yes, I worked on an ecommerce website where constantly changing promotions and products posed accessibility challenges.

Some ways I optimized it for low vision users included:

- Allowing text size adjustments without hurting layout
- Building color contrast compliant themes
- Keyboard navigation support
- Confirming carousel updates don't alter focus order unexpectedly
- Reader-friendly notifications for order status changes that don't rely solely on color cues -Semantic HTML to make browsing categories clear -Text alternatives for all product images

By considering contrast needs, semantics, focus handling and more from the start - I was able to greatly improve the store's accessibility for vision impaired online shoppers.

## Which accessibility tools like aXe, WAVE, Lighthouse etc. are you familiar with and used for audits?
I actively used tools like:

Lighthouse - for automated checks against WCAG criteria
axe and WAVE browser extensions - to catch missing attributes or semantic warnings
Color Contrast Analyzers - to confirm text colors meet 4.5:1 contrast ratio
Screen readers like NVDA and JAWS for manual testing
These helped surface common issues from interactive widgets missing text alternatives to insufficient color contrast needs early.

## How do you handle dynamic content updates to ensure they don't compromise accessibility?
When new content loads asynchronously, I reset logical focus order programmatically. I also confirm new elements like dialogs are announced to screen readers using ARIA live regions attributes. Updating content visually alone is not enough. The dynamic changes need to be made understandable and navigable for assistive technologies as well. So resetting focus, announcing additions, maintaining expected reading order are all critical.

