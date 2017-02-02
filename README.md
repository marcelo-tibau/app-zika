﻿<!DOCTYPE html>
<html lang="en">
<head>
  <title>Alerta Zika - Rio de Janeiro</title>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  
  <script src="https://d3js.org/d3.v4.min.js"></script>

  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>/
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
  <style> /* set the CSS */

    .axis--x path 
    {
    display: none;
    }

    .line {
    fill: none;
    stroke: steelblue;
    stroke-width: 1.5px;
    }

    .bar
    {
        fill: steelblue;     
    } 

    .selecaoData
    {
        background-color: cadetblue;
        color:whitesmoke;
        align:left;
    }

    .selectControl
    {
        color:black;
    }

    body {
        font: 400 15px Lato, sans-serif;
        line-height: 1.8;
        color: #818181;
    }
  h2 {
      font-size: 24px;
      text-transform: uppercase;
      color: #303030;
      font-weight: 600;
      margin-bottom: 30px;
  }
  h4 {
      font-size: 19px;
      line-height: 1.375em;
      color: #303030;
      font-weight: 400;
      margin-bottom: 30px;
  }  
  .jumbotron {
      background-color: #f4511e;
      color: #fff;
      padding: 100px 25px;
      font-family: Montserrat, sans-serif;
  }
  .container-fluid {
      padding: 60px 50px;
  }
  .bg-grey {
      background-color: #f6f6f6;
  }
  .logo-small {
      color: #f4511e;
      font-size: 50px;
  }
  .logo {
      color: #f4511e;
      font-size: 200px;
  }
  .thumbnail {
      padding: 0 0 15px 0;
      border: none;
      border-radius: 0;
  }
  .thumbnail img {
      width: 100%;
      height: 100%;
      margin-bottom: 10px;
  }
  .carousel-control.right, .carousel-control.left {
      background-image: none;
      color: #f4511e;
  }
  .carousel-indicators li {
      border-color: #f4511e;
  }
  .carousel-indicators li.active {
      background-color: #f4511e;
  }
  .item h4 {
      font-size: 19px;
      line-height: 1.375em;
      font-weight: 400;
      font-style: italic;
      margin: 70px 0;
  }
  .item span {
      font-style: normal;
  }
  .panel {
      border: 1px solid #f4511e; 
      border-radius:0 !important;
      transition: box-shadow 0.5s;
  }
  .panel:hover {
      box-shadow: 5px 0px 40px rgba(0,0,0, .2);
  }
  .panel-footer .btn:hover {
      border: 1px solid #f4511e;
      background-color: #fff !important;
      color: #f4511e;
  }
  .panel-heading {
      color: #fff !important;
      background-color: #f4511e !important;
      padding: 25px;
      border-bottom: 1px solid transparent;
      border-top-left-radius: 0px;
      border-top-right-radius: 0px;
      border-bottom-left-radius: 0px;
      border-bottom-right-radius: 0px;
  }
  .panel-footer {
      background-color: white !important;
  }
  .panel-footer h3 {
      font-size: 32px;
  }
  .panel-footer h4 {
      color: #aaa;
      font-size: 14px;
  }
  .panel-footer .btn {
      margin: 15px 0;
      background-color: #f4511e;
      color: #fff;
  }
  .navbar {
      margin-bottom: 0;
      background-color: #f4511e;
      z-index: 9999;
      border: 0;
      font-size: 12px !important;
      line-height: 1.42857143 !important;
      letter-spacing: 4px;
      border-radius: 0;
      font-family: Montserrat, sans-serif;
  }
  .navbar li a, .navbar .navbar-brand {
      color: #fff !important;
  }
  .navbar-nav li a:hover, .navbar-nav li.active a {
      color: #f4511e !important;
      background-color: #fff !important;
  }
  .navbar-default .navbar-toggle {
      border-color: transparent;
      color: #fff !important;
  }
  footer .glyphicon {
      font-size: 20px;
      margin-bottom: 20px;
      color: #f4511e;
  }
  .slideanim {visibility:hidden;}
  .slide {
      animation-name: slide;
      -webkit-animation-name: slide;
      animation-duration: 1s;
      -webkit-animation-duration: 1s;
      visibility: visible;
  }
  @keyframes slide {
    0% {
      opacity: 0;
      transform: translateY(70%);
    } 
    100% {
      opacity: 1;
      transform: translateY(0%);
    }
  }
  @-webkit-keyframes slide {
    0% {
      opacity: 0;
      -webkit-transform: translateY(70%);
    } 
    100% {
      opacity: 1;
      -webkit-transform: translateY(0%);
    }
  }
  @media screen and (max-width: 768px) {
    .col-sm-4 {
      text-align: center;
      margin: 25px 0;
    }
    .btn-lg {
        width: 100%;
        margin-bottom: 35px;
    }
  }
  @media screen and (max-width: 480px) {
    .logo {
        font-size: 150px;
    }
  }  
