# Turtle Fractal

## 1. Criando um triângulo turtle:

Fractal é um objeto geométrico que apresenta autossimilaridade em diferentes escalas. Em outras palavras, é uma figura que se repete infinitamente em uma estrutura hierárquica, apresentando o mesmo padrão de formas em diferentes tamanhos.

> Código para gerar um triangulo utilizando turtle:
```sh
import turtle

#Expessura da linha
turtle.pensize(5)

#Desenha um Triângulo
for i in range(3):
    turtle.forward(200)
    turtle.left(120)

#Abre a tela do desenho e fecha com um click
turtle.Screen().exitonclick()

```
> Resultado do código acima, desenhando um triângulo:

![image](./imagem/Triangulo.gif)

## 2. Criando um Estrela turtle:

> Código para gerar uma Estrela utilizando turtle:
```sh
import turtle

# Instanciando o Turtle
t = turtle.Turtle()

# Configurações iniciais. Espessura e cor.
t.pensize(3)
t.pencolor("red")

# Desenha a estrela
for i in range(5):
    t.forward(200)
    t.right(144)
    
#Abre a tela do desenho e fecha com um click
turtle.Screen().exitonclick()
```
> Resultado do código acima, desenhando uma estrela vermelha:

![image](./imagem/Estrela.gif)

## 3. Criando uma Espiral Quadrada turtle:

> Código para gerar uma Espiral Quadrada utilizando turtle:
```sh
import turtle

#Expessura da linha
turtle.pensize(5)

#Desenha um Quadrado em espiral
step = 10
angle = 90
distance = 0
for i in range(100):
    turtle.forward(distance)
    distance += step
    turtle.left(angle)

#Abre a tela do desenho e fecha com um click
turtle.Screen().exitonclick()
```
> Resultado do código acima, desenhando uma Espiral Quadrada:

![image](./imagem/Espiral_quadrada.gif)

## 4. Criando um Floco de Neve usando turtle:

> Código para gerar um Floco de Neve utilizando turtle:
```sh
import turtle

#Config. screen
WIDTH, HEIGHT = 1600, 900
screen = turtle.Screen()
screen.setup(WIDTH, HEIGHT)
screen.screensize(2*WIDTH, 2*HEIGHT)
screen.bgcolor('black')
screen.delay(0)

#Config. Turtle
trig = turtle.Turtle()
trig.pensize(2)
trig.speed(1)
trig.setpos(-WIDTH // 6, HEIGHT // 6)
trig.color('gold')

# Config L-system
generation = 5
axiom = 'F++F++F'
chr_1, rule_1 = 'F', 'F-F++F-F'
#chr_2, rule_2 = 'G', 'GG'
step = 600
angle = 60

def apply_rules(axiom):
    return ''.join([rule_1 if chr == chr_1 else chr for chr in axiom])

for gen in range(generation):
    turtle.pencolor('white')
    turtle.goto(-WIDTH // 2 + 60, HEIGHT // 2 - 100)
    turtle.clear()
    turtle.write(f'Geração: {generation}', font=('Arial', 60, "normal"))
    trig.setheading(0)
    trig.goto(-WIDTH // 6, HEIGHT // 6)
    trig.clear()
    length = step / pow(3, gen)

    for chr in axiom:
        if chr == chr_1:
            trig.forward(length)
        elif chr == '+':
            trig.right(angle)
        elif chr == '-':
            trig.left(angle)
    axiom = apply_rules(axiom)

#Abre a tela do desenho e fecha com um click
screen.exitonclick()
```
> Resultado do código acima, desenhando uma Floco de Neve :

![image](./imagem/Floco_de_neve.gif)

## 5. Criando uma Árvore turtle:

> Código para gerar uma Árvore utilizando turtle:
```sh
import turtle

# Config. Fractal 
turtle.bgcolor("black")
arv = turtle.Turtle()
arv.pensize(2)
arv.color("green")
arv.left(90)
arv.backward(100)
arv.speed(200)

# Cria a Árvore em Fractal
def drawTree(i):
    if i < 10:
        print("Inside")
        return
    else:
        print("Outside")
        arv.forward(i)
        arv.color("magenta")
        arv.circle(2)
        arv.color("brown")
        arv.left(30)
        drawTree(3*i/4)
        arv.right(60)
        drawTree(3*i/4)
        arv.left(30)
        arv.backward(i)

drawTree(100)
turtle.done()
```
> Resultado do código acima, desenhando uma Árvore:

![image](./imagem/Arvore.gif)

## 6. Criando meu Fractal de floco:

> Código para gerar meu Fractal de floco utilizando turtle:
```sh
import turtle

#Config. screen
WIDTH, HEIGHT = 1600, 900
screen = turtle.Screen()
screen.setup(WIDTH, HEIGHT)
screen.screensize(2*WIDTH, 2*HEIGHT)
screen.bgcolor('black')
screen.delay(0)

#Config. Turtle
trig = turtle.Turtle()
trig.pensize(2)
trig.speed(1)
trig.setpos(-WIDTH // 6, HEIGHT // 6)
trig.color('gold')

# L-system
generation = 5
axiom = 'F++F++F'
chr_1, rule_1 = 'F', 'F-F++F-F+F-F++F-F'
#chr_2, rule_2 = 'G', 'GG'
step = 350
angle = 60

def apply_rules(axiom):
    return ''.join([rule_1 if chr == chr_1 else chr for chr in axiom])

for gen in range(generation):
    turtle.pencolor('white')
    turtle.goto(-WIDTH // 2 + 60, HEIGHT // 2 - 100)
    turtle.clear()
    turtle.write(f'Geração: {generation}', font=('Arial', 60, "normal"))
    trig.setheading(0)
    trig.goto(-WIDTH // 6, HEIGHT // 6)
    trig.clear()
    length = step / pow(3, gen)

    for chr in axiom:
        if chr == chr_1:
            trig.forward(length)
        elif chr == '+':
            trig.right(angle)
        elif chr == '-':
            trig.left(angle)
    axiom = apply_rules(axiom)

#Abre a tela do desenho e fecha com um click
screen.exitonclick()
```
> Resultado do código acima, desenhando meu Fractal de floco:

![image](./imagem/Meu_Fractal2.gif)