# Installing from GitHub

1. Click the "Download Source" button.
2. Unzip the download
3. Rename the folder to JavaScript-tools.tmbundle
4. Double-click
5. TextMate handles the rest!

# Commands

## Validate

> With JavaScript Lint, you can check all your JavaScript source code for common mistakes without actually running the script or opening the web page.
<http://javascriptlint.com/>

*   **Validate with Javascript Lint** (⌃⇧V)
    
    Uses Matthias Miller's JavaScript Lint to check your script for errors and warnings and shows the results in a new window. The *Validate JavaScript* window will give you a description and hyperlink when problems are found. The hyperlink will take you straight to the line and column where JavaScript Lint suspects the problem arises.

*   **Validate Quick with Javascript Lint** (⌘S)
    
    Same as above except that instead of a dedicated window you simply get a tooltip showing the number of errors and warnings. This command overrides the Save behavior so every time you save your javascript it will be passed through Javascript Lint. Of course it only applies to javascript files so you don't need to worry about accidentally Javascript Lint'ing your non-javascript files.

*   **Edit JSLint Validation Settings**
    
    Allows you to customize what Javascript Lint considers when checking your script. The format and meaning of the options are straightforward and well documented within the settings file itself.

*   **Validate with Google Closure Compiler**

    Uses the Google Closure Compiler to check your script for errors and warnings and shows the results in a new window. The Closure Compiler provides warnings for illegal JavaScript and warnings for potentially dangerous operations, helping you to produce JavaScript that is less buggy and and easier to maintain.

## Compress

*   **Compress with JSMin** (⌃⌘C)

    Uses Douglas Crockford's JSMin to minimize your current javascript document. It will not do any semi-colon insertion or removal.

*   **Minimize Selection with JSMin** (⌃⌥⇧Q) 

    Same as the above except it only applies to the selected portion of your current javascript document.

*   **Compress with Dojo Shrinksafe** (⌃⌘C)

    Uses a custom Rhino build from the Dojo Toolkit project to compress your current javascript document. Before compressing it attempts to insert missing semi-colons so you should consider running *Validate Syntax* and fixing missing semi-colons prior to using this command.

*   **Compress with Dean Edwards Packer** (⌃⌘C)

    Compresses and obfuscates your current javascript document. It currently relies on the Packr ruby port which is based on version 3 of Packer. According to Dean Edwards, **"All statements, *including function declarations*, must be correctly terminated with semi-colons"** before you run this command. After an email exchange with James Coglan, author of Packr, it's been decided that base62 encoding not be on by default as having it off yields more efficiency when your scripts are gzipped.  

    However, if you would like base62 encoding, just set the Variable `TM_JST_PB62` to `true` in the Advanced pane of the TextMate preferences or in your TextMate Project variables (see the TextMate documentation for more info on setting environment variables).

*   **Compress with Google Closure Compiler** (⌃⌘C)

    Compresses your current javascript document. The Closure Compiler reduces the size of your JavaScript files and makes them more efficient, helping your application to load faster and reducing your bandwidth needs.

*   **Compress with YUI Compressor** (⌃⌘C)

    Compresses your current javascript document. By default it assumes your character set is UTF-8. Additionally it strictly preserves semi-colons, i.e. it will not drop or attempt to insert any semi-colons. Both of these settings can be easily changed by opening the Bundle editor and adjusting the second line of this command through the Bundle editor.

*   **Compress with YUI Compressor CSS** (⌃⌘C)

    Yikes, a CSS tool in the Javascript Tools bundle!  Minifies your current CSS document by removing all unneeded whitespaces and comments.

## Formatting

*   **Format Javascript** (⌃Q)

    Attempts to clean up your javascript by inserting uniform line breaks and indentation throughout your current document or selection.

*   **Reformat with JS Beautifier** (⌃⇧H)

    Uses Einar Lielmanis' [JS Beautifier][jbeau] to reformat and reindent bookmarklets, ugly javascript, unpack scripts packed by Dean Edward's packer, as well as deobfuscate scripts processed by javascriptobfuscator.com.

## Bookmarklets

*   **Convert Javascript to Bookmarklet** (⌃⌥⇧Q)

    Turns your current javascript selection or document into a [bookmarklet][bkml] for use in a web browser.

*   **Convert Bookmarklet to Javascript** (⌃⌥⇧Q)

    Does the opposite of the above; turns an existing bookmarklet into a standard javascript.

# Licenses

* **[JavaScript Lint][lint]** Based on [SpiderMonkey][smonk], which is licensed under the [MPL][mpl]/[GPL][gpl]/[LGPL][lgpl] tri-license
* **[Dojo Toolkit][dojo]** [BSD License][dbsd] or [Academic Free License version 2.1][dafl]
* **[Rhino][rhino]** [MPL 1.1/GPL 2.0][rmpl] [except where noted][radd]
* **[Dean Edwards Packer][pack]** [LGPL License][lgpl]
* **[Packr][packr]** [MIT License][mit]
* **[YUI! Compressor][yuic]** [BSD License][ybsd]
* **[JSMin][jsmin]** Copyright 2001 Douglas Crockford
* **[JS Beautifier][jbeau]** Copyright 2009 Einar Lielmanis

[rhino]:  http://developer.mozilla.org/en/docs/Rhino_documentation
[rmpl]:   http://www.mozilla.org/MPL/
[radd]:   http://developer.mozilla.org/en/docs/Rhino_License
[dojo]:   http://dojotoolkit.org/docs/shrinksafe
[dbsd]:   http://trac.dojotoolkit.org/browser/dojo/trunk/LICENSE#L13
[dafl]:   http://trac.dojotoolkit.org/browser/dojo/trunk/LICENSE#L43
[pack]:   http://dean.edwards.name/packer/
[packr]:  http://blog.jcoglan.com/packr/
[lint]:   http://www.javascriptlint.com/
[lgpl]:   http://creativecommons.org/licenses/LGPL/2.1/
[mit]:    http://www.opensource.org/licenses/mit-license
[yuic]:   http://developer.yahoo.com/yui/compressor/
[ybsd]:   http://developer.yahoo.com/yui/license.html
[jsmin]:  http://www.crockford.com/javascript/jsmin.html
[bkml]:   http://en.wikipedia.org/wiki/Bookmarklet
[mpl]:    http://www.mozilla.org/MPL/MPL-1.1.html
[gpl]:    http://www.gnu.org/copyleft/gpl.html
[lgpl]:   http://www.gnu.org/licenses/lgpl.html
[smonk]:  http://www.mozilla.org/js/spidermonkey/
[jbeau]:  http://jsbeautifier.org/