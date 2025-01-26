# Go Travel Landing Page

## Descripción del proyecto
A web project developed with Vuejs 3 + Vite + TailwindCSS.

Desarrollo de una landing page para un sitio web de viajes.

## Instalación 
1. Clonar el repositorio: 
```bash 
git clone https://github.com/Azfe/landingpage_gotravel.git
```

2. Navegar al directorio del proyecto:
```bash
cd landingpage_gotravel
```
3. En la terminal de comandos instalar dependencias definidas en el archivo `package.json` de Node.js:
```bash
npm install
```
4. En la terminal de comandos ejecutar el script de los estilos de Tailwind CSS:
```bash
npm run tw:build
```
5. Abrir el archivo `index.html` en tu navegador web favorito.

## Uso
### Navegación
- Utiliza el menú de navegación para explorar las diferentes secciones.
- Haz scroll hacia abajo para visualizar los diferentes apartados de la página.

## Tecnologías
### Languages ⌨
<code><img height="30" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/javascript/javascript.png"></code>
<code><img height="30" src="https://img.icons8.com/?size=160&id=Xf1sHBmY73hA&format=png"></code>
<code><img height="30" src="https://banner2.cleanpng.com/20180718/cbh/4924da87f795e6a7242d3f32fcd4b413.webp"></code>
<code><img height="30" src="https://adware-technologies.s3.amazonaws.com/uploads/technology/thumbnail/31/tailwind.png"></code>

<code><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/61/HTML5_logo_and_wordmark.svg/768px-HTML5_logo_and_wordmark.svg.png" alt="HTML5" width="30"></code>
<code><img src="https://cdn-icons-png.flaticon.com/512/919/919826.png" alt="CSS3" width="30"></code>

### Tools 🛠️
<code><img height="30" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/firebase/firebase.png"></code>
<code><img height="30" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/git/git.png"></code>
<code><img height="30" src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2d/Visual_Studio_Code_1.18_icon.svg/1200px-Visual_Studio_Code_1.18_icon.svg.png" alt="vscode"></code>
<code><img height="30" src="https://static-00.iconduck.com/assets.00/apps-figma-icon-1024x1024-cb4t8vyj.png" alt="Figma"></code>

## Decisiones técnicas

### Uso de Vue.js 3.  
    Vue.js es un framework progresivo y altamente eficiente para construir interfaces de usuario interactivas.

    Beneficios:
        - Reactividad integrada para actualizaciones dinámicas de la interfaz.
        - Componentes reutilizables que facilitan el mantenimiento y la escalabilidad.
        - Sintaxis clara y sencilla con <script setup> para un desarrollo más rápido.

### Tailwind CSS para el Diseño
    Tailwind CSS es un framework de utilidades que permite diseñar interfaces de manera rápida y consistente.
    Para este proyecto se utiliza la versión 4 de Tailwind CSS.
    
    Beneficios:
        - Estilos directamente en el HTML, lo que agiliza el desarrollo.
        - Diseño responsive integrado con clases como md:, lg:.
        - Personalización fácil mediante el archivo style.css y la directiva @theme.

### Uso de localStorage para Almacenar el Token JWT
    localStorage permite persistir el token de autenticación incluso después de cerrar el navegador.

    Beneficios:
    - El usuario no necesita iniciar sesión cada vez que recarga la página.
    - Fácil acceso al token para incluirlo en las cabeceras de las solicitudes HTTP.

## Autor
- Nombre: Alejandro Zapata
- Email: alexzapata1984@gmail.com
