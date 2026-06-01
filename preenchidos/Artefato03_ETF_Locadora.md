Artefato 03
Plano de Teste
Especificação de Teste Funcional
Laboratório de Teste Artefato 03 (2ª Avaliação)

Estudo de Caso: Locadora de veículos
Nome do Projeto: Super Veículos
Grupo Nº 1

Autor(es) ou participantes:
Enzo Nardelli
Camila Bontempo Sidersky

Brasília - DF

# Especificação de Testes Funcionais

## 1.1 Plano de Testes Funcionais

### 1. Identificador do Plano de Teste

| LOCADORA-PTF-01 (Plano de Teste Funcional) |
| :---- |

### 2. Aspectos a Testar

| Número de Ordem | Item | Referência a Especificação de Teste |
| :---: | ----- | ----- |
| 1 | Efetuar Login | LOC-ETF-LOG |
| 2 | Cadastrar Funcionário | LOC-ETF-FUN |
| 3 | Cadastrar Cliente PF e PJ | LOC-ETF-CLI |
| 4 | Cadastrar Veículo e Acessórios | LOC-ETF-VEI |
| 5 | Controlar Disponibilidade de Veículo | LOC-ETF-DIS |
| 6 | Realizar Locação | LOC-ETF-LOC |
| 7 | Registrar Devolução | LOC-ETF-DEV |
| 8 | Emitir Relatórios Gerenciais | LOC-ETF-REL |

### 3. Abordagem

| Os testes serão executados de forma funcional, validando entradas, regras de negócio, exceções e saídas previstas no sistema da locadora. Serão realizados testes positivos, negativos, validações de campos obrigatórios, regras de negócio (locação única por cliente e bloqueios por quilometragem/idade do veículo), e testes de interface. Os testes serão executados em ambiente de homologação com base nos requisitos funcionais e não funcionais do projeto. |
| :---- |

### 4. Critérios de Completeza e Sucesso

| Número de ordem | Critério |
| :---: | ----- |
| 1 | Todos os casos de teste planejados devem ser executados |
| 2 | Resultado obtido deve corresponder ao resultado esperado |
| 3 | Mensagens de validação e erro devem ser exibidas corretamente |
| 4 | Dados devem ser persistidos corretamente |
| 5 | Regras de negócio devem ser respeitadas |
| 6 | Não deve haver cadastro duplicado de CPF, CNPJ, CNH e placa |

# Especificações dos Testes Funcionais

## 2.1 Especificação do teste - EFETUAR LOGIN

### 2.1.1 Identificador da Especificação de teste

| LOC-ETF-LOG |
| :---- |

### 2.1.2 Aspectos a serem testados

| Número | Requisito | Comentários |
| :---: | ----- | ----- |
| 1 | Autenticação de usuário | Validar login com credenciais válidas |
| 2 | Credenciais inválidas | Validar mensagem de falha |
| 3 | Controle de acesso | Validar permissão por perfil |

### 2.1.3 Detalhes da abordagem

| Deve existir ao menos um usuário válido para cada perfil operacional (Atendente, Gerente, Administrativo, Equipe de Frota). Deve existir ao menos um usuário com credencial inválida para teste negativo. |
| :---- |

### 2.1.4 Procedimentos de teste

| Número | Procedimento de teste | Identificação do procedimento de teste |
| :---: | ----- | ----- |
| 1 | Realizar login com sucesso | LOC-LOG-PT-01 |
| 2 | Tentar login inválido | LOC-LOG-PT-02 |

### 2.1.5 Casos de teste

| Número | Caso de teste | Identificação do caso de teste |
| :---: | ----- | ----- |
| 1 | Login válido | LOC-LOG-CT-01 |
| 2 | Login com senha incorreta | LOC-LOG-CT-02 |
| 3 | Login com usuário inexistente | LOC-LOG-CT-03 |

### 2.1.6 Critérios de completeza e sucesso

| Número | Critério |
| :---: | ----- |
| 1 | Sistema deve autenticar usuário válido |
| 2 | Sistema deve bloquear acesso inválido com mensagem adequada |

### 2.1.7 Especificação dos Casos de Teste

#### 2.1.7.1 Caso de teste: "Login válido"

| Identificação | LOC-LOG-CT-01 |
| :---- | :---- |
| **Objetivo** | Verificar se o login com credenciais válidas autentica o usuário com sucesso. |
| **Requisitos especiais** | Deve existir ao menos um usuário cadastrado no sistema com status ativo. |
| **Fluxo** | Acesse a tela de login do sistema. Preencha o campo Usuário com um login válido. Preencha o campo Senha com a senha correspondente. Clique em "Entrar". Verifique se o sistema redireciona para a tela inicial. |

#### 2.1.7.2 Caso de teste: "Login com senha incorreta"

| Identificação | LOC-LOG-CT-02 |
| :---- | :---- |
| **Objetivo** | Verificar se o sistema bloqueia o acesso e exibe mensagem de erro quando a senha informada é incorreta. |
| **Requisitos especiais** | Deve existir ao menos um usuário cadastrado no sistema com status ativo. |
| **Fluxo** | Acesse a tela de login do sistema. Preencha o campo Usuário com um login válido. Preencha o campo Senha com uma senha incorreta. Clique em "Entrar". Verifique se o sistema exibe a mensagem de erro e permanece na tela de login. |

