<template>
  <div class="columns">
    <div class="column is-4 is-offset-4">
      <div class="field">
        <!-- <input type="text" name="" id="" v-model="userId"><br />
        <input type="text" name="" id="" v-model="id"><br />
        <input type="text" name="" id="" v-model="title"><br />
        <input type="text" name="" id="" v-model="body"><br /> -->
        <button class="button is-primary" @click="fetch">Get User</button>
      </div>

      <div>
        <template v-for="user in users">
            <div :key="user.id">
                <div class="colum">
                <div class="card">
                    <header class="card-header">
                        <p class="card-header-title">
                            <label for="">UserId :&nbsp;</label>
                            {{user.id}}
                        </p>
                        <a href="#" class="card-header-icon" aria-label="more options">
                        <span class="icon">
                            <i class="fas fa-angle-down" aria-hidden="true"></i>
                        </span>
                        </a>
                    </header>
                <div class="card-content">
                    <div class="content">
                        <label for=""><strong>Title :</strong></label>
                        {{user.title}}<hr>
                        <label for=""><strong>Body :</strong></label>
                        {{user.body}}
                    </div>
                </div>
            </div><br>
            </div>
                <!-- <label for="">UserId :</label>
                {{user.id}}
                <label for="">Title :</label>
                {{user.title}}
                <label for="">Body :</label>
                {{user.body}} -->
        </div>
    </template>
      </div>

    </div>
  </div>

</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      user:{
        userId: null,
        id: null,
        title: '',
        body: ''
      },
      users:[]
    }
  },
  methods:{
    async fetch(){
      let {data} = await axios.get('https://jsonplaceholder.typicode.com/posts')
      this.users= data
      console.log(this.users)
    }
  }
}
</script>