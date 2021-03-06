## Description

This module wraps [Turbolinks](https://github.com/turbolinks).

Also, if [Alpine](../alpinejs) is present, it adds a set of event listeners that
prepares/cleans the AlpineJS state. Most importantly, it pauses Alpine's mutation observer so Turbolinks can do its work without interuption.

## Installation

First, add the module import to your site or theme component's configuration's module section:

```toml
[module]
[[imports]]
path = "github.com/gohugoio/hugo-mod-jslibs/turbolinks"
```

Then add the script source in the head section of your template (typically in the `baseof.html`):


```html
<head>
{{ partialCached "jslibs/turbolinks/script-src.html" "-" }}
</head>
```

Note, if used with AlpineJS, the order matters:

```html
{{ partialCached "jslibs/alpinejs/script-src.html" "-" }}
{{ partialCached "jslibs/turbolinks/script-src.html" "-" }}
```

