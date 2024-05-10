<template>
    <div id="containerCard" class="containerCard">
        
        <form>
          <div>
            <label>Título de la tarjeta: </label>
            <input v-model="tarjeta.tituloTarjeta" />
          </div>
  
          <div>
            <label for="imagen">Chip SRC:</label>
        <select name="imagen" id="imagen" v-model="tarjeta.imagenSeleccionChip">
          <option disabled value="">Elige el chip a usar</option>
          <option v-for="imagen in tarjeta.imagenesChip" 
          :key="imagen.id" :value="imagen.path">{{ imagen.texto }}</option>
        </select>
          </div>
  
          <div>
            <label>Número: </label>
            <input v-model="tarjeta.numero" />
          </div>
  
          <div>
            <label>Fecha de expiración: </label>
            <input v-model="tarjeta.fechaDeExpiracion" />
          </div>
  
          <div>
            <label>Propietario: </label>
            <input v-model="tarjeta.propietario" />
          </div>
  
          <div>
            <label for="imagenBrand">Tipo de tarjeta SRC:</label>
        <select name="imagenBrand" id="imagenBrand" v-model="tarjeta.imagenSeleccionBrand">
          <option disabled value="">Elige la marca de tu tarjeta</option>
          <option v-for="imagen in tarjeta.imagenesBrand" 
          :key="imagen.id" :value="imagen.path">{{ imagen.texto }}</option>
        </select>
          </div>
        </form>
      
   
  
        <div class="tarjeta">
          <h3>{{ tarjeta.tituloTarjeta }}</h3>
          <img width="40" :src="tarjeta.imagenSeleccionChip" :alt="tarjeta.infoChip" />
          <div>
            <h2>{{ tarjeta.numero }}</h2>
            <span>Fecha Exp: <b>{{ tarjeta.fechaDeExpiracion }}</b></span>
          </div>
          <footer>
            <span>{{ tarjeta.propietario }}</span>
            <img :src="tarjeta.imagenSeleccionBrand" width="60" />
          </footer>
        </div>
    </div>
  </template>

<script>
export default {
  name: 'CreditsCard',
  data(){
    return{
        tarjeta: {
            tituloTarjeta: "",
            numero: "",
            imagenSeleccionChip: "",
            infoChip: "Imagen chip",
            imagenesChip: [
          {id: 1, path: "/assets/img/chip.png", texto: "chip 1"},
          {id: 2, path: "/assets/img/chip2.png", texto: "chip 2"},
          {id: 3, path: "/assets/img/chip3.png", texto: "chip 3"},
      ],
      fechaDeExpiracion: "",
      propietario: "",
      imagenSeleccionBrand: "",
      imagenesBrand: [
          {id: 1, path: "/assets/img/visa.png", texto: "Visa"},
          {id: 2, path: "/assets/img/masterCard.png", texto: "Mastercard"},
          {id: 3, path: "/assets/img/dinersClub.png", texto: "Diners Club"},
      ],
        }
    }
  }
  
}
</script>

<style scoped>
* {
  margin: 0;
}
.containerCard {
    background: linear-gradient(rgb(228, 148, 148), rgb(219, 235, 126));  
    border-radius: 15px;
    box-shadow: 0px 0px 10px 2px black;
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 60vh;
  font-size: 10px;
  font-family: sans-serif;
  gap: 40px;
}


form {
    background: linear-gradient(rgb(209, 226, 110), rgb(217, 127, 127));
  padding: 18px;
  border-radius: 20px;
  border: ridge 1px;
  box-shadow: 0px 0px 10px 2px black;
  font-weight: bold;
  display: flex;
  flex-direction: column;
  gap: 15px;
  justify-content: center;
}
form div {
  display: grid;
  grid-template-columns: 100px 200px;
  align-items: center;
  gap: 5px;
}

form div label {
  text-align: right;
}

.tarjeta {
  width: 400px;
  height: 230px;
  background: linear-gradient(rgb(209, 226, 110), rgb(217, 127, 127));
  color: rgb(0, 0, 0);
  border-radius: 20px;
  padding: 20px;
  box-shadow: 0px 0px 10px 2px black;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

h3 {
  font-size: 20px;
}

h2 {
  font-size: 30px;
  letter-spacing: 10px;
  margin-bottom: 15px;
  text-shadow: 0px 0px 1px gold;
  font-family: Times;
}

b {
  font-size: 16px;
}

footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  font-weight: bold;
  font-size: 18px;
  text-transform: uppercase;
  font-style: italic;
}
</style>