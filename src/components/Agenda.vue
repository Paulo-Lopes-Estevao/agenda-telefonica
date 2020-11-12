<template>
  <div class="jumbotron">
    <h4>{{ msg }}</h4>
    <table class="table table-striped">
      <tr>
        <th></th>
        <th>Nome</th>
        <th>Telefone</th>
        <th>Operadora</th>
      </tr>
      <tr>
        <td>
          <input type="checkbox" />
        </td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
    </table>

    <hr />

    <form name="contatoForm">
      <input class="form-control" type="text" name="nome" placeholder="Nome" />

      <input
        class="form-control"
        type="text"
        name="telefone"
        placeholder="Telefone"
      />

      <select class="form-control">
        <option value="">Selecione uma operadora</option>
      </select>
    </form>

    <div class="alert alert-danger">Por favor, preencha o nome</div>
    <div class="alert alert-danger">Por favor, preencha o telefone</div>

    <button class="btn btn-primary btn-block">Adicionar Contato</button>
    <button class="btn btn-danger btn-block">Apagar Contatos</button>
  </div>
</template>

<script>
export default {};
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
</style>