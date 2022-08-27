 <h2> pegue um atalho 👇🏻</h2>   
 
- [S](#s---single-responsibility-principle)
- [O](#o---open-closed-principle)
- [L](#l---liskov-substitution-principle)   
- [I](#i---interface-segregation-principle)      
- [D](#d---dependency-inversion-principle)   


<h2 align="center">Princípios do SOLID</h2>   
   
   ## S - Single-responsibility principle      
   uma classe/componente/função deve ter apenas uma responsabilidade.
   > Com entidades independentes e isoladas você consegue reaproveitar o código mais facilmente, refatorar melhor, testes automatizados mais facilmente alem de gerar menos BUG's e quando existir será mais facil isolar e concertar o problema.
   > O principal é que para implementar coisas novas basta focar num escopo de cada vez, vendo que seu código esta separado.   
   
   ## O - Open-closed principle   
   classes/entidades/funções devem estar abertas para extensão mas fechadas para modificação.
   > A abstração base não precisa saber as características especificas de cada objeto, condicionais para ver se fará uma ação com o objeto ou não. No limite a classe deve receber um objeto e pedir para ele mesmo se validar e essa abstração decide qual será o comportamento desse objeto a partir do retorno das validações.
   > Ex: entidade que processa pagamentos:
  
  ```
  ProcessaPagamentos(Objeto){      
    if(Objeto.tipo == boleto){     
        objeto.codigoDeBarras   
        }else{   
           objeto.numero   
           objeto.vencimento   
           objeto.nome
           antifraude(objeto)
        cobrar(objeto)
        }
   }
```   
> agora para cada tipo de pagamento diferente que surgisse teria que alem de implementar, modificar as rotinas e instruções no Processador de pagamentos, gerando uma "bola de neve".
o ideal seria:
```
ProcessaPagamentos (objeto){
  objeto.valido?
  objeto.cobrar!
}
```
>se objetos diferentes precisarem ser implementados futuramente  e respeitarem essa interface, não precisará mais mexer na classe base de processamento.

## L - Liskov Substitution principle
se temos uma classe e dela criarmos uma subclasse utilizando herança, o objeto ou instância resultante dessa subclasse, tem que conseguir substituir o objeto da classe principal, sem quebrar o programa.
>Essa é meio contraditória, porém te força a entender que respeitar o Princípio de Liskov, força seu programa a ter abstrações no nível certo e ser mais consistente.
>Ex:
>Note que se criar uma Super classe:   
```
Ave()
  bicar!
  voar!
```
>e se criar subclasses:
```
`PicaPau()       Pinguin()
  bicar!           bicar!
  voar!            XXX  
```
> se jogar para dentro da função um objeto da classe Pica-Pau herdando Ave, o programa roda como esperado. Porem um objeto da classe Pinguin herdando os métodos da classe Ave, vai gerar uma exceção...
>generalizando para o principio, se a cada herança que fizer, você está lutando com o que herda e precisa desfazer o que herdou, é bem possível que já começou com a abstração errada e quanto mais você insistir nessa estrutura errada, mais efeito destrutivo terá na evolução do seu software.

>Esse principio vai te forçar a pensar o que realmente a classe pai deveria fornecer de comum para todas as outras subclasses, principalmente caso queira respeitar o [Open-Closed principle](#O-Open-closed-principle).

## I - interface Segregation Principle
Classes não devem ser forçadas a dependerem de métodos que elas não usam, forçadas a implementar uma interface com métodos que ela não vai precisar e não faz sentido para ela.
*Muitas interfaces específicas são melhores do que uma interface única.

## D - Dependency Inversion principle
um módulo não deve depender de detalhes de implementação de outro módulo diretamente.
*dependa de uma abstração e não de uma implementação.
A partir disso, toda implementação que for injetada nesse módulo e respeitar essa abstração(uma interface por exemplo) consegue ser utilizado.

## -----------------é isso!--------------------   

## Referência pelo excelente video:
[SOLID fica FÁCIL com Essas Ilustrações](https://www.youtube.com/watch?v=6SfrO3D4dHM&ab_channel=FilipeDeschamps).

</br>

>if this project helped you, contribute by giving a ⭐ !! I'll be grateful 😁      

</br>   
<div align="center">   
  
   [![Linkedin Badge](https://img.shields.io/badge/-weslei%20tiago-292929?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/weslei-tiago-53b47a208/)](https://www.linkedin.com/in/weslei-tiago-53b47a208/)   
  
   </div>
