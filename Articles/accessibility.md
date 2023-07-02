# The Web is for Everyone: Accessible Web
In the age of technology in which everyone owns a laptop, tablet, or phone, accessibility is now more important than ever on the Web. A lot of websites focus on the look of their website, which is important, but often neglect to design for users who have more trouble surfing the web. Think of people who are blind, who can't see the page but still have to buy something from the internet. Now that everyone is dependent on the web, we have to realize that our websites need to be accessible to everyone. Why? Because the Web is for everyone! (Tim Berners-Lee).

## The Basics
A few things you can do to make your website more accessible is handling the font size to make it bigger, the line height, which is by default roughly 1.2 while it should be 1.5. Another example of this is `text-align: justify;` while it looks pretty, the gaps harm the readability. Another bad practice is using `::before` and `::after` and adding content, since this can’t be selected.

## Design with accessibility in mind
When designing, a lot of developers forget to make it accessible but why not make it both pretty and accessible? Adding a pretty letter animation on a word looks cool and it is! But these often contain <span> elements for each letter, causing a screen reader to say each letter instead of the word. To fix this, you could add an `aria-hidden: true;` on the spans and add an `aria-label=”Hello world”` to the container of the spans. This way your website can still look amazing while being accessible for users.


According to Cyd Stumpel, a Creative Developer who makes Accessible websites, there are more mistakes developers often tend to make. Examples are: Removing Focus styles with no replacement, Removing Scrolling Functionality, Not Alt in Buttons, images, etc. and Not respecting prefers-reduced-motion. 

## Testing
A great way to test if your websites are accessible is to test them. It’s basic, but it works. Ask people with a disability to test your website, ask older people to see if the font-size works and test in the dev tools if the colors have the right contrast. Testing is everything.

<hr/>

### Sources
Matuzovic, M. (2018, December 8). Writing CSS with Accessibility in Mind - Manuel Matuzovic - Medium. Medium. https://medium.com/@matuzo/writing-css-with-accessibility-in-mind-8514a0007939
