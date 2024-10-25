Vamos estruturar o estudo de Cálculo Numérico para cobrir esses tópicos detalhadamente. A abordagem será progressiva, partindo dos fundamentos e aprofundando-se em cada método. Vou começar com uma visão geral de cada tema e, em seguida, abordamos cada tópico com exemplos práticos e passos detalhados.

**Sumário do estudo inicial:**
1. **Introdução à Matemática Numérica**
2. **Métodos Iterativos**
   - Método das Aproximações Sucessivas
   - Método do Meio Intervalo
   - Método de Newton-Raphson
   - Método das Secantes
3. **Álgebra Linear**
   - Sistemas de Equações Lineares
   - Autovalores e Autovetores
4. **Interpolação**
5. **Integração Numérica**
6. **Equações Diferenciais Numéricas**

Ótimo! Vamos começar com a **Introdução à Matemática Numérica**.

##1.0 **Introdução à Matemática Numérica**

### O que é Cálculo Numérico?

Cálculo Numérico, ou Matemática Numérica, é o ramo da matemática que desenvolve e aplica métodos para obter soluções aproximadas de problemas matemáticos complexos. Esses métodos são especialmente úteis em problemas que envolvem funções complexas, equações de difícil solução analítica (ou seja, quando a resposta exata não pode ser encontrada de forma prática), ou quando trabalhamos com um grande volume de dados.

A área é crucial, pois muitos problemas reais, como cálculos de engenharia, física, economia, e várias áreas científicas, não têm soluções exatas ou são computacionalmente inviáveis. Através de métodos numéricos, conseguimos:

- **Obter aproximações** que são tão próximas da resposta exata quanto necessário;
- **Usar algoritmos iterativos** para resolver problemas com métodos que convergem para a solução com cada repetição (ou iteração);
- **Desenvolver algoritmos computacionais** para automatizar a solução de problemas complexos.

### Por que usar Métodos Numéricos?

Em muitos casos, resolver uma equação de maneira exata é impossível ou impraticável. Um exemplo disso é tentar encontrar as raízes de equações não lineares complexas. Nesses casos, técnicas de aproximação nos ajudam a encontrar soluções que podem ser suficientemente próximas do valor exato para uso prático.

### Características dos Métodos Numéricos

1. **Iteratividade**: A maioria dos métodos numéricos são iterativos, ou seja, eles aproximam a solução passo a passo. A cada iteração, chegamos mais perto da resposta, e o método pode ser interrompido quando a precisão desejada for atingida.

2. **Erro**: Em métodos numéricos, erros são inevitáveis, mas são controláveis. Existem duas principais fontes de erro:
   - **Erro de Truncamento**: Surge quando interrompemos um processo iterativo antes do ponto de convergência total.
   - **Erro de Arredondamento**: Resulta da limitação dos sistemas de numeração (computadores, por exemplo, não podem armazenar decimais exatos e infinitos).

3. **Convergência**: Um método numérico é dito convergente se, após várias iterações, ele se aproxima da solução desejada. A velocidade com que um método se aproxima da solução é chamada de **taxa de convergência**.

### Estrutura Básica dos Métodos Numéricos

Vamos agora explorar a estrutura básica dos métodos numéricos que vamos ver detalhadamente:
- **Métodos de Aproximação para Raízes de Funções**: Técnicas que encontramos em equações como \( f(x) = 0 \), onde buscamos os valores de \( x \) que tornam a função zero.
- **Métodos em Álgebra Linear**: Resolução de sistemas de equações lineares e cálculo de autovalores e autovetores, fundamentais para análise de sistemas de várias variáveis.
- **Interpolação e Ajuste de Curvas**: Quando temos dados discretos e queremos aproximar uma função contínua, a interpolação e o ajuste de curvas nos ajudam a obter uma função que "passa" ou se ajusta a esses dados.
- **Integração Numérica**: Serve para calcular áreas sob curvas quando a integral exata não pode ser resolvida.
- **Métodos para Equações Diferenciais**: Resolver equações diferenciais de forma exata nem sempre é possível, então usamos métodos numéricos para obter aproximações úteis.

---

Essa visão geral nos ajuda a entender que os métodos numéricos são essencialmente formas de "testar e melhorar" soluções, sempre se aproximando mais da resposta real sem a necessidade de uma solução exata.

Claro! Vamos usar um exemplo prático que pode ocorrer na construção civil: **calcular a quantidade exata de material necessária para encher uma viga de concreto**.

