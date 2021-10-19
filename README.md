<div align="center">
    <h1>vue-json-editor2z</h1>
    <strong>
        <a href="https://github.com/delpikye-v/vue-json-editor">vue-json-editor2z</a>
    </strong>
    <br />
    <br />
    <a href="https://codesandbox.io/s/vue-json-editor-zb4es">LIVE EXAMPLE</a>
</div>

---

### Usage
Install the package
```js
    npm install vue-json-editor2z
```

Import the module in the place you want to use:
```js
    import TextEditor from 'vue-json-editor2z'
    import 'vue-json-editor2z/dist/styles.css'

    Vue.component('editor', TextEditor)
```

#### Snippet
```js
    // json-edtor
    <Editor :dataSource="dataSource" height="400px" @change="editorChange" />
    /*
    editorChange({ error, dataSource }) {
        if (error) {
            this.label = 'JSON syntax error'
            return
        }
        this.dataSource = dataSource
    }
    */

    // =============================
    // =============================
    <Editor :dataSource="dataSource" :showHeader="false" />

    // =============================
    // =============================
    <Editor :dataSource="dataSource" :isFetchLoading="isFetchLoading" />
    <button @click="isFetchLoading = !isFetchLoading">Submit</button> // make lock editor when save api

    // =============================
    // =============================
    <Editor :dataSource="dataSource" :readOnly="true" />

    // =============================
    // no break (scroll x)
    <Editor :dataSource="dataSource" :wrap="false" /> //

    // =============================
    // =============================
    // ace options
    <Editor :dataSource="dataSource" :options="{showGutter : false}" />

    // =============================
    // =============================
    // text-area
    <Editor :dataSource="text" language="text" />
```

### Props
The following props are accepted:

#### language: (string)
```
`json` json editor (default)
`json_view` json view (json-viewer)
`text` like text-area
`...` other [ace](https://github.com/ajaxorg/ace)
```

#### dataSource 
```
if language = `json || json_view`:  any
else: string
```

#### height
height of Editor. `px, %, vh`

#### width
width of Editor. `px, %, vh`

#### readOnly
lock editor

#### wrap (boolean)
`true`   line break if long. (default)

`false`  no break

#### options (object)
see [ace](https://github.com/ajaxorg/ace). It's not necessary, the default has already configured enough info for the editor.

#### theme (string)
see ace theme

#### showSearch (boolean)
`true` search ctrl+f (default)

`false` disabled

#### disabledTab (boolean)
`true` disabled editor tab. (When keypress tab move next component)

`false` (default)

#### showAutoComplete (boolean)
`true` support ctrl+space (default)

`false` disabled

#### suggestDataComplete (array)
custom suggest snippet
```js
suggestDataComplete  = [
   { caption: 'imr', value: 'import react', meta: 'static' },
   ...more
]
```

#### isFetchLoading (boolean)
`true` when submit or fetch data api.

`false` request done.

```make loading spinner when submit or fetch data (not necessary)```


#### customLoading (boolean)
`isFetchLoading = true` && `customLoading = true`

```=> <Editor><div>custom loading</div></Editor>```


#### @change
See snippet

### Example
A working example can be found in the `example` directory. 

```js
npm install
```
```js
npm run dev
npm run start
```

### License
MIT
