[Home](/)

# HTML and a little CSS

HTML tells a web browser how to display a web page.

CSS makes the web page look nice.

## What you will build

HTML (Hypertext Markup Language) is the set of markup symbols or codes inserted in a file intended for display on a World Wide Web browser page. The markup tells the Web browser how to display a Web page's words and images for the user.

We will use html "tags" and css styles to create a "profile" or "vanity" web page that you can use to showcase yourself, your favorite cartoon character or superhero.

![Profile Web Page](/assets/img/profile-web-page-mr-handsome.png)

## html tags (elements)

Here are some common HTML "tags" that we will use to tell the web browser how to display our web page.

- `<div>`  - The `<div>` tag is nothing more than a container unit that encapsulates other page elements and divides the HTML document into sections.

- `<article>`  - The `<article>` element represents a component of a page that consists of a self-contained composition ...This could be a forum post, a magazine or newspaper article, a blog entry, a user-submitted comment, an interactive widget or gadget, or any other independent item of content, like  a profile web page ;).

- `<header>` - A `<header>` typically contains a group of introductory or navigational aids. The obvious place to start would be at the beginning of your page or at the top of an `<article>`.

- `<a>` - An anchor tag, `<a>`,  The `<a>` tag defines a hyperlink, which is used to link from one page to another. The most important attribute of the `<a>` element is the `href` attribute, which indicates the link's destination.

- `<img>` - The HTML `<img>` element represents an image in the document.  The image url is represented by the `src` attribute.

- `<h1>` and `<h2>` and `<h3>` - The HTML `<h1>` through `<h6>` elements represent six levels of section headings. `<h1>` is the highest section level and `<h6>` is the lowest.

- `<p>` - The HTML `<p>` element represents a paragraph of text.

- `<ul>` - unordered list.  The `<ul>` tag defines an unordered (bulleted) list. Use the `<ul>` tag together with the `<li>` tag to create unordered lists.

## CSS

The Cascading Style Sheets Specification (CSS) is a computer language that is used to write formatting instructions ( rules ). These rules tell a web browser how webpage content should 'look'— in terms of: layout. position, alignment, width, height, etc.

For this course we will use [Tachyons](http://tachyons.io/), which is a CSS toolkit.  It provides 100% responsive web pages with as little css as possible.  

See [CSS and Tachyons](/css-and-tachyons).

## CSS and Tachyons

[Tachyons](http://tachyons.io/) is a CSS toolkit.  It provides 100% responsive web pages with as little css as possible.  

Responsive means your website should work regardless of a users device or screensize.

Tachyons makes your website readable.  No matter the lighting, or the device, font-sizes should be large enough and contrast should be high enough for your users to easily read your content.

Tachyons uses a modular scale for spacing and sizes based on the powers of two. This is a common scaling system used in typography for 400 years.  

Tachyons features a spacing scale based on powers of two.

> "A modular scale, like a musical scale, is a prearranged set of harmonious proportions."

Getting started with Tachyons is as simple as adding a link in your webpage to a .css file located on content delivery network (cdn), like unpkg.com. unpkg is a fast, global content delivery network. Use it to quickly and easily load files using a simple URL.  

```
<!DOCTYPE html>
<html lang="en">
  <title> </title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="https://unpkg.com/tachyons/css/tachyons.min.css">
  <body>

  </body>
</html>
```


[Home](/)