Imagine que você precisa encher uma viga com concreto e sabe o volume aproximado da estrutura. No entanto, a forma da viga é irregular, com curvas e variações ao longo de seu comprimento. Calcular o volume exato por métodos analíticos pode ser complexo e demorado.

### Solução com Métodos Numéricos

Para estimar a quantidade de concreto necessária, podemos usar o **Método de Integração Numérica**. Esse método nos ajuda a calcular áreas e volumes quando a função ou forma não tem uma fórmula exata ou quando essa fórmula é complexa demais para uma solução exata. No caso da viga, poderíamos representar a seção transversal da estrutura com uma série de pequenas formas (retângulos ou trapézios) ao longo do comprimento da viga. 

**Método numérico utilizado: Regra do Trapézio (ou Integração por Partes)**

#### Passo a Passo da Solução com o Método Numérico

1. **Dividir o comprimento da viga** em pequenos intervalos de igual tamanho.
2. **Medir a altura da seção transversal** da viga em cada intervalo.
3. **Aplicar a Regra do Trapézio**: a área de cada pequeno intervalo é aproximada como a área de um trapézio, e a soma das áreas desses trapézios nos dará o volume aproximado da viga.

   A fórmula do Método do Trapézio para integração numérica é:
   \[
   \text{Área} \approx \frac{h}{2} (f(x_0) + 2f(x_1) + 2f(x_2) + \dots + 2f(x_{n-1}) + f(x_n))
   \]
   onde \( h \) é o comprimento de cada intervalo, e \( f(x_i) \) representa a altura da viga em cada ponto \( x_i \).

4. **Calcular o volume** usando o valor obtido com a integração numérica.

### Por que usar Integração Numérica?

A integração numérica é escolhida aqui porque:
- **Permite aproximar volumes** mesmo para formas complexas ou funções difíceis de integrar.
- **É eficiente** para uso em situações onde é necessária precisão prática, mas não necessariamente uma solução exata.
- **É flexível** e pode ser adaptada a várias formas e tamanhos de estruturas.

Esse método seria ideal para calcular a quantidade de concreto necessária com boa precisão, ajudando a evitar desperdício ou falta de material.

Vamos calcular um exemplo numérico para entender o método. Suponha que a seção transversal de uma viga tem um formato irregular, mas conseguimos medir a altura dessa seção em intervalos regulares. Assim, podemos calcular o volume usando o **Método do Trapézio**.

### Exemplo Detalhado: Cálculo de Volume de uma Viga Irregular

1. **Dados do Problema:**
   - Comprimento total da viga: \(L = 10\) metros.
   - Vamos dividir esse comprimento em 5 intervalos de 2 metros cada (ou seja, \(h = 2\) metros).
   - As alturas medidas em cada intervalo são: \(f(x_0) = 1.5\), \(f(x_1) = 2.0\), \(f(x_2) = 1.8\), \(f(x_3) = 2.2\), \(f(x_4) = 2.0\), \(f(x_5) = 1.6\) metros.

2. **Método do Trapézio:**
   A área de cada "trapézio" formado ao longo da viga será calculada. Como queremos o volume, multiplicaremos o comprimento de cada intervalo (2 metros) pela área calculada.

3. **Fórmula do Método do Trapézio para Volume:**
   A fórmula geral é:
   \[
   \text{Volume} \approx \frac{h}{2} \times [f(x_0) + 2f(x_1) + 2f(x_2) + 2f(x_3) + 2f(x_4) + f(x_5)]
   \]
   onde:
   - \(h = 2\) metros (intervalo entre cada ponto),
   - \(f(x_i)\) representa a altura da viga em cada ponto.

4. **Aplicação da Fórmula:**
   Vamos substituir os valores na fórmula para calcular o volume aproximado:

   \[
   \text{Volume} \approx \frac{2}{2} \times [1.5 + 2(2.0) + 2(1.8) + 2(2.2) + 2(2.0) + 1.6]
   \]

   Simplificando passo a passo:
   - Calcule as multiplicações por 2:
     \[
     = 1 \times [1.5 + 4.0 + 3.6 + 4.4 + 4.0 + 1.6]
     \]
   - Some os valores dentro dos colchetes:
     \[
     = 1 \times 19.1 = 19.1 \text{ metros cúbicos}
     \]

### Resultado

O volume aproximado da viga, usando o Método do Trapézio, é de **19,1 metros cúbicos**. Este cálculo fornece uma boa aproximação para o volume de concreto necessário para encher a viga.

