<template>

<div>

<div>
  ID:{{id}}
</div>
<div>
  body:{{body}}
</div>

  <q-btn class="btn1" @click="closePostModal"  color="primary" label="Close" />


</div>

</template>

<script>
    export default {
        name: "PostModal",
        props: {
          id: Number,
          body: String
         },
        methods: {
        closePostModal () {
          this.$emit('closePostModal', false )
        },
       }

       }
</script>

<style scoped>


</style>
