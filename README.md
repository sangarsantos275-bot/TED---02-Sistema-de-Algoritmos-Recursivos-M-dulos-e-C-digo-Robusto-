# Central Recursiva - TED 02

## 👥 Integrantes da Dupla
* Jaislane Santos da Silva 
* Sanggar Santos Guimarães 

## 📝 Descrição do Projeto
Este projeto consiste em uma central de operações matemáticas desenvolvida em Python para o **Beecrowd Academic**. O sistema processa um lote com Q operações enviadas via entrada padrão (`stdin`), utilizando exclusivamente algoritmos recursivos e aplicando boas práticas de programação orientada a objetos com a criação de exceções personalizadas, módulos e pacotes.

## 🛠️ Organização dos Módulos
O sistema foi estruturado e encapsulado seguindo as convenções de pacotes do Python para garantir a modularidade e legibilidade do código:
* `main.py`: Ponto de entrada que gerencia o fluxo de entrada e saída de dados, o particionamento das strings lidas do `sys.stdin` e o tratamento centralizado das exceções.
* `App/excecoes.py`: Centraliza as exceções customizadas do sistema que herdam da classe nativa `Exception`.
* `App/operacoes.py`: Módulo isolado contendo as funções estritamente recursivas focadas no processamento matemático.

## 🔄 Algoritmos Recursivos Implementados
1. **Máximo Divisor Comum (MDC - Algoritmo de Euclides):** Reduz o problema recursivamente por meio do cálculo do resto da divisão inteira (`a % b`) até atingir o caso base (`b == 0`), retornando o último divisor válido de forma performática.
2. **Soma de Dígitos:** Isola recursivamente o dígito menos significativo (`n % 10`) e soma-o ao resultado da redução do número (`n // 10`) até que a base de parada (`n == 0`) seja alcançada.

## 🚨 Exceções Personalizadas
Para cumprir as diretrizes do projeto e os requisitos de formatação rigorosos do Beecrowd, o controle de fluxo substituiu blocos condicionais simples por disparos de exceções customizadas:
* `OperacaoInvalidaError`: Lançada automaticamente se o código de operação fornecido for diferente de 'M' ou 'S'. Imprime a mensagem padronizada `ERRO: OperacaoInvalida`.
* `EntradaInvalidaError`: Disparada quando os argumentos da linha não são numéricos, não atendem à quantidade necessária de parâmetros, ou violam as restrições matemáticas (valores ≤ 0 para o MDC ou valores < 0 para a Soma). Imprime a mensagem padronizada `ERRO: EntradaInvalida`.

## 📦 Tratamento de Erros e Fluxo (Try, Except, Finally)
O laço principal de repetição faz o uso explícito de blocos `try-except` para interceptar as falhas de entrada em tempo de execução sem interromper o processamento das próximas operações do lote. O bloco opcional `finally` atua como âncora de encerramento para cada iteração do ciclo de leitura.

## 🚀 Como Executar o Projeto Localmente
Certifique-se de ter o Python 3 instalado. No terminal, execute a aplicação e envie os dados em lote:
```bash
python main.py < arquivo_de_testes.txt
```