## 2.0 **Métodos Iterativos**

## 2.1 **Método das Aproximações Sucessivas**
Vamos agora ao **Método das Aproximações Sucessivas**, uma técnica simples, mas poderosa, para encontrar a raiz de uma função (ou seja, o valor de \( x \) que faz \( f(x) = 0 \)).

Esse método é muito usado quando precisamos resolver equações em que uma solução exata é difícil ou impossível de obter. Ele nos permite aproximar a solução através de um processo iterativo — ou seja, repetindo cálculos até que a resposta esteja próxima do valor real desejado.

---

### Como funciona o Método das Aproximações Sucessivas?

O objetivo do método é resolver uma equação do tipo:
\[
f(x) = 0
\]
Para isso, reescrevemos a equação como:
\[
x = g(x)
\]
onde \( g(x) \) é uma função transformada de \( f(x) \) de forma que possamos resolver a equação por aproximações sucessivas. A ideia é criar uma sequência \( x_0, x_1, x_2, \dots \) onde cada \( x_{n+1} = g(x_n) \), isto é, calculamos um valor \( x_{n+1} \) baseado no valor anterior \( x_n \) até que a sequência converja (se aproxime cada vez mais) para a solução.

### Passos do Método

1. **Escolha de uma Aproximação Inicial \( x_0 \):** Começamos com um valor inicial para \( x \), chamado \( x_0 \).
2. **Iteração:** Calculamos o próximo valor usando a fórmula \( x_{n+1} = g(x_n) \).
3. **Convergência:** Repetimos o passo 2 até que a diferença entre \( x_n \) e \( x_{n+1} \) seja suficientemente pequena (ou seja, até que a solução esteja dentro da precisão desejada).

### Condições para Convergência

O método das aproximações sucessivas só funcionará se a função \( g(x) \) atender a certos requisitos matemáticos. Em geral, queremos que \( g(x) \) seja contínua e que a derivada \( g'(x) \) seja menor que 1 em módulo (|g'(x)| < 1) em um intervalo onde está a raiz.

### Exemplo Prático do Método das Aproximações Sucessivas

Vamos aplicar o método a um exemplo simples para entender o processo.

**Exemplo:** Resolver a equação
\[
x^2 - 3x + 2 = 0
\]

#### Passo 1: Transformação da Equação
Primeiro, vamos reescrever a equação na forma \( x = g(x) \):
\[
x = \frac{x^2 + 2}{3}
\]

Aqui, definimos:
\[
g(x) = \frac{x^2 + 2}{3}
\]

#### Passo 2: Escolher uma Aproximação Inicial \( x_0 \)
Vamos escolher \( x_0 = 1 \) como nossa primeira aproximação.

#### Passo 3: Iteração
Agora, aplicamos a fórmula iterativa \( x_{n+1} = g(x_n) \):

1. **Primeira Iteração:**  
   \[
   x_1 = g(x_0) = \frac{1^2 + 2}{3} = \frac{3}{3} = 1
   \]

   Nesse caso, o valor não mudou, o que indica que atingimos uma raiz de forma exata, mas vamos continuar para ver o método em ação em um caso mais complexo.

2. **Para valores mais difíceis:** Para situações onde a resposta não é exata, você repetiria o cálculo com o novo valor até que a diferença entre \( x_n \) e \( x_{n+1} \) seja pequena o suficiente para aceitar como resposta.

### Vantagens e Limitações do Método das Aproximações Sucessivas

**Vantagens:**
- Simplicidade: fácil de implementar em problemas onde a função é bem comportada.
- Boa opção para funções contínuas e com derivadas controladas.

**Limitações:**
- Pode não convergir para a solução, dependendo da função e do ponto inicial escolhido.
- A convergência pode ser lenta.

Esse método é amplamente utilizado em cálculos práticos onde é possível transformar a equação na forma iterativa e obter uma boa aproximação através de sucessivas iterações.

Claro! Vamos trabalhar com um exemplo que exige mais de três iterações para convergir. Vamos resolver a equação:

\[
x = \cos(x)
\]

Aqui, queremos encontrar o valor de \( x \) que satisfaz essa igualdade, o que corresponde a resolver \( f(x) = \cos(x) - x = 0 \).

### 1. Escolha de uma Aproximação Inicial \( x_0 \)

Como ponto de partida, escolhemos \( x_0 = 0.5 \). Essa escolha não é exata, mas está próxima da raiz, o que garantirá uma boa convergência.

