/* eslint-disable */
<template>
  <div class="container-fluid">

    <div class="row" >
      <div class="col"><historyListview /></div>
      <div id="historyInfo" class="col history-info-view"><historyInfoview /></div>
      <div class="col client-info-view">
        <h2 style="text-transform: uppercase">{{ currentName }}</h2>
        <div class="add-top-padding">
          <h3>Submitted</h3>
          <p>{{ submittedDate }}</p>
        </div>
        <div class="add-top-padding"><clientinfoview /></div>
      </div>
    </div>

  </div>
</template>

<script>
/* eslint-disable */
  import historyInfoview from '@/components/application/Examine/Recipe/history/historyInfo.vue';
  import historyListview from '@/components/application/Examine/Recipe/history/historyList.vue';
  import clientinfoview from '@/components/application/Examine/client/ClientInfo.vue';

  export default {
    name: 'historyRecipe',
    computed: {
      currentName() {
        return this.$store.getters.currentName;
      },
      submittedDate() {
        return this.$store.getters.submittedDate;
     },

    },
    components: {
      historyInfoview,
      historyListview,
      clientinfoview
    },
  }
</script>

<style scoped>
  .history-info-view {
    padding: 1px;
    margin-right: 1px;
  }
  .client-info-view {
    border: 1px solid #b3d9ff;
    background-color: #efefef;
    padding: 2px;
  }
</style>
