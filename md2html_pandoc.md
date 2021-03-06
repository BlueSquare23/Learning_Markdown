## Markdown to HTML with Pandoc

[Pandoc](https://pandoc.org) is the universal document converter. 

By default Pandoc will convert Markdown to HTML and output it on stdout.

#### Converting froggo.md file to HTML

* File: `froggo.md`

```
## Cool Froggo!

Look at this *Froggo!*

![Froggo](https://bluesquare23.sh/The_End_Of_The_Internet/froggo.jpg)
```

* Command: `pandoc froggo.md`

```
<h2 id="cool-froggo">Cool Froggo!</h2>
<p>Look at this <em>Froggo!</em></p>
<figure>
<img src="https://bluesquare23.sh/The_End_Of_The_Internet/froggo.jpg" alt="Froggo" /><figcaption>Froggo</figcaption>
</figure>
```

## Basic PDF Conversion

You can save that output to a file with the -o switch. Pandoc will try to use
the file extension to determine what type of conversion you want to do.

#### Convert to a PDF

* Command: `pandoc froggo.md -o froggo.pdf`

Note, sometimes you'll have to use the pandoc switch `--pdf-engine=pdflatex` to
convert documents to PDFs.

## Pandoc Templating

You can customize the HTML pages generated by Pandoc using templates.

I'm using the template below to turn a very basic Markdown document into a
simple web page that's nicely formatted for both desktop and mobile users and
includes a little hovering '/\ Top /\\' button. These special elements are
achieved via CSS which can be easily extended via Pandoc's templating.

* File: `pandoc_template.html`

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">

	<title>$pagetitle$</title>

    	<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.0/dist/css/bootstrap.min.css"
		rel="stylesheet"
		integrity="sha384-KyZXEAg3QhqLMpG8r+8fhAXLRk2vvoC2f3B09zVXn8CA5QIVfZOJ3BCsw2P0p/We"
		crossorigin="anonymous">

<style>
body {
	max-width: 1200px;
	padding: 10px;
}

#myBtn {
	position: fixed;
	right: 30px;
	bottom: 10px;
	font-size: 12px;
	border-color: rgba(85, 85, 85, 0.2);
	background-color: rgb(100,100,100);
}
</style>

</head>
<body>
$body$
</body>
</html>
```

We can now use our `pandoc_template.html` with the following command to convert
our README.md file into a decent looking HTML page.

#### Convert to HTML w/ Template 

* Command:

```
pandoc README.md \
	--template pandoc_template.html \
	--metadata pagetitle="Markdown Notes" \
	-o README.html 
```

#### Special HTML / CSS Elements

The floating top button and dynamically sized image are connected to the
`pandoc_template.html` sheet via a few HTML elements right in the README.md
file.

Specifically, this HTML code in the README.md is responsible for creating the
'/\ Top /\\' button.

```
<button id="myBtn"><a href="#top" style="color: white">/\\ Top /\\</a></button>
```

And this HTML code is responsible for setting an HTML top anchor.

```
<a name="top"></a>
```

The responsive image sizing is handled by a
[Bootstrap](https://en.wikipedia.org/wiki/Bootstrap_(front-end_framework)) CSS
class called "img-fluid".

[Responsive images](https://getbootstrap.com/docs/4.0/content/images/#responsive-images)

#### Pandoc Templating Final Thoughts

With just those few tweaks to the source Markdown and with Pandoc's templating
system you can easily convert a simple text file to a responsive and
interactive web page. 

For more information, see the pandoc docs on the subject linked below.

[Pandoc Templates](https://pandoc.org/MANUAL.html#templates)
