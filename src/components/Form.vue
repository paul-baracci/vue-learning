<template>
  <div class="container d-flex justify-content-center">
    <form @submit.prevent="handleSubmit"  >
      <div class="row text-center">
        <h1>Order submit form</h1>
      </div>
      <div class="row my-3" >
        <div class="form-group">                       
            <input type="text" class="form-control" placeholder="Full Name" required v-model="fullName" />
        </div>
      </div> 
      <div class="row my-3">
        <div class="form-group">                       
            <input type="email" class="form-control" placeholder="Email" required v-model="email" />
        </div>
      </div> 
      <div class="row my-3">        
        <div class="form-group">
            <input type="tel" class="form-control" placeholder="Phone" required v-model="phone" />
        </div>                       
      </div>  
      <div class="row my-3">        
        <div class="form-group">
          <input type="text" class="form-control" placeholder="Delivery City" required v-model="deliveryCity" />
        </div>
      </div>           
      <div class="row my-3">         
        <div class="form-group">
          <input type="text" class="form-control" placeholder="Delivery Address" required v-model="deliveryAddress" />
        </div>
      </div>
      <div class="row my-3">         
        <div class="form-group">
            <label>Desired Delivery Date</label>
            <input type="date" class="form-control" required v-model="deliveryDate" />
        </div>
      </div>
      <div class="row my-3">         
        <div class="form-group">
            <label>Desired Delivery Time</label>
            <input type="time" class="form-control" required v-model="deliveryTime" />
        </div>
      </div>
      <div class="row my-3">         
        <div class="form-group">
             <textarea name="message" rows="3" class="form-control" placeholder="Additional comments" v-model="comment"></textarea>
        </div>
      </div>
      <div class="row">         
        <div class="form-group text-center">
            <input type="checkbox" for="acceptTerms" required v-model="terms" />
            <label id="acceptTerms">Accept Terms and Conditions</label>
        </div>
      </div>
      <div class="text-center">
        <button type="submit" class="btn btn-primary">Send</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  el: '#alert',
  data() {
    return {
      fullName: "",
      email: "",
      phone: "",
      deliveryCountry: "",
      deliveryCity: "",
      deliveryAddress: "",
      deliveryDate: "",
      deliveryTime: "",
      comment: "",
      terms: false,
    };
  },
  methods: {
    handleSubmit() {
      console.log(this.fullName)
      console.log(this.email)
      console.log(this.phone)
      console.log(this.deliveryCountry)
      console.log(this.deliveryCity)
      console.log(this.deliveryAddress)
      console.log(this.deliveryDate)
      console.log(this.deliveryTime)
      console.log(this.comment)
      console.log(this.terms)
    },
    showAlert(event) {
      alert('Hello')
      if (event) {
        alert(event.target.tagName)
      }
    },
  },
};
</script>

<style>
</style>
