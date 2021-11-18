<template>
  <header>
      <div class="title">My Blog</div>
      <nav>
          <nuxt-link to="/">Home</nuxt-link>
          <nuxt-link to="/about">About</nuxt-link>
      </nav>
  </header>
</template>


<style>
*{
  margin: 0;
  padding:0;
  box-sizing: border-box;
  font-family: sans-serif;
}
body{
  background-color: #eee;
}
a{
  text-decoration: none;
}
p{
  margin-bottom: 15px;
}
p:last-of-type{
  margin-bottom: 0px;
}
header{
    background-color: white;
    display: flex;
    justify-content: space-between;
    padding: 20px 40px;
    box-shadow: lightgrey 0px 1px 5px;
}
.title{
    font-weight: bold;
    font-size: 20px;
}
nav{
    color: rgb(151, 151, 151);
}
nav > *{
    margin-right: 15px;
}

</style>