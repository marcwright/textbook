####What To Do When Your Webpage Doesn't Look The Way You Want and the CSS Isn't Behaving

1. Run your HTML through http://validator.w3.org , and address every error. CSS is much easier to work with it's describing valid HTML.

2. Run your CSS through http://jigsaw.w3.org/css-validator . This will alert you to any errors.

3. Remove any inline styling in your HTML -- that is, any `style='something something'` attributes, and all `<br />` and *especially* `<center>` tags.

4. Remove `absolute` and `fixed` positioning and floats. Generally you want everything else to look OK before you start adding these in, since they easily throw off the flow of everything else on your page. Once one thing is absolutely positioned, everything around it usually has to be absolutely positioned as well.

5. Remove any CSS that makes things show up only when you hover your mouse over them. Keep an eye out for `opacity:0`, `visibility:hidden`, and `display:none`.

6. Normalize your CSS -- that is, make your web browser's default stylesheets stop messing up stuff on your page. I usually insert this at the very top of my stylesheets:
```css
*
{
	margin:0;
	border:0;
	padding:0;
	border-collapse:collapse;
	border-spacing:0;
	font-weight:inherit;
	font-size:inherit;
	font-style:inherit;
	color:inherit;
	background-color:transparent;
	box-sizing:border-box;
	font-family:inherit;
}
```
`*` is a selector that means "everything". `inherit` means "use the value of this thing's parent element".
If you add this into a page of existing CSS, it's probably going to make your webpage look all crazy. That's OK -- fix your CSS to accommodate it, and you should find it's much easier to work with than it was before.

7. Add `outline:1px solid blue` and similar to the selectors you want to work with. Unlike borders, outlines don't push stuff around on your page. That makes them really useful for figuring out how much space elements actually occupy.

8. If you're working with `inline-block` elements, and you keep getting little gaps between them, that may be because the web browser is inserting a space character between them.
If you have this:
```
<div>
	<img />
	<img />
</div>
```
...the web browser is going to turn the carriage return between those images into a space character.
To get around this, you can give the `div` a `font-size` of `0px`, `float` the images, or just put them all on the same line:
```
<div><img /><img /></div>
```

Also, remember that in Rails you can't just link to a local stylesheet the way you can outside of Rails. You need to call the stylesheet using the asset pipeline. Generally that means using something like this:
```
<%= stylesheet_link_tag "mystylesheet" %>
```
Take a look at http://guides.rubyonrails.org/layouts_and_rendering.html
