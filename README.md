# Funcoes-JS
## Formas de declarar funções em JavaScript

## Declaration

A função é criada quando usamos a palavra-chave function para definir uma função. 

EXEMPLO:
	
 	function mensagem() {
		console.log("Hello Word")
	
	};
	
	mensagem()
	// Hello Word

Ao declaramos a função mensagem, toda vez que ele for chamada será exibido "Hello Word". Também existe funções que tem parâmetros e os que não tem, no exemplo anterior não tem parâmetro, já o do exemplo abaixo temos parâmetro.
EXEMPLO:

	function quadrado (x) {
		return x * x;
	
	};
	
	console.log(quadrado(4));
	// 16

##Vantagem

###Descrição clara e estruturada do código.
A utilização de declarações claras (let, const, function) facilita a compreensão e a manutenção do código.
###Controle de Hoisting .
As declarações de função são "hoisted" (elevadas ao topo), possibilitando sua utilização antes da linha em que foram escritas, o que pode simplificar a estruturação do código.
	

Desvantagem

###Hoisting confuso com var.
Var também é "hoisted", porém apenas a sua declaração, não a sua configuração inicial.  Isso pode resultar em falhas detectáveis:
	EXEMPLO: 
		console.log(x); // undefined
		var x = 18;


###Atribuição com var
A var possibilita a redefinição e a atribuição, o que pode gerar complicações em códigos extensos ou em loops.





##Expression:
	
A expressão de função tem uma sintaxe muito parecido com a declaração de função, a diferença é o nome da função que pode ser omitida para criar funções anônimas.
EXEMPLO:
	
 	var x = function (y) {
  		   return y * y;
		
		};

Caso queira se referir à função em execução dentro da função, será necessário criar uma expressão de função nomeada.  Apenas o corpo (escopo) da função receberá este nome.
EXEMPLO:
		var x = {
  		  factorial: function factorial(n) {
    		     if (n <= 1) return 1;
    		     return n * factorial(n - 1);
 			 
		  };
		};



##Vantagem

###Flexibilidade
Você tem a capacidade de desenvolver funções de maneira dinâmica, dentro de variáveis.
EXEMPLO:

	const x = function(a, b){
 	return a + b; 
  	};
	
###Abrangência mais previsível
Em uma expressão de função, o nome (se existir) é restrito ao âmbito da própria função, para evitar a poluição do escopo global.


##Desvantagens

###Não existem hoistings.
 Ao contrário das declarações de função, as expressões de função não são "elevadas" no código.  Não pode chamá-las antes que tenham sido definidas.
 
###Complicações na depuração de funções anônimas
Sem um nome, o rastreamento de erros torna-se mais complexo de compreender


##Arrow

A Arrow Function é uma forma mais curta de escrever funções em JavaScript, porque um código pode ser resumido em uma linha.
sintaxe básica:
	
 	const soma = (a, b) => a + b;
	
A função acima é a mesma que:
	
 	function soma(a, b) {
           return a + b;
	};

##Vantagens

###Código mais curto
Ideal para funções pequenas e expressões simples.
Boa para funções rápidas (callbacks, map, filter, reduce)
javascript:

EXEMPLO:
	
 	const numeros = [4, 5, 8];
	const dobrados = numeros.map(n => n * 2);
	console.log(dobrados);
 	// [8, 10, 16]


##Desvantagem

##Não possui argumentos.
Na maioria das funções, arguments é um objeto que armazena todos os argumentos fornecidos.  Em Funções de Arrows
Não possui sua própria this. Às vezes, não é recomendado usar Arrow para métodos de objetos que dependem de this.
