<template>
  <div id="app" class="app-container">
    <h1>Controla tu Figura</h1>
    <div class="content-container">
      <div class="form-container">
        <label>
          Color de fondo:
          <input v-model="colorFondo" placeholder="darkgreen"/>
        </label>
        <label>
          Color de texto:
          <input v-model="colorTexto" placeholder="white"/>
        </label>
        <label>
          Mostrar texto:
          <input type="checkbox" v-model="mostrarFigura"/>
        </label>
        <label>
          Borde:
          <input type="range" v-model="borde" min="0" max="20"/>
        </label>
        <label>
          Contenido textual:
          <textarea v-model="texto" rows="3" placeholder="Awesome Vue.js"></textarea>
        </label>
        <label>
          Tipografía:
          <select v-model="tipografia">
            <option value="cursive">Cursive</option>
            <option value="sans-serif">Sans-serif</option>
            <option value="monospace">Monospace</option>
          </select>
        </label>
        <label>
          Opaco:
          <input type="checkbox" v-model="opaco"/>
        </label>
        <label class="radio-group">
          Tamaño de letra:
          <div class="radio-options">
            <input type="radio" value="small" v-model="tamañoLetra"/> Pequeño
            <input type="radio" value="medium" v-model="tamañoLetra"/> Mediano
            <input type="radio" value="large" v-model="tamañoLetra"/> Grande
          </div>
        </label>
      </div>

      <div class="figura-container">
        <Figura :colorFondo="colorFondo" :colorTexto="colorTexto" :mostrarFigura="mostrarFigura"
                :borde="borde" :texto="texto" :tipografia="tipografia"
                :opaco="opaco" :tamañoLetra="tamañoLetra"/>
      </div>
    </div>
  </div>
</template>

<script>
import Figura from './components/Figura.vue'

export default {
  components: {
    Figura
  },
  data() {
    return {
      colorFondo: 'darkgreen',
      colorTexto: 'white',
      mostrarFigura: true,
      borde: 10,
      texto: 'Awesome Vue.js',
      tipografia: 'cursive',
      opaco: true,
      tamañoLetra: 'medium'
    }
  }
}
</script>

<style>
.app-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px;
  background-color: #e0f7fa;
  height: 100vh;
  text-align: center;
}

h1 {
  margin-bottom: 20px;
  color: #333;
}

.content-container {
  display: flex;
  width: 100%;
  justify-content: space-between;
  align-items: flex-start;
}

.form-container {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 20px;
  padding: 20px;
  background: #81c784;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  max-width: 300px;
  color: #fff;
}

.form-container label {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

input[type="text"], input[type="number"], select, textarea {
  margin-top: 5px;
  padding: 8px;
  border-radius: 5px;
  border: 1px solid #ccc;
  width: 100%;
}

textarea {
  resize: none;
}

input[type="checkbox"], input[type="radio"] {
  margin-left: 10px;
}

.radio-group {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.radio-options {
  display: flex;
  gap: 10px;
}

.figura-container {
  flex: 2;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px;
}
</style>
