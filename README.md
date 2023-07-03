# Quote Tool

Provides Quote Blocks for the [Editor.js](https://editorjs.io).

> **Warning:**  
> This is a fork of the upstream repository, that removes the alignment options, because I already handle alignment using https://github.com/kaaaaaaaaaaai/editorjs-alignment-blocktune, and the two options conflicted. If you want the most up-to-date version of the plugin, or you do need the alignment options, please use the [upstream](https://github.com/editor-js/quote) repo instead.

## Installation

### Download to your project's source dir

1. Upload folder `dist` from repository
2. Add `dist/bundle.js` file to your page.

### Load from CDN

You can load specific version of package from [jsDelivr CDN](https://www.jsdelivr.com/package/npm/@editorjs/quote).

`https://cdn.jsdelivr.net/npm/@editorjs/quote@latest`

Then require this script on page with Editor.js.

```html
<script src="..."></script>
```

## Usage

Add a new Tool to the `tools` property of the Editor.js initial config.

```javascript
var editor = EditorJS({
  ...
  
  tools: {
    ...
    quote: Quote,
  },
  
  ...
});
```

Or init Quote Tool with additional settings

```javascript
var editor = EditorJS({
  ...
  
  tools: {
    ...
    quote: {
      class: Quote,
      inlineToolbar: true,
      shortcut: 'CMD+SHIFT+O',
      config: {
        quotePlaceholder: 'Enter a quote',
        captionPlaceholder: 'Quote\'s author',
      },
    },
  },
  
  ...
});
```

## Config Params

| Field              | Type     | Description                 |
| ------------------ | -------- | ----------------------------|
| quotePlaceholder   | `string` | quote's placeholder string  |
| captionPlaceholder | `string` | caption's placeholder string|

## Output data

| Field     | Type     | Description          |
| --------- | -------- | -------------------- |
| text      | `string` | quote's text         |
| caption   | `string` | caption or an author |


```json
{
    "type" : "quote",
    "data" : {
        "text" : "The unexamined life is not worth living.",
        "caption" : "Socrates"
    }
}
```
