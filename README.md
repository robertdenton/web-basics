# Web basics

## Intro

The internet is kind of a big deal. I'm not sure if it's a fad or not but if you surf the web several times a day then I think you should have a basic understanding of how it works. I'll try to explain this fairly complex topic as simply and quickly as I can.

## Disclaimer

This document is intended for folks who have very little web design or development experience. It is certainly not an exhaustive tutorial, nor is it necessarily correct. I'll try to ensure that everything I say is accurate at the time of writing but things change fast and technology changes. Please take everything I say with a grain of salt and if something looks weird, go do some research on it. Google is your friend.

I should mention that there are a lot of other great resources for learning stuff like this. In fact, I don't know why you're even reading this. I you aren't some future archeologist and this is the only recoverable file on some disk. Ugh, so much pressure. I guess I try to make this not terrible.

## Servers 'n stuff

The internet (AP Stylebook just recently changed to lowercase) is basically a set of connected computers. My computer, your computer and thousands of specialized computers that are generally referred to as servers.

Servers can do a lot of different things but what you need to know is that they serve up information. All of the servers are linked up with your computer and mine and we call that the internet (or "cloud" if you prefer that marketing term).

There are some other computers in the network called domain name system (DNS). Think of these like a fancy internet phone book. What's a phone book you ask? Think of it like your contacts in your phone. When you want to call Ian, you just say call Ian and it looks up his number and calls it. (Hi Ian!)

So when you type in a URL like `myspace.com` your computer sends a request to a DNS server that translates `myspace.com` to it's real address (`63.135.90.70` at last check). Then your request gets routed to the address. Once it gets to the myspace servers your request is processed and the server sends information back to your computer. We'll talk about what it sends back in a second.

In summary, all the internet is is a complex network of computers sending information back and forth.

## Web documents

There are three basic types of web documents.

* HTML
* CSS
* JavaScript

In order to make a website you really only need an HTML document, but CSS and JS help give the page some character. You don't want a boring website, do you?

So when you request a page from a server it returns an HTML document. Typically, this HTML document will contain links to CSS and JS files to pull from other servers. All of these documents are downloaded by your browser and are rendered in front of you. It's really [pretty neat](https://www.youtube.com/watch?v=Hm3JodBR-vs).

Using browser-based developer tools you can actually view what files are being downloaded to your machine for each web page. Here's a very simple example from my website. Larger websites are known to download hundreds of documents for a single page.

