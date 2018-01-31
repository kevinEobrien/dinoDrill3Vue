<template>
<div class="form-div">
   <form id="application-input">    
        <label>Apply Here: </label>
        <textarea id="application-text" rows="8" cols="100" v-model="applicationText"></textarea><br/>
        <input id="submit" type="submit" value="Submit" @click.prevent="submitForm" />
    </form>
    <p id="message">{{message}}</p>
    <button @click="togglePreview = !togglePreview" id="preview-toggle">Show Preview</button>
    <Preview :texty="applicationText" :class="{hidden : togglePreview}"/> 
</div>   
</template>
<script>

import Preview from "./Preview"

export default {
  name: "InputForm",
  components:{
      Preview
      },
   props: {
    // getText: {
    //   type: Function,
    //   required: true
    //     }
    },
    data(){
        return{
            applicationText: "",
            message: "",
            togglePreview: true
        }
    },
    methods:{
    submitForm(){
        this.message = "Your application was submitted!"
            }
     }
}
</script>
<style scoped>

</style>