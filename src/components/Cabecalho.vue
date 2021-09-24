<template>
  <header>
      <h1>{{ valor }} </h1>
  </header>
</template>

<script>
export default {
  props: ["valor"]

}
</script>

<style>
header {
  text-align: center;
  background-color: gray;
  color: white;
  height: 50px;
  width: 100%;
 
}
</style>