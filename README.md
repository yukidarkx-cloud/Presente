# Presente
Para: Maduh
index.html
<!DOCTYPE html><html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Nosso Amor ❤️</title>  <!-- Google Fonts -->  <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;400;600&family=Dancing+Script:wght@400;600&display=swap" rel="stylesheet">  <style>
    body{
      margin:0;
      font-family:'Poppins', sans-serif;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      color:#333;
    }
    header{
      padding:60px 20px;
      text-align:center;
      color:white;
    }
    header h1{
      font-family:'Great Vibes', cursive;
      font-size:3em;
      margin-bottom:10px;
    }
    header p{
      font-family:'Dancing Script', cursive;
      font-size:1.5em;
    }
    section{
      background:white;
      margin:20px;
      padding:30px;
      border-radius:20px;
      box-shadow:0 10px 30px rgba(0,0,0,0.15);
    }
    h2{
      color:#ff5f8a;
      text-align:center;
      font-family:'Dancing Script', cursive;
      font-size:2em;
    }
    .editavel{
      border:2px dashed #ffb3c6;
      padding:15px;
      border-radius:15px;
      text-align:center;
      font-size:1.1em;
      outline:none;
    }
    .contador{
      font-size:1.3em;
      text-align:center;
      margin-top:10px;
      font-weight:600;
    }
    .galeria{
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(120px,1fr));
      gap:15px;
      margin-top:20px;
    }
    .galeria input{
      width:100%;
    }
    .foto img{
      width:100%;
      border-radius:15px;
    }
    .qr{
      text-align:center;
    }
    footer{
      text-align:center;
      padding:20px;
      color:white;
    }
  </style></head>
<body><header>
  <h1 contenteditable="true">Nome dela ❤️</h1>
  <p contenteditable="true">Um presente feito só pra você</p>
</header><section>
  <h2>💌 Mensagem</h2>
  <div class="editavel" contenteditable="true">
    Escreva aqui sua mensagem de amor ✨
  </div>
</section><section>
  <h2>⏳ Nosso Tempo Juntos</h2>
  <p class="editavel" contenteditable="true">Estamos juntos desde: 01/01/2024</p>
  <div class="contador" id="contador"></div>
</section><section>
  <h2>📸 Nossas Fotos</h2>
  <div class="galeria">
    <input type="file" accept="image/*" onchange="addFoto(event)">
    <input type="file" accept="image/*" onchange="addFoto(event)">
    <input type="file" accept="image/*" onchange="addFoto(event)">
  </div>
  <div class="galeria" id="fotos"></div>
</section><section>
  <h2>🎵 Nossa Música</h2>
  <p style="text-align:center">Escolha uma música especial pra vocês</p>
  <div style="text-align:center">
    <input type="file" accept="audio/*" onchange="addMusica(event)">
    <br><br>
    <audio id="player" controls style="width:100%"></audio>
  </div>
</section><section class="qr">
  <h2>📎 Link do Site</h2>
  <p>Copie o link do site para enviar ou gerar o QR Code:</p>
  <input id="link" placeholder="https://seusite.github.io/presente" style="padding:10px;width:80%;border-radius:10px;border:none">
  <br><br>
  <button onclick="copiarLink()" style="padding:12px 25px;border:none;border-radius:20px;background:#ff5f8a;color:white;font-weight:bold">📋 Copiar link</button>
  <p id="copiado" style="color:#ff5f8a;margin-top:10px"></p>
  <br>
  <img id="qrcode">
</section>
  <h2>📱 QR Code</h2>
  <p>Depois que o site estiver online, copie o link e cole aqui:</p>
  <input id="link" placeholder="https://meusite.com" style="padding:10px;width:80%;border-radius:10px;border:none">
  <br><br>
  <img id="qrcode">
</section><footer>
  Feito com amor 💖
</footer><script src="https://cdn.jsdelivr.net/npm/qrcode/build/qrcode.min.js"></script><script>
  // contador de tempo
  const inicio = new Date('2024-01-01');
  function atualizar(){
    const agora = new Date();
    const diff = agora - inicio;
    const dias = Math.floor(diff / (1000*60*60*24));
    document.getElementById('contador').innerText = dias + ' dias juntos ❤️';
  }
  atualizar();

  // fotos
  function addFoto(e){
    const file = e.target.files[0];
    const img = document.createElement('img');
    img.src = URL.createObjectURL(file);
    const div = document.createElement('div');
    div.className = 'foto';
    div.appendChild(img);
    document.getElementById('fotos').appendChild(div);
  }

  // QR code
  document.getElementById('link').addEventListener('input', e =>{
    QRCode.toDataURL(e.target.value, function (err, url) {
      document.getElementById('qrcode').src = url;
    })
  })
</script></body>
</html>
