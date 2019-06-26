<template>
    <div>
      <div>vue cli</div>
      <ul>
        <li v-for="(item,index) in list" v-bind:key="index" @click="choose(index)"
         :class="{'active':index == current && current !== ''}">
            {{item}}
        </li>
      </ul>
      <button @click="add()">添加</button>
      <ul>
        <li v-for="(item,index) in targetlist" :key="index">
          {{item}}
        </li>
      </ul>
    </div>
</template>

<script>
  export default {
    name: 'demo',
    data(){
      return{
        list: [1,2,3,4,5,6,7,8,9],
        isactive: true,
        current: '',
        targetlist: []
      }
    },
    methods: {
      choose(i){
        this.current = i;

      },
      add(){
        if(this.current === ''){
          return;
        }
        this.targetlist.push(this.list[this.current]);
        this.current = '';
      }
    }
  };
</script>

<style scoped>
li.active{
  background-color: green;
}
</style>
