<script>
  // pages/sample-editor.vue

  export default {
    data() {
      return {
        editorInput: '<p class="test">test</p>',
      };
    },
  };
</script>

<template>
  <rich-editor
    v-model="editorInput"
    @input="(event) => (editorInput = event)"
  />

  <div>
    <div class="container mt-3">
      <div class="row">
        <h2 class="col-md-12">Output</h2>
        <div>{{ editorInput }}</div>
      </div>
    </div>
    <div class="container mt-3">
      <div class="row">
        <h2 class="col-md-12">Preview</h2>
        <div v-html="editorInput"></div>
      </div>
    </div>
  </div>
</template>

<style>
  .test {
    background-color: red;
  }
</style>