</style>
</head>
<body id="myPage" data-spy="scroll" data-target=".navbar" data-offset="60">

<nav class="navbar navbar-default navbar-fixed-top">
  <div class="container">
    <div class="navbar-header">
      <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#myNavbar">
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>                        
      </button>
      <a class="navbar-brand" href="#myPage">Alerta Zika</a>
    </div>
    <div class="collapse navbar-collapse" id="myNavbar">
      <ul class="nav navbar-nav navbar-right">
        <li><a href="#sobre">Sobre</a></li>
        <li><a href="#emNumeros">Números da Zika</a></li>
        <li><a href="#focoZika">Focos da Doença</a></li>
        <li><a href="#visaoBairro">Visão por Bairros</a></li>
        <li><a href="#OutrasInfo">Outras Informações</a></li>
      </ul>
    </div>
  </div>
</nav>

<!-- Container (About Section) -->
<div id="sobre" class="container-fluid text-center">

    <h3>Alerta Zika</h3>
    <p> Site com informações sobre a Zika no Município do Rio de Janeiro.</p>       
    
</div>

<div id="emNumeros" class="container-fluid text-center">     
   <div class="row">    
      <div class="col-sm-6">
            <p><b>Número de casos nos últimos 12 meses</b></p>
            <div id="GrafUltimos12Meses"></div>
     </div>
     <div class="col-sm-6">
            <p><b>Os 5 bairros mais afetados</b></p>
            <div id="GrafTop10Bairros"></div>
     </div>     
</div>

<div id="focoZika" class="container-fluid text-center">  

    <div class="row selecaoData">
        <div class="col-sm-12">
            <div id="Calendario">
            <label>Para visualizar os focos do mosquito selecione o Ano:</label>
            <select name="SelAno"class="selectControl" >
            <option></option>
            <option>2015</option>
            <option>2016</option>
            </select>
            <label>Mês:</label>
            <select name="SelMes" class="selectControl">
            <option></option>
            <option>Janeiro</option>
            <option>Fevereio</option>
            <option>Março</option>
            <option>Abril</option>
            <option>Maio</option>
            <option>Junho</option>
            <option>Julho</option>
            <option>Agosto</option>
            <option>Setembro</option>
            <option>Outubro</option>
            <option>Novembro</option>
            <option>Dezembro</option>
            </select>
            </div>
        </div>
    </div>
    <div class="row">
        <div class="col-sm-12">
            <div id="MapadoRio"><img src="imagens/ZikaJaneiro.jpg" class="img-responsive img-rounded" width="100%"  /></div>
        </div>    
    </div>
</div>   
</div>
<div id="visaoBairro" class="container-fluid text-center">
    <div class="row selecaoData">
        <div class="col-sm-12">
            <div id="Calendario">
            <label>Para visualizar a evolução da Zika por semana selecione o Bairro:</label>
            <select name="SelBairro" id="SelBairro" class="selectControl" >
            <option></option> 
            </select>            
            </div>
        </div>
    </div>
    <div>
    <div class="row">
        <div class="col-sm-12">
            <div id="GrafVisaoBairro"><svg width="960" height="500"></svg></div>
        </div>    
    </div>
</div>   
</div>
<div id="OutrasInfo" class="container-fluid text-center">
    Outras informações 
</div>

<footer class="container-fluid text-center">
  <a href="#myPage" title="To Top">
    <span class="glyphicon glyphicon-chevron-up"></span>
  </a>
  <p>Bootstrap Theme Made By <a href="http://www.w3schools.com" title="Visit w3schools">www.w3schools.com</a></p>
</footer>

</body>

