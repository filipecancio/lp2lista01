# Lista de Execícios 01

### Questão 01 [Resolução]()
 Implemente uma classe, de nome `Data`, que apresente três atributos inteiros em cada instância, para armazenamento,
respectivamente, de mês, dia e ano correspondentes a uma determinada data. Em relação à implementação da classe, deve
haver métodos `get` e `set` para cada atributo e um construtor para fins de inicialização desses mesmos atributos (assuma que os valores fornecidos sejam corretos). Acrescente ainda um método, de nome `mostrarData()`, para retornar uma string
representativa, no formato _dd/mm/aaaa_, da data armazenada (dia, mês e ano separados por barras). Ao final, inclua ainda um método estático `main(String[] args) `ou ou uma classe utilitária à parte munida desse método para demonstração das
capacidades da classe implementada.

### Questão 02
Ainda em relação à implementação da questão anterior, implemente um método, de nome `getDiasTerminoAno()`, que
retorne a quantidade de dias restantes para o término do ano indicado através dos valores correntes dos atributos da instância através da qual tal método será invocado.

### Questão 03
Considere os métodos declarados na implementação abaixo (houve ocultação intencional do corpo dos métodos). Indique se está havendo sobrecarga ou sobrescrita dos mesmos. Em caso de sobrecarga ou sobrescrita, indique sob qual outro método ela está ocorrendo.

```java
public class A {
 ...
 public A() { ... }
 public A( int x ) { ... }
 public void m1() { ... }
 public void m1(int h) { ... }
}
public class B extends A {
 ...
 public B() { ... }
 public void m1() { ... }
 public void m1( double x, double y) { ... }
 public void m2() { ... }
}
```

### Questão 04
Implemente uma classe, de nome `ContaCorrente` e que represente uma conta corrente, contendo, para tal um atributo, de
nome `saldo`, para armazenamento do saldo corrente. Em relação aos métodos de encapsulamento do atributo, considere apenas o metódo get. Além disso, implemente dois outros métodos, conforme se segue abaixo:
- `registrarDeposito(double valor)`: sua execução deverá resultar no acréscimo, ao saldo corrente da conta, do valor
de depósito (indicado ao método na forma de parâmetro), após o que é esperado retorno do valor booleano `true`; em caso
do valor de depósito for negativo ou nulo, a operação de atualização de saldo deverá ser abortada, sendo seguida do retorno do valor booleano `false`;
- `registrarSaque(double valor)`: sua execução deverá resultar no débito, em relação ao saldo corrente da conta, do
valor de depósito (indicado ao método na forma de parâmetro) acrescido de um segundo débito, a título de tarifa de operação e correspondente à 0,5% desse valor, após o que é esperado retorno do valor booleano `true`; em caso do valor de depósito for negativo ou nulo ou ainda esse valor acrescido de tarifa de operação for superior ao saldo corrente da conta, a operação de atualização de saldo deverá ser abortada, sendo seguida do retorno do valor booleano `false`.
> Observação: ao final da implementação, inclua ainda um método estático `main(String[] args)` ou ou uma classe utilitária
à parte munida desse método para demonstração das capacidades da classe implementada.

### Questão 05
 Implemente uma subclasse da classe implementada na questão anterior, de nome ContaCorrenteEspecial, para a qual tarifa
de operação de saque corresponderá à 0,1% do valor de saque.

### Questão 06
Implemente uma classe, de nome `Voo`, em que cada objeto representa um voo que ocorre em determinada data e em
determinado horário. Cada voo possui no máximo 70 passageiros e a classe implementada permitirá controlar a ocupação dos assentos, devendo, para tal, dispor de atributo interno (um array de 70 valores booleanos). O acesso e a atualização do referido atributo se dará a partir dos métodos abaixo descritos:

