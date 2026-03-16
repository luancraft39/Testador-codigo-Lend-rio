<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Testador Código Lendário</title>
  <style>
    body {
      background-color: #1a001a; /* Roxo escuro */
      color: #fff;
      font-family: monospace;
      padding: 20px;
    }
    header {
      text-align: center;
      margin-bottom: 20px;
    }
    header img {
      width: 180px;
      display: block;
      margin: 0 auto;
    }
    header h1 {
      background: linear-gradient(90deg, #7b2fff, #00d4ff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      font-size: 2em;
      margin-top: 10px;
    }
    textarea {
      width: 100%;
      height: 200px;
      background-color: #2a0033;
      color: #0ff;
      font-family: monospace;
      padding: 10px;
      border: 1px solid #7b2fff;
    }
    button {
      margin: 5px;
      padding: 10px 20px;
      background: linear-gradient(90deg, #7b2fff, #00d4ff);
      color: #111;
      font-weight: bold;
      cursor: pointer;
      border: none;
      transition: 0.3s;
    }
    button:hover {
      opacity: 0.8;
    }
    iframe {
      margin-top: 20px;
      width: 100%;
      height: 400px;
      border: 2px solid #7b2fff;
      background: #fff;
    }
    footer {
      text-align: center;
      margin-top: 20px;
      color: #aaa;
    }
  </style>
</head>
<body>
  <header>
    <!-- Novo logo da Lendário Studio -->
    <img src="https://files.catbox.moe/om54bz.png" alt="Lendário Studio Logo">
    <h1>💻 Testador Código Lendário</h1>
  </header>

  <textarea id="codigo" placeholder="Cole seu código HTML/JS/CSS aqui..."></textarea>
  <br>
  <button onclick="testarCodigo()">Testar Código Lendário</button>
  <button onclick="limparCodigo()">Limpar</button>
  <button onclick="salvarCodigo()">Salvar</button>

  <iframe id="output"></iframe>

  <script>
    function testarCodigo() {
      const codigo = document.getElementById("codigo").value;
      const iframe = document.getElementById("output");
      const doc = iframe.contentDocument || iframe.contentWindow.document;
      doc.open();
      doc.write(codigo);
      doc.close();
    }

    function limparCodigo() {
      document.getElementById("codigo").value = "";
    }

    function salvarCodigo() {
      const codigo = document.getElementById("codigo").value;
      const blob = new Blob([codigo], { type: "text/html" });
      const link = document.createElement("a");
      link.href = URL.createObjectURL(blob);
      link.download = "codigo_lendario.html";
      link.click();
    }
  </script>

  <footer>
    <p>© 2026 Lendário Studio – Testador Código Lendário</p>
  </footer>
</body>
</html>
