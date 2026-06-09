[README_Mission_Control_AI.md](https://github.com/user-attachments/files/28764391/README_Mission_Control_AI.md)
# 🚀 Mission Control AI
## Sistema de Alerta por Lógica Digital para Missão Espacial Experimental

### Disciplina
Ciências da Computação

### Professor
Lucas Moreira

### Integrantes
- Mauricio Bertuci Saletti – RM 571229
- Leonardo Fortini Marcelo – RM 572566
- Mateus Eduardo Da Cruz Rocha – RM 570736

---

# 📖 Resumo

O projeto **Mission Control AI** consiste no desenvolvimento de um sistema inteligente de monitoramento capaz de identificar condições críticas em uma missão espacial experimental. Utilizando conceitos de lógica digital, expressões booleanas, sistemas embarcados e tomada de decisão automatizada, o sistema monitora variáveis operacionais da nave e aciona um alerta visual sempre que uma combinação de falhas representar risco para a missão.

## 🎯 Objetivo Geral

Desenvolver um sistema de monitoramento digital capaz de detectar falhas operacionais em uma missão espacial e emitir alertas automáticos sempre que forem identificadas condições críticas previamente definidas.

## 🔍 Variáveis de Entrada

| Variável | Descrição |
|-----------|------------|
| A | Falha de comunicação |
| B | Temperatura crítica |
| C | Baixo nível de energia |
| D | Falha em módulo operacional |
| E | Perda de estabilidade |

## 🧮 Expressão Booleana

```text
X = (A·C) + (B·D) + [E·(A+B)] + (C·D·¬E)
```

## 📐 Expressão Simplificada

```text
X = AC + BD + AE + BE + CD¬E
```

## 🔌 Componentes Utilizados

- Arduino Uno
- Protoboard
- LED Vermelho
- Resistor 220 Ω
- 5 Chaves Slide Switch
- Cabos Jumper

## 💻 Código

```cpp
int A = 2;
int B = 3;
int C = 4;
int D = 5;
int E = 6;

int X = 13;

void setup() {
  pinMode(A, INPUT_PULLUP);
  pinMode(B, INPUT_PULLUP);
  pinMode(C, INPUT_PULLUP);
  pinMode(D, INPUT_PULLUP);
  pinMode(E, INPUT_PULLUP);
  pinMode(X, OUTPUT);
}

void loop() {
  int a = !digitalRead(A);
  int b = !digitalRead(B);
  int c = !digitalRead(C);
  int d = !digitalRead(D);
  int e = !digitalRead(E);

  int alerta =
      (a && c) ||
      (b && d) ||
      (e && (a || b)) ||
      (c && d && !e);

  digitalWrite(X, alerta);
}
```

## 🧪 Casos de Teste

- A=1 e C=1 → LED aceso
- B=1 e D=1 → LED aceso
- A=1 e E=1 → LED aceso
- B=1 e E=1 → LED aceso
- C=1 e D=1 e E=0 → LED aceso

## 🔗 Simulação

https://www.tinkercad.com/things/05dVi0k6MuP-gs-computer-science

## ✅ Conclusão

O projeto demonstrou a aplicação prática de lógica digital, portas lógicas e programação embarcada para monitoramento de missões espaciais, atendendo aos requisitos propostos na atividade.
