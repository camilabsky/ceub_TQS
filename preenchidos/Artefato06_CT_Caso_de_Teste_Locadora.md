# Artefato 06 – Especificação de Casos de Teste

| Teste e Qualidade de Software  |
| :-: |
| **Documento de Especificação de Casos de Teste** |

**Laboratório de Teste – Artefato 06**

**Locadora de Veículos – Super Veículos**

| **Data da Implementação** | 31 de maio de 2026 |
| :---- | :---- |
| **Nome dos Responsáveis** | Enzo Nardelli Ribeiro, Camila Bontempo Sidersky – Grupo Nº 1 |
| **Doc ID** | LOC-CT-006/2026 |
| **Localização** | Laboratório de Teste – CEUB |
| **Versão do Documento** | 2.0 |

## Histórico de Revisão

| Data | Versão | Autor | Descrição |
| :---- | :---- | :---- | :---- |
| 31/05/2026 | 2.0 | Enzo Nardelli Ribeiro, Camila Bontempo Sidersky | Artefato 06 completo com 11 casos de teste (CT001-CT011). |
| 31/05/2026 | 1.0 | Enzo Nardelli Ribeiro, Camila Bontempo Sidersky | Versão inicial com estrutura base. |

## Revisores

| Nome | Papel | Data |
| :---- | :---- | :---- |
| Prof. Leonardo Pol | Professor Orientador | 31/05/2026 |

---

## Sumário

