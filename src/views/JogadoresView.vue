<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      jogadores: [
        { id: "6bdca00a-8ea1-4671-b7c1-897444469d47", nome: "Jogador 1" },
        { id: "2eae6b13-7029-4327-990e-d9ec2f543a76", nome: "Jogador 2" },
        { id: "953ad3b8-7476-4eb3-b15b-abdb907f16fe", nome: "Jogador 3" },
        { id: "c43de862-dbd8-4cba-89dd-99b11798fa8b", nome: "Jogador 4" },
      ],
      novo_time: "",
    };
  },
  methods: {
    salvar() {
      const novo_id = uuidv4();
      this.times.push({
        id: novo_id,
        nome: this.novo_time,
      });
    },
  },
};
</script>
<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de jogadores</h2>
    </div>
    <div class="form-input">
      <input type="text" v-model="novo_time" />
      <button @click="salvar">salvar</button>
    </div>
    <div class="list-times">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Nome</th>
            <th>Ações</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="jogadores in jogadores" :key="jogadores.id">
            <td>{{ jogadores.id }}</td>
            <td>{{ jogadores.nome }}</td>
            <td>???</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
<style>
.title {
  text-align: center;
  margin: 2rem 0;
}

.form-input {
  display: flex;
  justify-content: center;
  margin: 2rem 0;
}

.form-input input {
  width: 50%;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 10px;
}

.form-input button {
  padding: 0.5rem;
  width: 15%;
  border: 1px solid violet;
  border-radius: 10px;
  background-color: violet;
  color: white;
  font-weight: bold;
  margin-left: 1px;
}

.list-times {
  display: flex;
  justify-content: center;
}

table {
  width: 50%;
  border-collapse: collapse;
  margin: 0 auto;
  border: 1px solid black;
  font-size: 1 1rem;
  text-align: center;
}

table thead {
  background-color: rgb(255, 105, 180);
  color: whitesmoke;
  font-size: bold;
}
table thead th {
  background-color: rgb(255, 105, 180);
  color: whitesmoke;
}

table tbody tr:nth-child(odd) {
  background-color: violet;
}
</style>