#### 2.1.7.3 Caso de teste: "Login com usuário inexistente"

| Identificação | LOC-LOG-CT-03 |
| :---- | :---- |
| **Objetivo** | Verificar se o sistema bloqueia o acesso e exibe mensagem de erro quando o usuário informado não existe no cadastro. |
| **Requisitos especiais** | Deve-se utilizar um login que não esteja cadastrado no sistema. |
| **Fluxo** | Acesse a tela de login do sistema. Preencha o campo Usuário com um login inexistente. Preencha o campo Senha com qualquer valor. Clique em "Entrar". Verifique se o sistema exibe a mensagem de erro e permanece na tela de login. |

### 2.1.8 Especificação dos Casos de Teste

#### 2.1.8.1 Caso de teste: "Login válido"

| Identificação | LOC-LOG-CT-01 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Verificar se a autenticação com credenciais válidas ocorre com sucesso. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Usuário | atendente01 |
|  | Senha | Senha@123 |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Acesso concedido |
|  | Tela | Tela inicial do sistema |
| **Estado alcançado** | Usuário autenticado e sessão iniciada. |  |
| **Procedimentos** | LOC-LOG-PT-01 |  |

#### 2.1.8.2 Caso de teste: "Login com senha incorreta"

| Identificação | LOC-LOG-CT-02 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Verificar se o sistema bloqueia a autenticação quando a senha está incorreta. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Usuário | atendente01 |
|  | Senha | senhaerrada |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Usuário ou senha inválidos |
|  | Tela | Tela de login |
| **Estado alcançado** | Acesso negado e sessão não iniciada. |  |
| **Procedimentos** | LOC-LOG-PT-02 |  |

#### 2.1.8.3 Caso de teste: "Login com usuário inexistente"

| Identificação | LOC-LOG-CT-03 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Verificar se o sistema bloqueia a autenticação quando o usuário não existe. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Usuário | usuarionaoexiste |
|  | Senha | Senha@123 |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Usuário ou senha inválidos |
|  | Tela | Tela de login |
| **Estado alcançado** | Acesso negado e sessão não iniciada. |  |
| **Procedimentos** | LOC-LOG-PT-02 |  |

## 2.2 Especificação do teste - CADASTRAR FUNCIONÁRIO

### 2.2.1 Identificador da Especificação de teste

| LOC-ETF-FUN |
| :---- |

### 2.2.2 Aspectos a serem testados

| Número | Requisito | Comentários |
| :---: | ----- | ----- |
| 1 | Cadastro de funcionário | inserção com campos obrigatórios |
| 2 | Validação de CPF | Não permitir CPF duplicado |
| 3 | Atualização de dados | alteração de funcionário cadastrado |

### 2.2.3 Detalhes da abordagem

| Deve validar os campos CPF, nome, RG, endereço, telefone, gênero e data de nascimento. Realizar testes com dados completos, incompletos e duplicados. |
| :---- |

### 2.2.4 Procedimentos de teste

| Número | Procedimento de teste | Identificação do procedimento de teste |
| :---: | ----- | ----- |
| 1 | Inserir funcionário | LOC-FUN-PT-01 |
| 2 | Consultar funcionário | LOC-FUN-PT-02 |
| 3 | Alterar funcionário | LOC-FUN-PT-03 |

### 2.2.5 Casos de teste

| Número | Caso de teste | Identificação do caso de teste |
| :---: | ----- | ----- |
| 1 | Cadastro válido de funcionário | LOC-FUN-CT-01 |
| 2 | CPF duplicado | LOC-FUN-CT-02 |
| 3 | Campo obrigatório vazio | LOC-FUN-CT-03 |

### 2.2.6 Critérios de completeza e sucesso

| Número | Critério |
| :---: | ----- |
| 1 | Cadastro válido deve ser concluído com sucesso |
| 2 | CPF duplicado deve ser bloqueado |

### 2.2.7 Especificação dos Casos de Teste

#### 2.2.7.1 Caso de teste: "Cadastro válido de funcionário"

| Identificação | LOC-FUN-CT-01 |
| :---- | :---- |
| **Objetivo** | Verificar se o sistema cadastra um funcionário com dados válidos. |
| **Requisitos especiais** | Usuário autenticado com permissão de cadastro e CPF não cadastrado previamente. |
| **Fluxo** | Acesse a tela de cadastro de funcionário. Preencha CPF, nome, RG, endereço, telefone, gênero e data de nascimento. Clique em "Salvar". Verifique a mensagem de sucesso e a presença do registro na consulta. |

#### 2.2.7.2 Caso de teste: "CPF duplicado"

