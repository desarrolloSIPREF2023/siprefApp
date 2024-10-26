<template>
  <div id="auth">
      <div class="row h-100">
          <div class="col-lg-5 col-12 bg-white">
              <div id="auth-left">
                  <h1 class="auth-title" style="font-size: 3.3em !important;">Iniciar Sesión</h1>
                  <p class="auth-subtitle mb-3">Autenticación de usuario</p>

                  <div>
                      <div class="form-group position-relative has-icon-left mb-4">
                          <input type="number" class="form-control form-control-xl" placeholder="Número de Acceso" v-model="number" @input="limitCharts(number)">
                          <div class="form-control-icon">
                              <i class="bi bi-person"></i>
                          </div>
                      </div>
                      <div class="form-group position-relative has-icon-left mb-4">
                          <input type="password" class="form-control form-control-xl" placeholder="Contraseña" v-model="password" @keypress.enter="loginWithEnter">
                          <div class="form-control-icon">
                              <i class="bi bi-shield-lock"></i>
                          </div>
                      </div>

                      <div class="form-group">
                          <button type="button" class="btn btn-primary btn-block btn-lg shadow-lg mt-3" :disabled="textButtonLogin" @click="signIn">
                              <span v-if="textButtonLogin == false">Acceder</span>
                              <div v-else>
                                  <span class="spinner-border spinner-border-sm" role="status" aria-hidden="true"></span>
                                  verificando acceso...
                              </div>
                          </button>
                      </div>
                  
                  </div>
                  <div class="pt-3 text-center details-serv"></div>
              </div>
          </div>
          <div class="col-lg-7 d-none d-lg-block">
              <div id="auth-right"></div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      number : '',
      password : '',
      textButtonLogin : false
    }
  }
}
</script>

<style scoped>
h1, h2 {
  font-weight: normal;
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
  color: #42b983;
}
</style>
