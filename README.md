[![License Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg?style=true)](http://www.apache.org/licenses/LICENSE-2.0)
[![gitter](https://badges.gitter.im/Join%20Chat.svg)][gitter]

![logo.jloads.com](https://logo.jloads.com/6/cover.png)

# stay native and react faster!
only for old school javascript developers
+ JSON definition
+ native JS code over framework's
+ modularisation over refactoring

Are you for legacy code ready?

+ let's try with jLoads
     

## [Biblioteka jLoads](https://docs.jloads.com)

+ oferuje streamowanie interfejsu aplikacji

+ wspiera natywne rozwiązania, dzięki temu ułatwia rozwój projektów z tzw. kodem zastanym (legacy code)

+ stworzony dla programistów szukających prostych rozwiązań nastawionych na utrzymanie starszych aplikacji

+ zorientowany na modularyzację oraz płaską ale rozproszoną strukturę projektu

+ wspiera proces refaktoryzacji, modularyzacja pozwala na szybkie wdrożenie, dając gwarancję zgodnego, bo natywnego kodu na dekady

+ modularyzacja pozwala na stosowanie najnowszych rozwiązań i ominięcie pułapek stojących za frameworkami z ich aktualizacją

Obecnie rozwiązanie jLoads dotyczy frontendu, ale trwają pracę nad wykorzystaniem NodeJS do wsparcia backendu, co pozwoli na uruchomienie kodu bez opóźnieniea wynikającego z ładowania plików po załadowaniu strony.


## More ...
 + [All projects on github](https://github.com/jloads/)
 + [jLoads on github](https://github.com/jloads/get/)
 + [changelog.md](changelog.md)

## How to learn about jLoads?

+ [presentation](https://www.webslides.pl/event/2021/4developers/index.html)
+ [book](http://book.jloads.com/)

## How to use? 

### Load to Your project [get.jloads.com/jloads.min.js](https://get.jloads.com/jloads.min.js)
```js
<script src="//get.jloads.com/jloads.min.js">
 // Jloads is loading any media and content dynamically
</script>
```
 
### [Example dependencies](https://docs.jloads.com/test.html) 
+ first is loaded jquer and after bootstrap files
+ asynchronus, without special tags, only jloads logic to controll JS loading

```js
<script>
 jl.file({
     "//code.jquery.com/jquery-3.5.1.min.js": [
         "//stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js",
         "//stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
     ]
 });
</script>
```



# Przykładowe MVP
implementacja MVP z biblioteką jLoads

### Proste przeładowanie tła, tekstu, grafiki
+ [get.jloads.com](https://get.jloads.com/)


### Formularz
+ [FaaS](https://www.faas.ovh/)
+ [faas-ovh/www: Website](https://github.com/faas-ovh/www)

### Edytor
+ [edit](https://edit.ovh/)
+ [plainedit/flat: Edit is an example on ovh domain](https://github.com/plainedit/flat)

### Aplikacja do nauki gramatyki
+ [www.gramatyka .de](https://www.gramatyka.de/)
+ [tom-sapletta-com/gramatyka-de: Nauka Gramatyki Niemieckiej poprzez matrycę](https://github.com/tom-sapletta-com/gramatyka-de)

## Standardy
Programowanie aspektowe (aspect-oriented programming, AOP) to paradygmat tworzenia programów komputerowych wspomagający separację zagadnień i rozdzielenie programu na części w jak największym stopniu niezwiązane funkcjonalnie.
Zagadnienia te są w dużym stopniu rozłączne pomiędzy sobą pod względem funkcjonalnym. Aby je zrealizować, programista musi poprzeplatać ich implementacje (tzw. warkocz), co czyni kod mniej czytelnym, bardziej podatnym na błędy, trudniejszym w modyfikacji.
Programowanie aspektowe zapobiega tym negatywnym skutkom oddzielając fizycznie kod każdego zagadnienia poprzez umieszczenie ich w oddzielnych aspektach i logiczne zdefiniowanie punktów interakcji pomiędzy nimi.


## Funkcjonalność
możliwe jest ładowanie dynamiczne, poprzez dodawanie przez JS odpowiednich tagów dla:

+ javascript
+ link - style
+ image, file/base64
+ zagnieżdzony html, system pluginów



### kaskadowe ładowanie plików
coś więcej niż tylko łaodwanie plików, one są ładowane w dokładnie takiej samej kolejności
ale jako jeden plik, który pozwala na zaoszczędzenie czasu ładowania i pozwala na optymalizację bez użycia zasobów serwera.

Dzięki zastosowaniu rozproszeonej infrastruktury CDN można zwiększyć szybkość ładowania.
 
## Obecnie dostępne są rozwiązania:

+ jloads - klasa do wywołania każdego typu poniżej:
    + jloads.obj
    + jloads.url
    + jloads.content
    + jloads.event


### jloads
klasa do utworzenia dowolnej implementacji objektu jloads


### jloads.obj
loads json object from url as object

```js
jloadsObj("json/sentence.json", function (obj, url) {
 console.log(obj["q&a"], url);
 each(obj["q&a"], function (v,k) {
     var varr = v.split(' ');
     console.log(k,v,varr);
     $('input[name="first"]').val(varr);
 });
});
```

### jloads.url
check url an load what exactly is in url


### jloads.target
funkcja ma za zadanie rozpoznać typ pliku po rozszerzeniu i go załadować
może zostać przetworzone, i np wszystkie pliki js wstępnie pobrane, by skrócić czas ładowania plików oddzielnie.

W pliku JSON określa się selector i do niego ładuje zawartość pliku

#### przykład
```js
{
 "head": [
   "//code.jquery.com/jquery-3.5.1.min.js",
   "//stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js",
   "//stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css",
   "//app.wapka.pl/css/style.css"
 ],
 "body": [
   "//app.wapka.pl/html/body.html"
 ],
 "#form": [
   "//app.wapka.pl/html/create.html",
   "//app.wapka.pl/js/create.js"
 ],
 "#image": [
   "//logo.wapka.pl/wapka-300.png"
 ]
}
```
   
   

### jloads.event
   
w momencie zdarzenia jest ładowany określony plik lub zmieniana wartość 
Można określić precyzyjnie zdarzenie i zawartość jaka ma ulec zmianie


#### przykład

```js
  {  
     "#image": {
          "onclick": {
                   "#image.src::before": "//logo.wapka.pl/wapka-300.png"
                 }                      
          },
          "hover": {
                "#text.src": { 
                       "append": "//logo.wapka.pl/wapka-300.png"
                }                       
         }
     },
     "body": {
          "onload": [
               "//app.wapka.pl/js/create.js"
          ]
     }
  }    
```

```js
{ 
   "selector" : "#image" 
   "event" : "onclick",
   "function": "append",
   "selector": "#image.src"
   "value": "//logo.wapka.pl/wapka-300.png"    
},
```
   
definiowanie jaką wartość chce się zmienić, 
jeśli się nie definiuje to dodaje standardowo jak w jloads.target 
       
```js
  {  
     "#image:onclick": {
         "#image.title::before": "//logo.wapka.pl/wapka-300.png"                                    
     },                
     "html:onload":[
           "//app.wapka.pl/js/create.js"
     ]     
     "#image:onload": {              
           "#image.src": "//logo.wapka.pl/wapka-300.png",
           "#image.title::after": "image loaded"                                    
     }   
  }
```


### jloads.value

ma za zadanie załadować określoną treść w określony xpath

    xpath: value
    
tutaj jest istotne by nie zapomnieć dokładnej ścieżki, aby nie było konfliktów

to rozwiązanie dla bardziej doświadczonych użytkowników

możliwe jest załadowanie wielu treści pod jeden adres xpath
w przypadku gdy adres nie istnieje, jest w poczekalni do momentu aż pojawi się ten element w DOM tree

domyślnie dodaj element do strony

value nie jest analizowane, tylko kolejno wstrzykiwane

#### przykład
```js
{
   { "head.script.src": "//code.jquery.com/jquery-3.5.1.min.js" }, 

   { "head.script.src": "//stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js" }, 

   {
       "head.link.type": "text/css",
       "head.link.rel": "stylesheet",  
       "head.link.href": "//stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" 
   },

   {
       "head.link.type": "text/css",
       "head.link.rel": "stylesheet",  
       "head.link.href": "//app.wapka.pl/css/style.css" 
   },

 "body": [
   "//app.wapka.pl/html/body.html"
 ],
 "#form": [
   "//app.wapka.pl/html/create.html",
   "//app.wapka.pl/js/create.js"
 ],
 "#image": [
   "//logo.wapka.pl/wapka-300.png"
 ]
}
```
    
    
### jloads.form

ma pomóc w operacjach na danych wysyłanych i odbiernaych przez formularze

#### ładowanie pliku po załadowaniu formularza
dotyczy każdego formularza
```js        
"form:onload":[
 "//app.wapka.pl/js/create.js"
]
```

#### ładowanie danych do formularza po jego załadowaniu 
dotyczy wybranego formularza

```js
"#form1:onload":{
  "#form1[method]": "POST",
  "#form1[action]": "//url",
  "#form1 .first_name": "Tom",
  "#form1 .last_name": "Sap",
  "#form1 .email": "tom@sap.com",
  "#form1 .message": "example message",
}  
```
        
lista wyboru
```js
"#form1:onload":{
  "#form1 .servers":[
      {"1":"server 1"},
      {"2":"server 2"},
      {"3":"server 3"}
  ]
}  
```

#### wysłanie danych na podany w formularzu URL i metodą w momencie wysyłania formularza 

```js
   "form:submit":{
       "login": "#form1 .email",
       "name": "#form1 .last_name",
       "content": "#form1 .message",
   }

  {  

     "form:submit": {
         "#image.title::before": "//logo.wapka.pl/wapka-300.png"                                    
     },                

     "#image:onload": {              
           "#image.src": "//logo.wapka.pl/wapka-300.png",
           "#image.title::after": "image loaded"                                    
     }   
  }    
```


### jloads.content

Aplikacja po stronie backend, która pobiera konfigurację

    
Struktura: 
    
    selector : url zasobu
    
jest przetworzona do postaci:
    
    xpath: head, body, #image
    type: js, css, html, png,
    url: oryginalny url zasobu
    
rozszerzona:
    
    url_b64: base64 (local path, konwersja z url http do BASE64.txt)
    content_md5: wygenerowane poprzez md5( content ) 
    content_b64: base64 ( TEXT to BASE64 )
    time: timestamp
    
    
#### przykład

poniższe przykłady pochodzą z jednego z projektów firmy [Softreck](https://softreck.com/)
+ [faas , frontend app](https://github.com/faas-ovh/www)

#### ładowanie skryptów do poszczególnych elementów strony poprzez xpath, gdy element nie jest jeszcze gotowy/załadowany do drzewa DOM, to jloads czeka i załaduje go gdy będzie to możliwe 

```js
   // Load core of application
   jl.target({
       "head": [
           "css/fade-in.css",
           "form/form.js",
           "form/form.css",
           "form/inputs.css",
       ],
       "#forms": {
           "form/app.html": [
               "form/submit.js",
               "form/edit_list.js",
           ]
       },
       "#messages": [
           "js/messages.js"
       ],
       "#images": [
           "//logo.faas.ovh/4/cover.png",
       ],
       "#menu": [
           "html/menu.html",
       ],
       "footer": [
           "html/footer.html"
       ]
   });
``` 
      
#### ładowanie skryptów w zależności od hierarchii, najpierw jQuery a następnie Bootstrap 
        
```js
// load content ASAP with dependencies, that jquery must be first and after that bootstrap
jl.file({
  "//code.jquery.com/jquery-3.5.1.min.js": [
      "//stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js",
      "//stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
  ]
});
```
   
#### ładowanie zawartości w zalezności od wywołanego url 

```js
   // Load dynamically contents depends url #hash
   jl.url({
       "#app": {
           "#forms": {
               "form/app.html": [
                   "form/submit.js",
                   "form/edit_list.js"
               ]
           }
       },
       "#app_man": {
           "#forms": {
               "form/app_man.html": [
                   "form/submit.js",
                   "form/edit_list.js"
               ]
           }
       },
       "#server": {
           "#forms": {
               "form/server.html": [
                   "form/submit.js",
                   "form/edit_list.js"
               ]
           }
       },
       "#webservice": {
           "#forms": {
               "form/webservice.html": [
                   "form/submit.js",
                   "form/edit_list.js"
               ]
           }
       },
       "#cloud": {
           "#forms": {
               "form/cloud.html": [
                   "form/submit.js",
                   "form/edit_list.js"
               ]
           }
       },
       "#local": {
           "#forms": {
               "form/local.html": [
                   "form/submit.js",
                   "form/edit_list.js"
               ]
           }
       },
       "#iot": {
           "#forms": {
               "form/iot.html": [
                   "form/submit.js",
                   "form/edit_list.js"
               ]
           }
       },
       "#api": {
           "#forms": {
               "form/api.html": [
                   "form/submit.js",
                   "form/edit_list.js"
               ]
           }
       },
       "#api_func": {
           "#forms": {
               "form/api_func.html": [
                   "form/submit.js",
                   "form/edit_list.js"
               ]
           }
       },
       "#api_storage": {
           "#forms": {
               "form/api_storage.html": [
                   "form/submit.js",
                   "form/edit_list.js"
               ]
           }
       },
       "#test": {
           "#forms": {
               "form/test.html": [
                   "form/submit.js",
                   "form/edit_list.js"
               ]
           }
       }
   });
```
          
## konfiguracja
obsługiwane funkcje

+ environment:    
    + localhost
    + testing
    + stage
    + production
+ domain, zamiast podawać pełną ścieżkę,
+ target, gdzie mają być załaodowane skrypty domyślnie w head
+ delay, 
+ cache, on/off
   
### Environment
zmienne w zależności od środowiska

    .env({
        "local":{
            "domain": "//localhost:63342/"
        },
        "production":{
            "domain": "//js.jloads.com/"
        }
    })

### Cache
możliwość wyłączenia cache-owania
    
    .cacheOff()
    
    
## Przykladowa implementacja

aplikacja html 
    
     <script src="https://get.jloads.com/jloads-url.js"></script>
 

framework laravel

    {!! Html::script('https://get.jloads.com/jloads-url.js') !!}




## environment

npm upgrade

    npm install -g npm
 
### production
[jLoads.Load - get.jloads.com](https://get.jloads.com/)

### local
[jLoads.Load - localhost:8080](http://localhost:8080/)

start 
    
    start.bat
    
start as process in backgrund
[forever - npm](https://www.npmjs.com/package/forever)
    
    npm install forever -g
    
    start2.bat    
    forever start server.js



### TODO

### Environment friendly
+ sprawdzać czy funkcje już istnieją, informować i blokować
+ jeśli już np biblioteka bootstrap załadowana to informować i blokować 
+ jeśli inne pliki css, czy html załadowane, informować i blokować


### Funkcje
+ informacja przy kazdej funkcji skad pochodzi i jaka to wersja.
+ ladowanie plikow z roznych zrodel w zaleznosci od wersji: local/test/cdn

### Serwer, uslugi
+ odwrocone edytowanie, forkowanie
+ tworzenie wlasnych zestawow projektow
+ historia zmian, bazowanie na repozytoriach git
    + polaczenie z gitem
        + user
        + fork
Tworzenie w locei, poprzez APi i requesty
mozna wykorzystac bezposrednio zdefiniowane API/postman
wywolanie nawet z konsolie, zeby bylo mozna latwo obrabiac kod, zmieniac, doklejac
        
mozliwosc generowania wlasnego kodu online i dolaczania do projektu
lub bazujac na obcym kodzie zmienic go i wygenerowac link w ktorym bedzie mozna
go potem dalej edytowac,  

nodejs: 
+ OpenApi
+ deploy on api.jloads.com
+ ograniczenia dla ilosci requestow z jednego IP
+ kazdy kto publikuje - za darmo
+ plany platne dla tych, ktorzy wykorzytsuja devops, 1EUR/msc | lifetime 10EUR
    + ulatwienie automatycznego deployu biblitoeki w npmjs
    + edytor online
    + funkcja copy paste dla tych, ktorzy szukaja inspiracji
    + platforma uruchamianie kodu JS
    
    
W przszlosci wapka
    + mozna wybirac licencje, mozlwiosc generowania licencji, 
    + shop, market, aplikacji sprzedawanie swojego kodu, praw
    + 

Calls:
+ generator jednego pliku dla loadera z listy, get request
    + format url:  one.js?name=version&name=version&...
+ wyswietlanie dokumentacji konkretnej biblioteki
    + format url:  doc.html?name=version&name=version&...

+ 


## TODO:IDEA

ikonografiki są ładowane bezposrednio z serwisów
+ intergacja z SERWISAMI publicznymi  REST    
    
jloads podaje dane wejsciowe, simple version only GET:
        
        
    {        
        "https://www.crunchbase.com/organization/openbrand": {                        
            "name":"mama",
            "type":" string"
        
        }
    }

more details about connections:

```js
{        
   "URL": "https://www.crunchbase.com/organization/openbrand",
   "TYPE" : "GET"
   "DATA": {                        
       "name":"mama",
       "type":" string"

   }
}    



### Listeners

https://developer.mozilla.org/en-US/docs/Web/API/Window/load_event



### Przykładowe rozwiązanie zaproponowane przez @Comandeer https://github.com/Comandeer

```js
jLoads( {
     preload: {
          "head": [
               'arkusz-stylow.css',
               'jakis-skrypt.js'
          ],
          "nav": {
               "navbar_search/page.html": [
                    "navbar_search/script.js",
                    "navbar_search/init.js"
               ]
          },
          "#breadcrumbs": [
               "breadcrumbs/page.html"
          ],
          "footer": [
               "page/footer.html"
          ]
     },
     router: {
          "#a": {
               "article": "page/editor.html"
          },
          "#b": {
               "article": {
                    "grid/page.html": [
                         "grid/init.js",
                    ]
               }

          },
          "#c": {
               "article": "grid-image/page.html"
          },
          "#d": {
               "article": "page/text.html"
          },
          "#e": {
               "#submenu": {
                    "menu/organisation.html": [
                         "form/submit.js"
                    ]
               }
          },
          "#results": {
               "article": {
                    "grid/page.html": [
                         "grid/init.js",
                    ]
               }
          },
     }
} );

// lub

jLoads( '<URL pliku konfiguracyjnego>' );
```




# Community
---
[gitter]: https://gitter.im/UnitApi/community
[gitter]: https://gitter.im/jloads/community




### github npm

Use `publishConfig` option in your package.json
    
    "publishConfig": { "registry": "https://npm.pkg.github.com/" }

Authenticate
    https://github.com/settings/tokens
    
    npm login --registry=https://npm.pkg.github.com/

Publish
    
    npm publish

