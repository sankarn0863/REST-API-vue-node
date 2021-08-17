<template>
  <div class="hello">
    <h1 class="n3">{{ msg }}</h1>
    <p>
    This is the demonstration project of Rest API functionality, designed by Sankar Naredla
    </p>
   <p class="n1">Easy Access</p>
    <ul>
      <li>
        <a href="https://www.linkedin.com/in/sankar-n0863/" target="_blank" rel="noopener">Linkedin</a>
      </li>
      <li>
        <a href="https://github.com/sankarn0863" target="_blank" rel="noopener"
          >Github</a
        >
      </li>
      <li>
        <a href="resume.pdf" download
          >MyResume</a
        >
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.n1{
  padding-top:1.01cm ;
}
.n3{
  font-size: 20px;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  color: #045fb4;
  text-decoration: none;
}
.v2{
  padding-top: 1.8cm;
  padding-left: 35cm;
}


</style>
