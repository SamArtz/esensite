/* Objetos ocultos */
var formulario;

/* SEGURIDAD: proteccion CSRF - agrega el token de sesion como campo oculto a todos los formularios de la pagina */
function inicInyectarTokenCSRF(){
	var metaToken = document.querySelector('meta[name="csrf-token"]');
	if(!metaToken){
		return;
	}
	var token = metaToken.getAttribute('content');
	var formularios = document.getElementsByTagName('form');
	for(var i = 0; i < formularios.length; i++){
		if(!formularios[i].querySelector('input[name="csrf"]')){
			var campo = document.createElement('input');
			campo.setAttribute('type', 'hidden');
			campo.setAttribute('name', 'csrf');
			campo.setAttribute('value', token);
			formularios[i].appendChild(campo);
		}
	}
}
if(document.readyState === 'loading'){
	document.addEventListener('DOMContentLoaded', inicInyectarTokenCSRF);
}else{
	inicInyectarTokenCSRF();
}

function inicMostrarOcultar(obj, opc){
	var objeto = document.getElementById(obj);
	if(objeto.style.display=="" || objeto.style.display=="block"){
		if(opc==1){
			objeto.style.display = "none";
		}
		else{
			inicOcultarFormulario(objeto);
		}
	}
	else{
		if(opc==1){
			objeto.style.display = "";
		}
		else{
			inicMostrarFormulario(objeto);
		}
		
	}
}

function inicCrearfondo(color, transparencia){
	var fondo = document.createElement("div");
	var fondoAct;

	fondo.name = "fondoPantalla";
	fondo.id = "fondoPantalla";
	document.documentElement.appendChild(fondo);
	
	fondoAct = document.getElementById("fondoPantalla");
	fondoAct.style.position = "fixed";
	fondoAct.style.top = 0;
	fondoAct.style.top = 0;
	fondoAct.style.backgroundColor = color;
	fondoAct.style.width = "100%";
	fondoAct.style.height = "100%";
	fondoAct.style.zindex = "10";
	fondoAct.style.opacity = 0;
	inicAnimarTransparencia("fondoPantalla", transparencia/100);
}

function inicAnimarTransparencia(obj, transparencia){
	var fondoAct = document.getElementById(obj);
	var transActual = fondoAct.style.opacity;
	if(transActual<transparencia){
		fondoAct.style.opacity = parseFloat(transActual) + 0.1;
		setTimeout(function(){ inicAnimarTransparencia(obj, transparencia); }, 40);
	}
	else{
		var posicionY = window.pageYOffset + 80
		formulario.style.top = posicionY + "px";
		formulario.style.display = "";
	}
}

function inicMostrarFormulario(forma){
	formulario = forma;
	inicCrearfondo("#1C4986", 40);
}

function inicOcultarFormulario(forma){
	var fondoAct = document.getElementById("fondoPantalla");
	document.documentElement.removeChild(fondoAct);
	forma.style.display = "none";
}

function inicActivarMenu(obj){
	var nombre = obj.id;
	var subMenu;
	if(nombre.substr(0,1)!="s"){
		subMenu = document.getElementById("s" + obj.id);
		var npos = obj.offsetLeft;
		subMenu.style.left = npos + "px";
	}
	else{
		subMenu = obj;
		var menu = document.getElementById(nombre.substr(1, nombre.length));
		menu.className = "menuPrincipalActivo";
	}
	subMenu.style.display = "block";
}

function inicDesactivarMenu(obj){
	var nombre = obj.id;
	var subMenu;
	if(nombre.substr(0,1)!="s"){
		subMenu = document.getElementById("s" + obj.id);
	}
	else{
		subMenu = obj;
		var menu = document.getElementById(nombre.substr(1, nombre.length));
		menu.className = "menuPrincipal";
	}
	subMenu.style.display = "none";
}

/* Confirmacion */
function inicConfirmar(mensaje, direccion){
	if(confirm(mensaje)){
		document.location.href = direccion;
	}
}

/* Seleccionar checkbox */
function inicSeleccionarCheckBox(obj, selec){
	var contenedor;
	var selector;
	var nodosContenedor;
	var totalNodos;
	
	contenedor = document.getElementById(obj);
	selector = document.getElementById(selec);
	nodosContenedor = contenedor.getElementsByTagName("input");
	totalNodos = nodosContenedor.length;
	
	for(i=0; i<totalNodos; i++){
		if(nodosContenedor[i].getAttribute("type") == "checkbox"){
			if(selector.checked){
				nodosContenedor[i].checked = true;
			}
			else{
				nodosContenedor[i].checked = false;
			}
		}
	}
}