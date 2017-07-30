CKEditor 5 classic build
========================================

[![Join the chat at https://gitter.im/ckeditor/ckeditor5](https://badges.gitter.im/ckeditor/ckeditor5.svg)](https://gitter.im/ckeditor/ckeditor5?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![npm version](https://badge.fury.io/js/%40ckeditor%2Fckeditor5-build-classic.svg)](https://www.npmjs.com/package/@ckeditor/ckeditor5-build-classic)
[![Dependency Status](https://david-dm.org/ckeditor/ckeditor5-build-classic/status.svg)](https://david-dm.org/ckeditor/ckeditor5-build-classic)
[![devDependency Status](https://david-dm.org/ckeditor/ckeditor5-build-classic/dev-status.svg)](https://david-dm.org/ckeditor/ckeditor5-build-classic?type=dev)

Classic build of CKEditor 5. Features the [classic creator](https://github.com/ckeditor/ckeditor5-editor-classic) and the standard set of article features.

## Bundles

The package contains two bundles of the classic editor:

* `build/ckeditor.js` &ndash; A minified, ES6 version of the bundle.
* `build/ckeditor.compat.js` &ndash; A minified, backward-compatible version of the bundle ([babel-preset-env](https://github.com/babel/babel-preset-env) is configured to support `'last 2 versions'`, `'ie >= 11'`).

## Usage

First, install the build from npm:

```
npm install --save @ckeditor/ckeditor5-build-classic
```

And use it in your website:

```html
<div id="editor">
	<p>This is the editor content.</p>
</div>
<script src="./node_modules/@ckeditor/ckeditor5-build-classic/build/ckeditor.js"></script>
<script>
ClassicEditor.create( document.querySelector( '#editor' ) )
	.then( editor => {
		window.editor = editor;
	} )
	.catch( err => {
		console.error( err.stack );
	} );
</script>
```

Or in your JavaScript application:

```js
import { ClassicEditor } from '@ckeditor/ckeditor5-build-classic/build/ckeditor';

// Or using CommonJS verion:
// const ClassicEditor = require( '@ckeditor/ckeditor5-build-classic/build/ckeditor' ).ClassicEditor;

ClassicEditor.create( document.querySelector( '#editor' ) )
	.then( editor => {
		window.editor = editor;
	} )
	.catch( err => {
		console.error( err.stack );
	} );
```

**Note:** If you are planning to integrate CKEditor 5 deep into your application it is actually more convenient and recommended to install and import the source modules directly (like it happens in `ckeditor.js`).

## Rebuilding the bundle

**Note:** This section assumes that you cloned this package repository and execute the commands inside it.

You can modify `build-config.js` or any of the webpack configurations and run:

```
npm run build
```

to rebuild the entry point (`ckeditor.js`) and both builds (`build/*`).

You can also modify `ckeditor.js` directly and run one of `npm run build-ckeditor` or `npm run build-ckeditor-compat`.

## License

Licensed under the GPL, LGPL and MPL licenses, at your choice. For full details about the license, please check the `LICENSE.md` file.
