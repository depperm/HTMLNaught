# HTMLNaught

Based heavily on [The Web that Never Was -  Dylan Beattie](https://www.youtube.com/watch?v=8JOD1AQGqEg), with some differences
- 24:13 HTML naught
- 39:35 Hyper Lisp

## Syntax
- `~<element>{contents}` HTML Element with no attributes
- `~<element>(colon separated attributes)` Empty HTML element
- `~<element>(colon separated attributes){contents}` HTML Element with attributes

### Elements

#### Difference from normal HTML

- link (a): `~link(to:url){link text}` (video uses `~link(surf:url){...}`)
- code (script): `~code(type=text/javascript)` (video uses hyperlisp, which I'm not going to touch)
- metadata (head): `~metadata{...}`
- style (link): `~style(src:url)`

### Example
```
~html(lang:en){
	~metadata{
		~title{It's HTML, Jim, but not as we know it...}
	}
	~code(type=text/javascript){
	}
	~document{
		~h1{Hello, World!}
		~p{
			Using HTML, we can make paragraphs, and even
			~link(to:grid!cern.ch/hello.html){link}
			to other documents into our paragraphs!
			~span(id:greeting-span)
		}
		~form(method: SUBMIT, id:main-form){
			~input(type:text){What's your name?}
			~input(type:button, action: submit){Go!}
		}
		~img(src:grid!cern.ch/images/test.jpg){Test Image}
	}
}
```

## TODO
[ ] Flesh out syntax
[ ] Parser (Find cross OS lang, nim?)
[ ] Transpiler
[ ] Live transpilation
[ ] Get language accepted to not need Transpiler