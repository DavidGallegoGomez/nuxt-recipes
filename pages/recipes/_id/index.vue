<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img :src="recipe.thumbnail" :alt="recipe.title" class="recipe-image" />
    </div>
    <p>{{ recipe.description }}</p>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      resolve({
        recipe: [
          {
            id: '1',
            thumbnail:
              'https://image.shutterstock.com/display_pic_with_logo/136306/722718082/stock-photo-healthy-food-clean-eating-selection-fruit-vegetable-seeds-superfood-cereals-leaf-vegetable-on-722718082.jpg',
            title: 'Vegetables',
            previewText: 'Vegetables and fruits for a healthy meal',
            description:
              'Lorem ipsum dolor sit amet consectetur adipisicing elit. Explicabo nam, repellendus fugit unde eos labore doloremque delectus fuga officia porro?'
          },
          {
            id: '2',
            thumbnail:
              'https://restaurantden.com/wp-content/uploads/2017/09/iso-republic.jpg',
            title: 'Title',
            previewText: 'Text...',
            description:
              'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas aut obcaecati, inventore neque minus illum!'
          }
        ].find((el) => el.id === context.params.id)
      })
    })
  }
}
</script>

<style scoped>
.single-recipe {
  display: flex;
  flex-flow: column wrap;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}
.recipe-image {
  width: 100%;
}
</style>
