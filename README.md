# vue-code-preview

A vue code viewer component based on [Prettier](https://github.com/prettier/prettier) and [Highlight.js plugin for Vue.js v2](https://github.com/highlightjs/vue-plugin/tree/1-stable).

![default](https://github.com/wangchuan95/vue-code-preview/blob/main/themes/default.png 'default')

![dark](https://github.com/wangchuan95/vue-code-preview/blob/main/themes/dark.png 'dark')

![gradient-light](https://github.com/wangchuan95/vue-code-preview/blob/main/themes/gradient-light.png 'gradient-light')

## Installation

```bash
npm install vue-code-preview
# or
yarn add vue-code-preview
```

## Usage

### Import

```javascript
import VueCodePreview from 'vue-code-preview';
import 'highlight.js/styles/dark.css'; // import a style file

Vue.component('VueCodePreview', VueCodePreview);
```

### Example

```html
<VueCodePreview value="<h1>Hello World</h1>" />

<VueCodePreview :value="code" parser="vue" :options="{ printWidth: 180 }" />
```

```javascript
export default {
  data() {
    return {
      code: `
      <template>
        <h1>Hello World!</h1>
      </template>

      <script>
      export default {
        name: 'HelloWorld',
      };
      <\/script>
      `,
    };
  },
};
```

### Props

|    prop    | description                                                                    |  type   |                                                                    default                                                                     |
| :--------: | ------------------------------------------------------------------------------ | :-----: | :--------------------------------------------------------------------------------------------------------------------------------------------: |
|   value    | source code                                                                    | String  |                                                                       ''                                                                       |
|   parser   | [Prettier Parser](https://www.prettier.cn/docs/options.html#parser)            | String  |                                                                     'vue'                                                                      |
|  options   | [Prettier Options](https://www.prettier.cn/docs/options.html)                  | Object  | { printWidth: 80, tabWidth: 2, useTabs: false, endOfLine: 'auto', singleQuote: false, semi: true, trailingComma: 'all', bracketSpacing: true } |
|  language  | [Highlight.js plugin](https://github.com/highlightjs/vue-plugin/tree/1-stable) | String  |                                                                       ''                                                                       |
| autodetect | [Highlight.js plugin](https://github.com/highlightjs/vue-plugin/tree/1-stable) | Boolean |                                                                      true                                                                      |

## License

MIT
