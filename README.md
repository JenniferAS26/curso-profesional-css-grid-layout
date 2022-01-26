# curso-profesional-css-grid-layout

# Tips
- 1. No es necesario memorizar todas las propiedades y valores
    - Es mejor que nos enfoquemos en conocer para que sirven
- 2. Conoce los conceptos fundamentales
    - Layout: Toda la organizacion de nuestro diseño en la web
    - Selectores
    - Responsive
    - Flujo normal
    - Modelo de caja
    - Herencia y cascada
    - Formatting Contexts
- 3. Usar DevTools para encontrar errores y hacer pruebas rapidas
    - Inspeccionar en el navegador
    - Hacer pruebas rapidas
- 4. Saber que herramientas te sirven para aprender

# Historia
- Navegador Viola en 1993
    - tenia su propio lenguaje de estilos
    - Queria convertir su lenguaje en un estandar para la web
- En 1994 se presento la propuesta inicial de CSS
- Bert Bos
    - Respondio al primer borrador de CSS y unió las fuerzas con Hakon y se presentaron en la conf de WWW en 1995
- 1996 nace CSS como una recomendacion de la W3E
- Los primeros navegadores compatibles con CSS
    - IE3
    - NETSCAPE
    - OPERA

# Limitaciones de CSS y el problema de los elementos flotantes
- Los primeros diseños de CSS eran una mezcla entre los elementos flotantes y posicionados
    - Noodle Incident (Recursos en línea para copiar y pegar)
- Seguían frustrados por la falta de columnas de altura completa
    - Columnas falsas son Dan Cederholm
        - Se creaba una ilusión colocando una imagen de fondo daba la ilusión que la imagen bajaba y quedaba parejo
- Diseño responsivo por Ethan Marcotte
    - Contenido adaptativo
- El problema de los elementos flotantes
    - Funciona bien si se calcula con precisión el ancho y si el contenido tiene la misma altura.
- Se trabajó con display: table
    - Los valores se pueden ampliar a otros elementos HJTML direntes a tr y td como los div y ul
- Existe una gran cantidad de técnicas que son simplemente trucos
- Gracias a eso, el diseño con CSS parece difícil y frágil: No habían herramientas de diseño

# Herramientas que nos han facilitado el camino
- La comunidad desarolló herramientas para facilitar el camino
- 1. Objetivo: EValuar el panorama actual
    - Ya que las herramientas tienen un impacto en la forma en la que diseñamos y desarrollamos
        1. Arquitecturas
        2. Pre y Post procesadores
           - Pre -> nos va a permitir una sintaxis un poco diferente lo que ya conocemos como CSS
           - Post -> nos permite agregar prefijos
        3. Diseño de componentes
            - Atomic Design
        4. Frameworks
        5. Performance
            - Revisar cuanto pesa nuestro navegador
        6. Accesibilidad
            - Para que todas las personas puedan accedera nuestro sitio web
        7. Evergreen Browsers
            - Compatibilidad en los navegadores
        8. Aumentemos nuestra comprensión de por qué suceden las ciertas cosas
            - Es bastante importante ser cada vez más critico en construir nuestras páginas

# ¿CSS Grid es una idea nueva o simplemente viene desde hace mucho tiempo?
- No debería sorprendernos que los diseños basados en cuadrículas hayan sido un objetico de CSS desde el principio
- "CSS comenzó como algo muy simple, era solo una forma de crear una vista de un documento en una pantalla pequeña muy simple en ese momento..."
- Nacio de la necesidad de Microsoft de una herramienta de diseño robusta y flexible para la web si la web iba a ser una opción para el desarrollo de aplicaciones nativas en Windows.
- Hubo 3 ideas fundamentales
    - Idea de Microsoft
    - Diseño avanzado de Bos
    - Adición de líneas de cuadrícula de Linss
- Google consiguió una implementación de CSS Grid en Chromium 56 para Android en enero de 2017.
- Google consiguió su implementación de Chrome a principios de marzo, solo dos días después de que Mozilla enviara su propia implementación en Firefox.
- Antes de que terminara el mes, Opera y Safari también había enviado soporte para CSS Grid.

- CSS Grid pasa de ser una idea interesante con la que puedes jugar a algo que simplemente usas como tu único método de diseño sin tener que preocuparte por otras alternativas.

