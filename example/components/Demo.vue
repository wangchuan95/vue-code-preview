<template>
  <div class="demo">
    <VueCodePreview :value="code" parser="vue" :options="{ printWidth: 180 }" />
  </div>
</template>

<script>
import VueCodePreview from '@/components/VueCodePreview.vue';
import 'highlight.js/styles/dark.css';

export default {
  components: { VueCodePreview },
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
</script>

<style scoped>
.demo {
  text-align: left;
}
</style>
