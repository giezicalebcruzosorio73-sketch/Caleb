<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Honey Glow</title>
<link rel="stylesheet" href="style.css">
</head>

<body>

<header>
<h1>🍯 Honey Glow</h1>
<button onclick="modoOscuro()">🌙</button>
</header>

<section class="oferta">
<h2>🔥 Oferta termina en:</h2>
<p id="contador"></p>
</section>

<section id="productos">
<h2>Productos</h2>

<div class="producto">
<img src="images/mascarilla.jpg">
<h3>Mascarilla Natural</h3>
<p>Precio: $100</p>
<input type="number" id="cant1" value="1" min="1">
<button onclick="agregar('Mascarilla',100,'cant1')">Agregar</button>
</div>

<div class="producto">
<img src="images/parches.jpg">
<h3>Parches para Ojeras</h3>
<p>Precio: $80</p>
<input type="number" id="cant2" value="1" min="1">
<button onclick="agregar('Parches',80,'cant2')">Agregar</button>
</div>

</section>

<section id="carrito">
<h2>🛒 Carrito</h2>
<ul id="lista"></ul>
<p id="total"></p>
<button onclick="enviarWhats()">Finalizar Pedido</button>
</section>

<section>
<h2>Mayoreo</h2>
<p>10 piezas o más = 10% descuento automático</p>
</section>

<section>
<h2>Opiniones</h2>
<p>⭐⭐⭐⭐⭐ Excelente calidad</p>
<p>⭐⭐⭐⭐⭐ Entrega rápida</p>
</section>

<section>
<h2>Entrega</h2>
<p>✔ Solo en el pueblo</p>
<p>✔ Pago en efectivo contra entrega</p>
</section>

<footer>
<p>© 2026 Honey Glow</p>
</footer>

<script src="script.js"></script>

</body>
</html>style.cssbody{
font-family:Arial;
margin:0;
background:#fff8f0;
text-align:center;
}

header{
background:#f4b400;
padding:15px;
color:white;
display:flex;
justify-content:space-between;
align-items:center;
}

.producto{
background:white;
margin:20px;
padding:15px;
border-radius:10px;
box-shadow:0 0 10px rgba(0,0,0,0.1);
}

.producto img{
width:200px;
border-radius:10px;
}

button{
background:#f4b400;
border:none;
padding:8px 15px;
border-radius:15px;
cursor:pointer;
}

.oferta{
background:#ffe7a3;
padding:15px;
}

.dark{
background:#222;
color:white;
}script.jslet carrito = [];
let total = 0;

function agregar(nombre, precio, idCantidad){
let cantidad = parseInt(document.getElementById(idCantidad).value);
let subtotal = precio * cantidad;

if(cantidad >= 10){
subtotal = subtotal * 0.9;
}

carrito.push(nombre + " x" + cantidad);
total += subtotal;

document.getElementById("lista").innerHTML += "<li>" + nombre + " x" + cantidad + "</li>";
document.getElementById("total").innerText = "Total: $" + total;
}

function enviarWhats(){
let mensaje = "Pedido Honey Glow:%0A";
carrito.forEach(p => mensaje += p + "%0A");
mensaje += "Total: $" + total;

window.open("https://wa.me/5210000000000?text=" + mensaje);
}

function modoOscuro(){
document.body.classList.toggle("dark");
}

let tiempo = 3600;
setInterval(()=>{
let minutos = Math.floor(tiempo/60);
let segundos = tiempo%60;
document.getElementById("contador").innerText = minutos + "m " + segundos + "s";
tiempo--;
},1000);images/mascarilla.jpg
images/parches.jpgimages/mascarilla.jpghttps://TUUSUARIO.github.io/honey-glowhoney-glowindex.html