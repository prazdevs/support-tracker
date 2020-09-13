<template>
  <b-badge
    pill
    :variant="variant"
    class="d-flex align-items-center text-uppercase font-weight-normal"
    style="font-size: 16px"
  >
    <component :is="icon" class="mr-1" />
    {{ type }}
  </b-badge>
</template>

<script>
  import {
    BIconBoxSeam,
    BIconBug,
    BIconGem,
    BIconHeadset,
  } from 'bootstrap-vue';

  export default {
    name: 'TicketType',
    props: {
      type: {
        type: String,
        required: true,
      },
    },
    computed: {
      icon() {
        switch (this.type) {
          case 'bug':
          case 'declaration':
            return BIconBug;
          case 'intervention':
            return BIconHeadset;
          case 'patch':
            return BIconBoxSeam;
          case 'feature':
            return BIconGem;
          default:
            return '';
        }
      },
      variant() {
        switch (this.type) {
          case 'patch':
          case 'bugfix':
            return 'success';
          case 'bug':
            return 'danger';
          case 'intervention':
            return 'warning';
          case 'feature':
            return 'info';
          default:
            return '';
        }
      },
    },
  };
</script>

<style></style>
