<template>
    <div>
        <section id="application-preview">{{texty}}</section>
   </div>
   
</template>
<script>
export default {
  name: "Preview",
  props: {
      texty:{
        type: String,
        required: true
      }
    }
}
</script>
<style scoped>
#application-preview {
  border-radius: 6px;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.3);
  border: 1px solid darkgrey;
  min-height: 100px;
  margin-top: 20px;
  padding: 10px;
  text-align: left;
}

</style>