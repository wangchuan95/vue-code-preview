<template>
  <highlightjs :code="code" v-bind="hljsAttrs" v-on="$listeners" />
</template>

<script>
const prettier = require('prettier/standalone');
const plugins = (function () {
  var r = require.context('prettier', false, /parser-\S+\.js$/);
  return r.keys().map((key) => r(key));
})();

import hljs from 'highlight.js/lib/core';
import hljsVuePlugin from '@highlightjs/vue-plugin';
import 'highlight.js/styles/default.css';

export default {
  name: 'vue-code-preview',
  inheritAttrs: false,
  components: {
    highlightjs: hljsVuePlugin.component,
  },
  props: {
    value: {
      type: String,
      default: () => '',
    },
    // https://www.prettier.cn/docs/options.html#parser
    parser: {
      type: String,
      default: () => 'vue',
    },
    // https://www.prettier.cn/docs/options.html
    options: {
      type: Object,
      default: () => ({
        printWidth: 80,
        tabWidth: 2,
        useTabs: false,
        endOfLine: 'auto',
        singleQuote: false,
        semi: true,
        trailingComma: 'all',
        bracketSpacing: true,
      }),
    },
  },
  computed: {
    code() {
      let code = this.value;
      let parser = this.parser;
      let options = Object.assign({}, this.options);

      code = prettier.format(code, {
        parser,
        plugins,
        ...options,
      });

      return code;
    },
    // https://github.com/highlightjs/vue-plugin/tree/1-stable
    hljsAttrs() {
      return {
        autodetect: true,
        ...this.$attrs,
      };
    },
  },
};
</script>