| Identificação | LOC-FUN-CT-02 |
| :---- | :---- |
| **Objetivo** | Verificar se o sistema impede cadastro de funcionário com CPF já existente. |
| **Requisitos especiais** | Deve existir ao menos um funcionário cadastrado com o CPF utilizado no teste. |
| **Fluxo** | Acesse a tela de cadastro de funcionário. Informe um CPF já cadastrado e demais campos válidos. Clique em "Salvar". Verifique mensagem de duplicidade e ausência de novo registro. |

#### 2.2.7.3 Caso de teste: "Campo obrigatório vazio"

| Identificação | LOC-FUN-CT-03 |
| :---- | :---- |
| **Objetivo** | Verificar se o sistema valida campos obrigatórios no cadastro de funcionário. |
| **Requisitos especiais** | Usuário autenticado com permissão de cadastro. |
| **Fluxo** | Acesse a tela de cadastro de funcionário. Deixe ao menos um campo obrigatório sem preenchimento. Clique em "Salvar". Verifique a mensagem de validação e a não gravação do registro. |

### 2.2.8 Especificação dos Casos de Teste

#### 2.2.8.1 Caso de teste: "Cadastro válido de funcionário"

| Identificação | LOC-FUN-CT-01 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Inserção de funcionário com todos os campos obrigatórios válidos. |  |
| **Entradas** | **Campo** | **Valor** |
|  | CPF | 12345678901 |
|  | Nome | João da Silva |
|  | RG | 1234567 |
|  | Endereço | Rua A, 100 |
|  | Telefone | 61999990000 |
|  | Gênero | Masculino |
|  | Data de nascimento | 10/10/1990 |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Funcionário cadastrado com sucesso |
|  | Registro | Disponível para consulta |
| **Estado alcançado** | Funcionário cadastrado no sistema. |  |
| **Procedimentos** | LOC-FUN-PT-01 |  |

#### 2.2.8.2 Caso de teste: "CPF duplicado"

| Identificação | LOC-FUN-CT-02 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Bloqueio de cadastro com CPF já existente. |  |
| **Entradas** | **Campo** | **Valor** |
|  | CPF | 12345678901 |
|  | Nome | Maria Souza |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | CPF já cadastrado |
|  | Registro | Não inserido |
| **Estado alcançado** | Cadastro rejeitado por duplicidade. |  |
| **Procedimentos** | LOC-FUN-PT-01 |  |

#### 2.2.8.3 Caso de teste: "Campo obrigatório vazio"

| Identificação | LOC-FUN-CT-03 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Validação de campos obrigatórios no cadastro. |  |
| **Entradas** | **Campo** | **Valor** |
|  | CPF |  |
|  | Nome | Carlos Lima |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Preencha os campos obrigatórios |
|  | Registro | Não inserido |
| **Estado alcançado** | Cadastro não concluído. |  |
| **Procedimentos** | LOC-FUN-PT-01 |  |

## 2.3 Especificação do teste - CADASTRAR CLIENTE (PF E PJ)

### 2.3.1 Identificador da Especificação de teste

| LOC-ETF-CLI |
| :---- |

### 2.3.2 Aspectos a serem testados

| Número | Requisito | Comentários |
| :---: | ----- | ----- |
| 1 | Cadastro de cliente PF | Validar campos de PF, incluindo CNH |
| 2 | Cadastro de cliente PJ | Validar campos de PJ |
| 3 | Validação de documentos | Impedir CPF/CNPJ/CNH duplicados |

### 2.3.3 Detalhes da abordagem

| Executar testes de cadastro PF e PJ com dados válidos e inválidos, validando regras de obrigatoriedade e unicidade documental. |
| :---- |

### 2.3.4 Procedimentos de teste

| Número | Procedimento de teste | Identificação do procedimento de teste |
| :---: | ----- | ----- |
| 1 | Inserir cliente PF | LOC-CLI-PT-01 |
| 2 | Inserir cliente PJ | LOC-CLI-PT-02 |
| 3 | Consultar cliente | LOC-CLI-PT-03 |

### 2.3.5 Casos de teste

| Número | Caso de teste | Identificação do caso de teste |
| :---: | ----- | ----- |
| 1 | Cadastro PF válido | LOC-CLI-CT-01 |
| 2 | Cadastro PJ válido | LOC-CLI-CT-02 |
| 3 | CPF/CNPJ já cadastrado | LOC-CLI-CT-03 |

### 2.3.6 Critérios de completeza e sucesso

| Número | Critério |
| :---: | ----- |
| 1 | Cadastros válidos devem ser persistidos |
| 2 | Duplicidade documental deve ser bloqueada |

### 2.3.7 Especificação dos Casos de Teste

#### 2.3.7.1 Caso de teste: "Cadastro PF válido"

| Identificação | LOC-CLI-CT-01 |
| :---- | :---- |
| **Objetivo** | Verificar cadastro de cliente pessoa física com dados válidos. |
| **Requisitos especiais** | Usuário autenticado e dados de CPF/CNH ainda não cadastrados. |
| **Fluxo** | Acesse cadastro de cliente. Selecione PF. Preencha nome, sexo, CPF, RG, data de nascimento, CNH e endereço. Clique em "Salvar". Verifique sucesso do cadastro. |

