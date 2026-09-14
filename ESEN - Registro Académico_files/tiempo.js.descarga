var tiempo;

function inicIniciarTiempo(textoTiempo){
    tiempo = new Date(textoTiempo);
    inicActualizarTiempo();
}

function inicActualizarTiempo(){
    setTimeout(inicActualizarTiempo, 1000);
    tiempo.setSeconds(tiempo.getSeconds() + 1);
    inicActualizarHora();
    inicActualizarFecha();
}

function inicActualizarHora(){
    var hora = document.getElementById("hora");
    var horas = tiempo.getHours();
    var minutos = tiempo.getMinutes();
    var segundos = tiempo.getSeconds();
    var formato = "a.m.";
    
    if(horas>11){
        formato = "p.m.";
        if(horas>12){
            horas = horas - 12;
        }
    }
    
    hora.innerHTML = inicAjustarCeros(horas) + ":" + inicAjustarCeros(minutos) + ":" + inicAjustarCeros(segundos) + " " + formato;
}

function inicActualizarFecha(){
    var fecha = document.getElementById("fecha");
    var dia = tiempo.getDate();
    var diaS = tiempo.getDay();
    var mes = tiempo.getMonth();
    var anio = tiempo.getFullYear();
    
    fecha.innerHTML = inicConvertirDiaSemana(diaS) + " " + dia + " de " + inicConvertirMes(mes) + " de " + anio;
}

function inicAjustarCeros(valor){
    if(valor<10){
        valor = "0" + valor;
    }
    return valor;
}

function inicConvertirDiaSemana(dia){
    var dias = ['Domingo', 'Lunes', 'Martes', 'Mi&eacute;rcoles', 'Jueves', 'Viernes', 'S&aacute;bado'];
    return dias[dia];
}

function inicConvertirMes(mes){
    var meses = ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio', 'Julio', 'Agosto', 'Septiembre', 'Octubre', 'Noviembre', 'Diciembre'];
    return meses[mes];
}
