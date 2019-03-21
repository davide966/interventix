<template>
  <f7-page>
    <f7-navbar title="Interventi" back-link="Back"  />
    <f7-list media-list v-if="interventis">
      <f7-list-item v-for="(intervento, key) in interventis"
        :title="intervento.descrint" :subtitle="intervento.oremopera"
        :key="key" :text="key + ' Tot: ' + intervento.totint">
        <f7-icon slot="media" material="build"></f7-icon>
      </f7-list-item>
    </f7-list>
  </f7-page>
</template>
<script>
export default {
  data() {
    return {
      interventis: null,
      maxEntries: 50,
    }
  },
  created() {
    // this.$fireDB('interventis').orderByChild('custname').once('value').then((snapshot) => {
    this.$fireDB('interventis').orderByChild('date1').once('value').then((snapshot) => {
      this.interventis = snapshot.val()
      console.log(snapshot.val())
    })
  },
}
</script>
