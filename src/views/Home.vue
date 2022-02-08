<template>
  <div class="home">
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },

  mounted(){
    this.getData()
  },
  
  methods:{
    async getData(){
      let {data,salah}= await this.$supabase
      .from('tb_produk')
      .select()

      if(data) console.log(data)
      if(salah) console.error(salah)
    },
  },
};
</script>
