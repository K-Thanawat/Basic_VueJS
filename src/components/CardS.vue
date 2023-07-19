<template>
  <li>
    <img
      src="https://optimise2.assets-servd.host/maniacal-finch/production/animals/african-lion-01-01.jpg?w=1200&auto=compress%2Cformat&fit=crop&dm=1658933674&s=4b63f926a0f524f2087a8e0613282bdb" 
      alt="" />
    <hr>
    <slot name="card-header"></slot>
    <slot name="card-button"></slot>
    <slot name="card-content"></slot>
  </li>
</template>
  
  <script>
export default {
  name: "CardS",
};
</script>
  
<style>
li {
  margin: 1rem 0;
  font-size: 1.25rem;
  font-weight: bold;
  background-color: purple;
  padding: 0.5rem;
  color: white;
  border-radius: 25px;
}
img{
  width: 120px;
}
</style>