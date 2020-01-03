<template>
  <section class="recipes">
    <recipe
      v-for="recipe in recipes"
      :id="recipe.id"
      :key="recipe.id"
      :thumbnail="recipe.thumbnail"
      :title="recipe.title"
      :preview-text="recipe.previewText"
    />
  </section>
</template>

<script>
import Recipe from '@/components/Recipe'

export default {
  components: {
    Recipe
  },

  asyncData() {
    return new Promise((resolve, reject) => {
      resolve({
        recipes: [
          {
            id: '1',
            thumbnail:
              'https://image.shutterstock.com/display_pic_with_logo/136306/722718082/stock-photo-healthy-food-clean-eating-selection-fruit-vegetable-seeds-superfood-cereals-leaf-vegetable-on-722718082.jpg',
            title: 'Vegetables',
            previewText: 'Vegetables and fruits for a healthy meal'
          },
          {
            id: '2',
            thumbnail:
              'https://restaurantden.com/wp-content/uploads/2017/09/iso-republic.jpg',
            title: 'Title',
            previewText: 'Text...'
          }
        ]
      })
    })
  }
}
</script>

<style scoped>
.recipes {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
}
</style>
