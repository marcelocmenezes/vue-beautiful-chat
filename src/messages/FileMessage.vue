<template>
  <div class="attachment" :style="messageColors">
    <div class="file">
      <object :data="data.file.url">
        <p>File cannot be displayed.</p>
      </object>

      <a
        type="button"
        class="btn-download"
        title="Baixar arquivo anexado"
        :href="data.file.url"
        target="_blank"
      >
        <span class="material-icons">download</span>
      </a>
      <span>{{ data.text }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      required: true
    },
    messageColors: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.attachment {
  --player-color-text: #c5c6c8;
  --player-color-featured: #00e5c0;
  --player-color-background: #262d31;

  display: inline-flex;
  /* min-width: 240px;
  width: 336px;
  max-width: 100%; */
  border-radius: 0.4rem;
  padding: 0.4rem;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
  user-select: none;
  background: var(--player-color-background);
}

.attachment + .attachment {
  margin-top: 1rem;
}

.attachment .file {
  flex: 1;
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
}

.attachment .file object {
  width: 100%;
}

.attachment .file .btn-download {
  outline: none;
  appearance: none;
  cursor: pointer;
  background: none;
  border: 0;
  padding: 0 0.8rem 0 0.8rem;
  margin: 15px auto;
}

.attachment .file .btn-download:disabled {
  cursor: default;
}

.attachment .file .btn-download span {
  color: var(--player-color-text);
  font-size: 38px;
  opacity: 0.8;
}
</style>
