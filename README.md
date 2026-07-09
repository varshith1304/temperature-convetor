## temperature-convetor 

<!DOCTYPE html>
<html>
<head>
<title>Temperature Converter</title>

<style>

body{
font-family: Arial;
background: linear-gradient(135deg,#f50303,rgb(214, 246, 4));
display:flex;
justify-content:center;
align-items:center;
height:100vh;
}

.container{
background:white;
padding:30px;
border-radius:15px;
width:350px;
text-align:center;
box-shadow:0 10px 25px rgba(0,0,0,0.2);
}

input,select,button{
padding:10px;
margin:10px;
width:80%;
border-radius:8px;
border:1px solid #ccc;
}

button{
background:#192f76;
color:white;
border:none;
cursor:pointer;
}

button:hover{
background:#37aa11;
}

.result{
font-size:20px;
font-weight:bold;
margin-top:15px;
}

</style>
</head>

<body>

<div class="container">

<h2>Temperature Converter</h2>

<input type="number" id="temp" placeholder="Enter Temperature">

<select id="unit">
<option value="c">Celsius</option>
<option value="f">Fahrenheit</option>
<option value="k">Kelvin</option>
</select>

<button onclick="convertTemp()">Convert</button>

<div class="result" id="result"></div>

</div>

<script>

function convertTemp(){

let temp=document.getElementById("temp").value;
let unit=document.getElementById("unit").value;
let result="";

if(unit=="c"){
let f=(temp*9/5)+32;
let k=parseFloat(temp)+273.15;
result=`Fahrenheit: ${f.toFixed(2)} °F <br> Kelvin: ${k.toFixed(2)} K`;
}

else if(unit=="f"){
let c=(temp-32)*5/9;
let k=c+273.15;
result=`Celsius: ${c.toFixed(2)} °C <br> Kelvin: ${k.toFixed(2)} K`;
}

else{
let c=temp-273.15;
let f=(c*9/5)+32;
result=`Celsius: ${c.toFixed(2)} °C <br> Fahrenheit: ${f.toFixed(2)} °F`;
}

document.getElementById("result").innerHTML=result;

}

</script>

</body>
</html>
