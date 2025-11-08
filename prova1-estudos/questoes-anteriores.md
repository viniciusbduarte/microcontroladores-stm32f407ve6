# Lista de Exercícios – Microcontroladores STM32

---

## Questão 1

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

## Questão 2

Explique por que **não podemos classificar um microcontrolador STM32 como um computador CISC com arquitetura Von-Neumann.**

---

## Questão 3

A figura abaixo mostra o gráfico de um sinal PWM em um pino de um microcontrolador STM32 que opera com um sinal de clock de 60 MHz.  
O sinal controla a velocidade e a potência de um motor DC de 250 W e 2000 RPM.

![Diagrama do circuito](questao3.png)

```c
while(1){
    GPIOE->ODR &= ~(1 << 9);
    GPIOE->ODR &= ~(1 << 9);
    GPIOE->ODR |= (1 << 9);
    GPIOE->ODR |= (1 << 9);
    GPIOE->ODR &= ~(1 << 9);
}
```
Considerando o sinal observado, determine:

**a)** Qual o pino utilizado.  
**b)** Qual a frequência e o ciclo de trabalho (duty cycle) do sinal PWM.  
**c)** Qual a potência aplicada ao motor.  
**d)** Qual a velocidade de rotação do motor.  

---

## Questão 4

A figura abaixo mostra o esboço gráfico de um sinal PWM em um pino de um microcontrolador STM32 que opera com sinal de clock de 10 MHz.  
O sinal controla a corrente e a potência de um motor DC de 400 W e 800 RPM.

![Diagrama do circuito](questao4.png)

```c
while(1){
    GPIOE->ODR &= ~(1 << 6);
    GPIOE->ODR &= ~(1 << 6);
    GPIOE->ODR &= ~(1 << 6);
    GPIOE->ODR |= (1 << 6);
    GPIOE->ODR &= ~(1 << 6);
}
```
Determine:

**a)** Qual o pino utilizado.  
**b)** Qual a frequência e o ciclo de trabalho (duty cycle) do sinal PWM.  
**c)** Qual a potência aplicada ao motor.  
**d)** Qual a velocidade de rotação do motor.  

---

## Questão 5

Na figura abaixo, é mostrado um diagrama com dois microcontroladores STM32 e componentes externos que são ligados na mesma fonte de alimentação.  
Os pinos apresentados foram previamente configurados como saídas.  
Os programas 1 e 2 rodam nos microcontroladores e fazem o LED piscar.  
Considere que o **Programa 2** começa a ser executado com um atraso de 80 µs em relação ao **Programa 1**.  

![Diagrama do circuito](questao5.png)

```c
//Programa 1
while(1){
    GPIOE->ODR &= ~(1 << 3);
    Delay_us(2800);
    GPIOC->ODR |= (1 << 3);
    Delay_us(200);
}
```

```c
//Programa 2
while(1){
    GPIOE->ODR &= ~(1 << 7);
    Delay_us(4800);
    GPIOC->ODR |= (1 << 7);
    Delay_us(200);
}
```
**a)** Com qual frequência o LED piscará?  
**b)** Qual a largura do pulso aplicada sobre o LED?  

---

## Questão 6

Na figura abaixo, é mostrado um diagrama com dois microcontroladores STM32 que fornecem sinais PWM a dois LEDs por meio de programas distintos, que executam simultaneamente em cada microcontrolador.  

![Diagrama do circuito](questao6.png)

```c
//Programa 1
while(1){
    GPIOC->ODR |= (1 << 9);
    Delay_us(tempo);
    GPIOE->ODR &= ~(1 << 9);
    Delay_us(1250 - tempo);
    tempo+ = tempo + 50;;
    if(tempo==1250) tempo=0;
}
```

```c
//Programa 2
while(1){
    GPIOC->ODR |= (1 << 4);
    Delay_us(tempo);
    GPIOE->ODR &= ~(1 << 4);
    Delay_us(4000 - tempo);
    tempo+ = tempo + 10;;
    if(tempo==4000) tempo=0;
}
```

Determine:

**a)** Qual a frequência aproximada de cada sinal PWM.  
**b)** Sabendo que o brilho dos LEDs é controlado pelo PWM, em quanto tempo, após o início da execução dos programas, os dois LEDs estarão simultaneamente com o brilho mínimo pela primeira vez.  


