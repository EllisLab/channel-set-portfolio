# Portfolio Channel Set

Quickly create a Portfolio Channel in your ExpressionEngine install with this Channel Set.

The Media Portfolio Channel Set comes with custom fields, statuses, and categories to get you up and running fast. Here’s what’s inside:

### Custom Fields

* `{portfolio_images}`: a Grid field for images of your work
  * `:image` - a File field to hold the image
  * `:captio` - an optional Textarea to provide a caption to the image
* `{portfolio_description}`: a Textarea to describe your work
* `{portfolio_files}`: a Grid field for downloadable non-image files of your work (PDFs, zip files, etc.)
  * `:file` - a File field to hold the file
  * `:description` - an optional Textarea description for the file

### Statuses

* Open: published
* Closed: not published
* Featured: to call special attention to the entry

### Categories

* Branding
* Design
* Development
* Print

### Sample Tags

```
{exp:channel:entries channel='portfolio' limit='1' require_entry='yes'}
	{if no_results}
		{redirect='404'}
	{/if}

	<h1>{title}</h1>

	{if has_categories}
		<div>Categories:
			<ul>
				{categories}
					<li><a href="{path='portfolio/index'}">{category_name}</a></li>
				{/categories}
			</ul>
		</div>
	{/if}

	{portfolio_description}

	{if portfolio_images:total_rows > 0}
		{portfolio_images}
			<figure>
				<img src="{portfolio_images:image}" alt="{portfolio_images:caption}">
				<figcaption>{blog_image:caption}</figcaption>
			</figure>
		{/portfolio_images}
	{/if}

	{if portfolio_files:total_rows > 0}
		<ul>
			{portfolio_files}
				<li>{portfolio_files:file wrap='link'}</li>
			{/portfolio_files}
		</ul>
	{/if}
{/exp:channel:entries}
```

## License

Copyright (C) 2004 - 2016 EllisLab, Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL ELLISLAB, INC. BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Except as contained in this notice, the name of EllisLab, Inc. shall not be used in advertising or otherwise to promote the sale, use or other dealings in this Software without prior written authorization from EllisLab, Inc.