### 2. Aplicação do Método Iterativo

Vamos iterar usando a fórmula:
\[
x_{n+1} = \cos(x_n)
\]

E continuamos até que a diferença entre \( x_n \) e \( x_{n+1} \) seja suficientemente pequena (digamos, menos de 0.0001).

### Cálculos de cada Iteração

1. **Primeira Iteração:**
   \[
   x_1 = \cos(x_0) = \cos(0.5) \approx 0.8776
   \]

2. **Segunda Iteração:**
   \[
   x_2 = \cos(x_1) = \cos(0.8776) \approx 0.6390
   \]

3. **Terceira Iteração:**
   \[
   x_3 = \cos(x_2) = \cos(0.6390) \approx 0.8027
   \]

4. **Quarta Iteração:**
   \[
   x_4 = \cos(x_3) = \cos(0.8027) \approx 0.6948
   \]

5. **Quinta Iteração:**
   \[
   x_5 = \cos(x_4) = \cos(0.6948) \approx 0.7682
   \]

6. **Sexta Iteração:**
   \[
   x_6 = \cos(x_5) = \cos(0.7682) \approx 0.7192
   \]

7. **Sétima Iteração:**
   \[
   x_7 = \cos(x_6) = \cos(0.7192) \approx 0.7528
   \]

8. **Oitava Iteração:**
   \[
   x_8 = \cos(x_7) = \cos(0.7528) \approx 0.7302
   \]

9. **Nona Iteração:**
   \[
   x_9 = \cos(x_8) = \cos(0.7302) \approx 0.7451
   \]

10. **Décima Iteração:**
    \[
    x_{10} = \cos(x_9) = \cos(0.7451) \approx 0.7356
    \]

Após 10 iterações, notamos que o valor está se aproximando e estabilizando. A diferença entre \( x_{9} \) e \( x_{10} \) é de aproximadamente \( 0.0095 \), ainda um pouco longe da precisão de 0.0001. 

Continuando o processo por mais algumas iterações, veremos que os valores convergirão para aproximadamente **0.7391**, que é a solução da equação \( x = \cos(x) \) com a precisão desejada. 

### Observação

Neste exemplo, a aproximação é mais lenta, o que é comum para funções que convergem suavemente. O Método das Aproximações Sucessivas funciona bem neste caso, mas ele precisa de um número maior de iterações para alcançar a precisão desejada.

##2.2 **Método do Meio Intervalo**

O **Método do Meio Intervalo**, também conhecido como **Método da Bisseção**, é uma técnica simples e eficaz para encontrar raízes de funções contínuas em um intervalo. Ele é baseado no Teorema do Valor Intermediário, que afirma que, se uma função \( f(x) \) é contínua em um intervalo \([a, b]\) e \( f(a) \) e \( f(b) \) têm sinais opostos (ou seja, um é positivo e o outro é negativo), então existe pelo menos uma raiz no intervalo \((a, b)\).

Este método é útil quando se deseja encontrar uma raiz aproximada de uma função com garantia de convergência, mas é especialmente aplicável em funções que mudam de sinal, como \( f(x) = x^3 - x - 2 \).

---

### Como Funciona o Método do Meio Intervalo

1. **Escolha de um Intervalo Inicial** \([a, b]\):** Escolhemos um intervalo inicial \([a, b]\) onde sabemos que a função muda de sinal — isto é, \( f(a) \) e \( f(b) \) têm sinais opostos. Esse é o ponto de partida.
  
2. **Cálculo do Ponto Médio:** Calculamos o ponto médio do intervalo:
   \[
   m = \frac{a + b}{2}
   \]

3. **Verificação do Sinal em \( m \):** Avaliamos \( f(m) \):
   - Se \( f(m) = 0 \), então encontramos a raiz exata.
   - Se \( f(m) \neq 0 \), verificamos se \( f(m) \) tem o mesmo sinal de \( f(a) \) ou de \( f(b) \).

4. **Redução do Intervalo:** Dependendo do sinal de \( f(m) \), reduzimos o intervalo para metade:
   - Se \( f(a) \) e \( f(m) \) têm o mesmo sinal, então a raiz está no intervalo \([m, b]\).
   - Caso contrário, a raiz está no intervalo \([a, m]\).

5. **Iteração:** Repetimos os passos de 2 a 4 até que o comprimento do intervalo seja suficientemente pequeno, ou seja, até que \( |b - a| \) esteja abaixo de uma precisão desejada.

---

