<template>
<header>
    <div class="wrapper">
      <nav class="_mynav">
        <RouterLink to="/" class="_mybtn">Home</RouterLink>
        <h1>TO DO LIST APP</h1>
        <RouterLink to="/Trash" class="_mybtn">Trash bin</RouterLink>
      </nav>
    </div>
</header>
</template>

<script lang='ts'>

export default{

    name:'HeaderComponent',

    data() {
        return {
            
        }
    },
    methods: {
        
    },
}
</script>

<style scoped>
._mynav{
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-bottom: 1px solid ;
  padding: 5px;
}
._mybtn{
  padding: 5px;
  border: 1px solid black;
  border-radius: 5px;
}
</style>