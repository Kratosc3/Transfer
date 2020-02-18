## JS File upload with preview

````code  
###JS
```javascript
function start(){ // Works "onchange=()" eventCaller
var preview = document.querySelector('#preview');
var files   = document.querySelector('input[type=file]').files;

function ale(file){
var reader = new FileReader();
reader.addEventListener("load", function () {
var image = new Image();
image.height = 100;
image.src = this.result;
preview.appendChild( image );}
,false);
reader.readAsDataURL(file);
}

if(files){[].forEach.call(files,ale);}

}
```
### HTML
```HTML
<input type="file" value="Submit" multiple onchange = (start())>
<div id='preview'>a</div>
```
````