### Exemplo Prático: Encontrando a Raiz de uma Função

Vamos encontrar uma raiz da função:
\[
f(x) = x^3 - x - 2
\]
Queremos encontrar uma raiz de \( f(x) = 0 \) no intervalo \([1, 2]\).

#### Passo a Passo com o Método do Meio Intervalo

1. **Escolha do Intervalo Inicial** \([a, b] = [1, 2]\):
   - Calculamos \( f(1) = 1^3 - 1 - 2 = -2 \)
   - Calculamos \( f(2) = 2^3 - 2 - 2 = 4 \)
   - Como \( f(1) \) é negativo e \( f(2) \) é positivo, existe pelo menos uma raiz no intervalo \([1, 2]\).

2. **Primeira Iteração:**
   - Ponto médio: \( m = \frac{1 + 2}{2} = 1.5 \)
   - Avaliamos \( f(1.5) = (1.5)^3 - 1.5 - 2 = -0.875 \)
   - Como \( f(1.5) \) é negativo (mesmo sinal que \( f(1) \)), reduzimos o intervalo para \([1.5, 2]\).

3. **Segunda Iteração:**
   - Ponto médio: \( m = \frac{1.5 + 2}{2} = 1.75 \)
   - Avaliamos \( f(1.75) = (1.75)^3 - 1.75 - 2 = 1.609375 \)
   - Como \( f(1.75) \) é positivo, reduzimos o intervalo para \([1.5, 1.75]\).

4. **Terceira Iteração:**
   - Ponto médio: \( m = \frac{1.5 + 1.75}{2} = 1.625 \)
   - Avaliamos \( f(1.625) = (1.625)^3 - 1.625 - 2 = 0.666 \)
   - Como \( f(1.625) \) é positivo, reduzimos o intervalo para \([1.5, 1.625]\).

5. **Quarta Iteração:**
   - Ponto médio: \( m = \frac{1.5 + 1.625}{2} = 1.5625 \)
   - Avaliamos \( f(1.5625) = (1.5625)^3 - 1.5625 - 2 = -0.261 \)
   - Como \( f(1.5625) \) é negativo, reduzimos o intervalo para \([1.5625, 1.625]\).

6. **Iterações Seguintes:**
   - Continuamos iterando com o mesmo processo, reduzindo o intervalo cada vez mais.

Após algumas iterações, o intervalo ficará suficientemente pequeno, por exemplo, \([1.521, 1.523]\), indicando que a raiz está próxima de 1.521 com a precisão desejada.

---

### Vantagens e Desvantagens do Método do Meio Intervalo

**Vantagens:**
- Simples de implementar e sempre converge, desde que a função seja contínua no intervalo e tenha sinais opostos em \( a \) e \( b \).
- Não requer derivadas nem cálculos complicados, apenas a avaliação da função no ponto médio.

**Desvantagens:**
- Pode ser relativamente lento, pois reduz o intervalo pela metade a cada iteração.
- Só funciona se houver uma mudança de sinal, ou seja, não é aplicável para funções que não cruzam o eixo \( x \) dentro do intervalo dado.

O **Método do Meio Intervalo** é uma abordagem confiável e robusta, adequada para problemas em que precisamos de uma raiz aproximada com alta precisão, especialmente em funções bem comportadas em um intervalo específico.

## 2.3 **Método de Newton-Raphson**

O **Método de Newton-Raphson** é um método iterativo usado para encontrar aproximações de raízes de funções. Esse método é mais rápido que o Método do Meio Intervalo, mas requer que a função seja diferenciável. Ele é especialmente útil quando temos uma boa aproximação inicial da raiz, e é amplamente aplicado em ciência, engenharia, economia e outros campos que envolvem cálculos numéricos.

### Fundamentos do Método de Newton-Raphson

O método parte da ideia de que, dado um ponto inicial próximo da raiz, podemos melhorar a aproximação iterativamente ao usar a tangente da função no ponto escolhido.

