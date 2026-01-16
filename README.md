# CANVAS (HTML5)

## 01 - Canvas Context

### canvas

    <canvas id="canvas" width="600" height="400"></canvas>

### script

    <script>
        window.onload = function(){
            canvas = document.getElementById("canvas");
            if(canvas && canvas.getContext){
                ctx = canvas.getContext("2d");
                if(ctx){
                    ...
                }
            }
        }
    </script>

---

## 02 - Rectángulos

### fillStyle
Define el color de relleno. Recibe un color / código de color.

    ctx.fillStyle = "yellow";

### strokeStyle
Define el color del borde. Recibe un color / código de color.

    ctx.strokeStyle = "#ff0000";

### lineWidth
Define el grosor del borde. Recibe un valor numérico (pixels).

    ctx.lineWidth = 5;

### fillRect(x, y, width, height)
Define la ubicación (x, y) y el tamaño (width, height) del relleno.

    ctx.fillRect(50, 50, 100, 100);

### strokeRect(x, y, width, height)
Define la ubicación (x, y) y el tamaño (width, height) del borde.

    ctx.strokeRect(50, 50, 100, 100);

---

## 03 - Lineas

### lineWidth
Define el grosor de la linea. Recibe un valor numérico (pixels).  

    ctx.lineWidth = 5;

### strokeStyle
Define el color de la linea. Recibe un color / código de color.

    ctx.strokeStyle = "yellow";

### beginPath()
Inicia una nueva ruta de dibujo (trazo)

### moveTo(x, y)
Posiciona el cursor (x, y) sin dibujar. Establece punto inicial del trazado.

    ctx.moveTo(50,50);

### lineTo(x, y)
Dibuja una linea desde el punto establecido como punto inicial (moveTo(x, y)) hasta las coordenadas especificadas.

    ctx.lineTo(x, y);

### stroke()
Dibuja el contorno / linea definido previamente.

    ctx.stroke();

### lineCap
Define el estilo de los extremos de la linea.

    ctx.lineCap = "round"
    ctx.lineCap = "square"
    ctx.lineCap = "butt"

### lineJoin
Define el estilo de las uniones (vértices) entre trazos dentro de la linea.

    ctx.lineJoin = "round"
    ctx.lineJoin = "bevel"
    ctx.lineJoin = "miter"