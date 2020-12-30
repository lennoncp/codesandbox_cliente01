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
                  <input
                    class="input"
                    type="text"
                    placeholder="Nome"
                    v-model="nomeField"
                  />
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
                  <input
                    class="input"
                    type="email"
                    placeholder="E-mail"
                    v-model="emailField"
                  />
                  <span class="icon is-small is-left">
                    <i class="fas fa-lock"></i>
                  </span>
                </p>
              </div>

              <div class="field">
                <p class="control has-icons-left">
                  <input
                    class="input"
                    type="number"
                    placeholder="Idade"
                    v-model="idadeField"
                  />
                  <span class="icon is-small is-left">
                    <i class="fas fa-lock"></i>
                  </span>
                </p>
              </div>
              <div class="field">
                <p class="control">
                  <button class="button is-success" @click="cadastrarCliente()">
                    Cadastrar
                  </button>
                  <button class="button is-success" @click="limparCampos()">
                    Cancelar
                  </button>
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
      nomeField: "",
      emailField: "",
      idadeField: 0,

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
  methods: {
    cadastrarCliente: function () {
      this.clientes.push({
        id: Date.now(),
        nome: this.nomeField,
        email: this.emailField,
        idade: this.idadeField,
      });
      this.limparCampos();
    },
    limparCampos: function () {
      (this.nomeField = ""), (this.emailField = ""), (this.idadeField = 0);
    },
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