#### 2.3.7.2 Caso de teste: "Cadastro PJ válido"

| Identificação | LOC-CLI-CT-02 |
| :---- | :---- |
| **Objetivo** | Verificar cadastro de cliente pessoa jurídica com dados válidos. |
| **Requisitos especiais** | Usuário autenticado e CNPJ ainda não cadastrado. |
| **Fluxo** | Acesse cadastro de cliente. Selecione PJ. Preencha nome fantasia, razão social, CNPJ e endereço. Clique em "Salvar". Verifique sucesso do cadastro. |

#### 2.3.7.3 Caso de teste: "CPF/CNPJ já cadastrado"

| Identificação | LOC-CLI-CT-03 |
| :---- | :---- |
| **Objetivo** | Verificar bloqueio de cadastro quando documento já existe. |
| **Requisitos especiais** | Deve existir cliente previamente cadastrado com o CPF ou CNPJ informado. |
| **Fluxo** | Acesse cadastro de cliente. Informe documento já existente e demais campos válidos. Clique em "Salvar". Verifique mensagem de duplicidade e não inclusão. |

### 2.3.8 Especificação dos Casos de Teste

#### 2.3.8.1 Caso de teste: "Cadastro PF válido"

| Identificação | LOC-CLI-CT-01 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Cadastro de cliente pessoa física com dados obrigatórios válidos. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Tipo | PF |
|  | Nome | Ana Pereira |
|  | CPF | 98765432100 |
|  | CNH | 12345678910 |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Cliente cadastrado com sucesso |
|  | Registro | Disponível para consulta |
| **Estado alcançado** | Cliente PF cadastrado. |  |
| **Procedimentos** | LOC-CLI-PT-01 |  |

#### 2.3.8.2 Caso de teste: "Cadastro PJ válido"

| Identificação | LOC-CLI-CT-02 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Cadastro de cliente pessoa jurídica com dados válidos. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Tipo | PJ |
|  | Nome fantasia | Super Locações |
|  | CNPJ | 11222333000199 |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Cliente cadastrado com sucesso |
|  | Registro | Disponível para consulta |
| **Estado alcançado** | Cliente PJ cadastrado. |  |
| **Procedimentos** | LOC-CLI-PT-02 |  |

#### 2.3.8.3 Caso de teste: "CPF/CNPJ já cadastrado"

| Identificação | LOC-CLI-CT-03 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Validação de duplicidade de CPF/CNPJ/CNH. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Documento | 98765432100 |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Documento já cadastrado |
|  | Registro | Não inserido |
| **Estado alcançado** | Cadastro rejeitado por duplicidade documental. |  |
| **Procedimentos** | LOC-CLI-PT-01 |  |

## 2.4 Especificação do teste - CADASTRAR VEÍCULO E ACESSÓRIOS

### 2.4.1 Identificador da Especificação de teste

| LOC-ETF-VEI |
| :---- |

### 2.4.2 Aspectos a serem testados

| Número | Requisito | Comentários |
| :---: | ----- | ----- |
| 1 | Cadastro de veículo | Validar placa, chassi e dados técnicos |
| 2 | Cadastro de Acessórios | Associar Acessórios ao veículo |
| 3 | Duplicidade de dados | Bloquear placa/chassi duplicados |

### 2.4.3 Detalhes da abordagem

| Executar testes com frota inicial contendo veículos válidos e validar consistência dos dados técnicos e da lista de Acessórios. |
| :---- |

### 2.4.4 Procedimentos de teste

| Número | Procedimento de teste | Identificação do procedimento de teste |
| :---: | ----- | ----- |
| 1 | Inserir veículo | LOC-VEI-PT-01 |
| 2 | Associar Acessórios | LOC-VEI-PT-02 |
| 3 | Consultar veículo | LOC-VEI-PT-03 |

### 2.4.5 Casos de teste

| Número | Caso de teste | Identificação do caso de teste |
| :---: | ----- | ----- |
| 1 | Cadastro válido de veículo | LOC-VEI-CT-01 |
| 2 | Placa duplicada | LOC-VEI-CT-02 |
| 3 | Chassi duplicado | LOC-VEI-CT-03 |

### 2.4.6 Critérios de completeza e sucesso

| Número | Critério |
| :---: | ----- |
| 1 | Cadastro válido deve concluir sem erros |
| 2 | Placa ou chassi duplicado deve ser rejeitado |

### 2.4.7 Especificação dos Casos de Teste

#### 2.4.7.1 Caso de teste: "Cadastro válido de veículo"

| Identificação | LOC-VEI-CT-01 |
| :---- | :---- |
| **Objetivo** | Verificar cadastro de veículo com dados técnicos válidos. |
| **Requisitos especiais** | Usuário autenticado e placa/chassi não cadastrados previamente. |
| **Fluxo** | Acesse cadastro de veículo. Preencha placa, marca, modelo, chassi, cor, combustível, quilometragem e tipo de câmbio. Clique em "Salvar". Verifique cadastro concluído. |

#### 2.4.7.2 Caso de teste: "Placa duplicada"

