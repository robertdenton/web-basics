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

### CSS & JS

Coming soon...
