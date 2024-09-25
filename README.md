# Rosalind
Resolução dos exercícios propostos no site Rosalind
![image](https://github.com/user-attachments/assets/9426042b-1f3d-4762-a90a-48e9b580f10d)

# Badges 
![Badge em Desenvolvimento]( https://img.shields.io/badge/Em%20Produção%20-8A2BE2)

# Descrição do Projeto

Está é a resolução dos exercícios e  problemas propostos no site Rosalind, como método de ensino de bioinformática e programação em Python

O site pode ser acessado no link: <https://rosalind.info/problems/locations/>

# Resolução e códigos exercícios Rosalind

> **INI1 Installing Python: Enter "import this" into your Python command line and see what happens.**

```ruby
import this
```
*Resultado* ```The Zen of Python, by Tim Peters```

*Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!*

> **INI2	Variables and Some Arithmetic: Given: Two positive integers a and b, each less than 1000. Return: The integer corresponding to the square of the hypotenuse of the right triangle whose legs have lengths a and b.**

Essa questão nos pede para descobrir o quadrado da hipotenusa dados um ```a``` e um ```b```. De maneira simples podemos colocar os valores diretamente em um código, fazendo a soma do quadrado dos valores dados:

```ruby
hip = 945**2 + 827**2
print (hip)
```

Você pode também fazer:

```ruby
import math
q = 945 * 945
w = 827 * 827
e = q + w
print (e)
```
*Resultado* ```1576954```

Ou você pode perguntar ao usuário quais valores ele gostaria de descobrir a hipotenusa. Para isso utilizare-mos uma função ```input```:

```ruby
print('Vamos descobrir o quadrado da hipotenusa dados um valor a e um valor b')
a = int(input('Digite um valor para a:'))
b = int(input('Digite um valor para b:'))
hip = a**2 + b**2
print (hip)
```
Isso permite que o usuário coloque os números que deseja no terminal, fazendo com que o programa possa ser rodado sem a necessidade de realizar uma alteração no código para números diferentes dos dados inicialmente. 

> **INI3	Strings and Lists: Given: A string s of length at most 200 letters and four integers a, b, c and d. Return: The slice of this string from indices a through b and c through d (with space in between), inclusively. In other words, we should include elements s[b] and s[d] in our slice.**

```ruby
a = 22 
b = 27 
c = 97 
d = 102 
text =  'HumptyDumptysatonawallHumptyDumptyhadagreatfallAlltheKingshorsesandalltheKingsmenCouldntputHumptyDumptyinhisplaceagain'
print(text[a:b+1], text[c:d+1])
```
*Resultado*  ```Humpty Dumpty```

Em ```
a = 22 
b = 27 
c = 97 
d = 102 ```
Definimos as variáveis de acordo com os índices que nos foram fornecidos. Isso servirá para acessar uma parte específica da string específica mais tarde.

Definimos a string dada com uma função *text*:
```ruby
text =  'HumptyDumptysatonawallHumptyDumptyhadagreatfallAlltheKingshorsesandalltheKingsmenCouldntputHumptyDumptyinhisplaceagain'
```

Agora queremos extrair as strings da função *text* em relação as variáveis definidas:
```ruby
print(text[a:b+1], text[c:d+1])
```
Sabemos que quando vamos dar um *split* em uma string utilizamos por exemplo
```ruby
text[a:b+1]
```
Isso extrai uma substring de *text* que começa no ```a``` e vai até o ```b```, o '+1' é necessário para incluir o índice b.
Nesse caso quando temos ```text[a:b+1]```, estamos dizendo que queremos a string de ```text[22:27+1]``` ou ```text[22:28]```

Podemos também realizar essa mesma ação com outro tipo de código um pouco mais elaborado, onde utilizamos uma função ```def``` que irá criar um bloco de código e definir o nome de uma lista que contenha a string ```s``` que queremos analisar e as substrings ```a, b, c, d``` que servirão para realizar o split da string ```s```. Dentro desse bloco, devemos colocar os parâmetros com os quais o código irá trabalhar.

```ruby
def nova_lista(s, a, b, c, d):
    substring1 = s[a:b+1]
    substring2 = s[c:d+1]
    result = substring1 + ' ' + substring2
    return result
s = "EaJvHGBa9t9uVp6XK7yhHosQAbos94wQyijWmNq9EZl23eBgxkoDWnjn39bcbAvqROVIqF4AiRcOpCgzVJTAmphiumaeRreN0zZiaebsnMxYxzbSg5dqh08J2z0j5KGU8fA7epbengkuluensisKN3Cw8tnKL9YVhNOq63lrR8UVZRSdJZ4wq1lZrgfYWuHyUf8."
a, b, c, d = 83, 90, 134, 146
print(nova_lista(s, a, b, c, d))
```
*Resultado* ```Amphiuma bengkuluensis```

Da mesma forma como já fizemos anteriormente, podemos chamar um input para que o usuário insira seus dados:

```ruby
def nova_lista(s, a, b, c, d):
    substring1 = s[a:b+1]
    substring2 = s[c:d+1]
    result = substring1 + ' ' + substring2
    return result

s = str(input('Digite uma string:'))
a = int(input('Digite o valor de a:'))
b = int(input('Digite o valor de b:'))
c = int(input('Digite o valor de c:'))
d = int(input('Digite o valor de d:'))
print(nova_lista(s, a, b, c, d))
```
Se inserirmos as mesmas informações de string e valores do código anterior, chegamos no mesmo *Resultado* ```Amphiuma bengkuluensis```

> **INI4	Conditions and Loops: Given: Two positive integers a and b (a<b<10000). Return: The sum of all odd integers from a through b, inclusively.**

Este problema nos pede para somar todos os inteiros ímpares em um intervalo entre ```[a, b]```, onde a e b são inteiros positivos e a<b<10000. Para isso precisamos utilizar alguns conceitos de matemática e programação; se você ficar um pouco perdido em como realizar as equações, utilize um site de busca/IA para auxiliar na construção da lógica.

Começamos então definindo as equações que iremos utilizar para o nosso código poder calcular corretamente a soma dos números intieros naquele determinado intervalo.

Assim como no exercício anterior utilizamos a função ```def``` para definir um bloco de código, teremos aqui que:

```ruby
def soma_impares(a, b):
    if a % 2 == 0:
        a += 1
    if b % 2 == 0:
        b -= 1
    if a > b:
        return 0
    num_termos = (b - a) // 2 + 1
    soma = num_termos * (a + b) // 2
    return soma

print('Vamos descobrir a soma de todos os números inteiros em um intervalo onde a<b<10000!')
a = int(input("Digite o valor de a: "))
b = int(input("Digite o valor de b: "))
if a < b and b < 10000:
    resultado = soma_impares(a, b)
    print(f"A soma de todos os inteiros ímpares de {a} a {b} é: {resultado}")
elif: a == b
    print("Esses números são iguais!")
else:
    print("Valores inválidos. Certifique-se de que a < b < 10000.")
```
As funções matemáticas que estamos utilizando são operadores de módulo ```%```, eles nos retornam o resto da divisão por 2. Sabemos que se o resto for igual a 0, temos um número par; se o resto for diferente, temos um número ímpar. Quando fazemos ```a += 1``` ou ```b -= 1```: estamos somando ao valor de ```a``` +1 (tornando-o ímpar) e ao valor de ```b``` -1 (também tornando-o ímpar).

Para esse código estamos utilizando conceitos matemáticos que servem de base para o cálculo que queremos. Essa forma de fazer e buscar a soma dos números ímpares, pode ser procurada em um site de busca como o Google, que irá nos auxiliar na montagem do códigos e assim podemos definir as fuções ```num_termos``` e ```soma```.

Pedimos novamente um ```input``` do usuário para saber os valores e então passamos para uma nova função que aparece em nosso código, a utilização do ```if```, ```elif``` e ```else```.
Essas funções são utilizadas para expressar condicionais dentro do código, basicamente o código diz "se tal coisa: faça isso", "se tal outra: faça isso", "se não for nada disso: faça isso". 

Ex.if: Quando rodamos o código com uma condição que satisfaz ```if```: valor de ```a``` = 10 e ```b``` = 500 

*Resultado* ```A soma de todos os inteiros ímpares de 10 a 500 é: 62475```

Ex.elif: Quando rodamos o código com uma condição que satisfaz ```elif```: valor de ```a``` = 10 e ```b``` = 10 

*Resultado* ```Esses números são iguais!```

Ex.else: Quando rodamos o código com uma condição que satisfaz ```else```: valor de ```a``` = 500 e ```b``` = 10

*Resultado* ```Valores inválidos. Certifique-se de que a < b < 10000```

Mas você pode estar pensando: "Eu realmente preciso dessa matemática toda para fazer meu código funcionar?" e a resposta é não! O Python conta com funções integradas que permitem o nosso código ficar mais conciso. Uma outra forma de fazer o mesmo que acabamos de fazer é:

```ruby
print('Vamos descobrir a soma de todos os números inteiros em um intervalo onde a<b<10000!')
a = int(input("Digite o valor de a: "))
b = int(input("Digite o valor de b: "))

if a < b and b < 10000:
    print(sum(range(a|1, b+1, 2)))
elif a == b:
    print("Esses números são iguais!")
else:
    print("Valores inválidos. Certifique-se de que a < b < 10000.")
```

Aqui estamos utilizando uma função ```a|1``` que ira utilizar um operador 'bitwise' para ajustar o valor de ```a``` a ser o próximo número ímpar; a função ```range``` gera uma sequência de números ímpares com o valor de ```a``` (já ajustado), até ```b``` (incluindo o b: +1), com um 'passo' de 2; a função ```sum``` então soma essa determinada sequência de números e assim temos: ```sum(range(a|1, b+1, 2))``` como nossa equação matemática. 

Ao rodarmos esse código obtemos os mesmos resultados que o código anterior, mesmo eles possuindo estruturas diferentes. 

Nós utilizamos as funções de ```if```, ```elif``` e ```else``` para determinar condições ao código, isso auxilia no tratamento de possíveis erros que o usuário possa realizar; como introduzir um número inválido para a condição específica que você colocou, que nesse caso é ```Somar todos os inteiros ímpares em um intervalo entre [a, b], onde a e b são inteiros positivos e a<b<10000```.


> **INI4.1	Loops:**

Apesar de não termos utilizado uma função que realize um *loop* no código anterior, a explicação do exercício no site Rosalind nos demonstrava como realizar uma ação que se repete várias vezes até satisfazer uma condição que o programador defina. 

Para realizar um *loop* utilizamos uma função ```while```, como demonstramos a seguir:

```ruby
greetings = 1

while greetings <= 3:
    user_input = input("Diga um cumprimento (ou 'sair' para encerrar): ")
    if user_input.lower() == 'sair':
        break
    print('Hello! ')
    greetings += 1
```

Digamos que eu esteja respondendo no console de código várias vezes "Oi!", "Olá", "Heyy", etc; que irá me retornar toda vez que eu cumprimento a resposta *'Hello! '*. 

Com a função ```while``` eu poderia determinar que a resposta fosse emitida infinitas vezes desde que o usuário continuasse cumprimentando infinitas vezes. Mas isso muitas vezes não é ideal, pois cria-se um *loop* infinito e um *bug* no nosso código. 

Para evitar esse erro, iremos definir uma condição para quantas vezes eu irei retornar a resposta *'Hello! '* nesse caso. 

Assim colocamos um valor máximo de respostas que o código irá retornar, ```while``` = enquanto aquela condição não for satisfeita a resposta será  *'Hello! '*. Depois que a condição do ```while``` for satisfeita, o código para de retornar a resposta *'Hello! '*.

Assim a contagem de *greetings* retornará *'Hello! '* no máximo 3 vezes. Utilizamos também a função ```if``` vista anteriormente, e agora, se o usuário escolher colocar como resposta no *input*: *'sair'*, o código executará a função ```break``` que irá parar a função ```while``` de continuar a acontecer. 

Mas e se o usuário digitar no console "SAIR" ou "sair" ou "SaIr" ou...? Precisamos garantir que independente da forma com que ele digite a palavra *sair* o código entenda que a condição definida foi cumprida. Utilizamos então o método ```lower``` para que a comparação de strings seja feita de forma insensível a letras maiúsculas e minúsculas. Assim a resposta dada no *input* fará com que ```user_input.lower() == 'sair'``` seja verdadeira.


Podemos fazer a mesma coisa de forma diferente, utilizando um código com a função ```for``` para limitar o número de impressões de *'Hello! '*. 

```ruby
for greetings in range(1, 4):
    user_input = input("Diga um cumprimento (ou 'sair' para encerrar): ")
    if user_input.lower() == 'sair':
        break
    print('Hello! ')
```

O ```for``` é uma estrutura que permite que um bloco de código seja executado várias vezes em um determinado ```range``` (semelhante a função ```while```), iterando um número, sequência ou um objeto iterável por exemplo. 

O *loop* do código exemplificado, ```for``` irá executar três iterações, porque o ```range(1, 4)``` gera uma sequência de números de 1 a 3, sem a inclusão do número 4.


> **INI5	Working with Files: Given: A file containing at most 1000 lines. Return: A file containing all the even-numbered lines from the original file. Assume 1-based numbering of lines.**








