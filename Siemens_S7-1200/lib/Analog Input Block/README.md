# Siemens S7-1200: Biblioteca p/ Leitura de Entradas Analógicas
Esta biblioteca implementa um function block na linguagem SCL para PLC Siemens S7-1200. Inclui a conversão de sinal, além de funções para alarmes, simulação e mais. 
Esse bloco pode ser utilizado em projetos industriais genéricos para tratamento de sinais de entrada analógica, como sensores de nível, pressão, temperatura, etc. 
A Biblioteca também está preparada para trabalhar com faceplates.

## Funcionalidades Principais

**Funcionamento via Linking ou Operador**: Permite selecionar fonte dos comando via lógica (linking) ou via comando do operador (a partir de *faceplate*, por exemplo).

**Simulação:** Permite Simular valores e verifica se a simulação deve ser ativada, dependendo de entradas do operador e sinais de controle.

**Limite de Histerese:** Controla o modo de histerese, podendo operar em modo percentual ou absoluto, dependendo da seleção do operador.

**Modo periférico/Valor Real:** Seleciona o modo de operação para trabalhar com valores normalizados ou de entrada analógica bruta, conforme a configuração selecionada.

**Reset de Operação:** Gerencia o reset do sistema, seja por operador ou por link.

**Cálculo de Histerese:** Calcula os valores de histerese para controle em modo percentual ou absoluto, dependendo da configuração.

**Conversão de sinal:** Converte entradas analógicas (inteiros) em valores reais e os escala para o modo bipolar ou unipolar.

**Verificação de Erros no Modo de Simulação:** Confirma se os valores estão dentro dos limites esperados no modo de simulação.

**Verificação de Erros nos Modos Unipolar/Bipolar (4..20mA):** Checa erros no modo de operação unipolar (ex. sobrecarga, quebras de fio).

**Verificação de Erros no Valor Real:** Verifica se os valores reais estão dentro dos limites configurados.

**Erro Geral:** Avalia erros gerais no sistema, combinando diversos erros identificados.

**Alarme de Limite Superior:** Gera alarmes quando o valor excede o limite superior.

**Aviso de Limite Superior:** Gera avisos para o limite superior, similar ao alarme.

**Aviso de Limite Inferior:** Gera avisos para o limite inferior.

**Alarme de Limite Inferior:** Similar aos avisos, mas com alarmes para o limite inferior.

**Integração com faceplates:** Possui dados prontos para integrar com objetos ou faceplates de HMI/SCADA.

## Requisitos

- **Software**: TIA Portal V16 ou superior.
- **Hardware**: Siemens S7-1200/S7-1500 CPU.

## Como Executar

1. Importe o arquivo do projeto no TIA Portal.
2. Conecte o PLC e configure os dispositivos conforme o diagrama elétrico.
3. Faça o upload do programa e teste o sistema.

## Exemplos de uso

## Documentação

- [Diagrama Elétrico](./docs/Diagrama_Elétrico.pdf)
- [Descrição Funcional](./docs/Descrição_Funcional.txt)