| Identificação | LOC-VEI-CT-02 |
| :---- | :---- |
| **Objetivo** | Verificar bloqueio de cadastro de veículo com placa já existente. |
| **Requisitos especiais** | Deve existir veículo previamente cadastrado com a mesma placa. |
| **Fluxo** | Acesse cadastro de veículo. Informe uma placa já cadastrada com demais dados válidos. Clique em "Salvar". Verifique mensagem de duplicidade e bloqueio. |

#### 2.4.7.3 Caso de teste: "Chassi duplicado"

| Identificação | LOC-VEI-CT-03 |
| :---- | :---- |
| **Objetivo** | Verificar bloqueio de cadastro de veículo com chassi já existente. |
| **Requisitos especiais** | Deve existir veículo previamente cadastrado com o mesmo chassi. |
| **Fluxo** | Acesse cadastro de veículo. Informe chassi já cadastrado e demais dados válidos. Clique em "Salvar". Verifique mensagem de duplicidade e bloqueio. |

### 2.4.8 Especificação dos Casos de Teste

#### 2.4.8.1 Caso de teste: "Cadastro válido de veículo"

| Identificação | LOC-VEI-CT-01 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Cadastro de veículo com dados técnicos obrigatórios válidos. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Placa | ABC1D23 |
|  | Modelo | Onix |
|  | Chassi | 9BWZZZ377VT004251 |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Veículo cadastrado com sucesso |
|  | Registro | Disponível para consulta |
| **Estado alcançado** | Veículo cadastrado no sistema. |  |
| **Procedimentos** | LOC-VEI-PT-01 |  |

#### 2.4.8.2 Caso de teste: "Placa duplicada"

| Identificação | LOC-VEI-CT-02 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Validação de duplicidade da placa do veículo. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Placa | ABC1D23 |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Placa já cadastrada |
|  | Registro | Não inserido |
| **Estado alcançado** | Cadastro rejeitado por duplicidade de placa. |  |
| **Procedimentos** | LOC-VEI-PT-01 |  |

#### 2.4.8.3 Caso de teste: "Chassi duplicado"

| Identificação | LOC-VEI-CT-03 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Validação de duplicidade do chassi do veículo. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Chassi | 9BWZZZ377VT004251 |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Chassi já cadastrado |
|  | Registro | Não inserido |
| **Estado alcançado** | Cadastro rejeitado por duplicidade de chassi. |  |
| **Procedimentos** | LOC-VEI-PT-01 |  |

## 2.5 Especificação do teste - CONTROLAR DISPONIBILIDADE DE VEÍCULO

### 2.5.1 Identificador da Especificação de teste

| LOC-ETF-DIS |
| :---- |

### 2.5.2 Aspectos a serem testados

| Número | Requisito | Comentários |
| :---: | ----- | ----- |
| 1 | Atualização de status | Disponível, Alugado, Em negociação, Vendido |
| 2 | Regra por quilometragem | Bloqueio de locação acima de 80.000 km |
| 3 | Regra por tempo de uso | Bloqueio de locação acima de 4 anos |

### 2.5.3 Detalhes da abordagem

| Simular atualização de status da frota e validar bloqueios automáticos de disponibilidade para locação por regras de negócio. |
| :---- |

### 2.5.4 Procedimentos de teste

| Número | Procedimento de teste | Identificação do procedimento de teste |
| :---: | ----- | ----- |
| 1 | Atualizar status de veículo | LOC-DIS-PT-01 |
| 2 | Validar bloqueio por km | LOC-DIS-PT-02 |
| 3 | Validar bloqueio por idade | LOC-DIS-PT-03 |

### 2.5.5 Casos de teste

| Número | Caso de teste | Identificação do caso de teste |
| :---: | ----- | ----- |
| 1 | Atualização válida de status | LOC-DIS-CT-01 |
| 2 | Bloqueio por quilometragem | LOC-DIS-CT-02 |
| 3 | Bloqueio por tempo de uso | LOC-DIS-CT-03 |

### 2.5.6 Critérios de completeza e sucesso

| Número | Critério |
| :---: | ----- |
| 1 | Mudança de status deve refletir corretamente |
| 2 | Bloqueios por regras de frota devem ser aplicados |

### 2.5.7 Especificação dos Casos de Teste

#### 2.5.7.1 Caso de teste: "Atualização válida de status"

| Identificação | LOC-DIS-CT-01 |
| :---- | :---- |
| **Objetivo** | Verificar atualização de status de veículo para valores permitidos. |
| **Requisitos especiais** | Veículo cadastrado e usuário com permissão de gestão da frota. |
| **Fluxo** | Acesse a tela de frota. Selecione um veículo. Altere o status para "Em negociação" ou "Vendido". Salve a alteração e confirme na consulta. |

#### 2.5.7.2 Caso de teste: "Bloqueio por quilometragem"

