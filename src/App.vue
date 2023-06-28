<template>
  <div>

    <div class="row gap-3">

      <div class="col-3" v-for="(elem, index) in infoApi">
        <div class="card">
          <div class="card-body">
            <h5 class="card-title">{{ elem.name }}</h5>
            <p class="card-text">{{ elem.description }}</p>
            <a href="#" class="btn btn-primary">Go somewhere</a>
          </div>
        </div>
      </div>

    </div>

  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      infoApi: []
    }
  },
  methods: {
    callApi(){
      axios.get('http://127.0.0.1:8000/api/project').then(res => {
        this.infoApi = res.data.projects
        console.log(this.infoApi)
      })
    }
  },
  created() {
    this.callApi()
  },
}
</script>

<style>
  
</style>
