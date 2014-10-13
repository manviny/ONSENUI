ONSENUI
=======

#Patrones de navegación

##1. navegación

  Relación padre-hijo  
  Uso: mediante botones o enlaces  
  ```html
  <ons-navigator> o <ons-toolbar>
  ```  
  ```html
  <ons-navigator>
  ``` 
  És un administrador de una pila de páginas y animador de transiciones. Las páginas que puede almacenar son del tipo ons-page

  
##2. menú desplazable
  Se usa cuando necesitamos muchas páginas en el mismo nivel 
  Uso: mediante desplazamiento o botón en barra superior
  ```html
  <ons-sliding-menu>
  ```

##3. Tab bar
  Se usa para proporcionar de varias características a la aplicación
  Uso: botonera en barra inferior
  ```html
   <ons-tabbar>
  ```
  
  
##4. vista dividida
  Se usa generalmente en tablets o dispositivos con pantallas grandes
  Uso: menú lateral
  ```html
   <ons-split-view>
  ```
