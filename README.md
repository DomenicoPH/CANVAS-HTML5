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

### closePath()
Cierra el trazo conectando el último punto con el punto inicial.

### fill()
Rellena el trazo. Si el trazo no está cerrado, este método añade una linea del punto final al inicial. Rellena el trazo con el valor de la propiedad fillStyle (por defecto es negro).

---

## 04 - Estados

### save()
Guarda el estado actual del contexto en una pila interna.

    ctx.save();

### restore()
Restaura el último estado guardado con save().

    ctx.restore();

---

## 05 - Arcos

Sintaxis:

    ctx.arc( x, y, anguloInicial, anguloFinal, sentidoCC );

- Los ángulos están expresados en radianes.
- El ángulo 0 está a las 3:00 horas.
- El sentidoCC (Counterclockwise) viene por defecto como false.
- Para un círculo completo el ángulo inicial es 0 y el final es 2*PI.
- Las coordenadas X, Y representan el centro del círculo.
- Se actualiza el dibujo tanto con stroke() como con fill().

        radianes = (grados * PI) / 180
        grados = (180 * radianes) / PI

Arco incompleto:

    ctx.beginPath();
    ctx.arc(100, 150, 50, 1.1*Math.PI, 1.9*Math.PI);
    ctx.stroke();

Arco completo (con relleno):

    ctx.beginPath();
    ctx.arc(400, 150, 50, 0, 2*Math.PI);
    ctx.fill();
    ctx.stroke();

---

## 06 - Curvas Bezier Cuadráticas

Sintaxis:

    ctx.quadraticCurveTo( cpx, cpy, x, y );

**cpx**   : Control Point en X  
**cpy**   : Control Point en Y  
**X**     : punto final en X  
**Y**     : punto final en Y  

    ctx.beginPath();
                    
        var x1 = 20, y1 = 20;
        var cpx = 150, cpy = 200;
        var x2 = 400, y2 = 20;

    ctx.moveTo(x1, y1);
    ctx.quadraticCurveTo(cpx, cpy, x2, y2);
    ctx.stroke();

---

## 07 - Curvas Bezier Cúbicas