<template>
  <div id="app">
  <div class="search-wrapper">
     <label>Search title: </label>
    <input type="text" v-model="search" placeholder="search">
   
  </div>
  <div class="wrapper">
    <div class="card" v-for="post in filteredList" :key="post.link">
      <a v-bind:href="post.link" target="_blank">
        <img v-bind:src="post.img"/>
        <small>posted by: {{ post.author }}</small>
        {{ post.title }}
      </a>
    </div>
  </div>
</div>

</template>

<script>
class Post {
  constructor(title, link, author, img) {
    this.title = title;
    this.link = link;
    this.author = author;
    this.img = img;
  }}

export default {
  name: 'App',
  components: {
    
  },
  data(){
    return{
      search:"",
       postList: [
    new Post(
        'Vue.js', 
        'https://vuejs.org/', 
        'Chris', 
        'https://vuejs.org//images/logo.png'
      ),
      new Post(
        'React.js', 
        'https://facebook.github.io/react/', 
        'Tim',
        'https://daynin.github.io/clojurescript-presentation/img/react-logo.png'
      ),
      new Post(
        'Angular.js', 
        'https://angularjs.org/', 
        'Sam', 
        'https://angularjs.org/img/ng-logo.png'
      ),
      new Post(
        'Ember.js', 
        'http://emberjs.com/', 
        'Rachel',
        'http://www.gravatar.com/avatar/0cf15665a9146ba852bf042b0652780a?s=200'
      ),
      new Post(
        'Meteor.js', 
        'https://www.meteor.com/', 
        'Chris', 
        'http://hacktivist.in/introduction-to-nodejs-mongodb-meteor/img/meteor.png'
      ),
      new Post(
        'Aurelia', 
        'http://aurelia.io/', 
        'Tim',
        'https://cdn.auth0.com/blog/aurelia-logo.png'
      ),
      new Post(
        'Node.js', 
        'https://nodejs.org/en/', 
        'A. A. Ron',
        'https://code-maven.com/img/node.png'
      ),
      new Post(
        'Pusher', 
        'https://pusher.com/', 
        'Alex', 
        'https://avatars1.githubusercontent.com/u/739550?v=3&s=400'
      ),
      new Post(
        'Feathers.js', 
        'http://feathersjs.com/', 
        'Chuck',
        'https://cdn.worldvectorlogo.com/logos/feathersjs.svg'
      ),
]
  }},
  computed: {
    filteredList() {
      return this.postList.filter(post => {
        return post.title.toLowerCase().includes(this.search.toLowerCase())
      })
    }
  }
  }


</script>

<style>
html,body{
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  margin-top: 16px;
  margin-bottom: 16px;
}
#app {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
.search-wrapper{
  position: relative;
}
label{
  position: absolute;
  font-size: 15px;
  color: rgba(0,0,0,.50);
  top: -20px;
  left: 12px;
  z-index: -1;
  transition: .15s all ease-in-out;
}
input{
  padding: 4px 12px;
  color: rgba(0,0,0,.7);
  border: 1px solid rgba(0,0,0,.12);
  transition: .15s all ease-in-out;
  background: #fff;

    
  
}
 div#app .search-wrapper input:focus {
        outline: none;
        transform: scale(1.05);
 }
div#app .search-wrapper input:focus + laber {
  font-size: 10px;
  transform: translateY(-24px)
  translateX(-12px);

 }
 div#app .search-wrapper input::-webkit-input-placeholder {
  font-size: 12px;
  color: rgba(0, 0, 0, 0.5);
  font-weight: 100;
}
div#app .wrapper {
  display: flex;
  max-width: 444px;
  flex-wrap: wrap;
  padding-top: 12px;
}
div#app .card {
  box-shadow: rgba(0, 0, 0, 0.117647) 0px 1px 6px, rgba(0, 0, 0, 0.117647) 0px 1px 4px;
  max-width: 124px;
  margin: 12px;
  transition: 0.15s all ease-in-out;
}
div#app .card:hover {
  transform: scale(1.1);
}
div#app .card a {
  text-decoration: none;
  padding: 12px;
  color: #03a9f4;
  font-size: 24px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
div#app .card a img {
  height: 100px;
}
div#app .card a small {
  font-size: 10px;
  padding: 4px;
}
div#app .hotpink {
  background: hotpink;
}
div#app .green {
  background: green;
}
div#app .box {
  width: 100px;
  height: 100px;
  border: 1px solid rgba(0, 0, 0, 0.12);
}
</style>
