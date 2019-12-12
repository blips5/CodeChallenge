<template>
    <div class="container">
      <div class="row text-center">
         <div class="container">
        <img src="https://www.warrantywise.co.uk/img/logo.svg" width=50%/></div></div>
         <div class="row justify-content-center" v-for="item in products">
           <div  class="card col-md-8" style="margin:.5rem">
               <div class="card-header text-center">{{ item.name }}</div>
               <div class="card-body">
                 <div class="row">
                 <img class="col-md-4" src="" alt="" />
                 <div class="col-md-6 offset-md-2">
                 <ul>
                    <li>{{ item.color }}</li>
                    <li>{{ item.style }}</li>
                 </ul>
                 </div>
                 </div>
                 <div class="card text">"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</div>
                 <div class="card-footer">
                    <div class="row">
                    <div class="col-md-6 text-center">
                    <span>£{{item.price}}</span>
                    </div>
                    <div class="col-md-6">
                    <div class="col-md-4 offset-md-6">
                       <!-- button not implemented -->
                    <button class="btn btn-secondary">Delete</button></div>
                    </div>
                    </div>
                 </div>
               </div>
           </div>   
        </div>
      </div>
</template>

<script>
    export default {
      data: function (){
         return {
            // Data
            products: []
         }
      },
      mounted() {
         this.getProds();
      },
      methods:{
         // Methods
         getProds(){
            console.log(this.products);
            axios
               .get('http://127.0.0.1:8000/api/')
               .then(response => (this.products = response.data))
            
            }
         }
    }
</script>
