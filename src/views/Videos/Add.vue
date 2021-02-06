<template lang="">
    <div class ="view-add">
        <form @submit.prevent="handleSubmit">
  <div class="mb-3">
    <label class="form-label">Título</label>
    <input v-model="form.title" type= "text" class="form-control"  aria-describedby="emailHelp">
   
  </div>
  <div class="mb-3">
    <label class="form-label">URL Video</label>
    <input v-model="form.url" type= "text" class="form-control" >
  </div>
  <div class="mb-3">
    <label class="form-label">Descripción</label>
    <textarea  v-model="form.description" rows="6" class="form-control" >
    </textarea>
  </div>
  <div class="d-flex justify-content-center" >
      <Button class="me-4" type="primary" type-button="submit">Agregar</Button>
      <Button>Cancelar</Button>
      </div>
  
  
</form>
    </div>
</template>
<script>
import Button from "@/ui/Button.vue";
import {mixin} from "@/mixin/mixin";
export default {
    name: "VideoAdd",
    mixin: [mixin],
components: {
    Button,
},
data(){
  return {
    form:{
      title:"",
      url: "",
      description:"",
    },
  };
},
methods: {
saveVideo(payload){
  fetch("http://localhost:3000/videos",{
  method: 'POST',
  body: JSON.stringify(payload),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
  });
},

async handleSubmit() {
  try{
await this.saveVideo(this.form);
 alert('Se creó correctamente')
 this.$router.push("/");
 } catch(e) {
this.alertError(e)
  }
  
},
},
};
</script>
<style lang="scss">
    
</style>