<template>
  <div class="home">
    <section class="ftco-section">
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-md-6 text-center">
            <h1 class="text-white">Sign Up</h1>
          </div>
        </div>
        <div class="row justify-content-center">
          <div class="col-md-6 col-lg-4">
            <div class="login-wrap p-0">
              <h3 class="mb-4 text-center">Create an account?</h3>
              <form action="#" class="signin-form" @submit="get_signupInputs">
                <div class="form-group">
                  <input
                    type="text"
                    class="form-control"
                    placeholder="Name"
                    v-model="signup.name"
                  />
                </div>
                <div class="form-group">
                  <input
                    type="text"
                    class="form-control"
                    placeholder="E-mail"
                    v-model="signup.email"
                  />
                </div>
                <div class="form-group">
                  <input
                    type="password"
                    class="form-control"
                    placeholder="Password"
                    v-model="signup.password"
                  />
                  <span
                    toggle="#password-field"
                    class="fa fa-fw fa-eye field-icon toggle-password"
                  ></span>
                </div>
                <div class="form-group">
                  <input
                    type="password"
                    class="form-control"
                    placeholder="Confirm password"
                    v-model="signup.password_confirmation"
                  />
                  <span
                    toggle="#password-field"
                    class="fa fa-fw fa-eye field-icon toggle-password"
                  ></span>
                </div>
                <div class="form-group">
                  <button
                    type="submit"
                    class="form-control btn submit px-3 signup_btn"
                  >
                    Sign Up
                  </button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data(){
    return{
      signup:{
        name:null,
        email:null,
        password:null,
        password_confirmation:null,
      }
    }
  },
  methods:{
    get_signupInputs(e){
      e.preventDefault;
      const formdata = JSON.parse(JSON.stringify(this.signup));
      console.log(formdata); 
    }
  }
 
};
</script>



<style scoped>
.home{
  background-image: url('~@/assets/img/home.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}
#remember_me{
  margin-right: 10px
}
.signup_btn:hover{
  border: #4a8181 1px solid;
  color:  #75ffff !important;
}

@import url('~@/assets/customcss/login.css');
</style>