[1. Introdução](#introdução)  
[2. Matrizes de Rastreabilidade](#matrizes-de-rastreabilidade)  
[3. Casos de Teste](#casos-de-teste)  
[4. Critérios de Aprovação](#critérios-de-aprovação)

---

## 1. Introdução {#introdução}

Este documento apresenta os Casos de Teste derivados da Especificação de Casos de Uso (Artefato 02) e dos Requisitos Funcionais (Artefato 01) do Sistema de Gestão para Locadora de Veículos.

O objetivo é garantir a rastreabilidade entre requisitos, casos de uso e testes, assegurando que todas as funcionalidades definidas sejam devidamente validadas através de procedimentos sistemáticos de teste funcional.

---

## 2. Matrizes de Rastreabilidade {#matrizes-de-rastreabilidade}

### 2.1. Matriz de Rastreabilidade de Requisitos

| Especificação de Requisitos | ID dos Casos de Teste |
| :---- | :---- |
| RF006 – Cadastro Cliente PF | CT001 |
| RF007 – Cadastro Cliente PJ | CT002 |
| RF010 – Cadastro de Veículo | CT003 |
| RF012 – Consulta de Veículos | CT004 |
| RF014 – Realizar Locação | CT005 |
| RF016 – Registro Quilometragem Inicial | CT005 |
| RF017 – Registrar Devolução | CT006 |
| RF018 – Registro Quilometragem Final | CT006 |
| RF019 – Cálculo da Locação | CT007 |
| RF020 – Restrição de Locação Simultânea | CT008 |
| RF021 – Restrição de Quilometragem | CT009 |
| RF022 – Restrição por Tempo de Uso | CT010 |
| RF023 – Emissão de Relatórios | CT011 |

### 2.2. Matriz de Rastreabilidade de Casos de Uso

| ID dos Casos de Uso | ID dos Casos de Teste |
| :---- | :---- |
| UC01 – Cadastrar Cliente PF | CT001 |
| UC02 – Cadastrar Cliente PJ | CT002 |
| UC03 – Cadastrar Veículo | CT003 |
| UC04 – Consultar Veículos | CT004 |
| UC05 – Realizar Locação | CT005, CT007, CT008, CT009, CT010 |
| UC06 – Registrar Devolução | CT006 |
| UC07 – Emitir Relatórios | CT011 |

---

## 3. Casos de Teste {#casos-de-teste}

### 3.1. [CT001] – Cadastro de Cliente Pessoa Física

| **Descrição** | Validar o cadastro de cliente pessoa física. |
| :---- | :---- |
| **Pré-condição** | Usuário autenticado no sistema. |
| **Pós-condição** | Cliente pessoa física cadastrado com sucesso. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar menu "Clientes" |
| 02 | Selecionar "Novo Cliente PF" |
| 03 | Informar dados válidos (nome, CPF, endereço, telefone) |
| 04 | Confirmar cadastro |
| 05 | Sistema grava informações no banco de dados |
| 06 | Sistema exibe mensagem de sucesso |

---

### 3.2. [CT002] – Cadastro de Cliente Pessoa Jurídica

| **Descrição** | Validar cadastro de empresa (cliente pessoa jurídica). |
| :---- | :---- |
| **Pré-condição** | Usuário autenticado no sistema. |
| **Pós-condição** | Empresa cadastrada com sucesso. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar menu "Clientes" |
| 02 | Selecionar "Novo Cliente PJ" |
| 03 | Informar dados válidos (razão social, CNPJ, endereço, telefone) |
| 04 | Confirmar cadastro |
| 05 | Sistema grava informações no banco de dados |
| 06 | Sistema exibe mensagem de sucesso |

---

### 3.3. [CT003] – Cadastro de Veículo

| **Descrição** | Validar cadastro de veículo na frota. |
| :---- | :---- |
| **Pré-condição** | Usuário autenticado no sistema. |
| **Pós-condição** | Veículo disponível para operação na frota. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar menu "Frota" |
| 02 | Selecionar "Novo Veículo" |
| 03 | Informar dados válidos (marca, modelo, placa, quilometragem, ano de fabricação) |
| 04 | Confirmar cadastro |
| 05 | Sistema grava informações no banco de dados |
| 06 | Veículo aparece como disponível para locação |

---

### 3.4. [CT004] – Consulta de Veículos

| **Descrição** | Validar pesquisa de veículos disponíveis. |
| :---- | :---- |
| **Pré-condição** | Existir veículos cadastrados no sistema. |
| **Pós-condição** | Lista de veículos apresentada ao usuário com informações atualizadas. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar tela de "Consultar Veículos" |
| 02 | Informar filtros desejados (marca, modelo, disponibilidade) |
| 03 | Solicitar pesquisa |
| 04 | Sistema exibe lista de veículos que correspondem aos critérios |
| 05 | Cada veículo mostra status de disponibilidade |

---

### 3.5. [CT005] – Realizar Locação (Fluxo principal)

| **Descrição** | Validar processo completo de locação. |
| :---- | :---- |
| **Pré-condição** | Cliente sem locação ativa e veículo disponível no sistema. |
| **Pós-condição** | Locação registrada com sucesso no sistema. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar tela de "Nova Locação" |
| 02 | Selecionar cliente válido sem locação ativa |
| 03 | Selecionar veículo disponível |
| 04 | Informar data de retirada e devolução |
| 05 | Sistema calcula valor total |
| 06 | Atendente confirma locação |
| 07 | Sistema registra quilometragem inicial do veículo |
| 08 | Contrato de locação é gerado e impresso |

---

### 3.6. [CT006] – Registrar Devolução

| **Descrição** | Validar devolução do veículo com registro de quilometragem final. |
| :---- | :---- |
| **Pré-condição** | Locação ativa no sistema. |
| **Pós-condição** | Contrato encerrado e valores finalizados. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar tela de "Devolução de Veículo" |
| 02 | Localizar contrato de locação ativa |
| 03 | Registrar quilometragem final do veículo |
| 04 | Sistema calcula valores finais (multas, adicionais, etc.) |
| 05 | Sistema exibe resumo da devolução |
| 06 | Confirmar encerramento do contrato |

---

### 3.7. [CT007] – Validar Cálculo da Locação

| **Descrição** | Validar corretitude do cálculo automático de valor de locação. |
| :---- | :---- |
| **Pré-condição** | Locação em andamento. |
| **Pós-condição** | Valor calculado corretamente e exibido ao usuário. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Selecionar cliente válido |
| 02 | Selecionar veículo disponível |
| 03 | Informar diária de R$ 150,00 |
| 04 | Informar período de 5 dias |
| 05 | Confirmar locação |
| 06 | Sistema realiza cálculo automático (5 × 150 = 750) |
| 07 | Sistema apresenta valor total de R$ 750,00 |

---

### 3.8. [CT008] – Cliente com Locação Ativa

| **Descrição** | Validar restrição de múltiplas locações simultâneas. |
| :---- | :---- |
| **Pré-condição** | Cliente possui contrato de locação aberto. |
| **Pós-condição** | Operação bloqueada com mensagem de erro apropriada. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar tela de locação |
| 02 | Selecionar cliente com contrato ativo |
| 03 | Selecionar veículo disponível |
| 04 | Tentar confirmar nova locação |
| 05 | Sistema verifica contrato existente |
| 06 | Sistema bloqueia operação |
| 07 | Sistema exibe mensagem "Cliente já possui locação em aberto" |

---

### 3.9. [CT009] – Veículo Acima de 80.000 km

| **Descrição** | Validar bloqueio de locação por quilometragem elevada. |
| :---- | :---- |
| **Pré-condição** | Veículo cadastrado com 82.000 km. |
| **Pós-condição** | Operação bloqueada com mensagem apropriada. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar tela de locação |
| 02 | Selecionar veículo com quilometragem de 82.000 km |
| 03 | Tentar confirmar locação |
| 04 | Sistema verifica quilometragem do veículo |
| 05 | Sistema identifica quilometragem > 80.000 km |
| 06 | Sistema bloqueia operação |
| 07 | Sistema exibe mensagem "Veículo indisponível para locação" |

---

### 3.10. [CT010] – Veículo com Mais de 4 Anos

| **Descrição** | Validar bloqueio de locação por idade do veículo. |
| :---- | :---- |
| **Pré-condição** | Veículo com mais de 4 anos de uso (anterior a 2022). |
| **Pós-condição** | Operação bloqueada com mensagem apropriada. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar tela de locação |
| 02 | Selecionar veículo com mais de 4 anos de fabricação |
| 03 | Tentar confirmar locação |
| 04 | Sistema verifica data de fabricação do veículo |
| 05 | Sistema identifica idade > 4 anos |
| 06 | Sistema bloqueia operação |
| 07 | Sistema exibe mensagem "Veículo indisponível para locação" |

---

### 3.11. [CT011] – Emissão de Relatórios

| **Descrição** | Validar geração de relatórios do sistema. |
| :---- | :---- |
| **Pré-condição** | Existirem dados cadastrados (clientes, veículos, locações). |
| **Pós-condição** | Relatório gerado com sucesso. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar menu "Relatórios" |
| 02 | Selecionar tipo de relatório (locações, clientes, frota) |
| 03 | Informar filtros (período, cliente, veículo) se necessário |
| 04 | Solicitar emissão do relatório |
| 05 | Sistema gera relatório em formato PDF ou Excel |
| 06 | Sistema exibe relatório para visualização ou download |

---

## 4. Critérios de Aprovação {#critérios-de-aprovação}

O sistema será considerado **aprovado** quando:

- Todos os casos de teste (CT001 a CT011) forem executados com sucesso;
- Todos os resultados obtidos coincidirem com os resultados esperados;
- Nenhuma regra de negócio for violada durante a execução;
- Não existirem defeitos críticos ou bloqueantes;
- Todos os requisitos funcionais (RF006 a RF023) estiverem cobertos e validados pelos testes;
- As restrições de negócio (locação simultânea, quilometragem, idade do veículo) estiverem funcionando corretamente;
- Os cálculos de locação forem precisos e sem erros.

---

**Documento preparado para fins acadêmicos – Disciplina de Teste e Qualidade de Software (TQSW)**

**Professor: Leonardo Pol**

**Autores: Enzo Nardelli Ribeiro e Camila Bontempo Sidersky – Grupo Nº 1**
