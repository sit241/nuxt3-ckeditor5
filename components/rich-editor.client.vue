<script setup>
  // components/rich-editor.client.vue

  defineProps({
    value: {
      type: String,
    },
  });
  const emit = defineEmits(['input']);
  const emitInput = (event) => {
    emit('input', event);
  };
  const { $ckeditor } = useNuxtApp();
  const editor = $ckeditor.customEditor;
</script>

<template>
  <ckeditor
    :editor="editor"
    :value="value"
    @input="emitInput"
  />
</template>
