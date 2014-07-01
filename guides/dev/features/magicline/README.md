# Magic Line

Depending on your environment (OS, browser) it might be difficult to place the cursor and add content near some document elements. This pertains to, for example, images, tables or `<div>` elements that start or end a document, lists, or even adjacent horizontal lines.

CKEditor 4 introduced the [Magic Line](http://ckeditor.com/addon/magicline) plugin that helps overcome these limitations. The plugin is included in the Standard and Full installation packages.

## Usage
The Magic Line plugin causes a red line with a handle (<img src="guides/dev_magicline/magicline_01.png" alt="Magic Line handle">) to appear when you hover you mouse over any such otherwise inaccessible place in an active editor.

{@img magicline_02.png}

When you click the magic line's handle, a new paragraph will be inserted into the document. In this example it was added after a table nested in another table, as visible below.

{@img magicline_03.png}

## Styling the Magic Line

If the default striking red color does not suit you, you can easily modify it by setting the CKEDITOR.config.magicline_color configuration option, for example:

    CKEDITOR.config.magicline_color = '#0000FF';
    
This will change magic line's color to blue, as presented in the image below.

{@img magicline_04.png}

## Keyboard Shortcuts

To further enhance CKEditor's accessibility, the following keyboard shortcuts are available for working with magic line:

* *Shift+Ctrl+3* &ndash; to enable enetring content (by adding a new paragraph) **before** a problematic element.
* *Shift+Ctrl+4* &ndash; to enable entering content (by adding a new paragraph) **after** a problematic element.

You can also adjust the keyboard shortcuts by setting the CKEDITOR.config.magicline_keystrokeNext and CKEDITOR.config.magicline_keystrokePrevious configuration options, respectively. For example:

    // Changes the keyboard shortcut to Ctrl + ".".
    CKEDITOR.config.magicline_keystrokeNext = CKEDITOR.CTRL + 190;
    
    // Changes the keyboard shortcut to Ctrl + ",".
    CKEDITOR.config.magicline_keystrokePrevious = CKEDITOR.CTRL + 188;

## Adjusting List of Elements Activating Magic Line

It is also possible to modify the default list of elements that trigger the appearance of magic line.

The CKEDITOR.config.magicline_putEverywhere option activates the all-encompassing mode which causes magic line to appear for all block-level elements as defined in CKEDITOR.dtd.$block.

    CKEDITOR.config.magicline_putEverywhere = true;

The CKEDITOR.config.magicline_tabuList option lets you blacklist certain elements by providing a list of attributes that, if assigned, prevent magic line from appearing for these elements.

    CKEDITOR.config.magicline_tabuList = [ 'data-tabu' ];

## Magic Line Demo 

See the [working "Magic Line" sample](http://sdk.ckeditor.com/samples/magicline.html) that showcases how Magic Line helps solve issues with cursor placement before or after elements such as nested tables, `<div>` elements, adjacent lists, or multiple horizontal rules.