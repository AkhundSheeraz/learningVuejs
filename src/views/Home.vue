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
                    :class="{ brdrred: redborder }"
                    class="form-control inpx"
                    placeholder="Name"
                    v-model="signup.name"
                  />
                </div>
                <div class="form-group">
                  <input
                    type="text"
                    :class="{ brdrred: redborder }"
                    class="form-control inpx"
                    placeholder="E-mail"
                    v-model="signup.email"
                  />
                </div>
                <div class="form-group">
                  <input
                    type="password"
                    :class="{ brdrred: redborder }"
                    class="form-control inpx"
                    placeholder="Password"
                    v-model="signup.password"
                  />
                  <span
                    toggle="#password-field"
                    class="fa fa-fw fa-eye field-icon toggle-password"
                    ><font-awesome-icon
                      :class="{ cross: crossIcon }"
                      class="text-danger"
                      icon="exclamation-circle"
                  /></span>
                </div>
                <div class="form-group">
                  <input
                    type="password"
                    :class="{ brdrred: redborder }"
                    class="form-control inpx"
                    placeholder="Confirm password"
                    v-model="signup.password_confirmation"
                  />
                  <span
                    toggle="#password-field"
                    class="fa fa-fw fa-eye field-icon toggle-password"
                    ><font-awesome-icon
                      :class="{ cross: crossIcon }"
                      class="text-danger"
                      icon="exclamation-circle"
                  /></span>
                </div>
                <div class="form-group">
                  <button
                    id="btn_signup"
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
  data() {
    return {
      signup: {
        name: null,
        email: null,
        password: null,
        password_confirmation: null,
      },
      redborder: false,
      crossIcon: true,
    };
  },
  methods: {
    remove_error(nodeArray) {
      setTimeout(() => {
        this.redborder = false;
        nodeArray.forEach((element) => {
          let val = element.placeholder;
          if (val) {
            if (element.classList.contains("brdrred")) {
              element.classList.remove("brdrred");
            }
            element.placeholder = val.replace(" required!", "");
          }
          document.getElementById("btn_signup").disabled = false;
        });
      }, 3000);
    },

    validator(data) {
      const validated = {};
      document.getElementById("btn_signup").disabled = true;
      for (let element of data) {
        if (element.value == null || element.value.trim().length == 0) {
          let pl = element.placeholder;
          element.placeholder = pl + " required!";
          element.classList.add("brdrred");
          validated[element.placeholder] = false;
        } else {
          validated[element.placeholder] = true;
        }
      }
      let passed = Object.values(validated).every((val) => val == true);
      this.remove_error(data);
      return passed;
    },

    get_signupInputs(e) {
      e.preventDefault();
      const formdata = JSON.parse(JSON.stringify(this.signup));
      let placeholders = document.querySelectorAll(".inpx");
      let checkvalidation = this.validator(placeholders);
      if (checkvalidation) {
        console.log(formdata);
      }

      //let checkKeys = !Object.values(formdata).every(val => val === null || val == '');
    },
  },
};
</script>



<style scoped>
.home {
  background-image: url("~@/assets/img/home.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}
#remember_me {
  margin-right: 10px;
}
.signup_btn:hover {
  border: #4a8181 1px solid;
  color: #75ffff !important;
}
.brdrred {
  border: red 1.5px solid !important;
}
.brdrred::placeholder {
  color: red !important;
}
.btn:disabled {
  background: rgba(255, 255, 255, 0.08) !important;
  border-radius: 40px;
  box-shadow: none !important;
  font-size: 15px;
  text-transform: uppercase;
}
.cross {
  display: none !important;
}

@import url("~@/assets/customcss/login.css");
</style>