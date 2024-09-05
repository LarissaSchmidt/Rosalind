# Rosalind
Resolução dos exercícios propostos no site Rosalind
# Badges 
![Badge em Desenvolvimento]( https://img.shields.io/badge/Em%20Produção%20-8A2BE2)

# Descrição do Projeto

Está é a resolução dos exercícios e  problemas propostos no site Rosalind, como método de ensino de bioinformática e programação em Python

O site pode ser acessado no link: <https://rosalind.info/problems/locations/>

# Construção código Rosalind

> **INI1 Installing Python: Enter "import this" into your Python command line and see what happens.**

```ruby
import this
```
*Resultado* ```The Zen of Python, by Tim Peters```

Beautiful is better than ugly.
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
Namespaces are one honking great idea -- let's do more of those!

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

Explicação:

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

Este problema nos pede para somar todos os inteiros ímpares em um intervalo entre ```[a, b]```, onde a e b são inteiros positivos e a<b<10000. Para isso precisamos 
Ler os valores de a e b 
Iterar sobre o intervalo [a, b]
Verificar se o número é ímpar
Somar os números ímpares

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
```