<script>
$(document).ready(function(){
  // Add smooth scrolling to all links in navbar + footer link
  $(".navbar a, footer a[href='#myPage']").on('click', function(event) {
    // Make sure this.hash has a value before overriding default behavior
    if (this.hash !== "") {
      // Prevent default anchor click behavior
      event.preventDefault();

      // Store hash
      var hash = this.hash;

      // Using jQuery's animate() method to add smooth page scroll
      // The optional number (900) specifies the number of milliseconds it takes to scroll to the specified area
      $('html, body').animate({
        scrollTop: $(hash).offset().top
      }, 900, function(){
   
        // Add hash (#) to URL when done scrolling (default click behavior)
        window.location.hash = hash;
      });
    } // End if
  });
  
  $(window).scroll(function() {
    $(".slideanim").each(function(){
      var pos = $(this).offset().top;

      var winTop = $(window).scrollTop();
        if (pos < winTop + 600) {
          $(this).addClass("slide");
        }
    });
  });
})
</script>

<script>

//Script Gráfico Número de Casos por mês na Cidade
var dataNumCasosMes =[
            {"Mes": "Jan-16", "NumCasos" : 6665 },
            {"Mes": "Fev-16", "NumCasos" : 8194 },
            {"Mes": "Mar-16", "NumCasos" : 6160 },
            {"Mes": "Abr-16", "NumCasos" : 5951 },
            {"Mes": "Mai-16", "NumCasos" : 3815 },
            {"Mes": "Jun-16", "NumCasos" : 1175 },
            {"Mes": "Jul-16", "NumCasos" : 378 },
            {"Mes": "Ago-16", "NumCasos" : 305 },
            {"Mes": "Set-16", "NumCasos" : 75 },
            {"Mes": "Out-16", "NumCasos" : 35 },
            {"Mes": "Nov-16", "NumCasos" : 2208 },
            {"Mes": "Dez-16", "NumCasos" : 2378 },            
        ]; 


// set the dimensions and margins of the graph
var margin = {top: 20, right: 40, bottom: 20, left: 40},
    width = 500 - margin.left - margin.right,
    height = 300 - margin.top - margin.bottom;

// set the ranges
var x = d3.scaleBand()
          .range([0, width])
          .padding(0.1);
var y = d3.scaleLinear()
          .range([height, 0]);
          
// append the svg object to the body of the pNumCasos

// append a 'group' element to 'svg'
// moves the 'group' element to the top left margin
var svg = d3.select("#GrafUltimos12Meses").append("svg")
    .attr("width", width + margin.left + margin.right)
    .attr("height", height + margin.top + margin.bottom)
  .append("g")
    .attr("transform", 
          "translate(" + margin.left + "," + margin.top + ")");

// get the data
//d3.csv("NumCasos.csv", function(error, data) {
//  if (error) throw error;

  // format the data
  dataNumCasosMes.forEach(function(d) {
    d.NumCasos = +d.NumCasos;
  });

  // Scale the range of the data in the domains
  x.domain(dataNumCasosMes.map(function(d) { return d.Mes ; }));
  y.domain([0, d3.max(dataNumCasosMes, function(d) { return d.NumCasos; })]);

  // append the rectangles for the bar chart
  svg.selectAll(".bar")
      .style("font-size", "12px" )
      .data(dataNumCasosMes)
    .enter().append("rect")
      .attr("class", "bar")
      .attr("x", function(d) { return x(d.Mes); })
      .attr("width", x.bandwidth())
      .attr("y", function(d) { return y(d.NumCasos); })
      .attr("height", function(d) { return height - y(d.NumCasos); });
      

  // add the x Axis
  svg.append("g")
      .attr("transform", "translate(0," + height + ")")
      .call(d3.axisBottom(x));

  // add the y Axis
  svg.append("g")
      .call(d3.axisLeft(y));

//});
</script>

<script>

//Script Gráfico Número de Casos por Bairro
var dataTopBairros =[
            { "Bairro": "CAMPO GRANDE", "NumCasos" : 2138 },
            { "Bairro": "SANTA CRUZ", "NumCasos" : 1800 },
            { "Bairro": "GUARATIBA", "NumCasos" : 1524},
            { "Bairro": "SEPETIBA", "NumCasos" : 1099},
            { "Bairro": "REALENGO", "NumCasos" : 1094},          
        ]; 


// set the dimensions and margins of the graph
var margin = {top: 20, right: 40, bottom: 20, left: 40},
    width = 500 - margin.left - margin.right,
    height = 300 - margin.top - margin.bottom;

