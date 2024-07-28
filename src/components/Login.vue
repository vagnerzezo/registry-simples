<template>
  <div id="login">
    <div class="card-login col-md-6">
      <div class="card-header row">
        <div class="logo col-12 col-md-4">
          <img alt="mountain app logo" src="@/assets/img/logo.svg">
        </div>
        <div class="menu col-12 col-md-4">
          <ul>
            <li>
              <a href="http://">Home</a>
            </li>
            <li>
              <a href="http://">Login</a>
            </li>
          </ul>
        </div>
      </div>
      <div class="card-content row">
        <div class="card-texts">
          <h2>Create new account<span>.</span></h2>
          <span>Already a member? <a href="">Login</a></span>
        </div>
        <div class="card-inputs">
          <form action="" class="row">
            <div class="input-group">
              <input class="col-12" type="text" name="First Name" id="nameFirst" placeholder="First Name">
              <input class="col-12" type="text" name="Last Name" id="nameLast" placeholder="Last Name">
            </div>
            <input class="col-12" type="email" name="Email" id="email" placeholder="Email">

            <div class="password-login">
              <input class="col-12" :type="toggleLook ? 'text' : 'password'" placeholder="Password">
              <span class="look-password" @click="clickToggleLook" :class="{ visivel: toggleLook }"></span>
            </div>
            <div class="buttons">
              <button>Other method</button>
              <button class="create">Create account</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'AppLogin',
  data() {
    return {
      toggleLook: false,
    };
  },
  methods: {
    clickToggleLook() {
      this.toggleLook = !this.toggleLook
    }
  }
}
</script>
<style lang="css" scoped>
#login {
  background: linear-gradient(to right, #272a37, #272a37, #585964, #8c8c94, #FFFFFE);
  border-radius: 20px;
  background-image: url('@/assets/img/bg.png');
  background-repeat: no-repeat;
  background-size: cover;
  width: 70%;
  height: 70vh;
}

.card-login {
  padding: 40px;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}

input {
  display: flex;
  margin: 5px 0;
  height: 40px;
  border-radius: 10px;
  border: none;
  background-color: #ffffff0d;
  color: #fff !important;
}

ul {
  display: flex;
}

li {
  margin-left: 10px;
}

h2 {
  font-size: var(--size5);
  font-weight: 600;
}

h2 span {
  color: var(--color2);
}

.card-texts {
  margin-bottom: 25px;
}

.password-login {
  position: relative;
}

.password-login,
.input-group {
  display: flex;
  width: 100%;
  gap: 1rem;
  padding: 0;
}

.password-login input,
.input-group input {
  flex: 1;
  display: flex;
  border-radius: 0 !important;
  border-radius: 10px !important;
  padding: 0 10px;
}

.buttons {
  margin-top: 10px;
  display: flex;
  gap: 1rem;
  padding: 0;
}

button {
  font-size: var(--size2);
  border: none;
  border-radius: 10px;
  width: 100%;
  max-width: 50%;
  height: 40px;
  color: #fff;
  font-weight: 600;
  background-color: #ffffff0d;
}

.create {
  background-color: var(--color2);
}

.look-password {
  background-image: url('@/assets/img/eyesopen.svg');
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  width: 28px;
  height: 28px;
  position: absolute;
  right: 2%;
  top: 20%;
  cursor: pointer;
}

span.look-password.visivel {
  background-image: url('@/assets/img/eyesclose.svg');
}


@media (max-width: 1024px) {
  #login {
    width: 95%;
  }

  .menu {
    margin-top: 10px;
  }

  .menu ul {
    justify-content: center;
  }

  button {
    max-width: 100%;
  }
}
</style>