![dev tools](https://cloud.githubusercontent.com/assets/4853944/15237498/38e85e16-1883-11e6-9d1b-219a6de87d8a.png)

In this example you can see there is one document (that's HTML), there are three stylesheets (that's CSS), two scripts (that's JS), three fonts and one jpeg image. Let's break this down a bit more.

### HTML

HTML stands for HyperText Markup Language and is a really simple tag-based system for displaying content. A *super* simple example of an HTML document looks like this:

```html
<html>
	<head>
		<meta charset="utf-8">
	</head>
	<body>
		<h1>Simple example headline</h1>
		<p>Here is a paragraph.</p>
		<!-- This is a comment -->
		<img src="link/to/image/file.jpg">
		<p>Here is another paragraph.</p>
	</body>
</html>
```

You should notice a distinct structure and several patterns here.

#### Tags

HTML documents are structured with tags. This allows your browser to read the pages and display the content that you want it to.

We start off the example with the `<html>` tag and close with a closing `</html>` tag. It should go without saying but a tag like this: `<tag>` opens up a new block and a tag like this: `</tag>` closes the block.

There are a lot of different tags and I'm too lazy to explain all of them.

Briefly, here are some used in the example above:

* `<h1>` - Think of this as headline-1, or the most important headline. You can also have `<h2>` or `<h3>` which step down in size and prominence. 
* `<p>` - A paragraph tag. You wrap these around paragraphs.
* `<img>` - This tag is what we call a self-closing tag, in other words it doesn't have a closing tag. This one in particular calls for an image at a specific URL or source.

And you might be wondering what the `<!-- comment -->` is. Well, in all coding languages you have to have a way to make comments without your comments getting in the way of the code. In HTML you have `<!--` to open a comment and `-->` to close a comment. In between you can say whatever you want and it won't be shown in the page. It *will* show in the source code though, so use it to explain code but not to store secret information. Ok, let's move on.

#### The head

Every HTML document is broken up into two main parts, the head and the body. The head part of the document goes before the body and contains non-rendered metadata about the document. This means that the browser will not display the information up here but the information is important to how your browser displays the body information.

In our example, I declare that this page's character encoding should be set to "utf-8". What character encoding and "utf-8" are is not important. What is important is to remember that this content is not displayed, but rather is used by the broswer to display the information correctly.

#### The body

Now on to the fun part. The body contains all of the content that will be displayed on you page. I went over some of the tags earlier so I'll try not to repeat myself.

Basically, this is where you have headlines, paragraphs, images, buttons, menus, etc.

I have set up our very basic example [here](). For those of you who are lazy like me, here's a screen grab:

![simple example screengrab](https://cloud.githubusercontent.com/assets/4853944/15237941/abb75f88-1887-11e6-80ca-096b90b67478.png)

This page is being rendered from this code, which is *very* similar to our simple example:

```html
<html>
	<head>
		<meta charset="utf-8">
	</head>
	<body>
		<h1>Simple example headline</h1>
		<p>Here is a paragraph.</p>
		<!-- This is a comment -->
		<img src="http://i.giphy.com/26tk1rgzY5mgjTuFy.gif">
		<p>Here is another paragraph.</p>
	</body>
</html>
```

I won't belabor the point but you can see the headline, image and paragraphs (but not the comment!) are displayed. And boom. There's a simple web page!

#### index.html

You might have noticed that I named the file index.html and there's a good reason for that. When you type in a URL like example.com/about/ the server is going to go look in the about folder of that website. I'm sure there are files in there but which one do you want it to return?

If you do not specify a file the server will get the index.html by default. So when you request example.com/about you're really requesting example.com/about/index.html. There could be another file in there called hello.html and you could request that by going to example.com/about/hello.html.

It's generally a good practice to simply create a new folder for each sub-page that you want and then create an index.html for each.

#### Wrap up HTML

There's a lot more that I could say about HTML but I'm kind of tired and I think that's all I want to write tonight. 

### CSS 

WHile HTML is the content of a webpage, CSS is the styling like fonts, sizes and colors. Of course CSS is a handy acronym (Cascading Style Sheets). What CSS does is it targets specific elements of an HTML page. There are different ways to target content to style (elements, classes and IDs) but we'll get to that a bit later.

While you can include CSS **inline** in an HTML document, generally CSS is written in it's own file with a `.CSS` extension and linked to from the HTML. You can have multiple CSS documents that target similar things, but the web page will only display the final style it's given. That's where the *cascade* in the Cascading Style Sheets comes in.

You can think of it as a series of text messages. The first text says:

>"Hey, let's meet at Café Roma at 7 p.m."

Then you get another that says:

>"Jk let's meet outside Taylor's at 7:30 p.m."

...and then you get a third and final text that says: 

>"Ok, sorry I'm running late, let's meet at my place at 8 p.m."

Of course you would go off of the latest text. That's how CSS works. You can have multiple style sheets, but only the final command is used.

Let's look at some examples.

#### Elements

Remember all those HTML tags? They're also called HTML elements. One of the most common is `<h1>`. By default, an h1 will be rendered as a bold 32px Times font. Let's pretend we want to change the font to a bold 24px Helvetica font. Here's how you would target an h1 element:

```css
// target the h1
h1 {
	// set the weight, see: https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight
	font-weight: bold;
	// set the size, see: https://developer.mozilla.org/en-US/docs/Web/CSS/font-size
	font-size: 24px;
	// set the font family, see: https://developer.mozilla.org/en-US/docs/Web/CSS/font-family
	font-family: Helvetica, Arial, sans-serif;
}
```

That make sense? Hopefully you noted the comments in the CSS. Unlike HTML where the comments look like `<!-- comment -->`, to comment out CSS you start a line with two forward slashes like this `// Comment`.

You may be wondering why we set two fonts. Well, not all computers are loaded with every font. Historically, Windows machines didn't carry Helvetica, but they did have Arial. To be safe, just in case your user doesn't have either font, you tell the browser to use a generic sans-serif font. 

Anyway, let's hammer this cascade thing home. If you have another CSS file loaded after the one above becuase you want to make the headline a different color, like red.

```css
h1 {
	color: red;
	font-size: 72px;
}
```

Here we see a color selector given attribute of red. That's how we set the color of a font. And we bump up the font size a little to 72px. Because this stylesheet is loaded after the one above, the h1 will be displayed as a red, bold, 72px, Helvetica font.

#### Classes

For simple web pages you can usually get by with just targeting HTML elements but with complex websites you need to be able to target a bit more accurately. Say you have some long quotes in your page that you want to italicize. You code may look something like this: 

```html
<p>This is a sentance that introduces a long quote.</p>
<p class="quote">This is the first graf of a long quote.</p>
<p class="quote">This is the second graf of a long quote.</p>
<p>And here we're back to your beautiful writing after the quote.</p>
...
<p class="quote">Here's another quote later on.</p>
<p>And back to normal text.</p>
```
This is a perfect example of a time when using a class to target multiple elements is worthwhile. Classes are great because they can be re-used multiple times on a page and the styling is consistant. Moreover, you only have to write the styling once and you get to use it over and over again, keeping your site consistant.

The CSS to target a clss looks like this:

```css
.quote{
	font-style: italic;
	font-family: Georgia, Times, serif;
}
```

In CSS a class begins with a period followed by the name of the class, then you put in styling just like you would an element. In this case, our quote is in an italic Georgia font. If your computer doesn't have Georgia it will try Times or fall back to a standard serif font.

#### IDs

The main difference between IDs and classes is that you're only supposed to us an ID once per page. Other than that you can handle them the same way. Here's an example for a large flag across the top of your page.

```html
<h1 id="myflag">This is my super awesome website</h1>
```

and the CSS may look like:

```css
#myflag{
	font-size: 120px;
	color: red;
	text-transform: uppercase;
	font-weight: bold;
	font-family: Arial, sans-serif;
}
```

You target an ID using pound (for those of you who have ever used a pay phone) or a hashtag (for those of you who have never used a pay phone) followed by the ID name. In his case your flag is an all 120px, upercase, bold, red, Arial font. Seems kind of tacky but it's your website...

#### Wrapping up CSS

There are a ton of other ways to use CSS other than just modifying the font and color of text. You can add borders, play with margins, set backgrounds and even do some basic hover functionality.

### JS

So, to be totally honest, I really don't like JavaScript. Using JavaScript to build websites is super hot right now and I'm not totally on board with that.

![JS is so hot right now](https://cloud.githubusercontent.com/assets/4853944/15266080/26b62130-194e-11e6-9a08-4ed5c8208bfc.jpg)

Don't get me wrong, when JavaScript works well it's *so* nice, but I deal with so much bad JavaScript that requires more JavaScript to fix, which is totally not how things should be done. Regardless of how I feel about it, JavaScript is absolutely necessary for any web designer to be aware of and understand.

So what is JavaScript? Well, HTML provides the content and structure for a page, CSS provides the style and JavaScript provides the interactiveness. Is that a word? Whatever. Interactiveness. So at a really basic level you can use JavaScript to manipulate content and styles when the user interacts with your page. Let's try a brief example.

```html
<button id="button" onClick="changeColor()">Click this button to change the text color.</button>
```

And let's throw in some CSS...

```css
#button{
	padding: 10px;
	border: 1px solid black;
}
```

And here's some JavaScript...

```javascript
function changeColor(){
	document.getElementById("button").style.background='red';
}
```

Ok, so what are we doing here? We set up a button in HTML with an ID of `#button` and when we click on it we want to fire the changeColor() function. This is a bit of JavaScript worked into our HTML. We give it a bit of styling just for fun. And we have the actual JavaScript. This defines the function that is called when we click the button. It says when this function is triggered then get the document (the HTML document) and look for this specific ID (#button in this case), and then change its style, specifically its background to be red.

JavaScript can be loaded in from seperate files or included *inline* in HTML but it's usually best to separate them.

#### jQuery

This is something you will surely run into when you begin to do web development. I won't say much other than jQuery is a powerful tool to do stuff in JavaScript really easily. I strongly encourage you to learn some, what's called, vanilla, or plain, JavaScript before you start trying to be fancy with jQuery. It's a great tool but you'll never learn what's really going on if you just use jQuery all the time. Then when you get to an issue that jQuery doesn't solve you'll be in trouble.

#### JavaScript wrap up

I don't want to get too into JavaScript because it gets complicated quick. Hopefully this at least made sense, though I wouldn't expect you to go out and do a bunch of JavaScript tonight. Or maybe you will. Surprise me. No, just kidding, that would not be fun for you.

## Next steps and resources

By this point you should have realized that I have absolutely no idea what I'm talking about and should have jumped ship for literally any other web design tutorial. If you're still reading this you should know that I've spent the last five years of my life learning about this stuff and I'm still learning new things every day. There is **a lot** I don't know about web development and blah blah blah. That sentence was getting too long.

Anyway, always use [MDN](https://developer.mozilla.org/en-US/) when you're looking up documentation. They also have some tutorials that I've never looked at but are probably pretty good. There's always things like CodeCademy although I've never really been wowed by any of their courses. Really the only way you're going to learn how to do this stuff is by trial and error. Try to make a really simple HTML-only webpage. Then add some CSS. Don't even worry about JavaScript until later. Much later. The first few basic websites you build shouldn't even need JavaScript.

Learn about [responsive web design](http://alistapart.com/article/responsive-web-design). Learn about [HTML5](http://diveintohtml5.info/). Start using [developer tools to inspect CSS](https://developer.mozilla.org/en-US/Learn/Common_questions/What_are_browser_developer_tools) and see how other people build websites. Sign up for email news letters that interest you.

Above all else, never stop learning. You don't just learn web development one day and become a master. The ground is always moving under your feet and just when you think you understand something, you read something that says the exact opposite.

Feel free to contact me if you want to give me free things. Please to not contact me to tell me how many times I was wrong in the post. It was probably more than five times, but definitely less than 100.

Ok, I'm going to go do something better with my time. Peace.