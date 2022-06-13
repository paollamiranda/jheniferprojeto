<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      jogadores: [
        {
          id: "7681ca69-b8de-44cb-b1c8-64590a1154b9",
          nome: "Neymar Junior",
          time: "???",
          timeid: "PSG",
        },
        {
          id: "29a4b3d8-57e0-45b5-b489-fbdc1e0864fd",
          nome: "Roberto Firmino",
          time: "???",
          timeid: "Liverpool",
        },
        {
          id: "26a58ccf-df47-46d8-9bfb-9fde58678557",
          nome: "Erison",
          time: "???",
          timeid: "Botafogo",
        },
      ],
      novo_jogador: "",
      novo_time: "",
    };
  },
  methods: {
    salvar() {
      const novo_id = uuidv4();
      this.jogadores.push({
        id: novo_id,
        nome: this.novo_jogador,
        time: this.novo_time,
        timeid: this.novo_timeid,
      });
    },
  },
};
</script>

<template>
  <main>
    <div class="container">
      <div class="title">
        <h2>Gerenciamento de times</h2>
      </div>
      <div class="form-input">
        <input
          type="text"
          placeholder="jogador"
          v-model="novo_jogador"
          @keydown.enter="salvar"
        />
        <input type="text" placeholder="time" v-model="novo_time" />
        <button @click="salvar">Salvar</button>
      </div>
      <div class="list-times">
        <table>
          <thead>
            <tr>
              <th>ID</th>
              <th>Nome</th>
              <th>time</th>
              <th>Time.id</th>
              <th>Ações</th>
            </tr>
          </thead>

          <tbody>
            <tr v-for="jogador in jogadores" :key="jogador.id">
              <td>{{ jogador.id }}</td>
              <td>{{ jogador.nome }}</td>
              <td>{{ jogador.time }}</td>
              <td>{{ jogador.timeid }}</td>
              <td>???</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </main>
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
  border: 1px solid black;
  border-radius: 10px;
  background-color: rgb(6, 103, 40);
  color: #fff;
  font-weight: bold;
  margin-left: 1%;
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
