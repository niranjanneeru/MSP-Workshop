<template>
  <div class="appcontainer">
    <div class="logo" style="margin-bottom: 10px;margin-top: 20px">

      <svg width="48" height="48" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M17.8 18.0996L10.4 25.3996L6.2 21.2996L4 23.4996L10.4 29.8996L20 20.2996L17.8 18.0996Z"
              fill="#3F51B5"/>
        <path d="M17.8 5.09961L10.4 12.3996L6.2 8.29961L4 10.4996L10.4 16.8996L20 7.29961L17.8 5.09961Z"
              fill="#3F51B5"/>
        <path d="M17.8 31.0996L10.4 38.3996L6.2 34.2996L4 36.4996L10.4 42.8996L20 33.2996L17.8 31.0996Z"
              fill="#3F51B5"/>
        <path d="M24 22H44V26H24V22Z" fill="#90CAF9"/>
        <path d="M24 9H44V13H24V9Z" fill="#90CAF9"/>
        <path d="M24 35H44V39H24V35Z" fill="#90CAF9"/>
      </svg>


    </div>

    <p style="font-size: 22px">todo</p>


    <div v-for="item in $store.state.todos" v-if="item.completed===true">


      <div class="row" style="border-bottom: 1px solid lightgrey;">


        <div class="col-2" style="border-right: 1px solid lightgrey ;padding-top: 5px">

          <button @click="deletetodo(item.id)" class="deletebtn"><i class="material-icons" style="color: red">close</i>
          </button>
        </div>
        <div class="col-8" style="padding-top: 5px">

          <span>{{  item.text  }}</span>
        </div>
        <div class="col-2" style="padding-top: 5px">


        </div>


      </div>


    </div>




    <div style="margin-top: 20px">


      <router-link to="/">


        <i class="material-icons" style="position: relative;top:7px;width:30px">arrow_backward </i>
        todo({{this.$store.state.count}})
       </router-link>

    </div>

  </div>
</template>

<script>
  export default {
    name: 'Home',


    data() {


      return {


        inputvalue: "",


      }
    },

    methods: {





      deletetodo(id) {

        this.$store.state.todos = this.$store.state.todos.filter(function (x) {

          return id !== x.id


        })

        console.log(this.$store.state.todos)


      },




    }


  }
</script>
<style>
  .deletebtn, .donebtn, .addbtn {

    background-color: transparent;
    border: none;

  }

  .appcontainer {


    width: 350px;
    height: 500px;
    margin: auto;
    text-align: center;


  }
</style>
