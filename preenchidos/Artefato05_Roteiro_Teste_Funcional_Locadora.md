**Teste e Qualidade de Software**

# **Artefato 05**

# **Roteiro de Teste Funcional — UC006: Realizar Locação de Veículo**

**Laboratório de Teste Artefato 05 (2ª Avaliação)**

**Estudo de Caso: Locadora de veículos**  
**Nome do Projeto: Super Veículos**  
**Grupo Nº 1**

**Autor(es) ou Participantes:**  
**Enzo Nardelli Ribeiro**  
**Camila Bontempo Sidersky**

**Brasília - DF**

# **Histórico de Revisão**

| Data | Versão | Descrição | Autor | Revisor |
| ----- | ----- | ----- | ----- | ----- |
| 31/05/2026 | 1.0 | Elaboração do roteiro de teste funcional | Enzo e Camila | Leonardo Pol |
| 31/05/2026 | 1.1 | Revisão e padronização final | Enzo e Camila | Leonardo Pol |

# **Roteiro de Teste**

## **1. Identificação**

| Campo | Valor |
| :---- | :---- |
| Nº da Solicitação | LOC-RTF-001/2026 |
| **Data** | 31/05/2026 |
| **Sistema** | Sistema de Gestão para Locadora de Veículos |
| **Solicitante** | Prof. Leonardo Pol |
| **Ambiente de Teste** | Homologação |
| **Nome das Funcionalidades** | Realizar Locação de Veículo |

## **2. Introdução**

Neste artefato são definidos os roteiros de teste e seus respectivos casos de teste para avaliar se o Caso de Uso 006 - Realizar Locação de Veículo está conforme os requisitos funcionais, a especificação de caso de uso, o plano de teste funcional e os cenários de teste definidos para o sistema da locadora.

### **2.1 Objetivo**

O objetivo deste roteiro é definir os casos de teste que deverão ser executados para verificar a funcionalidade de locação de veículos e garantir que ela atende às regras de negócio definidas para o sistema.

- Validar a funcionalidade de realizar locação de veículo.
- Validar as restrições de locação ativa por cliente.
- Validar as regras de indisponibilidade da frota.
- Validar o cálculo do valor total da locação.
- Validar o registro da quilometragem inicial.

#### **2.1.1 Item de Teste**

- Artefato 02 - Caso de Uso 006 - Realizar Locação de Veículo

#### **2.1.2 Tipo de Teste**

Este roteiro abrange os seguintes tipos de teste:

- Teste funcional
- Teste de regras de negócio
- Teste de interface
- Teste de validação
- Teste de regressão

#### **2.1.3 Referências**

- Artefato 01 - Requisitos da Locadora
- Artefato 02 - Especificação de Caso de Uso
- Artefato 03 - Especificação de Teste Funcional
- Artefato 04 - Cenários de Teste

#### **2.1.4 Identificação de Cenário Operacional**

| Cenário | Descrição |
| ----- | ----- |
| Realizar locação com sucesso | Validar o registro da locação, o cálculo do valor total, o registro da quilometragem inicial e a atualização do status do veículo |
| Cancelar locação | Validar o encerramento da operação sem gravação da locação |
| Cliente com locação ativa | Validar o bloqueio de nova locação para cliente com contrato em aberto |
| Veículo não apto para locação | Validar o bloqueio de locação para veículo acima de 80.000 km ou com mais de 4 anos de uso |

## **3. Cenários Operacionais**

### **3.1 Cenário: Realizar Locação com Sucesso**

#### **CT001 - Abrir tela de locação**

##### **3.1.1 Descrição**

O objetivo deste caso de teste é verificar se o sistema apresenta corretamente a tela de locação ao acessar a funcionalidade.

##### **3.1.2 Pré-condição**

- Atendente autenticado no sistema.
- Funcionalidade de locação disponível no menu do sistema.

##### **3.1.3 Procedimentos**

| Passo e Verificação | Descrição |
| ----- | ----- |
| P1 | O atendente acessa o menu de locação. |
| V1 | O sistema exibe a tela de locação. |
| V2 | O sistema apresenta os campos de cliente, veículo, período e forma de pagamento. |

##### **3.1.4 Pós-condição**

Tela de locação exibida e pronta para preenchimento.

#### **CT002 - Realizar locação com sucesso**

##### **3.1.1 Descrição**

O objetivo deste caso de teste é verificar se o sistema registra corretamente a locação quando todas as informações fornecidas são válidas.

##### **3.1.2 Pré-condição**

- Atendente autenticado.
- Cliente cadastrado no sistema.
- Cliente sem locação ativa.
- Veículo com status disponível.
- Veículo com menos de 80.000 km.
- Veículo com até 4 anos de uso.

##### **3.1.3 Procedimentos**

| Passo e Verificação | Descrição |
| ----- | ----- |
| P1 | O atendente acessa a tela de locação. |
| P2 | O atendente seleciona um cliente cadastrado. |
| V1 | O sistema verifica que o cliente não possui locação ativa. |
| P3 | O atendente seleciona um veículo disponível. |
| V2 | O sistema confirma a disponibilidade do veículo. |
| P4 | O atendente informa o período da locação e a forma de pagamento. |
| V3 | O sistema calcula o valor total e apresenta o resumo da locação. |
| P5 | O atendente confirma a locação. |
| V4 | O sistema registra a locação. |
| V5 | O sistema grava a quilometragem inicial do veículo. |
| V6 | O sistema altera o status do veículo para Alugado. |
| V7 | O sistema exibe mensagem de sucesso. |

