ONSENUI
=======

#Patrones de navegación

##1. navegación

  Relación padre-hijo  
  Uso: mediante botones o enlaces  
    
  ```html
  <ons-navigator title="Navigator" var="myNavigator">
    <ons-page>
      <ons-toolbar>
        <div class="center">Simple Navigation</div>
      </ons-toolbar>
      <div style="text-align: center">
        <br>
        <ons-button modifier="light" onclick="myNavigator.pushPage('page1.html', { animation : 'slide' } )">
          Push Page
        </ons-button>
      </div>
    </ons-page>
  </ons-navigator>
  ```  

  **ons-navigator**: És un administrador de una pila de páginas y animador de transiciones. Las páginas que puede almacenar son del tipo ons-page, este no es visible en nuestra app  
  **ons-toolbar**: nos permite navegar por diferentes páginas, este debe incluirse dentro de ons-page

###Uso desde javascript
  ```javascript
  var options = {
    animation: 'slide', // Tipo de animación ( slide, lift, fade, none )
    onTransitionEnd: function() {} // LLamada cuando termina la animación de transición
  };
  // traer pagina al frente
  myNavigator.pushPage("page2.html", options);
  // volver a la pagina en la pila
  myNavigator.popPage();
  ```
###Uso de la pila de páginas
####navigator.getCurrentPage()

  ```javascript
  myNavigator.pushPage("page2.html", { param1: "value1", param2: "value2" });
  var page = myNavigator.getCurrentPage();
  console.log(page.options.param1); // Will return "value1"
  // page.destroy() -> quita la pagina de la pila
  ```
####navigator.getPages()
  ```javascript
  // Remove the 2nd topmost page from the page stack
  var pages = navigator.getPages();
  pages[1].destroy();
// Now a popPage() will display the 3rd page
  ```

####navigator.insertPage(index, page, options)
  
  index = 0  -> al fondo de la pila  
  index = -1 -> debajo de la página actual    
  ```html
  <ons-navigator var="myNavigator">
    <ons-page>
      <ons-toolbar>
        <div class="left"><ons-back-button ng-show="myNavigator.pages.length > 1">Back</ons-back-button></div>
        <div class="center">Navigator</div>
      </ons-toolbar>
  
      <div style="text-align: center">
        <br>
        <ons-button modifier="light"
                    onclick="myNavigator.insertPage(-1, 'page1.html', {param: 'value'})">
          Insert Page Below
        </ons-button>
      </div>
    </ons-page>
  </ons-navigator> 
  ```

####navigator.resetToPage(page, options)
  Limpia la pila y añade la página a una nueva pila  
  
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
