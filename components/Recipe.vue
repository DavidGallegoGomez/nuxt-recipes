<template>
  <nuxt-link :to="'/recipes/' + id">
    <article class="recipe">
      <div
        :style="{ backgroundImage: 'url(' + thumbnail + ')' }"
        class="thumbnail"
      ></div>
      <h1>{{ title }}</h1>
      <p>{{ previewText }}</p>
    </article>
  </nuxt-link>
</template>

<script>
export default {
  props: {
    thumbnail: {
      type: String,
      default:
        'https://image.shutterstock.com/display_pic_with_logo/136306/722718082/stock-photo-healthy-food-clean-eating-selection-fruit-vegetable-seeds-superfood-cereals-leaf-vegetable-on-722718082.jpg'
    },
    title: {
      type: String,
      default: 'My Title'
    },
    previewText: {
      type: String,
      default: 'Some text...'
    },
    id: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
a {
  text-decoration: none;
  color: black;
}
.recipe {
  box-sizing: border-box;
  width: 300px;
  padding: 10px;
  border: 1px solid grey;
  box-shadow: 0 2px 2px #aaa;
  margin: 10px;
}
.thumbnail {
  background-position: center;
  background-size: cover;
  width: 100%;
  height: 200px;
}
</style>