| Identificação | LOC-DIS-CT-02 |
| :---- | :---- |
| **Objetivo** | Verificar bloqueio de disponibilidade para locação quando quilometragem excede 80.000 km. |
| **Requisitos especiais** | Veículo cadastrado com quilometragem superior a 80.000 km. |
| **Fluxo** | Acesse a tela de frota. Selecione veículo com quilometragem acima do limite. Tente marcar como "Disponível" para locação. Verifique bloqueio e mensagem de regra. |

#### 2.5.7.3 Caso de teste: "Bloqueio por tempo de uso"

| Identificação | LOC-DIS-CT-03 |
| :---- | :---- |
| **Objetivo** | Verificar bloqueio de disponibilidade para locação quando o veículo possui mais de 4 anos de uso. |
| **Requisitos especiais** | Veículo cadastrado com tempo de uso superior a 4 anos. |
| **Fluxo** | Acesse a tela de frota. Selecione veículo fora da regra de idade. Tente marcar como "Disponível" para locação. Verifique bloqueio e mensagem de regra. |

### 2.5.8 Especificação dos Casos de Teste

#### 2.5.8.1 Caso de teste: "Atualização válida de status"

| Identificação | LOC-DIS-CT-01 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Alteração de status de veículo para valores permitidos. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Veículo | ABC1D23 |
|  | Novo status | Em negociação |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Status atualizado com sucesso |
|  | Status | Em negociação |
| **Estado alcançado** | Status persistido corretamente. |  |
| **Procedimentos** | LOC-DIS-PT-01 |  |

#### 2.5.8.2 Caso de teste: "Bloqueio por quilometragem"

| Identificação | LOC-DIS-CT-02 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Regra de bloqueio por quilometragem acima de 80.000 km. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Quilometragem | 85000 |
|  | Status desejado | Disponível para locação |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Veículo indisponível por quilometragem |
|  | Status | Não disponível para locação |
| **Estado alcançado** | Disponibilização para locação bloqueada. |  |
| **Procedimentos** | LOC-DIS-PT-02 |  |

#### 2.5.8.3 Caso de teste: "Bloqueio por tempo de uso"

| Identificação | LOC-DIS-CT-03 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Regra de bloqueio por veículo com mais de 4 anos de uso. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Tempo de uso | 5 anos |
|  | Status desejado | Disponível para locação |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Veículo indisponível por tempo de uso |
|  | Status | Não disponível para locação |
| **Estado alcançado** | Disponibilização para locação bloqueada. |  |
| **Procedimentos** | LOC-DIS-PT-03 |  |

## 2.6 Especificação do teste - REALIZAR LOCAÇÃO

Corresponde ao Caso de Uso 006 - Realizar Locação de Veículo.

### 2.6.1 Identificador da Especificação de teste

| LOC-ETF-LOC |
| :---- |

### 2.6.2 Aspectos a serem testados

| Número | Requisito | Comentários |
| :---: | ----- | ----- |
| 1 | Registro de locação | Atendente seleciona cliente, veículo, período e pagamento |
| 2 | Regra de locação única | Cliente não pode ter 2 locações ativas |
| 3 | Cálculo do valor | Valor = dias x diária |
| 4 | Registro de km inicial | Quilometragem inicial deve ser armazenada |

### 2.6.3 Detalhes da abordagem

| Testar locações válidas e inválidas, verificando regras de cliente, disponibilidade do veículo, cálculo automático do valor e atualização do status do veículo. |
| :---- |

### 2.6.4 Procedimentos de teste

| Número | Procedimento de teste | Identificação do procedimento de teste |
| :---: | ----- | ----- |
| 1 | Realizar locação válida | LOC-LOC-PT-01 |
| 2 | Tentar locação com cliente ativo | LOC-LOC-PT-02 |
| 3 | Validar cálculo de valor | LOC-LOC-PT-03 |

### 2.6.5 Casos de teste

| Número | Caso de teste | Identificação do caso de teste |
| :---: | ----- | ----- |
| 1 | Locação concluída com sucesso | LOC-LOC-CT-01 |
| 2 | Bloqueio por locação simultânea | LOC-LOC-CT-02 |
| 3 | Bloqueio por veículo não apto | LOC-LOC-CT-03 |

### 2.6.6 Critérios de completeza e sucesso

| Número | Critério |
| :---: | ----- |
| 1 | Locação válida deve alterar status para Alugado |
| 2 | Sistema deve impedir segunda locação ativa para o mesmo cliente |
| 3 | Valor deve ser calculado corretamente |

### 2.6.7 Especificação dos Casos de Teste

#### 2.6.7.1 Caso de teste: "Locação concluída com sucesso"

| Identificação | LOC-LOC-CT-01 |
| :---- | :---- |
| **Objetivo** | Verificar registro de locação com cálculo correto e alteração de status do veículo. |
| **Requisitos especiais** | Cliente sem locação ativa e veículo apto para locação. |
| **Fluxo** | Acesse o módulo de locação. Selecione um cliente elegível. Selecione um veículo disponível. Informe o período da locação e a forma de pagamento. Confirme a operação. Verifique o cálculo do valor total, o registro da quilometragem inicial e a alteração do status para "Alugado". |

#### 2.6.7.2 Caso de teste: "Bloqueio por locação simultânea"

