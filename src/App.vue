<template>
  <div id="app">
    <div class="tile is-ancestor">
      <div class="tile is-vertical is-8">
        <div class="tile is-parent">
          <article class="tile is-child notification is-danger">
            <p class="title">Cadastro de Clientes</p>
            <p class="subtitle">listagemde clientes cadastrados</p>
            <div class="content">
              <div class="field">
                <p class="control has-icons-left has-icons-right">
                  <input class="input" type="email" placeholder="Email" />
                  <span class="icon is-small is-left">
                    <i class="fas fa-envelope"></i>
                  </span>
                  <span class="icon is-small is-right">
                    <i class="fas fa-check"></i>
                  </span>
                </p>
              </div>
              <div class="field">
                <p class="control has-icons-left">
                  <input class="input" type="password" placeholder="Password" />
                  <span class="icon is-small is-left">
                    <i class="fas fa-lock"></i>
                  </span>
                </p>
              </div>
              <div class="field">
                <p class="control">
                  <button class="button is-success">Cadastrar</button>
                  <button class="button is-success">Cancelar</button>
                </p>
              </div>
            </div>

            <table class="table is-fullwidth">
              <thead>
                <tr>
                  <th><abbr title="Nome">Nome</abbr></th>
                  <th><abbr title="E-mail">E-mail</abbr></th>
                  <th><abbr title="Idade">Idade</abbr></th>
                </tr>
              </thead>
              <tfoot>
                <tr>
                  <th><abbr title="Nome">Nome</abbr></th>
                  <th><abbr title="E-mail">E-mail</abbr></th>
                  <th><abbr title="Idade">Idade</abbr></th>
                </tr>
              </tfoot>
              <tbody v-for="cliente in clientes" :key="cliente.id">
                <Cliente :cliente="cliente" />
              </tbody>
            </table>
          </article>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Cliente from "./components/Cliente.vue";

export default {
  name: "App",
  data() {
    return {
      clientes: [
        {
          nome: "Cliente 01",
          email: "cliente01@gmail.com",
          idade: 15,
        },
      ],
    };
  },
  components: {
    Cliente,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
