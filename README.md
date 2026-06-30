# Aniversario-milagros
index.html<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Joaquín ❤️ Milagros</title>

<link rel="stylesheet" href="style.css">

<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&family=Great+Vibes&display=swap" rel="stylesheet">
</head>

<body>

<div id="stars"></div>

<section class="inicio">

<h1>Joaquín ❤️ Milagros</h1>

<p class="subtitulo">
Una historia que comenzó el 6 de julio de 2024
</p>

<button id="entrar">
💖 Comenzar nuestra historia
</button>

</section>

<section class="carta oculto">

<h2>Para Milagros ❤️</h2>

<p id="textoCarta">

Mi amor...

Hoy no quiero regalarte solo una página.

Quiero regalarte un pedacito de mi corazón.

Desde aquel 6 de julio de 2024 mi vida cambió para siempre.

Sos la luz de mi vida.

Sos lo mejor que me pasó.

Gracias por cada abrazo, cada sonrisa y cada momento.

No puedo imaginar un futuro donde vos no estés.

Te prometo seguir eligiéndote todos los días.

Gracias por hacerme feliz.

Feliz aniversario.

Te amo infinitamente.

❤️

Joaquín.

</p>

</section>

<script src="script.js"></script>

</body>
</html>
*{
margin:0;
padding:0;
box-sizing:border-box;
}

body{
font-family:'Poppins',sans-serif;
background:linear-gradient(180deg,#09091f,#111138,#1c1c52);
color:white;
overflow-x:hidden;
}

#stars{
position:fixed;
width:100%;
height:100%;
background-image:
radial-gradient(white 1px, transparent 1px),
radial-gradient(white 1px, transparent 1px);
background-size:70px 70px;
background-position:0 0,35px 35px;
opacity:.35;
animation:starsMove 60s linear infinite;
z-index:-2;
}

@keyframes starsMove{
from{
transform:translateY(0);
}
to{
transform:translateY(-400px);
}
}

.inicio{
height:100vh;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
text-align:center;
padding:20px;
}

h1{
font-family:'Great Vibes',cursive;
font-size:70px;
color:#ff9ecf;
text-shadow:0 0 20px rgba(255,158,207,.7);
margin-bottom:20px;
}

.subtitulo{
font-size:22px;
opacity:.9;
margin-bottom:40px;
}

button{
background:#ff4f91;
color:white;
border:none;
padding:18px 35px;
border-radius:40px;
font-size:20px;
cursor:pointer;
transition:.3s;
box-shadow:0 0 20px rgba(255,79,145,.5);
}

button:hover{
transform:scale(1.08);
background:#ff6aa7;
}

.carta{
max-width:900px;
margin:auto;
padding:80px 30px;
line-height:2;
font-size:22px;
}

.carta h2{
text-align:center;
font-family:'Great Vibes',cursive;
font-size:60px;
color:#ffd6ea;
margin-bottom:40px;
}

.oculto{
display:none;
}

#textoCarta{
background:rgba(255,255,255,.08);
padding:35px;
border-radius:20px;
backdrop-filter:blur(10px);
box-shadow:0 0 30px rgba(255,255,255,.08);
}

@media(max-width:700px){

h1{
font-size:48px;
}

.carta h2{
font-size:42px;
}

.subtitulo{
font-size:18px;
}

button{
font-size:18px;
padding:15px 30px;
}

#textoCarta{
font-size:18px;
}

}
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
}