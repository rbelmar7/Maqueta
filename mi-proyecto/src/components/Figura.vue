<template>
  <div :style="estilosFigura" class="figura" v-if="mostrarFigura">
    {{ texto }}
  </div>
</template>

<script>
export default {
  props: {
    colorFondo: String,
    colorTexto: String,
    mostrarFigura: Boolean,
    borde: Number,
    texto: String,
    tipografia: String,
    opaco: Boolean,
    tamañoLetra: String
  },
  computed: {
    estilosFigura() {
      return {
        backgroundColor: this.colorFondo,
        color: this.colorTexto,
        borderRadius: this.borde + 'px',
        fontFamily: this.tipografia,
        opacity: this.opaco ? 1 : 0.5,
        fontSize: this.tamañoLetra === 'small' ? '12px' : this.tamañoLetra === 'medium' ? '16px' : '20px',
        padding: '20px',
        margin: '10px',
        textAlign: 'center',
        boxShadow: '0 4px 8px rgba(0, 0, 0, 0.2)',
        transition: 'all 0.3s ease',
        border: '2px solid #000'
      }
    }
  }
}
</script>

<style scoped>
.figura {
  width: 300px; 
  height: 300px; 
  display: flex;
  align-items: center;
  justify-content: center;
  margin: auto;
}
</style>
