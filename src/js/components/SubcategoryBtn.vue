<template>
  <button class="btn" @click="onBtnClick">{{ name }}</button>
</template>

<script>
export default {
  name: 'subcategory-btn',
  props: ['name'],
  methods: {
    onBtnClick(e) {
      const allButtons = document.querySelectorAll('.subcategories .btn');
      allButtons.forEach((btn) => {
        btn.classList.remove('active');
      });
      e.target.classList.add('active');
      this.$store.commit('updateInteraction', true);
      this.$store.commit('updateSubcategory', this.name)
    }
  }
}
</script>