// set the ranges
var x = d3.scaleBand()
          .range([0, width])
          .padding(0.1);
var y = d3.scaleLinear()
          .range([height, 0]);
          
// append the svg object to the body of the pNumCasos

// append a 'group' element to 'svg'
// moves the 'group' element to the top left margin
var svg = d3.select("#GrafTop10Bairros").append("svg")
    .attr("width", width + margin.left + margin.right)
    .attr("height", height + margin.top + margin.bottom)
  .append("g")
    .attr("transform", 
          "translate(" + margin.left + "," + margin.top + ")");

// get the data
//d3.csv("NumCasos.csv", function(error, data) {
//  if (error) throw error;

  // format the data
  dataTopBairros.forEach(function(d) {
    d.NumCasos = +d.NumCasos;
  });

  // Scale the range of the data in the domains
  x.domain(dataTopBairros.map(function(d) { return d.Bairro; }));
  y.domain([0, d3.max(dataTopBairros, function(d) { return d.NumCasos; })]);

  // append the rectangles for the bar chart
  svg.selectAll(".bar")
      .data(dataTopBairros)
    .enter().append("rect")
      .attr("class", "bar")
      .attr("x", function(d) { return x(d.Bairro); })
      .attr("width", x.bandwidth())
      .attr("y", function(d) { return y(d.NumCasos); })
      .attr("height", function(d) { return height - y(d.NumCasos); });

  // add the x Axis
  svg.append("g")
      .attr("transform", "translate(0," + height + ")")
      .call(d3.axisBottom(x));

  // add the y Axis
  svg.append("g")
      .call(d3.axisLeft(y));

//});
</script>

<script>

//Gráfico de linha com casos de Zika por Bairro

