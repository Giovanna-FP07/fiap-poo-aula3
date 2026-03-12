# 🎫 Sistema de Bilhete Único - Programação Orientada a Objetos

## Descrição do Projeto

Este projeto simula o funcionamento de um Bilhete Único, representando regras básicas de validação de entrada em transporte público.

O sistema foi desenvolvido utilizando Programação Orientada a Objetos (POO) em Java, aplicando conceitos como classe e objeto, atributos, métodos, regras de negócio, organização lógica e controle de estado.

---

## O que o objeto representa no mundo real?

A classe `BilheteUnico` representa um cartão de transporte público, semelhante ao utilizado em ônibus, metrô ou trem.

Cada objeto criado a partir dessa classe representa um cartão individual contendo:

- Tipo do cartão (Comum ou Estudante)
- Saldo disponível
- Data de validade

---

## Estrutura da Classe

### 🔹 Atributos

- `tipo` → Define se o cartão é "Comum" ou "Estudante"
- `saldo` → Valor disponível para pagamento de passagens
- `dataValidade` → Data limite de uso do cartão

---

## Métodos Implementados

### ✅ `estaVencido()`

```java
public boolean estaVencido()
```

Verifica se a data atual é posterior à data de validade do cartão.

Retorna:
- `true` se o cartão estiver vencido
- `false` se estiver válido

---

### ✅ `pagarPassagem(double valorTarifa)`

```java
public boolean pagarPassagem(double valorTarifa)
```

Realiza a tentativa de pagamento da passagem.

Regras aplicadas:

1. Se o cartão estiver vencido → não permite pagamento.
2. Se for do tipo "Estudante" → aplica 50% de desconto.
3. Se não houver saldo suficiente → não permite pagamento.
4. Caso todas as validações sejam atendidas → desconta o valor do saldo.

Retorna:
- `true` se a entrada foi liberada
- `false` se a entrada foi bloqueada.

---

### ✅ `validarEntrada(double valorTarifa)`

```java
public boolean validarEntrada(double valorTarifa)
```

Método que reutiliza a lógica de `pagarPassagem()` para validar a entrada no transporte.

---

## Encapsulamento

Os atributos da classe são definidos como `private`, garantindo que o estado interno do objeto não possa ser alterado diretamente por outras classes.

O acesso às informações é feito por meio de métodos `get`, enquanto a modificação dos atributos é controlada internamente pela própria classe, garantindo maior segurança e consistência dos dados.

---

## Regras de Negócio

O sistema respeita a seguinte ordem de validação:

1. Validade do cartão
2. Aplicação de desconto (se estudante)
3. Verificação de saldo

Essa ordem garante que o objeto nunca entre em estado inconsistente, como:

- Saldo negativo
- Desconto aplicado indevidamente
- Pagamento realizado com cartão vencido

---

## Como Utilizar

Exemplo de criação de um bilhete:

```java
BilheteUnico bilhete = new BilheteUnico(
    "Estudante",
    20.00,
    LocalDate.of(2026, 12, 31)
);
```

Validar entrada:

```java
boolean entradaLiberada = bilhete.validarEntrada(5.0);
```

Verificar se está vencido:

```java
bilhete.estaVencido();
```

---

## Tecnologias utilizadas

- Java
- Programação Orientada a Objetos (POO)
- Eclipse IDE

---

## Objetivo Acadêmico

Este projeto demonstra a aplicação prática de:

- Modelagem de objetos do mundo real
- Implementação de regras de negócio
- Controle de estado interno do objeto
- Organização e reutilização de métodos

Desenvolvido para fins acadêmicos na disciplina de Programação Orientada a Objetos.
