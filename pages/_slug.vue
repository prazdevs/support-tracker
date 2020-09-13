<template>
  <div>
    <ticket v-for="item in items" :key="item.reference" v-bind="item" />
  </div>
</template>
<script>
  export default {
    async asyncData({ $content, params }) {
      const iteration = await $content('', params.slug).fetch();
      const [prev, next] = await $content('')
        .only(['slug'])
        .sortBy('slug', 'asc')
        .surround(params.slug)
        .fetch();
      return { iteration, prev, next };
    },

    computed: {
      items() {
        return this.iteration.items;
      },
    },
  };
</script>
