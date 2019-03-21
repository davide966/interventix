<template>
<f7-page>
  <f7-navbar title="Clienti" back-link="Back" />
  <f7-list media-list v-if="customers">
    <f7-list-item v-for="(customer, key) in customers"
      :title="customer.custname" :subtitle="customer.indfatt"
      :key="key" :text="key + ' (' + customer.id + ')'">
      <f7-icon slot="media" material="face"></f7-icon>
    </f7-list-item>
  </f7-list>
</f7-page>
</template>
<script>
export default {
  data() {
    return {
      customers: null,
      maxEntries: 50,
    }
  },
  created() {
    this.$fireDB('customers').orderByChild('custname').once('value').then((snapshot) => {
      this.customers = snapshot.val()
      console.log(snapshot.val())
    })
  },
}
</script>

<style scoped>
.list-block .item-media {
  min-width: 0;
}

.item-media .material-icons {
  font-size: 30px;
  line-height: 32px;
}

.list-block .item-content {
  padding-left: 8px;
}
</style>
