<template>
<div class="main-container">
    <div class="header-container">
        <h1>Almacen Fuxia</h1>
        <h4>Quieres un descuento?</h4>
        <h6>prueba tu suerte</h6>
    </div>
    <div class="roulette-container">
        <div>
            <Roulette ref="wheel" :items="items" @click="launchWheel" base-display base-background="#e294c0">
                <template #baseContent>
                    <div >presiona<br><strong>aqui!</strong></div>
                </template>
            </Roulette>
        </div>
        <button class="restartBtn" @click="back_normal">Reiniciar</button>
    </div>

</div>
</template>

<script setup>
import { ref } from 'vue';
import { Roulette } from 'vue3-roulette';
const wheel = ref(null)
const items = [
  { id: 1, name: "10", htmlContent: "10%", textColor: "#fff", background: "#7f0f4e" },
  { id: 2, name: "12", htmlContent: "15%", textColor: "#fff", background: "#a4206b" },
  { id: 3, name: "15", htmlContent: "15%", textColor: "#fff", background: "#7f0f4e" },
  { id: 4, name: "20", htmlContent: "20%", textColor: "#fff", background: "#a4206b" },
  { id: 5, name: "22", htmlContent: "20%", textColor: "#fff", background: "#7f0f4e" },
  { id: 6, name: "25", htmlContent: "25%", textColor: "#fff", background: "#a4206b" },
  { id: 7, name: "30", htmlContent: "30%", textColor: "#fff", background: "#7f0f4e" },
  { id: 8, name: "40", htmlContent: "40%", textColor: "#fff", background: "#a4206b" },
];

function launchWheel (){
  wheel.value.launchWheel();
}

function back_normal() {
    wheel.value.reset()
}
</script>

<style>
.restartBtn {
    color: #7f0f4e;
    margin: auto;
    margin-top: 50px;
    padding: 7px;
    width: 200px;
}
.main-container {
    display: flex;
    flex-direction: column;
}
.roulette-container {
    display: flex;
    flex-direction: column;
}
</style>