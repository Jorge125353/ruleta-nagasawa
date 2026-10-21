
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Ruleta Nagasawa</title>
<style>
:root {
  --green:#20352b;
  --cream:#f5eddb;
  --gold:#c7a461;
}
* { box-sizing:border-box; }
body {
  margin:0;
  background:var(--cream);
  color:#29271f;
  font-family:Georgia,serif;
}
header {
  background:var(--green);
  color:var(--cream);
  text-align:center;
  padding:28px 16px;
  border-bottom:4px solid var(--gold);
}
.eyebrow {
  color:var(--gold);
  font:11px Arial,sans-serif;
  letter-spacing:3px;
  text-transform:uppercase;
}
h1 { font-size:clamp(30px,8vw,44px); font-weight:normal; margin:12px 0; }
header p { line-height:1.6; margin:0 auto; max-width:450px; }
main { max-width:560px; margin:auto; padding:22px 16px 36px; }
.intro { text-align:center; line-height:1.6; }
.wheel-wrap {
  position:relative;
  width:100%;
  max-width:430px;
  margin:24px auto;
  padding:7px;
  background:var(--green);
  border-radius:50%;
}
canvas { display:block; width:100%; height:auto; border-radius:50%; }
.pointer {
  position:absolute; z-index:2; top:-3px; left:50%;
  transform:translateX(-50%);
  width:0; height:0;
  border-left:15px solid transparent;
  border-right:15px solid transparent;
  border-top:30px solid #a44432;
}
button {
  display:block; width:100%; padding:16px;
  margin:12px auto; border:0; border-radius:4px;
  font:bold 14px Arial,sans-serif; letter-spacing:1px;
  cursor:pointer;
}
.primary { background:var(--green); color:var(--cream); }
.secondary { background:transparent; color:var(--green); border:1px solid var(--green); }
button:disabled { opacity:.6; }
#result {
  display:none; background:#fffaf0; padding:22px;
  margin-top:24px; border-top:4px solid var(--gold);
  line-height:1.65;
}
#result.show { display:block; }
#bookTitle { font-size:28px; line-height:1.2; }
.author { font-style:italic; }
.details { font:12px Arial,sans-serif; color:#655f53; }
.question { border-left:3px solid var(--gold); padding-left:12px; }
footer {
  background:var(--green); color:var(--cream);
  text-align:center; padding:22px; font-size:12px; line-height:1.7;
}
footer strong { color:var(--gold); }
</style>
</head>
<body>
<header>
  <div class="eyebrow">Una experiencia literaria</div>
  <h1>Ruleta Nagasawa</h1>
  <p>Sal de los algoritmos. Abre la puerta a otra época. Deja que el azar elija tu próxima lectura.</p>
</header>

<main>
  <p class="intro">
    Una regla: autores fallecidos hace al menos 30 años.
    Veinticuatro caminos posibles. ¿Cuál será el tuyo?
  </p>

  <div class="wheel-wrap">
    <div class="pointer"></div>
    <canvas id="wheel" width="700" height="700"></canvas>
  </div>

  <button id="spin" class="primary">GIRAR LA RULETA</button>

  <section id="result" aria-live="polite">
    <div>✨ TU PRÓXIMA LECTURA</div>
    <h2 id="bookTitle"></h2>
    <p class="author" id="bookAuthor"></p>
    <p class="details" id="bookDetails"></p>
    <p id="bookDescription"></p>
    <p class="question" id="bookQuestion"></p>
    <button id="share" class="secondary">COMPARTIR RESULTADO</button>
    <button id="again" class="secondary">VOLVER A GIRAR</button>
  </section>
  <p style="text-align:center;font:12px Arial,sans-serif;line-height:1.6">
    Sin registros. Sin recomendaciones algorítmicas. Solo libros y azar.
  </p>
</main>

<footer>
  <strong>LEE DIFERENTE.</strong><br>
  Menos algoritmos. Más descubrimientos.<br>
  Ruleta Nagasawa
</footer>

<script>
"use strict";

const books = [
["Don Quijote de la Mancha","Miguel de Cervantes","1605–1615",1616,"Aventura","Un hidalgo sale al mundo decidido a vivir según sus ideales.","¿Es mejor ver el mundo como es o como podría ser?"],
["La vida es sueño","Pedro Calderón de la Barca","1635",1681,"Teatro","Un príncipe se enfrenta al destino, la libertad y sus decisiones.","¿Cómo actuarías si no supieras distinguir sueño y realidad?"],
["Orgullo y prejuicio","Jane Austen","1813",1817,"Novela","Elizabeth Bennet y Darcy desafían sus primeras impresiones.","¿Cuántas veces confundimos prejuicio con verdad?"],
["Frankenstein","Mary Shelley","1818",1851,"Gótico","Una creación extraordinaria revela la soledad y la responsabilidad de su creador.","¿Quién es el verdadero monstruo?"],
["Jane Eyre","Charlotte Brontë","1847",1855,"Novela","Una joven busca independencia y dignidad en un mundo desigual.","¿Qué sacrificarías para no traicionarte?"],
["La Regenta","Leopoldo Alas, Clarín","1884–1885",1901,"Realismo","Ana Ozores vive atrapada entre las convenciones y sus deseos.","¿Cuánto nos condiciona la presión social?"],
["Fortunata y Jacinta","Benito Pérez Galdós","1887",1920,"Realismo","Dos mujeres de mundos distintos protagonizan un retrato del Madrid del siglo XIX.","¿Hasta qué punto determina nuestra vida la clase social?"],
["El retrato de Dorian Gray","Oscar Wilde","1890–1891",1900,"Filosofía","Un retrato envejece mientras su protagonista conserva la juventud.","¿Qué precio tiene vivir sin asumir consecuencias?"],
["La máquina del tiempo","H. G. Wells","1895",1946,"Ciencia ficción","Un viajero descubre una humanidad transformada en un futuro remoto.","¿Progreso significa siempre vivir mejor?"],
["La llamada de lo salvaje","Jack London","1903",1916,"Aventura","Buck debe adaptarse a la dureza del Yukón para sobrevivir.","¿Qué aparece cuando desaparecen las comodidades?"],
["El árbol de la ciencia","Pío Baroja","1911",1956,"Filosofía","Un estudiante de medicina trata de comprender una sociedad que le decepciona.","¿Saber más nos ayuda siempre a vivir mejor?"],
["Niebla","Miguel de Unamuno","1914",1936,"Metaficción","Augusto Pérez cuestiona su existencia y los límites de la ficción.","¿Cuánto control tenemos sobre nuestra historia?"],
["La metamorfosis","Franz Kafka","1915",1924,"Existencialismo","La transformación de Gregor Samsa pone a prueba los vínculos familiares.","¿Qué ocurre cuando dejamos de ser útiles para otros?"],
["La señora Dalloway","Virginia Woolf","1925",1941,"Modernismo","Un día en Londres entrelaza recuerdos, heridas y expectativas.","¿Cuánto escondemos detrás de lo que mostramos?"],
["El proceso","Franz Kafka","1925",1924,"Absurdo","Josef K. afronta una acusación que nadie le explica. Publicada póstumamente.","¿Cómo defenderte de una acusación incomprensible?"],
["El asesinato de Roger Ackroyd","Agatha Christie","1926",1976,"Misterio","Poirot investiga una muerte entre secretos y sospechosos.","¿Qué detalles ignoramos cuando creemos conocer la respuesta?"],
["Una habitación propia","Virginia Woolf","1929",1941,"Ensayo","Una reflexión sobre las condiciones necesarias para que las mujeres puedan crear.","¿Qué necesita una persona para desarrollar su talento?"],
["El halcón maltés","Dashiell Hammett","1930",1961,"Novela negra","El detective Sam Spade persigue una estatuilla rodeada de engaños.","¿Qué sucede cuando todos persiguen su propio interés?"],
["Asesinato en el Orient Express","Agatha Christie","1934",1976,"Misterio","Un asesinato obliga a Poirot a reconstruir los hechos en un tren.","¿Puede la justicia legal diferir de la moral?"],
["El principito","Antoine de Saint-Exupéry","1943",1944,"Fábula","Un pequeño viajero enseña a mirar de otra manera el afecto y la pérdida.","¿Qué dejamos de ver al hacernos mayores?"],
["El extranjero","Albert Camus","1942",1960,"Existencialismo","Meursault se enfrenta a una sociedad que juzga su forma de sentir.","¿Juzgamos los actos o las emociones de los demás?"],
["Ficciones","Jorge Luis Borges","1944",1986,"Relatos","Laberintos, bibliotecas y mundos imaginarios desafían la realidad.","¿Puede una idea transformar tu mundo?"],
["Siddhartha","Hermann Hesse","1922",1962,"Búsqueda interior","Un joven busca sabiduría a través de experiencias muy distintas.","¿Se puede aprender a vivir solo con las enseñanzas ajenas?"],
["Pedro Páramo","Juan Rulfo","1955",1986,"Realismo mágico","Juan Preciado llega a Comala, un pueblo lleno de voces y recuerdos.","¿Cómo sigue gobernando el pasado a quienes vienen después?"]
].map(([title,author,years,death,genre,description,question])=>({title,author,years,death,genre,description,question}));

const canvas = document.getElementById("wheel");
const ctx = canvas.getContext("2d");
const spinButton = document.getElementById("spin");
const resultBox = document.getElementById("result");
const colors = ["#314b3b","#f0dfbd","#8a4335","#c7a461"];
const TAU = Math.PI * 2;
let rotation = 0;
let spinning = false;
let chosen = null;

function drawWheel() {
  const size = canvas.width;
  const c = size / 2;
  const r = c - 5;
  const slice = TAU / books.length;

  ctx.clearRect(0,0,size,size);

  books.forEach((book,i)=>{
    const start = -Math.PI/2 + i*slice;
    const end = start + slice;
    ctx.beginPath();
    ctx.moveTo(c,c);
    ctx.arc(c,c,r,start,end);
    ctx.closePath();
    ctx.fillStyle = colors[i%colors.length];
    ctx.fill();
    ctx.strokeStyle = "#f5eddb";
    ctx.lineWidth = 2;
    ctx.stroke();

    ctx.save();
    ctx.translate(c,c);
    ctx.rotate(start+slice/2);
    ctx.textAlign = "right";
    ctx.textBaseline = "middle";
    ctx.fillStyle = i%4===1 ? "#29271f" : "#fff8e9";
    ctx.font = "bold 15px Georgia";
    let label = book.title;
    if(label.length>25) label=label.slice(0,23)+"…";
    ctx.fillText(label,r-18,0,r*0.55);
    ctx.restore();
  });

  ctx.beginPath();
  ctx.arc(c,c,54,0,TAU);
  ctx.fillStyle = "#20352b";
  ctx.fill();
  ctx.strokeStyle = "#c7a461";
  ctx.lineWidth = 4;
  ctx.stroke();
  ctx.fillStyle = "#f5eddb";
  ctx.textAlign = "center";
  ctx.textBaseline = "middle";
  ctx.font = "bold 15px Georgia";
  ctx.fillText("LEE",c,c-9);
  ctx.fillText("DIFERENTE",c,c+10);
}

function showResult(book) {
  chosen = book;
  document.getElementById("bookTitle").textContent = book.title;
  document.getElementById("bookAuthor").textContent = book.author;
  document.getElementById("bookDetails").textContent =
    "Publicación: "+book.years+" · "+book.genre+
    " · Fallecimiento: "+book.death;
  document.getElementById("bookDescription").textContent = book.description;
  document.getElementById("bookQuestion").textContent = book.question;
  resultBox.classList.add("show");
  resultBox.scrollIntoView({behavior:"smooth",block:"nearest"});
}

function spin() {
  if(spinning) return;
  spinning = true;
  spinButton.disabled = true;
  resultBox.classList.remove("show");

  const index = Math.floor(Math.random()*books.length);
  const sliceDegrees = 360/books.length;
  const target = (360-(index+0.5)*sliceDegrees+360)%360;
  const current = ((rotation%360)+360)%360;
  const adjustment = (target-current+360)%360;
  const startRotation = rotation;
  const endRotation = rotation+2160+adjustment;
  const startTime = performance.now();
  const duration = 4200;

  function animate(now) {
    const progress = Math.min((now-startTime)/duration,1);
    const eased = 1-Math.pow(1-progress,4);
    rotation = startRotation+(endRotation-startRotation)*eased;
    canvas.style.transform = "rotate("+rotation+"deg)";

    if(progress<1) {
      requestAnimationFrame(animate);
    } else {
      rotation = ((endRotation%360)+360)%360;
      canvas.style.transform = "rotate("+rotation+"deg)";
      spinning = false;
      spinButton.disabled = false;
      showResult(books[index]);
    }
  }
  requestAnimationFrame(animate);
}

spinButton.addEventListener("click",spin);
document.getElementById("again").addEventListener("click",spin);

document.getElementById("share").addEventListener("click",async()=>{
  if(!chosen) return;
  const text = "Mi próxima lectura en la Ruleta Nagasawa: "+
    chosen.title+", de "+chosen.author+". ¿Qué libro te tocará a ti?";
  if(navigator.share) {
    try {
      await navigator.share({title:"Ruleta Nagasawa",text,url:location.href});
    } catch(e) {
      if(e.name!=="AbortError") copyResult(text+"\n"+location.href);
    }
  } else {
    copyResult(text+"\n"+location.href);
  }
});

function copyResult(text) {
  if(navigator.clipboard && navigator.clipboard.writeText) {
    navigator.clipboard.writeText(text)
      .then(()=>alert("Texto copiado. Ya puedes compartirlo."))
      .catch(()=>window.prompt("Copia tu resultado:",text));
  } else {
    window.prompt("Copia tu resultado:",text);
  }
}

drawWheel();
</script>
</body>
</html>
