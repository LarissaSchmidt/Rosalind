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
*Resultado*

The Zen of Python, by Tim Peters

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
*Resultado* 

1576954

> **INI3	Strings and Lists: Given: A string s of length at most 200 letters and four integers a, b, c and d. Return: The slice of this string from indices a through b and c through d (with space in between), inclusively. In other words, we should include elements s[b] and s[d] in our slice.**

Para definir uma li
```ruby
a = 22 
b = 27 
c = 97 
d = 102 
text =  'HumptyDumptysatonawallHumptyDumptyhadagreatfallAlltheKingshorsesandalltheKingsmenCouldntputHumptyDumptyinhisplaceagain'
print(text[a:b+1], text[c:d+1])
```
*Resultado*  

Humpty Dumpty

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
Isso extrai uma substring de *text* que começa no a e vai até o b, o '+1' é necessário para incluir o índice b.
Nesse caso quando temos ```text[a:b+1]```, estamos dizendo que queremos a string de ```text[22:27+1]``` ou ```text[22:28]```


Podemos também realizar essa mesma ação com outro tipo de código um pouco mais elaborado:
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
*Resultado* 

Amphiuma bengkuluensis

