<template>
 <ul>
     <li><button :class="{active:modelValue=='poor' }" @click="activate('poor')" type="button">Poor</button></li>
      <li><button :class="{active:modelValue=='average' }" @click="activate('average')" type="button">Average</button></li>
       <li><button :class="{active:modelValue=='great' }" @click="activate('great')" type="button"> Great</button></li>
 </ul>
</template>
<script>
export default {
    props:['modelValue'],
    emits:['update:modelValue'],
    // computed:{
    //     activeOption(){
    //         return this.modelValue
    //     }
    // },
    // data() {
    //     return {
    //         activeOption:this.modelValue
    //     }
    // },
    methods: {
        activate(opt){
            // alert(opt)
            // this.activeOption=opt;
            this.$emit('update:modelValue',opt)
        }
    },
}
</script>

<style scoped>
ul{
    list-style-type: none;
    margin: 0.5rem 0;
    padding: 0;
    display: flex;
}

li{
    margin: 1rem 0;
    border: 1px solid #ccc;
    padding: 1rem;
    display: flex;
    justify-content: center;
    align-items: center;
}

button{
    font: inherit;
    background: transparent;
    cursor: pointer;
    border: none;
}
.active{
    /* border-color: green; */
    border: 1px solid green;
}
.active button{
     border-color: green;
     border: 1px solid green;
}
</style>