# projeto-relogio-digital
<!doctype html>
<html lang=“pt-br”>
	<head>
		<title>Curso de Javascript</title>
		<meta charset=“UTF-8”>
		<script>
		
			function relogio(){
				var data=new Date();
				var hor=data.getHours();
				var min=data.getMinutes();
				var seg=data.getSeconds();
				
				if(hor < 10){
					hor="0"+hor;
				}
				if(min < 10){
					min="0"+min;
				}
				if(seg < 10){
					seg="0"+seg;
				}
				
				var horas=hor + ":" + min + ":" + seg;
				
				document.getElementById("rel").value=horas;
			}

			var timer=setInterval(relogio,1000);

		</script>
	</head>
	<body>
		<input type="text" id="rel">
	</body>
</html>


No script o primeiro passo é criar a função que irá “preparar” o relógio, demos o nome para esta função de “relogio()”, vamos entender como ele funciona.

function relogio(){

Primeiramente na função “relogio()” criamos o objeto data do tipo Date e obtivemos as horas, minutos e segundos devidamente armazenados nas variáveis hor, min, seg.

var data=new Date();
var hor=data.getHours();
var min=data.getMinutes();
var seg=data.getSeconds()

Estas funções retornam os valores menores que 10 com um dígito só, no caso de relógios, estes valores são mostrados com dois dígitos, com o zero na frente, 01, 02, …, 09, então, precisamos “ajustar” estes valores, vamos usar IF para testar se o valor é menor que dez, se for, vamos adicionar o “0” na frente do valor.                                       

if(hor < 10){
                hor=”0″+hor;
}
if(min < 10){
                min=”0″+min;
}
if(seg < 10){
                seg=”0″+seg;
}

Em seguida vamos juntar todas as informações de horas, minutos e segundos em uma só variável, no caso, a variável “horas”.

var horas=hor + “:” + min + “:” + seg;

O último passo da função é adicionar a hora devidamente preparada que está na variável “horas” no <input>.

document.getElementById(“rel”).value=horas;

Com a função pronta, basta criar o timer “setInterval” que irá chamar a função “relogio()” de um em um segundo.

var timer=setInterval(relogio,1000);
