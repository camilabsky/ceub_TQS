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
| 01/06/2026 | 2.1 | Enzo Nardelli Ribeiro, Camila Bontempo Sidersky | Inclusão de cobertura de RF001-RF005, RF008, RF009, RF011, RF013 e RF015. Ajustes de consistência entre artefatos. |
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
| RF001 – Autenticação de Usuários | CT012 |
| RF002 – Cadastro de Funcionários | CT013 |
| RF003 – Consulta de Funcionários | CT014 |
| RF004 – Alteração de Funcionários | CT015 |
| RF005 – Exclusão de Funcionários | CT016 |
| RF006 – Cadastro Cliente PF | CT001 |
| RF007 – Cadastro Cliente PJ | CT002 |
| RF008 – Consulta de Clientes | CT017 |
| RF009 – Alteração de Clientes | CT018 |
| RF010 – Cadastro de Veículo | CT003 |
| RF011 – Cadastro de Acessórios | CT019 |
| RF012 – Consulta de Veículos | CT004 |
| RF013 – Controle de Disponibilidade | CT020 |
| RF014 – Realizar Locação | CT005 |
| RF015 – Seleção de Forma de Pagamento | CT021 |
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
| UC00 – Efetuar Login | CT012 |
| UC00 – Gerenciar Funcionários | CT013, CT014, CT015, CT016 |
| UC01 – Cadastrar Cliente PF | CT001 |
| UC02 – Cadastrar Cliente PJ | CT002 |
| UC02 – Consultar/Alterar Clientes | CT017, CT018 |
| UC03 – Cadastrar Veículo | CT003 |
| UC03 – Cadastrar Acessórios | CT019 |
| UC04 – Consultar Veículos | CT004 |
| UC04 – Controlar Disponibilidade | CT020 |
| UC05 – Realizar Locação | CT005, CT007, CT008, CT009, CT010 |
| UC05 – Selecionar Forma de Pagamento | CT021 |
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
| 03 | Informar dados válidos obrigatórios (nome, sexo, CPF, RG, data de nascimento, CNH e endereço) |
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
| 03 | Informar dados válidos obrigatórios (nome fantasia, razão social, CNPJ e endereço) |
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
| 08 | Sistema altera o status do veículo para "Alugado" |

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
| 04 | Sistema valida registro da devolução e encerra a locação |
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
| 04 | Informar período de 3 dias |
| 05 | Confirmar locação |
| 06 | Sistema realiza cálculo automático (3 × 150 = 450) |
| 07 | Sistema apresenta valor total de R$ 450,00 |

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
| **Pré-condição** | Veículo com ano de fabricação 2020 (mais de 4 anos de uso). |
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

### 3.12. [CT012] – Login Válido

| **Descrição** | Validar autenticação com credenciais corretas. |
| :---- | :---- |
| **Pré-condição** | Usuário ativo cadastrado no sistema. |
| **Pós-condição** | Usuário autenticado e sessão iniciada. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar tela de login |
| 02 | Informar usuário válido |
| 03 | Informar senha correta |
| 04 | Clicar em "Entrar" |
| 05 | Sistema valida credenciais |
| 06 | Sistema redireciona para tela inicial |

---

### 3.13. [CT013] – Cadastro de Funcionário com Sucesso

| **Descrição** | Validar cadastro de funcionário com dados obrigatórios. |
| :---- | :---- |
| **Pré-condição** | Usuário autenticado com permissão administrativa. |
| **Pós-condição** | Funcionário cadastrado e disponível para consulta. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar menu "Funcionários" |
| 02 | Selecionar "Novo Funcionário" |
| 03 | Informar CPF, nome, RG, endereço, telefone, gênero e data de nascimento |
| 04 | Confirmar cadastro |
| 05 | Sistema grava os dados |
| 06 | Sistema exibe mensagem de sucesso |

---

### 3.14. [CT014] – Consulta de Funcionário por CPF

| **Descrição** | Validar busca de funcionário por CPF cadastrado. |
| :---- | :---- |
| **Pré-condição** | Funcionário previamente cadastrado no sistema. |
| **Pós-condição** | Dados do funcionário exibidos corretamente. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar menu "Funcionários" |
| 02 | Selecionar opção "Consultar" |
| 03 | Informar CPF válido cadastrado |
| 04 | Solicitar pesquisa |
| 05 | Sistema localiza o funcionário |
| 06 | Sistema exibe os dados correspondentes |

---

### 3.15. [CT015] – Alteração de Dados de Funcionário

| **Descrição** | Validar alteração de dados cadastrais de funcionário. |
| :---- | :---- |
| **Pré-condição** | Funcionário previamente cadastrado e usuário autorizado. |
| **Pós-condição** | Dados alterados com sucesso no sistema. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar menu "Funcionários" |
| 02 | Localizar funcionário por CPF |
| 03 | Alterar campo endereço |
| 04 | Confirmar alteração |
| 05 | Sistema persiste os novos dados |
| 06 | Sistema exibe mensagem de atualização concluída |

