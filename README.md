# Qualidade e Teste de Software

## 1. Apresentação

Este repositório contém a implementação e os testes automatizados desenvolvidos para o trabalho prático de Qualidade e Teste de Software.

O projeto reúne três exercícios:
- `CalculadoraDesconto`
- `ContaBancaria`
- `ReservaHotel`

## 2. Objetivos

O trabalho aplica conceitos de teste de software por meio de:

- Identificação de classes de equivalência
- Análise de valores-limite
- Elaboração de casos de teste
- Testes funcionais de caixa-preta
- Verificação da execução interna do código por meio de testes de caixa-branca
- Implementação de testes automatizados com JUnit
- Análise da cobertura de testes com JaCoCo

## 3. Tecnologias utilizadas

| Tecnologia | Finalidade |
|---|---|
| Java  | Linguagem de programação e versão definida no `pom.xml` |
| Maven | Gerenciamento do projeto e execução dos testes |
| JUnit Jupiter 6.1.3 | Implementação dos testes automatizados |
| Maven Surefire 3.6.1 | Execução dos testes pelo Maven |
| JaCoCo 0.8.16 | Análise da cobertura de testes |
| IntelliJ IDEA | Ambiente de desenvolvimento |

## 4. Organização

Os arquivos principais estão organizados da seguinte forma:

```text
src/main/java/org/example/
  CalculadoraDesconto.java
  ContaBancaria.java
  Main.java
  ReservaHotel.java

src/test/java/org/example/
  CalculadoraDescontoTest.java
  ContaBancariaTest.java
  ReservaHotelTest.java
```

## 5. Exercícios e casos testados

### 5.1 CalculadoraDesconto

A classe calcula o valor final de uma compra a partir do valor da compra e do percentual de desconto.

Os testes verificam:

- Valores de compra negativos
- Valor de compra igual a zero
- Percentuais negativos
- Percentuais entre 0% e 100%
- Percentuais acima de 100%
- Cálculos com diferentes percentuais de desconto

Classe de teste: `CalculadoraDescontoTest`.

### 5.2 ContaBancaria

A classe representa uma conta bancária com saldo, depósito e saque.

Os testes verificam:

- Criação com saldo positivo ou igual a zero
- Rejeição de saldo inicial negativo
- Depósitos positivos
- Rejeição de depósitos iguais a zero ou negativos
- Saques válidos
- Saque de todo o saldo
- Rejeição de saques iguais a zero ou negativos
- Rejeição de saque superior ao saldo
- Preservação do saldo após uma operação de saque inválida

Classe de teste: `ContaBancariaTest`.

### 5.3 ReservaHotel

A classe representa uma reserva de hotel com número de diárias, valor da diária, café da manhã, desconto e cancelamento.

Os testes verificam:

- Número de diárias inválido ou válido
- Valor da diária inválido ou válido
- Valor total sem desconto
- Desconto para sete ou mais diárias
- Café da manhã em uma diária
- Café da manhã combinado com desconto
- Cancelamento da reserva
- Valor zero após o cancelamento
- Rejeição de cancelamento repetido
- Rejeição de alteração em reserva cancelada

Classe de teste: `ReservaHotelTest`.

## 6. Pré-requisitos

- JDK 27 ou outra versão compatível com a configuração do `pom.xml`
- Maven instalado e disponível no terminal
- IntelliJ IDEA ou outro ambiente de desenvolvimento Java, caso desejado

## 7. Execução dos testes

Para executar os testes pelo terminal:

```bash
mvn clean test
```

Para executar a verificação completa e gerar o relatório JaCoCo:

```bash
mvn clean verify
```

O relatório gerado pelo Maven fica em:

```text
target/site/jacoco/index.html
```

Também há uma cópia das evidências de cobertura em:

```text
evidencias/cobertura/index.html
evidencias/cobertura/jacoco.csv
```

Para abrir o projeto no IntelliJ IDEA:

1. Abra o IntelliJ IDEA.
2. Selecione a opção para abrir um projeto existente.
3. Selecione a pasta do projeto ou o arquivo `pom.xml`.
4. Aguarde o carregamento das dependências Maven.
5. Localize as classes de teste em `src/test/java`.
6. Execute os testes pelo próprio IntelliJ IDEA.

## 8. Resultados dos testes

Na validação realizada com `mvn clean test`, foram executados 42 testes automatizados, todos aprovados:

| Classe de teste | Testes | Falhas | Erros |
|---|---:|---:|---:|
| `CalculadoraDescontoTest` | 11 | 0 | 0 |
| `ContaBancariaTest` | 15 | 0 | 0 |
| `ReservaHotelTest` | 16 | 0 | 0 |
| **Total** | **42** | **0** | **0** |

## 9. Cobertura de testes

O relatório JaCoCo 0.8.16 disponível em `evidencias/cobertura` apresenta os seguintes resultados:

| Métrica | Resultado |
|---|---:|
| Cobertura de instruções | 90% |
| Cobertura de ramos | 93% |
| Instruções cobertas | 181 de 199 |
| Ramos cobertos | 28 de 30 |

### Cobertura por classe

| Classe | Instruções | Ramos |
|---|---:|---:|
| `CalculadoraDesconto` | 100% | 100% |
| `ContaBancaria` | 100% | 100% |
| `ReservaHotel` | 100% | 100% |
| `Main` | 0% | 0% |

As três classes dos exercícios apresentam 100% de cobertura de instruções e ramos. A cobertura geral é menor porque `Main` não é exercitada pelos testes automatizados.

A cobertura não garante, sozinha, a ausência de defeitos. A qualidade dos testes também depende dos cenários escolhidos, das classes de equivalência, dos valores-limite e das regras de negócio verificadas.

## 10. Materiais complementares

- [Mapeamento sistemático dos testes](MapeamentoSistematico/)
- [Diagramas dos exercícios](DiagramasSlides/)
- [Relatório de cobertura JaCoCo](evidencias/cobertura/index.html)
- [Dados de cobertura em CSV](evidencias/cobertura/jacoco.csv)

## 11. Considerações finais

O projeto aplica testes automatizados com JUnit para verificar três implementações com regras de negócio diferentes.

Os resultados validados mostram 42 testes aprovados e cobertura completa de instruções e ramos nas três classes dos exercícios. O JaCoCo complementa os resultados ao mostrar quais partes do código foram exercitadas pela suíte.