# ¿Qué significa Grid para CSS?
- CSS Grid requiere una forma completamente nueva de pensar en diseño en CSS.
- Bert Bos "No se trata simplemente de agregar propiedades a cada elemento individual. Ahora puedes tener un modelo diferente en el que comienzas con tu diseño primero y luego incorporas los diferentes elementos en ese diseño."
- Atkins "Es la herramienta de diseño más poderosa que hemos inventado hasta ahora para CSS."
- Etemad "CSS Grid toma todas esas cosas complicadas que tuvimos que hacer para lograr diseños básicos y lo hace completamente innecesario."

# Técnicas de alineamiento antes de CSS Grid: margin y line-height
1. margin -> arriba derecha abajo izquierda // shorthand property
    - margin-top
    - margin-right
    - margin-botton
    - margin-left

2. line-hight
    - text-align -> nos permite alinear textos de forma horizontal
        - text-align: left|right|center|justify|initial|inherit;
    - vertical-align -> nos permite alinear de forma vertical
        - vertical-align: baseline|length|sub|super|top|text-top|middle|bottom|text-bottom|initial|inherit;
    - line-height -> Nos permite alinear de manera vertical, ns permite controlar los altos

3. table-cell
    - display: table-cell -> hace que cualquier elemento se comporte como si fuera un elemento de tabla
    - text-align
    - vertical-align

4. positions
    - position: relative
    - position: absolute
    - top
        - top: <longitud>|<porcentaje>|auto|inherit
                px, em... | % | valor por defeco|hereda del padre
    - right
    - botton
    - left
    - transform: translate()
        - transform: none|transform-functions|initial|inherit;
            - translae(x,y) -> nos ayuda a organizar bien nustras coordenadas x e y
# Pros y contras de las tecnicas de alineamientos antes de CSS Grid
- No hay una propiedad especifica para alinear elementos de bloque en CSS2. No dejan de ser trucos para alinear elementos de bloque.

- Margin
    - ventaja -> El valor auto alinea horizontalmente cualquier elemento con cualquier ancho.
    - deventaja -> Alinear verticalmente, ya que, en cada caso, deberan calcularse estos valores.

- Line-Height
    - ventaja -> Correcta alineación
    - desventaja -> Si el texto ocupa más de una línea el elemento toma un alto más grande que lo necesario paralos cálculos

- Table-Cell
    - ventaja -> La alineación vertical no está condicionada por fuentes, tamaños de fuentes o alturas de línea
    - desventaja -> vertical-align se aplica solo a elementos Inline

# La mayor limitantes
- Propiedades Físicas
    - margin-top
    - padding-botton
    - border-right
    - left

- Ahora debemos empezar a pensar en propuedades lógicas
- Nuestro modo de escritura es el Latin por lo tanto escribimos de izquierda a derecha y nuestro origen es "Left to Right" pero hay otro tipos de escritura como por ejemplo:
    - Left to Right -> Latin
    - Right to Left -> Arabic
    - Bi-Directional -> Latin + Arabic
    - Vertical -> Asian charac
    - Modos de escritura
        - Hozontal TB -> top-botton, escribimos horizontal de izq a der y arriba para abajo
        - Vertical LR ->
        - Sideways LR ->
        - Sideways RL ->
        - Esta propiedad no es apa para tablas -> raw/column
    - Algo a tener muy en cuenta es el modo de escritura, la dirección y la orientación del texto:
        - Block -> Vertical
        - Inline -> Horizontal

# Propiedades Físicas y Lógicas en CSS
- Conceptos fundamentales Block e Inline
    - Propiedades físicas
        - margin
        - padding
        - border
    - Propiedades lógicas
        - margin -> block or inline -> start or end
        - padding -> block or inline -> start or end
        - border -> block or inline -> start or end

- Modelo de caja
    1. Fisico
        - margin-top/right/botton/left
        - padding-top/right/botton/left
        - border-top/right/botton/left
    2. Lógico
        - margin-block-start/end (vertical)
        - padding-block-start/end (vertical)
        - border-block-start/end (vertical)
        - margin-inline-start/end (horizontal)
        - padding-inline-start/end (horizontal)
        - border-inline-start/end (horizontal)