var dataBairros = [{"Bairro":"ABOLICAO"},{"Bairro":"ACARI"},{"Bairro":"AGUA SANTA"},{"Bairro":"ANCHIETA"},{"Bairro":"ANDARAI"},{"Bairro":"ANIL"},{"Bairro":"BANCARIOS"},{"Bairro":"BANGU"},{"Bairro":"BARRA DA TIJUCA"},{"Bairro":"BARRA DE GUARATIBA"},{"Bairro":"BARROS FILHO"},{"Bairro":"BENFICA"},{"Bairro":"BENTO RIBEIRO"},{"Bairro":"BONSUCESSO"},{"Bairro":"BOTAFOGO"},{"Bairro":"BRAS DE PINA"},{"Bairro":"BRAS DE PINA"},{"Bairro":"CACHAMBI"},{"Bairro":"CACUIA"},{"Bairro":"CAJU"},{"Bairro":"CAMORIM"},{"Bairro":"CAMPINHO"},{"Bairro":"CAMPO DOS AFONSOS"},{"Bairro":"CAMPO GRANDE"},{"Bairro":"CASCADURA"},{"Bairro":"CATETE"},{"Bairro":"CATUMBI"},{"Bairro":"CAVALCANTI"},{"Bairro":"CENTRO"},{"Bairro":"CIDADE DE DEUS"},{"Bairro":"CIDADE NOVA"},{"Bairro":"CIDADE UNIVERSITARIA"},{"Bairro":"COCOTA"},{"Bairro":"COELHO NETO"},{"Bairro":"COLEGIO"},{"Bairro":"COMPLEXO DO ALEMAO"},{"Bairro":"COPACABANA"},{"Bairro":"CORDOVIL"},{"Bairro":"COSME VELHO"},{"Bairro":"COSMOS"},{"Bairro":"COSTA BARROS"},{"Bairro":"CURICICA"},{"Bairro":"DEL CASTILHO"},{"Bairro":"DEODORO"},{"Bairro":"ENCANTADO"},{"Bairro":"ENGENHEIRO LEAL"},{"Bairro":"ENGENHO DE DENTRO"},{"Bairro":"ENGENHO NOVO"},{"Bairro":"ESTACIO"},{"Bairro":"FLAMENGO"},{"Bairro":"GALEAO"},{"Bairro":"GAMBOA"},{"Bairro":"GARDENIA AZUL"},{"Bairro":"GAVEA"},{"Bairro":"GLORIA"},{"Bairro":"GRAJAU"},{"Bairro":"GRUMARI"},{"Bairro":"GUADALUPE"},{"Bairro":"GUARATIBA"},{"Bairro":"HIGIENOPOLIS"},{"Bairro":"HONORIO GURGEL"},{"Bairro":"HUMAITA"},{"Bairro":"INHAUMA"},{"Bairro":"IPANEMA"},{"Bairro":"IRAJA"},{"Bairro":"ITANHANGA"},{"Bairro":"JACARE"},{"Bairro":"JACAREPAGUA"},{"Bairro":"JACAREZINHO"},{"Bairro":"JARDIM AMERICA"},{"Bairro":"JARDIM BOTANICO"},{"Bairro":"JARDIM CARIOCA"},{"Bairro":"JARDIM GUANABARA"},{"Bairro":"JARDIM SULACAP"},{"Bairro":"JOA"},{"Bairro":"LAGOA"},{"Bairro":"LARANJEIRAS"},{"Bairro":"LEBLON"},{"Bairro":"LEME"},{"Bairro":"LINS DE VASCONCELOS"},{"Bairro":"MADUREIRA"},{"Bairro":"MAGALHAES BASTOS"},{"Bairro":"MANGUEIRA"},{"Bairro":"MANGUINHOS"},{"Bairro":"MARACANA"},{"Bairro":"MARECHAL HERMES"},{"Bairro":"MARIA DA GRACA"},{"Bairro":"MEIER"},{"Bairro":"MONERO"},{"Bairro":"OLARIA"},{"Bairro":"OSWALDO CRUZ"},{"Bairro":"PACIENCIA"},{"Bairro":"PADRE MIGUEL"},{"Bairro":"PAQUETA"},{"Bairro":"PARADA DE LUCAS"},{"Bairro":"PARQUE ANCHIETA"},{"Bairro":"PARQUE COLUMBIA"},{"Bairro":"PAVUNA"},{"Bairro":"PECHINCHA"},{"Bairro":"PEDRA DE GUARATIBA"},{"Bairro":"PENHA"},{"Bairro":"PENHA CIRCULAR"},{"Bairro":"PIEDADE"},{"Bairro":"PILARES"},{"Bairro":"PITANGUEIRAS"},{"Bairro":"PORTUGUESA"},{"Bairro":"PRACA DA BANDEIRA"},{"Bairro":"PRACA SECA"},{"Bairro":"QUINTINO BOCAIUVA"},{"Bairro":"RAMOS"},{"Bairro":"REALENGO"},{"Bairro":"RECREIO DOS BANDEIRANTES"},{"Bairro":"RIACHUELO"},{"Bairro":"RIBEIRA"},{"Bairro":"RICARDO DE ALBUQUERQUE"},{"Bairro":"RIO COMPRIDO"},{"Bairro":"ROCHA"},{"Bairro":"ROCHA MIRANDA"},{"Bairro":"ROCINHA"},{"Bairro":"SAMPAIO"},{"Bairro":"SANTA CRUZ"},{"Bairro":"SANTA TERESA"},{"Bairro":"SANTISSIMO"},{"Bairro":"SANTO CRISTO"},{"Bairro":"SAO CONRADO"},{"Bairro":"SAO CRISTOVAO"},{"Bairro":"SAO FRANCISCO XAVIER"},{"Bairro":"SAUDE"},{"Bairro":"SENADOR CAMARA"},{"Bairro":"SENADOR VASCONCELOS"},{"Bairro":"SEPETIBA"},{"Bairro":"TANQUE"},{"Bairro":"TAQUARA"},{"Bairro":"TAUA"},{"Bairro":"TIJUCA"},{"Bairro":"TODOS OS SANTOS"},{"Bairro":"TOMAS COELHO"},{"Bairro":"TURIACU"},{"Bairro":"URCA"},{"Bairro":"VARGEM GRANDE"},{"Bairro":"VARGEM PEQUENA"},{"Bairro":"VAZ LOBO"},{"Bairro":"VICENTE DE CARVALHO"},{"Bairro":"VIDIGAL"},{"Bairro":"VIGARIO GERAL"},{"Bairro":"VILA DE PENHA"},{"Bairro":"VILA ISABEL"},{"Bairro":"VILA KOSMOS"},{"Bairro":"VILA MILITAR"},{"Bairro":"VILA VALQUEIRE"},{"Bairro":"VISTA ALEGRE"},{"Bairro":"ZUMBI"}];

