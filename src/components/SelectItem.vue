<template>
  <div class="text-xs-center">
    <v-img :src="logoPath" class="my-3" contain height="150" />

    <v-btn @click.stop="orderopen = true">注文する</v-btn>
    <v-dialog v-model="orderopen" max-width="290">
      <div :id="formId" >

        <v-card>
          <v-card-title class="headline">{{ item }}</v-card-title>
          <v-text-field v-model="amountmoney" label="円" placeholder="金額を入力" outline />
          <v-card-text>↓↓↓↓下へPull↓↓↓↓</v-card-text>
        </v-card>

      </div>
    </v-dialog>
  </div>
</template>

<script>
export default {
  name: "SelectItem",
  props: {
    item: String,
  },
  data: () => ({
    orderopen: false,
    amountmoney: 0,
  }),
  computed: {
    logoPath: function () {
      return require("../assets/" + this.item + ".svg")
    },
    formId: function () {
      return "form-" + this.item
    },
  },
  mounted: function () {
    // TouchEmulator()
    PullToRefresh.init({
      mainElement: '#' + this.formId,
      triggerElement: '#' + this.formId,
      onRefresh: (done) => {
        done()
        this.orderopen = false
        console.log(this.item + " : " + this.amountmoney)
      },
    })
  },
}
</script>

<style scoped>

</style>

