<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view/>
  
  <ul class="shows">
     <li
       v-for="show in shows"
       v-bind:key="show.sys.id"
       class="show"
     >
       <div class="show-info">
         <div class="show-name">
           <p>{{ show.name }}</p>
         </div>
       </div>
     </li>
   </ul>
</template>
// App.vue
<script>
export default {
 data() {
   return {
     shows: []
   };
 },
 async created() {
   this.shows = await this.getShows();
 },
 methods: {
   getShows: async () => {
     const query = `{
       showCollection {
         items {
           sys {
             id
           }
           name
         }
       }
     }`;
     const fetchUrl = `https://graphql.contentful.com/content/v1/spaces/${process.env.VUE_APP_CONTENTFUL_SPACE_ID}`;
     const fetchOptions = {
       method: "POST",
       headers: {
         Authorization: `Bearer ${process.env.VUE_APP_CONTENTFUL_ACCESS_TOKEN}`,
         "Content-Type": "application/json"
       },
       body: JSON.stringify({ query })
     };

     try {
       const response = await fetch(fetchUrl, fetchOptions).then(response =>
         response.json()
       );
       return response.data.showCollection.items;
     } catch (error) {
       throw new Error("Could not receive the data from Contentful!");
     }
   }
 }
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