| Identificação | LOC-LOC-CT-02 |
| :---- | :---- |
| **Objetivo** | Verificar bloqueio de nova locação quando cliente já possui locação ativa. |
| **Requisitos especiais** | Cliente com locação ativa no sistema. |
| **Fluxo** | Acesse o módulo de locação. Selecione cliente com locação ativa. Tente concluir nova locação. Verifique bloqueio com mensagem de regra. |

#### 2.6.7.3 Caso de teste: "Bloqueio por veículo não apto"

| Identificação | LOC-LOC-CT-03 |
| :---- | :---- |
| **Objetivo** | Verificar bloqueio de locação para veículo fora das regras de disponibilidade. |
| **Requisitos especiais** | Veículo com quilometragem acima de 80.000 km ou mais de 4 anos de uso. |
| **Fluxo** | Acesse o módulo de locação. Selecione cliente elegível e veículo não apto. Tente confirmar locação. Verifique bloqueio e mensagem de regra. |

### 2.6.8 Especificação dos Casos de Teste

#### 2.6.8.1 Caso de teste: "Locação concluída com sucesso"

| Identificação | LOC-LOC-CT-01 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Registro de locação válida com cálculo do valor total. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Cliente | CPF 98765432100 |
|  | Veículo | ABC1D23 |
|  | Dias | 3 |
|  | Diária | 150,00 |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Valor total | 450,00 |
|  | Status do veículo | Alugado |
|  | Mensagem | Locação registrada com sucesso |
| **Estado alcançado** | Locação ativa criada e veículo indisponível para nova locação. |  |
| **Procedimentos** | LOC-LOC-PT-01 |  |

#### 2.6.8.2 Caso de teste: "Bloqueio por locação simultânea"

| Identificação | LOC-LOC-CT-02 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Regra de uma locação ativa por cliente. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Cliente | CPF com locação ativa |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Cliente já possui locação em aberto |
|  | Locação | Não criada |
| **Estado alcançado** | Nova locação bloqueada. |  |
| **Procedimentos** | LOC-LOC-PT-02 |  |

#### 2.6.8.3 Caso de teste: "Bloqueio por veículo não apto"

| Identificação | LOC-LOC-CT-03 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Regra de bloqueio para veículo fora dos limites de uso. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Veículo | km > 80000 ou uso > 4 anos |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Veículo não apto para locação |
|  | Locação | Não criada |
| **Estado alcançado** | Locação bloqueada por regra de disponibilidade. |  |
| **Procedimentos** | LOC-LOC-PT-02 |  |

## 2.7 Especificação do teste - REGISTRAR DEVOLUÇÃO

### 2.7.1 Identificador da Especificação de teste

| LOC-ETF-DEV |
| :---- |

### 2.7.2 Aspectos a serem testados

| Número | Requisito | Comentários |
| :---: | ----- | ----- |
| 1 | Registro de devolução | Encerrar locação ativa |
| 2 | Registro de km final | Quilometragem final obrigatória |
| 3 | Consistência de km | Km final não pode ser menor que km inicial |

### 2.7.3 Detalhes da abordagem

| Executar devolução com dados válidos e inválidos para garantir consistência e atualização da frota. |
| :---- |

### 2.7.4 Procedimentos de teste

| Número | Procedimento de teste | Identificação do procedimento de teste |
| :---: | ----- | ----- |
| 1 | Registrar devolução válida | LOC-DEV-PT-01 |
| 2 | Informar km final inválida | LOC-DEV-PT-02 |

### 2.7.5 Casos de teste

| Número | Caso de teste | Identificação do caso de teste |
| :---: | ----- | ----- |
| 1 | Devolução concluída com sucesso | LOC-DEV-CT-01 |
| 2 | Erro de quilometragem final | LOC-DEV-CT-02 |

### 2.7.6 Critérios de completeza e sucesso

| Número | Critério |
| :---: | ----- |
| 1 | Devolução válida deve encerrar locação |
| 2 | Km final inválida deve gerar erro e impedir encerramento |

### 2.7.7 Especificação dos Casos de Teste

#### 2.7.7.1 Caso de teste: "Devolução concluída com sucesso"

| Identificação | LOC-DEV-CT-01 |
| :---- | :---- |
| **Objetivo** | Verificar encerramento de locação com registro válido de quilometragem final. |
| **Requisitos especiais** | Deve existir locação ativa para o cliente/veículo. |
| **Fluxo** | Acesse o módulo de devolução. Selecione a locação ativa. Informe quilometragem final maior que a inicial. Confirme devolução e verifique encerramento da locação. |

#### 2.7.7.2 Caso de teste: "Erro de quilometragem final"

| Identificação | LOC-DEV-CT-02 |
| :---- | :---- |
| **Objetivo** | Verificar bloqueio quando quilometragem final é menor que a inicial. |
| **Requisitos especiais** | Deve existir locação ativa com quilometragem inicial registrada. |
| **Fluxo** | Acesse o módulo de devolução. Selecione locação ativa. Informe quilometragem final menor que a inicial. Tente confirmar e verifique mensagem de erro. |