---

### 3.16. [CT016] – Exclusão de Funcionário

| **Descrição** | Validar exclusão de funcionário cadastrado. |
| :---- | :---- |
| **Pré-condição** | Funcionário cadastrado e sem vínculo impeditivo. |
| **Pós-condição** | Funcionário marcado como excluído/inativo. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar menu "Funcionários" |
| 02 | Localizar funcionário alvo |
| 03 | Selecionar opção "Excluir" |
| 04 | Confirmar operação |
| 05 | Sistema executa exclusão lógica do registro |
| 06 | Sistema informa exclusão com sucesso |

---

### 3.17. [CT017] – Consulta de Cliente

| **Descrição** | Validar consulta de clientes PF/PJ cadastrados. |
| :---- | :---- |
| **Pré-condição** | Cliente previamente cadastrado. |
| **Pós-condição** | Cliente exibido conforme filtro informado. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar menu "Clientes" |
| 02 | Selecionar opção "Consultar" |
| 03 | Informar filtro por CPF ou CNPJ |
| 04 | Solicitar pesquisa |
| 05 | Sistema retorna os dados do cliente |

---

### 3.18. [CT018] – Alteração de Endereço do Cliente

| **Descrição** | Validar alteração de endereço de cliente cadastrado. |
| :---- | :---- |
| **Pré-condição** | Cliente cadastrado e usuário autorizado. |
| **Pós-condição** | Endereço atualizado no cadastro do cliente. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar menu "Clientes" |
| 02 | Localizar cliente por CPF/CNPJ |
| 03 | Editar campo endereço |
| 04 | Confirmar alteração |
| 05 | Sistema salva o novo endereço |
| 06 | Sistema apresenta mensagem de atualização concluída |

---

### 3.19. [CT019] – Cadastro de Acessório em Veículo

| **Descrição** | Validar associação de acessório a veículo cadastrado. |
| :---- | :---- |
| **Pré-condição** | Veículo previamente cadastrado no sistema. |
| **Pós-condição** | Acessório vinculado ao veículo com sucesso. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar menu "Frota" |
| 02 | Selecionar veículo existente |
| 03 | Selecionar opção "Adicionar acessório" |
| 04 | Informar acessório válido |
| 05 | Confirmar inclusão |
| 06 | Sistema registra vínculo do acessório ao veículo |

---

### 3.20. [CT020] – Controle de Disponibilidade do Veículo

| **Descrição** | Validar atualização e consulta do status de disponibilidade. |
| :---- | :---- |
| **Pré-condição** | Veículo cadastrado com status inicial conhecido. |
| **Pós-condição** | Status atualizado e refletido na consulta de veículos. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar menu "Frota" |
| 02 | Selecionar veículo cadastrado |
| 03 | Alterar status para "Em negociação" |
| 04 | Confirmar alteração |
| 05 | Sistema atualiza o status |
| 06 | Consulta de veículos reflete novo status |

---

### 3.21. [CT021] – Seleção de Forma de Pagamento na Locação

| **Descrição** | Validar seleção de forma de pagamento no processo de locação. |
| :---- | :---- |
| **Pré-condição** | Cliente elegível e veículo apto para locação. |
| **Pós-condição** | Forma de pagamento registrada junto à locação. |

| Passo | Verificação |
| :---- | :---- |
| 01 | Acessar tela de "Nova Locação" |
| 02 | Selecionar cliente e veículo válidos |
| 03 | Informar período da locação |
| 04 | Selecionar forma de pagamento (cartão, dinheiro ou PIX) |
| 05 | Confirmar operação |
| 06 | Sistema registra a forma de pagamento escolhida |

---

## 4. Critérios de Aprovação {#critérios-de-aprovação}

O sistema será considerado **aprovado** quando:

- Todos os casos de teste (CT001 a CT021) forem executados com sucesso;
- Todos os resultados obtidos coincidirem com os resultados esperados;
- Nenhuma regra de negócio for violada durante a execução;
- Não existirem defeitos críticos ou bloqueantes;
- Todos os requisitos funcionais (RF001 a RF023) estiverem cobertos e validados pelos testes;
- As restrições de negócio (locação simultânea, quilometragem, idade do veículo) estiverem funcionando corretamente;
- Os cálculos de locação forem precisos e sem erros.

---

**Documento preparado para fins acadêmicos – Disciplina de Teste e Qualidade de Software (TQSW)**

**Professor: Leonardo Pol**

**Autores: Enzo Nardelli Ribeiro e Camila Bontempo Sidersky – Grupo Nº 1**
