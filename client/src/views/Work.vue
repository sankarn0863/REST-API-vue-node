<template>
  <div class="Work">


<!-- Advertisement or Promotional Content -->

    <div class="columns is-desktop">
  <div class="column">
    <div class="card">
  <div class="card-image">
    <figure class="image is-4by3">
      <img src="../assets/card.png" alt="Placeholder image">
    </figure>
  </div>
  <div class="card-content">
    <div class="media">
      <div class="media-left">
        <figure class="image is-64x64">
          <img src="../assets/company.png" alt="Placeholder image">
        </figure>
      </div>
      <div class="media-content">
        <p class="title is-4">BEST MART STORES</p>
        <p class="subtitle is-6">New York, US</p>
      </div>
    </div>

    <div class="content">
      We provide the best quality of Products to our Costumers<a>@United States</a>.
      <a href="#">#NYC</a>
      <br>
   
    </div>
  </div>
</div>
</div>



<!-- REST API GET OPERTATION -->

  <div class="column">

<div class="container">
      <p v-html="error"></p>

   <h1>TABULAR DATA FORMAT</h1>
      <div class="portlet box blue" style="width:500px; opacity:0.95">
        <div class="portlet-title">
        </div>
              <div class="venu">
        <div class="portlet-body">
          <div class="mycss">
            <table class="table">
              <thead>
                <tr>
                  <td><b> Receipt No</b></td>
                  <td><b> Price</b></td>
                  <td><b> Rewards</b></td>
                </tr>
              </thead>
              <tbody>
                <tr :key="friend._id" v-for="friend in friends">
                  <td>{{ friend.id }}</td>
                  <td>{{ friend.price }}</td>
                  <td>{{ friend.rewards }}</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
    </div>
  </div>

  
  <!-- REST API POST FUNCTION -->

  <div class="column">
    <p>DATA INSERTION</p> <br>
      <form @submit="postData" method="POST">
        
       <div class="field">
  <label class="label">Receipt Number</label>
  <div class="control">
            <input class="input is-medium" type="text" name="Id" v-model="posts.author" placeholder="Receipt No">
  </div>
</div>

 <div class="field">
  <label class="label">Price</label>
  <div class="control">
         <input class="input is-medium" type="number" name="Price" v-model="posts.title" placeholder="Price in USD">
  </div>
</div>
  
        <button type="submit">Submit Data</button>
      </form>
</div>

</div>
  </div>
</template>



<style>

.n2{
  font-size: 22px;
}
    @import "https://cdn.jsdelivr.net/npm/bulma@0.9.3/css/bulma.min.css";

.venu{
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
  text-align: left;
  color: rgb(18, 6, 128);
  padding-left: 2.5cm;
}

.card{
  padding-right: 2cm;

}

button {
  background-color: #051499d8;
  color: rgb(255, 255, 255);
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  cursor: pointer;
  width: 50%;
}

button:hover {
  opacity: 0.8;
  background-color: rgb(13, 170, 34);
}
</style>




<script>

//  axios is used to connect to the REST API
import axios from "axios";

export default {
  data() {
    return {
      friends: [],
      posts:{
        title:null,
        author:null
      }
    };
  },

// Logic of the program(Functionality)

  methods: {
    postData(e)
    {
      console.warn(this.posts.title);
      e.preventDefault();
     
     var  price = this.posts.title;
     function calculateRewards(price) {      
          if (price >=50 && price < 100) {
              return price-50;
          } else if (price >100){
              return (2*(price-100) + 50);
          }
            return 0;
          }

// Posting data

      axios
        .post("http://localhost:8000/api/company", {
          id: this.posts.author,
          price: this.posts.title,
          rewards: calculateRewards(price),

        })
        .then((res) => {
          console.log(res);
          location.reload();
        })
        .catch((err) => {
          console.log(err.message);
        });

    }
  },

// Getting Data
    
    mounted() {
    axios
      .get("http://localhost:8000/api/company")
      .then((response) => {
        this.friends = response.data;
      })
      .catch((err) => {
        console.log(err);
      });
  },
  
};

</script>


