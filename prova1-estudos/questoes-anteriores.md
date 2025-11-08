# Lista de Exercícios – Microcontroladores STM32

---

## Questão 2

Durante as atividades práticas, foi utilizado um teclado de membrana, formado por teclas organizadas em uma matriz de 4 linhas e 4 colunas.  
Quando pressionada, uma tecla conecta uma linha com uma coluna.  
As linhas são conectadas a pinos de saída do tipo *open-drain* com resistores de *pull-up* habilitados, enquanto as colunas são conectadas a pinos de entrada com resistores de *pull-up* também habilitados.  

Para detectar qual tecla está sendo pressionada, o microcontrolador leva uma linha de cada vez para nível lógico baixo e lê o nível lógico das colunas.

**a)** Explique o que acontece no hardware se duas teclas quaisquer forem pressionadas simultaneamente e como o software pode tratar esse evento.  

**b)** Se as saídas de linha não forem configuradas como *open-drain*, mas sim como saídas normais (*push-pull*), explique o que acontece no hardware se duas teclas quaisquer forem pressionadas simultaneamente e como o software pode tratar esse evento.  

---

## Questão 3

Na figura abaixo, é mostrado um diagrama com dois microcontroladores STM32 e componentes externos que são ligados na mesma fonte de alimentação.  
Os pinos apresentados foram previamente configurados como saídas.  
Os programas 1 e 2 rodam nos microcontroladores e fazem o LED piscar.  
Considere que o **Programa 2** começa a ser executado com um atraso de 80 µs em relação ao **Programa 1**.  

**a)** Com qual frequência o LED piscará?  
**b)** Qual a largura do pulso aplicada sobre o LED?  

---

## Questão 4

Considere que o microcontrolador STM32 executa um trecho de código e exibe o resultado em um display de 7 segmentos de cátodo comum.  
Determine qual o dígito hexadecimal será exibido após a execução.  

---

## Questão 5

A posição do eixo de um servomotor está sendo controlada por um microcontrolador STM32.  
Um segundo microcontrolador deseja “ler” a posição do eixo desse servo.  
Para isso, a linha de controle do servomotor é conectada ao pino PA0, configurado como entrada, do segundo microcontrolador.  

Escreva um trecho de código para que o segundo microcontrolador armazene constantemente em uma variável a posição (em graus) do eixo do servomotor com resolução de fração de grau.  

---

## Questão 6

Considere o circuito da figura abaixo.  
A posição do eixo do servomotor é fixa e está sendo controlada pelo microcontrolador STM32 A.  
Sabe-se que um pulso de controle de 500 µs movimenta o eixo do servomotor para a posição de 0 grau, enquanto um pulso de 2500 µs movimenta o eixo do servomotor para a posição de 180 graus.  

Para manter a posição do eixo do servomotor, os pulsos são enviados periodicamente com uma frequência de 40 Hz.  
O microcontrolador STM32 B foi configurado para ler o pino PC2 como entrada e executar um programa que mede a duração do pulso.  

Após um tempo maior que um segundo de execução, determine os possíveis valores da variável observada.  

---

## Questão 7

Leia as afirmações abaixo sobre o microcontrolador STM32:

1. O STM32 é uma família de microcontroladores baseada na arquitetura ARM Cortex-M4.  
2. Os microcontroladores STM32 possuem unidade para operações de ponto flutuante (FPU) em todas as versões da família.  
3. O STM32 pode ser programado unicamente na linguagem Assembly, apenas em linguagem de alto nível, devido à sua arquitetura avançada.  
4. A ferramenta de desenvolvimento utilizada para programar o STM32 é o STM32CubeIDE.  
5. O microcontrolador STM32 é do tipo ARM Cortex-M7 e é capaz de operar a frequências de até 168 MHz.  

**É verdadeiro o que se afirma:**
- a) Apenas IV  
- b) Apenas I e IV  
- c) Apenas II e IV  
- d) Apenas IV e V  
- e) Apenas I e V  

---

## Questão 8

Explique por que **não podemos classificar um microcontrolador STM32 como um computador CISC com arquitetura Von-Neumann.**

---

## Questão 9

A figura abaixo mostra o gráfico de um sinal PWM em um pino de um microcontrolador STM32 que opera com um sinal de clock de 60 MHz.  
O sinal controla a velocidade e a potência de um motor DC de 250 W e 2000 RPM.

Considerando o sinal observado, determine:

**a)** Qual o pino utilizado.  
**b)** Qual a frequência e o ciclo de trabalho (duty cycle) do sinal PWM.  
**c)** Qual a potência aplicada ao motor.  
**d)** Qual a velocidade de rotação do motor.  

---

## Questão 10

A figura abaixo mostra o esboço gráfico de um sinal PWM em um pino de um microcontrolador STM32 que opera com sinal de clock de 10 MHz.  
O sinal controla a corrente e a potência de um motor DC de 400 W e 800 RPM.

Determine:

**a)** Qual o pino utilizado.  
**b)** Qual a frequência e o ciclo de trabalho (duty cycle) do sinal PWM.  
**c)** Qual a potência aplicada ao motor.  
**d)** Qual a velocidade de rotação do motor.  

---

## Questão 11

Na figura abaixo, é mostrado um diagrama com dois microcontroladores STM32 que fornecem sinais PWM a dois LEDs por meio de programas distintos, que executam simultaneamente em cada microcontrolador.  

Determine:

**a)** Qual a frequência aproximada de cada sinal PWM.  
**b)** Sabendo que o brilho dos LEDs é controlado pelo PWM, em quanto tempo, após o início da execução dos programas, os dois LEDs estarão simultaneamente com o brilho mínimo pela primeira vez.  

---

## Questão 12

Considere o circuito da figura abaixo.  
A posição do eixo do servomotor é fixa e está sendo controlada pelo microcontrolador STM32 A.  
Sabe-se que um pulso de 2500 µs posiciona o eixo do servomotor a 180 graus, enquanto um pulso de 500 µs o posiciona a 0 grau.  

O microcontrolador STM32 B foi configurado para ler o pino PC2 como entrada e medir a duração do pulso.  
Após um tempo maior que um segundo de execução, determine os possíveis valores da variável analisada.  
