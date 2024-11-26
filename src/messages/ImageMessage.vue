<template>
  <div class="image" :style="messageColors">
    <div class="file">
      <picture>
        <img :src="data.file.url" :alt="data.text" />
      </picture>
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
.image {
  --player-color-text: #c5c6c8;
  --player-color-featured: #00e5c0;
  --player-color-background: #262d31;

  display: inline-flex;
  min-width: 240px;
  width: 336px;
  max-width: 100%;
  border-radius: 0.4rem;
  padding: 0.4rem;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
  user-select: none;
  background: var(--player-color-background);
}

.image + .image {
  margin-top: 1rem;
}

.image .file {
  flex: 1;
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
}

.image .file picture {
  margin: 1em auto 2em;
}

.image .file picture img {
  max-width: 100%;
  border-radius: 0.4rem;
}
</style>
