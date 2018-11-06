<template>
  <div>
    <div class="olho">
      <div class="piscar">
        <span></span>
      </div>
      <div class="bola"></div>
    </div>
    
    <div class="fundo">`</div>
    
    <div class="form">
      <form @submit.prevent.stop>
        <label for="nome">Preencha o nome:</label>
        <input type="text" id="nome" v-model="nome"><br>      
        <label for="senha">Preencha a senha:</label>
        <input type="password" id="senha" v-model='senha'><br>
        <button id="enviar">enviar</button>
        <button id="limpar" @click="limpar">limpar</button>
      </form>
    </div>
  </div>
</template>

<script>

export default {

  data() {
    return { 
      nome: '',
      senha: ''
    }
  },
  methods: {
    limpar() {
      this.nome = ''
      this.senha = ''
      return nome, senha
    },
    fechado() {
      let senha = document.getElementById('senha')
      let olho = document.getElementsByClassName('olho')[0]
      let piscar = olho.children[0]
      let spanEx = piscar.children[0] 
        
      senha.onkeydown = () => {
        spanEx.style.height = '100%'
      }
      senha.onkeyup = () => {
        setTimeout(() => spanEx.style.height = '15%',1000)
      }
    }
  },

  mounted() {
    nome.focus();
    this.fechado();
  }
};
</script>

<style scoped>
.olho{
  width: 200px;
  height: 200px;
  background-color: #FFF;
  position: absolute;
  left: 50%;
  top: 25%;
  transform: translate(-50%, -50%) rotate(45deg);
  border-radius: 75% 0;
  overflow: hidden;
}
.bola{
  width: 40px;
  height: 40px;
  background-color: #34495E;
  border-radius: 50%;
  border: 30px solid #B2BABB;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}
.piscar{
  width: 300px;
  height: 160px;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%) rotate(-45deg);
  z-index: 999;
}
.piscar span{
  display: block;
  width: 100%;
  height: 15%;
  background-color: #734d26;
  border-radius: 0 0 60% 60%;
  transition: 1.0s all;
}
.olho:hover > .piscar span{
  height: 100%;
}
.form{
  background-color: #2983B7;
  position: absolute;
  top: 40%;
  left: 35%;
  padding: 30px;
  border-radius: 4px;
  border-top: solid 4px #076397 ;
  border-bottom: solid 4px #076397;
}
input{
  margin-bottom: 15px;
  border: none;
  border-radius: 4px;
  height: 30px;
  width: 200px;
}
label{
  color: #FFF;
} 
button{
  height: 25px;
  width: 55px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
#enviar{
  background-color: #52BE80;
  color: #515A5A;
}
#enviar:hover{
  background-color: #0E6655;
  color: #FFF;
}
#limpar{
  background-color: #F1948A;
  color: #34495E;
}
#limpar:hover{
  background-color: #E74C3C;
  color: #FFF;
}
</style>
