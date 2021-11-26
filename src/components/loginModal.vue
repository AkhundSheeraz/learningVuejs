<template>
  <div
    class="modal fade"
    id="exampleModal1"
    tabindex="-1"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog frmwidth">
      <form
        method="POST"
        id="login"
        class="modal-content modal-body px-2 bg-dark"
        aria-labelledby="dropdownMenuButton1"
      >
        <div class="text-center">
          <img src="~@/assets/img/user.png" class="w-50 my-1 invert" alt="user" />
        </div>
        <div class="form-group">
          <input type="text" class="form-control" placeholder="Email" />
        </div>
        <div class="form-group">
          <input type="password" class="form-control" placeholder="Password" />
        </div>
        <div class="form-group">
          <button type="submit" class="form-control btn submit px-3 signup_btn">
            Login
          </button>
        </div>
        <div>
          <p id="login_error" class="logmsg"></p>
        </div>
        <a id="forgotcode" class="text-center" type="button">forgot password</a>
      </form>
    </div>
  </div>
</template>

<script>
export default {};
</script>


<style lang="css" scoped>
#login {
  background-color: #000912 !important;
  border: #4a8181 1px solid;
}

.frmborder {
  margin: 5px 0 !important;
  border: white 1px solid !important;
  border-radius: 5px !important;
}
.frminputs {
  margin: 5px 0;
  padding: 0 5px;
  border: 1px white solid;
  border-radius: 5px;
}

.frminputs::placeholder {
  color: black;
}
.frmwidth {
  width: 20% !important;
}
#forgotcode {
  text-decoration: none;
  color: #4a8181;
}
.signup_btn:hover {
  border: #4a8181 1px solid;
  color: #75ffff !important;
}
</style>