##### **3.1.4 Pós-condição**

- Locação registrada com sucesso.
- Veículo indisponível para novas locações.
- Quilometragem inicial armazenada no sistema.

#### **CT003 - Validar cálculo da locação**

##### **3.1.1 Descrição**

O objetivo deste caso de teste é verificar se o sistema calcula corretamente o valor total da locação com base na quantidade de dias e no valor da diária.

##### **3.1.2 Pré-condição**

- Cliente elegível para locação.
- Veículo disponível e apto para locação.
- Valor da diária previamente cadastrado.

##### **3.1.3 Procedimentos**

| Passo e Verificação | Descrição |
| ----- | ----- |
| P1 | O atendente seleciona cliente e veículo válidos. |
| P2 | O atendente informa 3 dias de locação. |
| V1 | O sistema consulta o valor da diária do veículo. |
| V2 | O sistema calcula o valor total da locação. |
| V3 | O sistema apresenta o valor total de R$ 450,00 no resumo da operação. |

##### **3.1.4 Pós-condição**

Valor total da locação calculado corretamente e apresentado ao atendente.

### **3.2 Cenário: Cancelar Locação**

#### **CT004 - Cancelar locação**

##### **3.2.1 Descrição**

O objetivo deste caso de teste é verificar se o sistema encerra a operação quando o atendente opta por cancelar a locação antes da confirmação.

##### **3.2.2 Pré-condição**

- Atendente autenticado no sistema.
- Cliente cadastrado e elegível para locação.
- Veículo cadastrado e disponível para locação.
- Tela de locação aberta.
- Dados da locação em preenchimento.

##### **3.2.3 Procedimentos**

| Passo e Verificação | Descrição |
| ----- | ----- |
| P1 | O atendente acessa a tela de locação. |
| P2 | O atendente inicia o preenchimento da operação. |
| P3 | O atendente seleciona a opção Cancelar. |
| V1 | O sistema encerra a operação sem gravar a locação. |

##### **3.2.4 Pós-condição**

Nenhuma locação registrada no sistema.

### **3.3 Cenário: Cliente com Locação Ativa**

#### **CT005 - Bloqueio por locação ativa**

##### **3.3.1 Descrição**

O objetivo deste caso de teste é verificar se o sistema impede nova locação para cliente que já possui contrato em aberto.

##### **3.3.2 Pré-condição**

- Cliente cadastrado com uma locação ativa no sistema.
- Atendente autenticado.

##### **3.3.3 Procedimentos**

| Passo e Verificação | Descrição |
| ----- | ----- |
| P1 | O atendente acessa a tela de locação. |
| P2 | O atendente seleciona um cliente com locação ativa. |
| V1 | O sistema identifica a existência de contrato em aberto. |
| V2 | O sistema informa que o cliente já possui locação em aberto. |
| V3 | O sistema impede a conclusão da locação. |

##### **3.3.4 Pós-condição**

Nova locação não registrada.

### **3.4 Cenário: Veículo Não Apto para Locação**

#### **CT006 - Bloqueio por quilometragem acima do limite**

##### **3.4.1 Descrição**

O objetivo deste caso de teste é verificar se o sistema impede a locação de um veículo com quilometragem acima de 80.000 km.

##### **3.4.2 Pré-condição**

- Atendente autenticado no sistema.
- Veículo cadastrado com quilometragem superior a 80.000 km.
- Cliente apto para locação.

##### **3.4.3 Procedimentos**

| Passo e Verificação | Descrição |
| ----- | ----- |
| P1 | O atendente acessa a tela de locação. |
| P2 | O atendente seleciona um cliente elegível. |
| P3 | O atendente seleciona um veículo com 82.000 km. |
| V1 | O sistema verifica a quilometragem do veículo. |
| V2 | O sistema exibe a mensagem "Veículo indisponível para locação.". |
| V3 | O sistema impede a conclusão da locação. |

##### **3.4.4 Pós-condição**

Locação não registrada para o veículo selecionado.

#### **CT007 - Bloqueio por veículo com mais de 4 anos**

##### **3.4.1 Descrição**

O objetivo deste caso de teste é verificar se o sistema impede a locação de um veículo com mais de 4 anos de uso.

##### **3.4.2 Pré-condição**

- Atendente autenticado no sistema.
- Veículo cadastrado com mais de 4 anos de uso.
- Cliente apto para locação.

##### **3.4.3 Procedimentos**

| Passo e Verificação | Descrição |
| ----- | ----- |
| P1 | O atendente acessa a tela de locação. |
| P2 | O atendente seleciona um cliente elegível. |
| P3 | O atendente seleciona um veículo com mais de 4 anos de uso. |
| V1 | O sistema verifica o tempo de uso do veículo. |
| V2 | O sistema exibe a mensagem "Veículo indisponível para locação.". |
| V3 | O sistema impede a conclusão da locação. |

##### **3.4.4 Pós-condição**

Locação não registrada para o veículo selecionado.

## **4. Critérios de Aprovação**

O roteiro será considerado aprovado quando:

- Todos os casos de teste forem executados.
- Os resultados obtidos coincidirem com os resultados esperados.
- As regras de negócio da locação forem respeitadas.
- As mensagens de validação e bloqueio forem exibidas corretamente.
- O cálculo do valor da locação estiver correto.
- A quilometragem inicial for registrada ao concluir a locação.
- Nenhum erro crítico for identificado durante a execução dos testes.
