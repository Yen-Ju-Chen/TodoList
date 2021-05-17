<template>
  <div class="view">
      <h1 class="title">{{title}}</h1>

      <input v-model="newStr" @keyup.enter= "addData"/>

      <ul>
          <li v-for="item in items" v-bind:class="{finish:item.isFinished}" 
          @click="toggleFinish(item)">
              {{item.text}}
          </li>
      </ul>
  </div>
</template>

<script>
export default{
    name: "List",
    data () {
        return {
            title: "TodoList",
            items:[
            // {
            //     text: "今天晚上6:00跑步",
            //     isFinished: true
            // },
            // {
            //     text: "今天早餐",
            //     isFinished: false
            // },
            ],
            newStr: ''
        }
    },
    methods: {
        toggleFinish (item) {
            item.isFinished = !item.isFinished;
        },
        addData () {
            this.items.push(
                {
                text: this.newStr,
                isFinished: false
            },
            );

            this.$emit('myMsg', this.newStr);

            this.newStr= '';
        }
    }
    }
</script>

<style>
.view{
    width:400px;
    border: 1px solid gray;
    margin: 20px auto;
}
.view .title{
    border-bottom: 1px solid gray;
}
.view ul li{
    margin: 10px 0;
    list-style: none;
}
.view .finish{
    color: gray;
    text-decoration: line-through;
}
</style>