| Método | Descrição|
|--|--|
| `getProximoAssentoLivre()` | Retorno de número, entre 1 e 70, correspondente ao próximo assento livre do voo |
| `isAssentoLivre(int n)` | Retorno de valor booleano para indicar se o número de assento indicado na forma de parâmetro se encontra ou não disponível para ocupação e/ou reserva |
| `ocuparAssento(int n)` | Indicação de que o número de assento referenciado pelo parâmetro n passará a estar ocupado e/ou reservado, seguido do retorno de valor booleano verdadeiro; no entanto, se o parâmetro não representar um assento válido (qualquer número inferior a 1 ou superior a 70) ou este assento já estiver ocupado, o método apenas retornará o valor booleano falso, sem que haja qualquer modificação de estado do objeto |
| `getTotalAssentosLivres() `| Retorno da quantidade de assentos livres |
| `getTaxaOcupacao()` | Retorno de percentual de ocupação do voo (quantidade de assentos ocupados em relação à capacidade máxima de assentos) |

Além de atributo interno para controle de assentos livres e ocupados, considere dois outros atributos cujos valores devem ser inicializados através de um construtor: número e data e horário de voo (a serem associados com os nomes de atributo `numero` e `dataHorario`, respectivamente). Ainda em relação a esse construtor, certifique-se de que o objeto seja instanciado de modo que todos os assentos estejam livres inicialmente. Em relação aos métodos de encapsulamento de tais atributos, considere apenas aqueles de acesso (`get`). Por fim, para a declaração do atributo `dataHorario`, considere o uso da classe `java.util.Date`.

### Questão 07
Dado que a classe implementada na questão anterior herda todos os métodos definidos na classe `java.lang.Object`,
sobrescreva um destes métodos: `clone()`. Tal método é projetado para retornar um novo objeto da mesma classe, de modo a haver cópia de todos os valores dos atributos da instância a partir da qual ele é invocado.

### Questão 08
8. Implemente uma classe herdeira da classe da questão anterior, de nome `VooFlexivel` e que permita, quando da instanciação
de um objeto, definir capacidade máxima de passageiros (e, por consequência, de assentos do voo). Para tal, um novo
construtor deve ser definido e que receba, além dos parâmetros já recebidos pelo construtor da superclasse, um parâmetro
adicional para indicação do número de assentos do voo. Além disso, um novo método, de nome `getTotalAssentos(`), deve
ser implementado para retornar quantidade de assentos ou capacidade máxima de passageiros do voo instanciado.
Observação: caso julgue necessário, sobrescreva métodos já definidos na superclasse.

### Questão 09
Implemente hierarquia de interfaces e classes, conforme se segue abaixo:
- Interface para representação de qualquer forma geométrica, de nome `FormaGeometrica`, no qual constem assinaturas de métodos para cálculo de perímetro e de área da forma;
- Classe abstrata para representação de quadriláteros que implementa a interface `FormaGeometrica`, de nome `Quadrilatero` e munida de construtor ao qual são indicados parâmetros correspondentes aos comprimentos de seus 4 (quatro) lados; pelo que, exige-se apenas implementação de método de cálculo de perímetro;
- Classes concretas para representação de retângulos e quadrados que herdem da classe abstrata `Quadrilatero`, distinguindo-se desta última pelo construtor: a primeira classe, de nome `Retangulo`, deve dispor de dois parâmetros (comprimentos, respectivamente, da base e da altura); a segunda classe, de nome Quadrado, deve possuir como parâmetro
apenas o comprimento de um dos lados, já que todos possuem, por definição, o mesmo valor;
- Classe para representação de círculos que implementa a interface `FormaGeometrica`, de nome Circulo e cujo construtor
possua apenas comprimento do raio como parâmetro;
- Classe utilitária na qual conste implementação de método estático main(String[] args), no qual seja indicado quantidade de formas geométricas cujas dimensões serão informadas; em seguida, para cada forma, deverá ser indicado o tipo (retângulo, quadrado ou círculo) e após isso, conforme tipo de forma, dimensões necessárias (todas as formas instanciadas deverão ser armazenadas em um array que armazena objetos que implementam a interface `FormaGeometrica`); por fim, os métodos de cálculo de perímetro e de área de cada um dos objetos instanciados deverão
ser invocados, para fins de exibição dos dados por ele retornados em conjunto com suas respectivas dimensões.
> Observação: para a indicação dos dados através de operações de entrada, sugere-se aqui o uso da classe `java.util.Scanner`.
