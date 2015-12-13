simpler-sidebar
===
[![GitHub version](https://badge.fury.io/gh/dcdeiv%2Fsimpler-sidebar.svg)](https://badge.fury.io/gh/dcdeiv%2Fsimpler-sidebar) [![Bower version](https://badge.fury.io/bo/simpler-sidebar.svg)](https://badge.fury.io/bo/simpler-sidebar) [![npm version](https://badge.fury.io/js/simpler-sidebar.svg)](https://badge.fury.io/js/simpler-sidebar) ![MIT adnd GPL-2 license](https://img.shields.io/badge/license-MIT%20and%20GPL--2.0-blue.svg)

A jQuery plugin that allows to *create a side nav* as in modern mobile apps. It aims to *simplicity* so that *everybody can use it* no matter if expert programmers or not.

- [Download](#download)
- [Getting Started](#getting-started)
- [Options](#options)
- [Contributing](#contributing)
- [License](#license)

***
## Download
Run one of these commands in your bash according to your needs.

`git clone https://github.com/dcdeiv/simpler-sidebar.git`

`bower install simpler-sidebar`

`npm install simpler-sidebar`

Or download the latest version from the [releases](https://github.com/dcdeiv/simpler-sidebar/releases) pages.

If you are updating, remember to read the [Release History](#release-history) and check for uncompatibility issues.

## Getting Started
You will need to prepare a specified HTML template in order to make it work properly. The code below is just an example from which you can and have to draw inspiration.

```html
<div id="navbar">
	<!--
	#navbar is positioned fixed.

	It does not matter what element #toggle-sidebar is, give it a selector (in this example #toggle-sidebar).
	-->
	<span id="toggle-sidebar" class="button icon"></span>
</div>

<div id="sidebar">
    <!--
    simpler-sidebar will handle #sidebar's position.

    To let the content of your sidebar overflow, especially when you have a lot of content in it, you have to add a "wrapper" that wraps all content.
    -->
    <div id="sidebar-wrapper" class="sidebar-wrapper">
        <!--
        Links below are just an example. Give each clickable element, for example links, a class to trigger the closing animation.
        -->
        <a class="close-sidebar" href="#">Link</a>
        <a class="close-sidebar" href="#">Link</a>
        <a class="close-sidebar" href="#">Link</a>
        <a class="close-sidebar" href="#">Link</a>
    </div>
</div>
```

If you add the sidebar-wrapper (and you should), remember to give it this style attributes:

```css
.sidebar-wrapper {
    position: relative;
    height: 100%;
    overflow: auto;
}
```

At the bottom of the web page, just before the `</body>` tag, include the **jQuery** library. If you are interested in better *easing*, include the **jQuery-UI** library too. Eventually include simpler-sidebar.

```html
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
<script src="https://ajax.googleapis.com/ajax/libs/jqueryui/1.11.4/jquery-ui.min.js"></script>
<script src="simpler-sidebar/dist/jquery.simpler-sidebar.min.js"></script>
```

Call the simpler-sidebar plugin function and fill it with the options you need. Here is an example of some required options. Read the [Options](#options) section for further informations.

```html
<script>
    $(document).ready(function() {
        $('#sidebar').simplerSidebar({
            opener: '#toggle-sidebar',
            sidebar: {
                align: 'left', //or 'right' - This option can be ignored, the sidebar will automatically align to right.
                width: 300, //You can ignore this option, the sidebar will automatically size itself to 300px.
                closingLinks: '.close-sidebar' // If you ignore this option, the plugin will look for all links and this can be buggy. Choose a class for every object inside the sidebar that once clicked will close the sidebar.
            }
        });
    });
</script>
```

## Contributing
Help me improve simpler-sidebar and make it as perfect as possible, but first read the [contribution guidelines](CONTRIBUITING.md).

## License
Dual licensed under the [MIT](LICENSE-MIT) and [GPLv2](LICENSE-GPL) licenses.
