<template>
  <div  :style="{ backgroundColor: background, fontSize: fontSize, color: color }" contenteditable="true" @input="$emit('update', $event.target)" >
  </div>

</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: {
      default: ''
    },
    color: {
      type: String,
      default: 'black'
    },
    background: {
      type: String,
      default: 'red'
    },
    fontSize: {
      type: Number,
      default: 12
    }
  },
  mounted:function(){
    this.$el.innerText = this.msg;
  },

  methods: {
    update(event){
      console.log(event)
      this.$emit('update',event.target);
    }
  }
}
</script>

<style scoped>
</style>