Dado um valor inicial \( x_0 \) próximo da raiz da função \( f(x) = 0 \), a fórmula iterativa do método de Newton-Raphson é:
\[
x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}
\]
onde:
- \( x_n \) é a aproximação atual,
- \( f(x_n) \) é o valor da função em \( x_n \),
- \( f'(x_n) \) é a derivada da função em \( x_n \).

### Intuição do Método

1. Escolhemos um ponto inicial \( x_0 \) perto da raiz.
2. No ponto \( x_n \), traçamos a tangente de \( f(x) \).
3. Encontramos onde essa tangente cruza o eixo \( x \), e usamos esse ponto de interseção como uma nova aproximação da raiz, \( x_{n+1} \).
4. Repetimos o processo até que a diferença entre \( x_n \) e \( x_{n+1} \) seja suficientemente pequena, indicando que estamos próximos da raiz.

Esse método funciona bem quando a função é "suave" (ou seja, continuamente diferenciável) e quando a aproximação inicial está próxima da raiz.

### Exemplo Prático: Encontrando a Raiz de uma Função

Vamos resolver a equação \( f(x) = x^2 - 2 = 0 \), que tem uma raiz em \( \sqrt{2} \approx 1.4142 \).

#### Passo a Passo com o Método de Newton-Raphson

1. **Escolha da Função e Derivada:**
   - Função: \( f(x) = x^2 - 2 \)
   - Derivada: \( f'(x) = 2x \)

2. **Escolha de um Valor Inicial \( x_0 \):**
   - Escolhemos \( x_0 = 1 \) como nosso ponto inicial.

3. **Iterações com a Fórmula do Método de Newton-Raphson:**
   - Utilizamos a fórmula \( x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)} \).

Vamos calcular algumas iterações para ver como o método converge para a raiz.

---

#### Iterações

1. **Primeira Iteração**:
   \[
   x_1 = x_0 - \frac{f(x_0)}{f'(x_0)} = 1 - \frac{1^2 - 2}{2 \cdot 1} = 1 - \frac{-1}{2} = 1 + 0.5 = 1.5
   \]

2. **Segunda Iteração**:
   \[
   x_2 = x_1 - \frac{f(x_1)}{f'(x_1)} = 1.5 - \frac{1.5^2 - 2}{2 \cdot 1.5} = 1.5 - \frac{0.25}{3} = 1.5 - 0.0833 = 1.4167
   \]

3. **Terceira Iteração**:
   \[
   x_3 = x_2 - \frac{f(x_2)}{f'(x_2)} = 1.4167 - \frac{1.4167^2 - 2}{2 \cdot 1.4167}
   \]
   Calculando os valores, obtemos:
   \[
   x_3 \approx 1.4142
   \]

Após três iterações, já temos uma aproximação de \( \sqrt{2} \) com quatro casas decimais. Em muitos casos, o método converge rapidamente, e poucas iterações são necessárias para atingir alta precisão.

---

### Exemplo Aplicado: Encontrando a Raiz de Outra Função

Vamos agora resolver a equação \( f(x) = x^3 - x - 2 = 0 \), usando um valor inicial \( x_0 = 1.5 \).

1. **Função e Derivada**:
   - \( f(x) = x^3 - x - 2 \)
   - \( f'(x) = 3x^2 - 1 \)

2. **Primeira Iteração:**
   - Com \( x_0 = 1.5 \):
     \[
     x_1 = x_0 - \frac{f(x_0)}{f'(x_0)} = 1.5 - \frac{1.5^3 - 1.5 - 2}{3 \cdot 1.5^2 - 1} = 1.5 - \frac{-0.875}{5.75} \approx 1.6522
     \]

3. **Segunda Iteração:**
   \[
   x_2 = x_1 - \frac{f(x_1)}{f'(x_1)} \approx 1.6522 - \frac{f(1.6522)}{f'(1.6522)} \approx 1.5265
   \]

4. **Terceira Iteração:**
   \[
   x_3 = x_2 - \frac{f(x_2)}{f'(x_2)} \approx 1.5265 - \frac{f(1.5265)}{f'(1.5265)} \approx 1.5214
   \]

Após algumas iterações, \( x \) converge para um valor próximo de **1.5214**, que é uma boa aproximação da raiz.

---

### Vantagens e Desvantagens do Método de Newton-Raphson

**Vantagens:**
- Convergência rápida, especialmente quando \( x_0 \) está próximo da raiz.
- Muito eficiente em termos de número de iterações.

**Desvantagens:**
- Requer o cálculo da derivada da função, o que pode ser complicado para funções complexas.
- Pode divergir se o valor inicial \( x_0 \) estiver longe da raiz ou se a função tiver pontos de inflexão perto da raiz.
- Não é adequado para funções não diferenciáveis ou quando \( f'(x) \) é zero próximo da raiz.

O Método de Newton-Raphson é extremamente útil em muitas aplicações, mas requer cuidado na escolha do ponto inicial e uma função bem comportada para garantir convergência.