### 2.7.8 Especificação dos Casos de Teste

#### 2.7.8.1 Caso de teste: "Devolução concluída com sucesso"

| Identificação | LOC-DEV-CT-01 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Encerramento da locação com quilometragem final válida. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Quilometragem inicial | 25000 |
|  | Quilometragem final | 25220 |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Devolução registrada com sucesso |
|  | Locação | Encerrada |
|  | Status do veículo | Disponível (se apto) |
| **Estado alcançado** | Locação encerrada e veículo atualizado. |  |
| **Procedimentos** | LOC-DEV-PT-01 |  |

#### 2.7.8.2 Caso de teste: "Erro de quilometragem final"

| Identificação | LOC-DEV-CT-02 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Validação da consistência entre quilometragem inicial e final. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Quilometragem inicial | 25000 |
|  | Quilometragem final | 24990 |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Quilometragem final inválida |
|  | Locação | Permanece ativa |
| **Estado alcançado** | Devolução não concluída por inconsistência de dados. |  |
| **Procedimentos** | LOC-DEV-PT-02 |  |

## 2.8 Especificação do teste - EMITIR RELATÓRIOS GERENCIAIS

### 2.8.1 Identificador da Especificação de teste

| LOC-ETF-REL |
| :---- |

### 2.8.2 Aspectos a serem testados

| Número | Requisito | Comentários |
| :---: | ----- | ----- |
| 1 | Emissão de relatórios | Clientes, veículos, locações e pagamentos |
| 2 | Filtros de consulta | Período, status e tipo de registro |
| 3 | Desempenho | Resposta de consulta em até 3 segundos |

### 2.8.3 Detalhes da abordagem

| Executar consultas com e sem dados para validar geração, consistência e mensagem de ausência de resultados. |
| :---- |

### 2.8.4 Procedimentos de teste

| Número | Procedimento de teste | Identificação do procedimento de teste |
| :---: | ----- | ----- |
| 1 | Emitir relatório com dados | LOC-REL-PT-01 |
| 2 | Emitir relatório sem dados | LOC-REL-PT-02 |

### 2.8.5 Casos de teste

| Número | Caso de teste | Identificação do caso de teste |
| :---: | ----- | ----- |
| 1 | Relatório com resultados | LOC-REL-CT-01 |
| 2 | Relatório sem resultados | LOC-REL-CT-02 |

### 2.8.6 Critérios de completeza e sucesso

| Número | Critério |
| :---: | ----- |
| 1 | Relatório deve apresentar dados corretos para filtros informados |
| 2 | Sistema deve informar quando não houver resultados |
| 3 | Tempo de resposta deve atender requisito de desempenho |

### 2.8.7 Especificação dos Casos de Teste

#### 2.8.7.1 Caso de teste: "Relatório com resultados"

| Identificação | LOC-REL-CT-01 |
| :---- | :---- |
| **Objetivo** | Verificar emissão de relatório com registros para os filtros selecionados. |
| **Requisitos especiais** | Deve existir base de dados com registros compatíveis com os filtros. |
| **Fluxo** | Acesse o módulo de relatórios. Selecione o tipo de relatório. Informe filtros válidos com dados existentes. Clique em "Gerar". Verifique a apresentação dos resultados. |

#### 2.8.7.2 Caso de teste: "Relatório sem resultados"

| Identificação | LOC-REL-CT-02 |
| :---- | :---- |
| **Objetivo** | Verificar comportamento do sistema quando não há dados para os filtros informados. |
| **Requisitos especiais** | Utilizar filtros sem registros correspondentes. |
| **Fluxo** | Acesse o módulo de relatórios. Selecione tipo de relatório e filtros sem dados. Clique em "Gerar". Verifique mensagem de ausência de resultados. |

### 2.8.8 Especificação dos Casos de Teste

#### 2.8.8.1 Caso de teste: "Relatório com resultados"

| Identificação | LOC-REL-CT-01 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Geração de relatório com retorno de dados. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Tipo | Locações |
|  | Período | 01/05/2026 a 31/05/2026 |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Resultado | Lista de registros encontrada |
|  | Tempo de resposta | Até 3 segundos |
| **Estado alcançado** | Relatório exibido com dados corretos. |  |
| **Procedimentos** | LOC-REL-PT-01 |  |

#### 2.8.8.2 Caso de teste: "Relatório sem resultados"

| Identificação | LOC-REL-CT-02 |  |
| :---- | ----- | ----- |
| **Itens a testar** | Geração de relatório sem retorno de dados para o filtro aplicado. |  |
| **Entradas** | **Campo** | **Valor** |
|  | Tipo | Pagamentos |
|  | Período | 01/01/2020 a 31/01/2020 |
| **Saídas esperadas** | **Campo** | **Valor** |
|  | Mensagem | Nenhum dado encontrado |
|  | Resultado | Lista vazia |
| **Estado alcançado** | Relatório processado com mensagem de ausência de dados. |  |
| **Procedimentos** | LOC-REL-PT-02 |  |



