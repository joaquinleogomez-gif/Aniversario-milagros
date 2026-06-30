// Cuando cargue la página
document.addEventListener("DOMContentLoaded", () => {

const boton = document.getElementById("entrar");
const carta = document.querySelector(".carta");
const inicio = document.querySelector(".inicio");

// 👉 Mostrar carta al hacer click
boton.addEventListener("click", () => {
inicio.style.display = "none";
carta.classList.remove("oculto");

// Efecto suave de aparición
carta.style.opacity = 0;
setTimeout(() => {
carta.style.transition = "1.5s";
carta.style.opacity = 1;
}, 100);
});

// 💖 Corazones flotando
function crearCorazon() {
const corazon = document.createElement("div");
corazon.innerHTML = "❤️";
corazon.style.position = "fixed";
corazon.style.left = Math.random() * 100 + "vw";
corazon.style.top = "100vh";
corazon.style.fontSize = Math.random() * 20 + 10 + "px";
corazon.style.opacity = 0.7;
corazon.style.animation = "subir 5s linear";

document.body.appendChild(corazon);

setTimeout(() => {
corazon.remove();
}, 5000);
}

setInterval(crearCorazon, 600);

// ⏳ Contador desde 6 de julio de 2024
function actualizarContador() {
const inicio = new Date("2024-07-06");
const ahora = new Date();

let diff = ahora - inicio;

let dias = Math.floor(diff / (1000 * 60 * 60 * 24));

document.title = `Joaquín ❤️ Milagros - ${dias} días juntos`;
}

setInterval(actualizarContador, 1000);

});@keyframes subir {
0% {
transform: translateY(0);
opacity: 1;
}
100% {
transform: translateY(-110vh);
opacity: 0;
}
}body {
overflow-x: hidden;
}