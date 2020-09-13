<template>
  <div class="mb-2">
    <b-card-header
      class="d-flex flex-row justify-content-between align-items-center"
    >
      <h5 style="margin: 0">{{ reference }}</h5>
      <ticket-type :type="type" />
    </b-card-header>
    <b-card-body>
      <b-card-title>{{ subject }}</b-card-title>
      <b-card-text><b-icon-calendar /> {{ formattedDate }}</b-card-text>
      <b-card-text>
        {{ description }}
      </b-card-text>
    </b-card-body>
    <b-card-footer>
      <download-button link="https://google.com" />
    </b-card-footer>
  </div>
</template>

<script>
  import moment from 'moment';

  export default {
    name: 'Ticket',
    props: {
      reference: {
        type: String,
        default: '',
      },
      date: {
        type: String,
        default: '',
      },
      type: {
        type: String,
        default: '',
      },
      subject: {
        type: String,
        default: '',
      },
      description: {
        type: String,
        default: '',
      },
    },
    computed: {
      formattedDate() {
        return moment(this.date).format('DD/MM/YYYY');
      },
    },
  };
</script>

<style>
  h5 {
    margin-bottom: none;
  }
</style>
