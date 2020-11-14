<template>
  <div class="jumbotron">
    <h4>{{ msg }}</h4>
    <table class="table table-striped">
      <tr>
        <th></th>
        <th>id</th>
        <th>Nome</th>
        <th>Telefone</th>
        <th>Operadora</th>
      </tr>

      <tr v-for="(value, index) in contactos" :key="index">
        <td>
          <input type="checkbox" />
        </td>
        <td>{{ index + 1 }}</td>
        <td>
          {{ value.nome }}
        </td>
        <td>
          {{ value.numero }}
        </td>
        <td>
          {{ value.operadora }}
        </td>
      </tr>
    </table>

    <hr />

    <form>
      <input
        class="form-control"
        type="text"
        v-model="nome"
        name="nome"
        placeholder="Nome"
      />

      <input
        class="form-control"
        type="number"
        name="telefone"
        v-model="numero"
        placeholder="Telefone"
      />

      <select class="form-control" v-model="operadora">
        <option value="">Selecione uma operadora</option>
        <option value="Unitel">Unitel</option>
        <option value="Movicel">Movicel</option>
      </select>
    </form>

    <div v-show="controleNome" class="alert alert-danger">
      Por favor, preencha o nome
    </div>
    <div v-show="controleTelefone" class="alert alert-danger">
      Por favor, preencha o telefone
    </div>

    <button
      :disabled="disabled"
      class="btn btn-primary btn-block"
      v-on:click="addContactos()"
    >
      Adicionar Contato
    </button>
    <button class="btn btn-danger btn-block" @click="delContactos(index)">
      Apagar Contatos
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return { 
      nome: "",
      numero: "",
      operadora: "",
      disabled: "disabled",
      controleNome: false,
      controleTelefone: false,

      contactos: [
        {
          nome: "Paulo Lopes Estevão",
          numero: 937868133,
          operadora: "Unitel",
        },
      ],
    };
  },
  methods: {
    addContactos: function () {
      this.operadora == "" ? (this.operadora = "Unitel") : this.operadora;
      this.contactos.push({
        nome: this.nome,
        numero: this.numero,
        operadora: this.operadora,
      });
    },
    delContactos: function (index) {
      console.log(index)
    },
    conditionadd: function () {
      if (this.nome == "" || this.nome == " ") {
        this.controleNome = true;
        this.disabled = "disabled";
      } else if (this.numero == "" || this.numero == " ") {
        this.controleTelefone = true;
        this.disabled = "disabled";
      } else {
        this.disabled = false;
        this.controleTelefone = false;
        this.controleNome = false;
      }
    },
  },

  updated() {
    this.conditionadd();
  },
  props: {
    msg: String,
  },
};
</script>

<style scoped>
.jumbotron {
  width: 400px;
  text-align: center;
  margin-top: 20px;
  margin-left: auto;
  margin-right: auto;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding: 48px 0;
  }
}
.jumbotron {
  padding: 30px 15px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eee;
}
.table {
  margin-top: 20px;
}

.form-control {
  margin-bottom: 5px;
}
.table {
  border-spacing: 0;
  border-collapse: collapse;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 20px;
}
.table {
  background-color: transparent;
}

.form-control {
  margin-bottom: 5px;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075),
    0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075),
    0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control {
  display: block;
  width: 100%;
  height: 34px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out 0.15s,
    -webkit-box-shadow ease-in-out 0.15s;
  -o-transition: border-color ease-in-out 0.15s, box-shadow ease-in-out 0.15s;
  transition: border-color ease-in-out 0.15s, box-shadow ease-in-out 0.15s;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
input {
  line-height: normal;
}
button,
input,
optgroup,
select,
textarea {
  margin: 0;
  font: inherit;
  color: inherit;
}

.alert-danger {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.alert {
  padding: 15px;
  margin-bottom: 20px;
  border: 1px solid transparent;
  border-radius: 4px;
}

.btn {
  display: inline-block;
  padding: 6px 12px;
  margin-bottom: 0;
  font-size: 14px;
  font-weight: normal;
  line-height: 1.42857143;
  text-align: center;
  white-space: nowrap;
  vertical-align: middle;
  -ms-touch-action: manipulation;
  touch-action: manipulation;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 4px;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: thin dotted;
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}

.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}

.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}

.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}

button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}

button,
select {
  text-transform: none;
}

button {
  overflow: visible;
}

.btn-primary:hover,
.btn-primary:focus,
.btn-primary.focus,
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}

.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}

.btn-primary.disabled,
.btn-primary[disabled],
fieldset[disabled] .btn-primary,
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus,
.btn-primary.disabled:active,
.btn-primary[disabled]:active,
fieldset[disabled] .btn-primary:active,
.btn-primary.disabled.active,
.btn-primary[disabled].active,
fieldset[disabled] .btn-primary.active {
  background-color: #337ab7;
  border-color: #2e6da4;
}

.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}

* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
</style>