var dataCasosPrevistoReal = [{"Data":20151005,"Bairro":"CAMPO GRANDE","Previsto":28.0,"Real":10.0},{"Data":20151012,"Bairro":"CAMPO GRANDE","Previsto":28.0,"Real":10.0},{"Data":20151019,"Bairro":"CAMPO GRANDE","Previsto":27.0,"Real":10.0},{"Data":20151026,"Bairro":"CAMPO GRANDE","Previsto":13.0,"Real":10.0},{"Data":20151102,"Bairro":"CAMPO GRANDE","Previsto":15.0,"Real":12.0},{"Data": 20151109,"Bairro":"CAMPO GRANDE","Previsto":12.0,"Real":1.0}];

var Colunas = ['Data','Real', 'Previsto']

var selBairro = d3.select("#SelBairro")
  .selectAll('option')
	.data(dataBairros).enter()
	.append('option')
		.text(function (d) { return d.Bairro; });

/*var svg = d3.select("svg"),
    margin = {top: 20, right: 80, bottom: 30, left: 50},
    width = svg.attr("width") - margin.left - margin.right,
    height = svg.attr("height") - margin.top - margin.bottom,
    g = svg.append("g").attr("transform", "translate(" + margin.left + "," + margin.top + ")");
*/


var margin = {top: 20, right: 80, bottom: 30, left: 50},
    width = 960 - margin.left - margin.right,
    height = 500 - margin.top - margin.bottom;


// append the svg object to the body of the pNumCasos

// append a 'group' element to 'svg'
// moves the 'group' element to the top left margin
var svg = d3.select("#GrafVisaoBairro").append("svg")
    .attr("width", width - margin.left - margin.right)
    .attr("height", height - margin.top - margin.bottom)
  /*.append("g")
    .attr("transform", 
          "translate(" + margin.left + "," + margin.top + ")");*/
 g = svg.append("g").attr("transform", "translate(" + margin.left + "," + margin.top + ")");


var parseTime = d3.timeParse("%Y%m%d");

var x = d3.scaleTime().range([0, width]),
    y = d3.scaleLinear().range([height, 0]),
    z = d3.scaleOrdinal(d3.schemeCategory10);

var line = d3.line()
    .curve(d3.curveBasis)
    .x(function(d) { return x(d.date); })
    .y(function(d) { return y(d.temperature); });

//d3.tsv("data.tsv", type, function(error, data) {
  //if (error) throw error;

  //var cities = data.columns.slice(1).map(function(id) {
    var cities = Colunas.slice(1).map(function(id) {
    return {
      id: id,
      values: dataCasosPrevistoReal.map(function(d) {
        return {date: d.Data, temperature: d[id]};
      })
    };
  });

  x.domain(d3.extent(dataCasosPrevistoReal, function(d) { return d.data; }));

  y.domain([
    d3.min(cities, function(c) { return d3.min(c.values, function(d) { return d.temperature; }); }),
    d3.max(cities, function(c) { return d3.max(c.values, function(d) { return d.temperature; }); })
  ]);

  z.domain(cities.map(function(c) { return c.id; }));

  g.append("g")
      .attr("class", "axis axis--x")
      .attr("transform", "translate(0," + height + ")")
      .call(d3.axisBottom(x));

  g.append("g")
      .attr("class", "axis axis--y")
      .call(d3.axisLeft(y))
    .append("text")
      .attr("transform", "rotate(-90)")
      .attr("y", 6)
      .attr("dy", "0.71em")
      .attr("fill", "#000")
      .text("Temperature, ºF");

  var city = g.selectAll(".city")
    .data(cities)
    .enter().append("g")
      .attr("class", "city");

  city.append("path")
      //.filter(function(d) { return d.close < 40000 })
      .attr("class", "line")
      .attr("d", function(d) { return line(d.values); })
      .style("stroke", function(d) { return z(d.id); });

  city.append("text")
      .datum(function(d) { return {id: d.id, value: d.values[d.values.length - 1]}; })
      .attr("transform", function(d) { return "translate(" + x(d.value.date) + "," + y(d.value.temperature) + ")"; })
      .attr("x", 3)
      .attr("dy", "0.35em")
      .style("font", "10px sans-serif")
      .text(function(d) { return d.id; });


//});

function type(d, _, columns) {
  d.date = parseTime(d.date);
  for (var i = 1, n = columns.length, c; i < n; ++i) d[c = columns[i]] = +d[c];
  return d;
}

</script>

</html>
