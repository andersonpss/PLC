# Siemens S7-1200/S7-1500: Biblioteca p/ Leitura de Entradas Analógicas
Esta biblioteca implementa um function block na linguagem SCL para PLC Siemens S7-1200. Inclui a conversão de sinal, além de funções para alarmes, simulação e mais. 
Esse bloco pode ser utilizado em projetos industriais genéricos para tratamento de sinais de entrada analógica, como sensores de nível, pressão, temperatura, etc. 
A Biblioteca também está preparada para trabalhar com faceplates.

## Funcionalidades Principais

**Funcionamento via Linking ou Operador**: Permite selecionar fonte dos comando via lógica (linking) ou via comando do operador (a partir de *faceplate*, por exemplo).

**Simulação:** Permite Simular valores e verifica se a simulação deve ser ativada, dependendo de entradas do operador e sinais de controle.

**Limite de Histerese:** Controla o modo de histerese, podendo operar em modo percentual ou absoluto, dependendo da seleção do operador.

**Modo Periférico/Valor Real:** Seleciona o modo de operação para trabalhar com valores normalizados ou de entrada analógica bruta, conforme a configuração selecionada.

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

**Uso no modo Valor Real:** 

No modo Valor Real, o bloco utiliza o valor do endereço da variável real conectada à entrada *#iRRealIn*. O valor será lido diretamente e utilizado pelo bloco sem nenhuma modificação.

Para utilizar o modo "Valor Real", você deve:

1. Certificar-se de que o valor de entrada está conectado corretamente ao bloco e que a variável conectada é do tipo Real;
2. A entrada *#iXInMode* deve estar com valor *false* e a variável *#iXLiOp_Sel* em *true*, para uso no modo Linking;
3. O bit 14 (*#iqDOpCmd.%X14*) da variável de comando de operação deve estar com valor *true* e a variável *#iXLiOp_Sel* em *false*, para uso no modo operador.


**Uso no modo Periférico:** 

No modo Valor de Periférico, o bloco utiliza o valor do endereço da variável inteira conectada à entrada *#iIAnalogIn*. O valor lido é convertido para um valor real, usando como parâmetros o tipo de entrada (Unipolar ou Bipolar) e o range do instrumento (HiLim e LoLim).

Para utilizar o modo "Periférico", você deve:

1. Certificar-se de que a tag com endereço da entrada analógica (%IW) está conectada corretamente ao bloco na entrada *#iIAnalogIn*;
2. As entradas *#iXInMode* e *#iXLiOp_Sel* devem estar com valor *true*, para uso no modo Linking;
3. O bit 15 (*#iqDOpCmd.%X15*) da variável de comando de operação deve estar com valor *true* e a variável *#iXLiOp_Sel* em *false*, para uso no modo operador.

**Modo Simulação:**

O modo Simulação permite testar o sistema com valores pré-definidos, sem depender dos sensores ou dispositivos reais.

Quando ativado, o bloco ignora os valores reais e periféricos, e utiliza o valor de simulação inserido manualmente. Este modo é útil para fazer testes e diagnósticos do sistema, garantindo que as lógicas de controle e alarme funcionem corretamente mesmo antes da conexão dos dispositivos reais.

O valor de simulação pode ser inserido diretamente em *#iRSimIn* quando o bloco está no modo Linking (*#iXLiOp_Sel=true*). Quando está no modo Operador, o valor é definido na variável *#statOpSimValue* e é habilitado quando o bit 20 da palavra de comando do operador (*#iqDOpCmd.%X20*) está em *true* e a entrada de modo *#iXLiOp_Sel* em *false*.



## Documentação

- [Diagrama Elétrico](./docs/Diagrama_Elétrico.pdf)
- [Descrição Funcional](./docs/Descrição_Funcional.txt)
