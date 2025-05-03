
To start the slide show:

- `pnpm install`
- `pnpm dev`
- visit <http://localhost:3030>

Edit the [slides.md](./slides.md) to see the changes.

Let's get to the Tutorial
Slides are written in Markdown in the slides.md file.
To create a new slide, just add three dashes (---) on a new line:

1. Adding Titles
---
# Slide Title

Some paragraph text here.

3. Add Content
You can use regular Markdown:

Headers:
# H1
## H2
### H3

3. Text and Formatting:
This is * italic *, this is ** bold **, this is ~~ strikethrough ~~. 
Note: You're not meant to add space, I just did, so it doesnt just render them. 

4. Code Blocks
To add code blocks, all you have to do is add three backticks (```)
```Followed by the language. After the code block, close with three backticks. Example below:

``` js
function greet(name) { return `Hello, ${name}!`; }
```

5. To add styles, you can add class to your elements. Example below:
'# Project Title {.header}'
.header is your class and then you can now style it. It should also come at the bottom of each slide. To style this Project Title, see below:

<style>
.header {
  color: #3B82F6;
  font-size: 2.5em;
}
</style>

6. To end each slide, use three dashes ---. So, usually, three dashes come after the styling. 


This isn't as comprehensive as the documentation. I'll advise you read the documentation as I'm also doing that.
Learn more about Slidev at the [documentation](https://sli.dev/).
