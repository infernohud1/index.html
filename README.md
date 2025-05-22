<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Búsqueda Interna de Imágenes</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      background: #f9f9f9;
    }
    .search-container {
      margin-bottom: 20px;
    }
    input[type="text"] {
      width: 300px;
      padding: 8px;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 4px;
    }
    button {
      padding: 8px 12px;
      font-size: 16px;
      margin-left: 5px;
      border: none;
      background-color: #0073e6;
      color: white;
      border-radius: 4px;
      cursor: pointer;
    }
    button:hover {
      background-color: #005bb5;
    }
    ul {
      list-style: none;
      padding: 0;
    }
    li {
      padding: 5px 0;
    }
    li a {
      text-decoration: none;
      color: #0073e6;
    }
  </style>
</head>
<body>
  <div class="search-container">
    <input type="text" id="searchInput" placeholder="Buscar...">
    <button id="searchButton">Buscar</button>
  </div>
  
  <!-- Lista de imágenes (o enlaces) ordenada ascendentemente desde R-01 -->
  <ul id="imageList">
    <li data-code="r-01"><a href="#R-01">R-01 - Imagen</a></li>
    <li data-code="r-02"><a href="#R-02">R-02 - Imagen</a></li>
    <li data-code="r-03"><a href="#R-03">R-03 - Imagen</a></li>
    <li data-code="r-04"><a href="#R-04">R-04 - Imagen</a></li>
    <li data-code="r-05"><a href="#R-05">R-05 - Imagen</a></li>
    <li data-code="r-06"><a href="#R-06">R-06 - Imagen</a></li>
    <li data-code="r-07"><a href="#R-07">R-07 - Imagen</a></li>
    <li data-code="r-08"><a href="#R-08">R-08 - Imagen</a></li>
    <li data-code="r-09"><a href="#R-09">R-09 - Imagen</a></li>
    <li data-code="r-10"><a href="#R-10">R-10 - Imagen</a></li>
    <li data-code="r-11"><a href="#R-11">R-11 - Imagen</a></li>
    <li data-code="r-12"><a href="#R-12">R-12 - Imagen</a></li>
    <li data-code="r-13"><a href="#R-13">R-13 - Imagen</a></li>
    <li data-code="r-14"><a href="#R-14">R-14 - Imagen</a></li>
    <li data-code="r-15"><a href="#R-15">R-15 - Imagen</a></li>
  </ul>

  <script>
    // Función que filtra la lista según el término ingresado
    function filterList() {
      const input = document.getElementById("searchInput").value.toLowerCase().trim();
      const items = document.querySelectorAll("#imageList li");
      
      items.forEach(function(item) {
        const code = item.getAttribute("data-code").toLowerCase();
        // Si el término está incluido, muestra el elemento; si no, lo oculta
        if (code.includes(input)) {
          item.style.display = "list-item";
        } else {
          item.style.display = "none";
        }
      });
    }

    // Asignar la función al botón y al evento "keyup" para búsqueda en tiempo real
    document.getElementById("searchButton").addEventListener("click", filterList);
    document.getElementById("searchInput").addEventListener("keyup", filterList);
  </script>
</body>
</html>
