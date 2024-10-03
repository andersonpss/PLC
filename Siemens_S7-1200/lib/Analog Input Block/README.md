# Siemens S7-1200: Biblioteca p/ Leitura de Entradas Analógicas
Este projeto implementa um function block na linguagem SCL para PLC Siemens S7-1200. Inclui a conversão de sinal, além de funções para alarmes, simulação e mais. 
Esse bloco pode ser utilizado em projetos industriais genéricos para tratamento de sinais de entrada analógica, como sensores de nível, pressão, temperatura, etc.

## Funcionalidades Principais

- **Connversão do sinal analógico para unidade de engenharia**: Acionada automaticamente com base na detecção de peças por sensores.
- **Alarmes HiHI, Hi, Lo, LoLo**: Alarmes para diferentes níveis de sinal.
- **Alarmes de falha**: Monitoramento e sinalização de falhas de sinal (Overrun, High range, Low range, Wire breakage).
- **Simulação**: Permite Simulação de valores de processo.

## Requisitos

- **Software**: TIA Portal V16 ou superior.
- **Hardware**: Siemens S7-1200 CPU.

## Como Executar

1. Importe o arquivo do projeto no TIA Portal.
2. Conecte o PLC e configure os dispositivos conforme o diagrama elétrico.
3. Faça o upload do programa e teste o sistema.

## Documentação

- [Diagrama Elétrico](./docs/Diagrama_Elétrico.pdf)
- [Descrição Funcional](./docs/Descrição_Funcional.txt)
