# The power of customization: Designing a Chrome extension
We all know and love them. Chrome Extensions, Whether it’s for fun, educational or accessibility purposes, almost everyone uses them. These last few weeks I have been looking into Chrome extensions, how they work, and how to make your own extensions. 

## What are Chrome Extensions?
Chrome extensions are powerful tools that add extra functionality and customization options to the Google Chrome browser. these small software programs offer a wide range of features and tools to enhance productivity, privacy, and convenience while browsing the web. From ad-blockers to note-taking apps and language translators, Chrome extensions provide a way to personalize your browsing experience

## How do you make your own Chrome Extension?
There are multiple uses for a Chrome Extension so the first thing you have to ask yourself is what do you want to make? Do you want to make a cheat sheet for a game you’re playing online? Then you can make an extension with a simple html/css page that shows up upon clicking on your extension. If you want a cheat sheet you can simply make a map with an index.html and style.css file. Do you want to change an existing webpage because you simply want a funny image on the background? Then you have to make a style.css and override it on the webpage.

## Manifest.json
In both cases, you will have to make a Manifest.json in you the map of your files to make them work. Depending on the cheat sheet (in this case) or replacing the style/adding Javascript you will need a different Manifest.

### Index/css

```json
{
    "name": "Change body image",
    "version": "1.0.0",
    "description": "Change body image",
    "manifest_version": 3,
    "author": "Martijn van der Lans",
    "action":{
        "default_popup": "index.html",
        "default_title": "Cheatsheet"
    }
}
```

### Replacing css/js
For replacing the CSS you need to add more text to the manifest. In this case, you need to add ‘concent_scripts’ to add js and css to the page.

```json
{
    "name": "Change body image",
    "version": "1.0.0",
    "description": "Change body image",
    "manifest_version": 3,
    "author": "Martijn van der Lans",
    "action":{
        "default_popup": "index.html",
        "default_title": "Cheat sheet"
    },
    "content_scripts": [{
        "js": ["content.js"],
        "css": ["replace.css"],
        "matches": ["https://*/*"]
      }]
}

```

As for the ‘matches’, this refers to the pages these files will be added to. In my case, it replaces every website as * means all, but you can also limit it to all pages on Google for example by changing it to ‘https://google.com/*’

### CSS

```css
body {
    background-image: url('https://cdn.wallpapersafari.com/96/10/EwQZK2.jpg')!important;
    background-position: center;
    background-size: cover;
}
```

As an example, I wrote this very small and very quick css code to replace the body image on every website on Chrome. And once we added our extension folder to Chrome, we get something like this"":

<img src="https://i.imgur.com/ScSiQug.png" WIDTH="45%" alt="Chrome extension displayed">
<img src="https://i.imgur.com/ruGp1Md.png" WIDTH="45%" alt="Chrome extension displayed">

## Conclusion
Writing a Chrome extension is a very fun and cool skill to have and it’s just as easy as writing a regular code. The only file you have to add for a Chrome extension is the Manifest.json file and understand what’s happening in it to make a functioning Chrome extension. 

<hr/>

Chapagain, S. (2022). How to Create Your Own Google Chrome Extension. freeCodeCamp.org. https://www.freecodecamp.org/news/building-chrome-extension/#how-to-create-a-chrome-extension
