<div align="center">
    <h1>vue-json-editor-z</h1>
    <strong>
        <a href="https://github.com/delpikye-v/vue-json-editor">vue-json-editor-z</a>
    </strong>
    <br />
    <a href="https://codesandbox.io/s/vue-json-editor-zb4es">LIVE EXAMPLE</a>
</div>

---

#### Description
+ Simple vue-json-editor
+ Apply `perfect scrollbar`


#### Usage
Install the package
```js
    npm install vue-json-editor-z
```

Import the module in the place you want to use:
```js
    import TextEditor from 'vue-json-editor-z'
    import 'vue-json-editor-z/dist/styles.css'
    import 'perfect-scrollbar/css/perfect-scrollbar.css'; // perfect-scrollbar

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

`options` and `theme`: see [brace](https://www.npmjs.com/package/brace)
It's not necessary, the default has already configured enough info for the editor.


| **props**               | **type**   | **description**                                            |
|-------------------------|------------|------------------------------------------------------------|
| language                | String     | `json/json_view/text`                                      |
| dataSource              |            | if [`json or json_view` any]. [else `string`]              |
| height                  | String     | px, %, vh                                                  |
| width                   | String     | px, %, vw                                                  |
| readOnly                | boolean    |                                                            |
| wrap                    | boolean    | breakline. Default `true`                                  |
| showSearch              | boolean    | search ctrl+f. Default `true`                              |
| disabledTab             | boolean    | When keypress tab move next component. Default `false`     |
| showAutoComplete        | boolean    | Ctrl+space. Default `true`                                 |
| isFetchLoading          | boolean    | when submit or fetch data api (`true`). Done `false`       |
| customLoading           | boolean    |<Editor><div>custom loading</div></Editor>                  |
| change                  | function   |See snippet                                                 |

#### suggestDataComplete (array)
custom suggest snippet
=> `It's not necessary`
```js
suggestDataComplete  = [
   { caption: 'imr', value: 'import react', meta: 'static' },
   ...more
]
```

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
