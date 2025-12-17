# Teste de Performance – BlazeDemo

Este projeto contém testes de performance desenvolvidos com **Apache JMeter** para validar o fluxo de **compra de passagens aéreas** no site BlazeDemo.

URL testada: https://www.blazedemo.com

---

## Objetivo

Validar se a aplicação suporta:
- **250 requisições por segundo**
- **P90 inferior a 2 segundos**
- **0% de erro funcional**

---

## Ferramentas

- Apache JMeter 5.6.x  
- Java 11+  
- Git / GitHub  

---

## Estrutura do Projeto

```text
blazedemo-performance-test/
├── jmeter/
│   ├── load-test.jmx
│   └── spike-test.jmx
├── results/
│   ├── load-test.jtl
│   └── spike-test.jtl
├── reports/
│   ├── load-test-report/
│   └── spike-test-report/
└── README.md

Cenário Testado

Acesso à página inicial

Busca de voos

Seleção do voo

Compra e confirmação da passagem

Validação:

HTTP 200

Texto: "Thank you for your purchase today!"

Testes Executados
Load Test

Usuários: 250

Ramp-up: 10s

Throughput: 250 req/s

jmeter -n -t jmeter/load-test.jmx -l results/load-test.jtl -e -o reports/load-test-report

Spike Test

Usuários: 500

Ramp-up: 5s

Loop: 5

jmeter -n -t jmeter/spike-test.jmx -l results/spike-test.jtl -e -o reports/spike-test-report

Resultados
Load Test

Throughput conforme esperado

P90 < 2s

Erro: 0%

✔️ Critério de aceitação atendido.

Spike Test

Nenhum erro funcional

Aumento de latência esperado sob pico

Sistema manteve estabilidade

Evidências

Relatórios HTML disponíveis em:

reports/

## Relatórios

Os relatórios HTML gerados pelo JMeter estão disponíveis na pasta:

- reports/load-test-report/index.html
- reports/spike-test-report/index.html

Para visualizar, basta abrir o arquivo `index.html` em um navegador.



