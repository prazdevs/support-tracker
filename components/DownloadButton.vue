<template>
  <b-button v-b-tooltip.hover variant="success" title="Click to download">
    <b-icon-download />
    Patch available
  </b-button>
</template>

<script>
  export default {
    name: 'DownloadButton',
    props: {
      link: {
        type: String,
        required: true,
      },
    },
  };
</script>

<style></style>
