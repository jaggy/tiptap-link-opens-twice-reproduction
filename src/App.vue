<script setup>
import {Editor, EditorContent} from '@tiptap/vue-3'
import StarterKit from '@tiptap/starter-kit'
import Link from '@tiptap/extension-link'

const editor = new Editor({
  content: '<p><a href="https://duckduckgo.com/">This is a link to DuckDuckGo</a></p>',
  extensions: [
    StarterKit,
    Link,
  ],
})

const reader = new Editor({
  editable: false,
  content: '<p><a href="https://duckduckgo.com/">This is a link to DuckDuckGo</a></p>',
  extensions: [
    StarterKit,
    Link,
  ],
})

</script>

<template>
  <main>
    <h1>Editor Link Issue</h1>

    <div class="editors">
      <div>
        <h2><code>editable: true</code></h2>
        <EditorContent :editor="editor" />
      </div>

      <div>
        <h2><code>editable: false</code></h2>
        <EditorContent :editor="reader" />
      </div>
    </div>
  </main>
</template>

<style scoped>
.editors {
  margin-top: 2rem;
  display: grid;
  gap: 4rem;
}
</style>
