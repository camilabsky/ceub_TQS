Teste e Qualidade de Software

Artefato 02

Especificação de Caso de Uso

# **Histórico da Revisão**

| Data | Versão | Descrição | Autor |
| :---: | :---: | :---: | :---: |
| 31/05/2026 | 1.0 | Elaboração do documento | Enzo e Camila |
| 31/05/2026 | 1.1 | Padronização do conteúdo | Enzo e Camila |
| 31/05/2026 | 1.2 | Revisão do Caso de Uso 006 | Enzo e Camila |
| 31/05/2026 | 1.3 | Versão final para entrega | Enzo e Camila |
| 31/05/2026 | 1.4 | Harmonização dos atores do UC006 (cliente como ator secundário) | Enzo e Camila |

# **Especificação de Caso de Uso**

## **Finalidade**

Este documento tem como finalidade descrever, com maior clareza, os casos de uso do sistema de gestão da locadora de veículos, com base no documento de levantamento de requisitos.

# **Caso de Uso 001**

## **Nome**

Efetuar Login

## **Descrição**

Este caso de uso descreve como ocorre o acesso de usuarios autorizados ao sistema da locadora.

## **Atores Envolvidos**

Atendente, Gerente, Administrativo, Equipe de Frota

## **Prototipo**

Nao se aplica.

## **Pre-condicoes**

- Estar com acesso a internet;
- Possuir usuario e senha cadastrados no sistema.

## **Pos-condicao**

- Usuario autenticado com acesso ao sistema conforme seu perfil;
- Em caso de falha, o sistema deve exibir mensagem informando o motivo.

# **Fluxos de Eventos**

## **Fluxo Basico**

1. Usuario acessa a tela de login.
2. Informa usuario e senha.
3. Clica em Entrar.
4. O sistema valida as credenciais.
5. O sistema redireciona para tela inicial.

## **Fluxos Alternativos**

1. Permissao negada.
1.1 Usuario informa credenciais invalidas.
1.2 O sistema exibe mensagem de erro e permanece na tela de login.

# **Relacionamento com Outros Casos de Usos**

## **Casos de Uso de Inclusao**

Nao possui.

## **Casos de Uso de Extensao**

Todos os demais casos de uso dependem de autenticacao.

# **Requisitos Especiais**

O sistema deve garantir que apenas usuarios autorizados acessem funcionalidades internas.

# **Cenarios**

| ID | Nome | Possiveis caminhos do caso de uso |  |  |
| :---- | ----- | ----- | :---- | :---- |
| C1 | Acesso ao sistema | Fluxo Basico |  |  |
| C2 | Falha no login | Fluxo Basico | Fluxo Alternativo 1 |  |

# **Caso de Uso 002**

## **Nome**

Cadastrar Funcionario

## **Descricao**

Este caso de uso descreve o cadastro de funcionarios da locadora com os dados obrigatorios.

## **Atores Envolvidos**

Administrativo, Gerente

## **Exemplo**

Cadastro contendo: CPF, nome, RG, endereco, telefone, genero e data de nascimento.

## **Pre-condicoes**

- Usuario autenticado;
- Usuario com permissao de cadastro.

## **Pos-condicao**

- Funcionario cadastrado com sucesso;
- Dados disponiveis para consulta e manutencao.

# **Fluxos de Eventos**

## **Fluxo Basico**

1. Acessar tela de cadastro de funcionarios.
2. Informar os dados obrigatorios.
3. Confirmar cadastro.
4. O sistema valida os dados.
5. O sistema registra o funcionario.

## **Fluxos Alternativos**

1. Dados invalidos ou incompletos.
1.1 O sistema identifica inconsistencia nos dados.
1.2 O sistema exibe mensagens de validacao.
1.3 O usuario corrige os campos e tenta novamente.

# **Relacionamento com Outros Casos de Usos**

## **Casos de Uso de Inclusao**

Efetuar Login

## **Casos de Uso de Extensao**

Consultar Funcionario

# **Requisitos Especiais**

O sistema deve impedir cadastro com CPF duplicado.

# **Cenarios**

| ID | Nome | Possiveis caminhos do caso de uso |  |  |
| :---- | ----- | ----- | :---- | :---- |
| C1 | Cadastro valido de funcionario | Fluxo Basico |  |  |
| C2 | Falha na validacao de dados | Fluxo Basico | Fluxo Alternativo 1 |  |

# **Caso de Uso 003**

## **Nome**

Cadastrar Cliente (PF e PJ)

## **Descricao**

Este caso de uso descreve o cadastro de clientes pessoa fisica e pessoa juridica.

## **Atores Envolvidos**

Atendente, Administrativo, Gerente

## **Exemplo**

- PF: nome, sexo, CPF, RG, data de nascimento, CNH e endereco.
- PJ: nome fantasia, razao social, CNPJ e endereco.

## **Pre-condicoes**

- Usuario autenticado;
- Usuario com permissao de cadastro.

## **Pos-condicao**

- Cliente cadastrado com sucesso;
- Cliente apto para processos de locacao.

# **Fluxos de Eventos**

## **Fluxo Basico**

1. Acessar tela de cadastro de clientes.
2. Selecionar tipo de cliente (PF ou PJ).
3. Informar os dados obrigatorios do tipo selecionado.
4. Confirmar cadastro.
5. O sistema valida e grava o cadastro.

## **Fluxos Alternativos**

1. Documento duplicado.
1.1 O sistema identifica CPF ou CNPJ ja cadastrado.
1.2 O sistema exibe mensagem e bloqueia gravacao.

# **Relacionamento com Outros Casos de Usos**

## **Casos de Uso de Inclusao**

Efetuar Login

## **Casos de Uso de Extensao**

Realizar Locacao

# **Requisitos Especiais**

O sistema deve impedir registros duplicados de CPF, CNPJ e CNH.

# **Cenarios**

| ID | Nome | Possiveis caminhos do caso de uso |  |  |
| :---- | ----- | ----- | :---- | :---- |
| C1 | Cadastro de cliente PF | Fluxo Basico |  |  |
| C2 | Cadastro de cliente PJ | Fluxo Basico |  |  |
| C3 | Documento ja existente | Fluxo Basico | Fluxo Alternativo 1 |  |

# **Caso de Uso 004**

## **Nome**

Cadastrar Veiculo e Acessorios

## **Descricao**

Este caso de uso descreve o cadastro de veiculos da frota, incluindo dados tecnicos e lista de acessorios.

## **Atores Envolvidos**

Equipe de Frota, Gerente

## **Prototipo**

Nao se aplica.

## **Pre-condicoes**

- Usuario autenticado;
- Usuario com permissao de gestao de frota.

## **Pos-condicao**

- Veiculo cadastrado com sucesso;
- Veiculo disponivel para analise de status e locacao.

# **Fluxos de Eventos**

## **Fluxo Basico**

1. Acessar tela de cadastro de veiculos.
2. Informar placa, marca, modelo, chassi, cor, combustivel, quilometragem e cambio.
3. Associar acessorios ao veiculo.
4. Confirmar cadastro.
5. O sistema registra o veiculo.

## **Fluxos Alternativos**

1. Placa ou chassi duplicados.
1.1 O sistema identifica duplicidade.
1.2 O sistema exibe mensagem e impede cadastro.

# **Relacionamento com Outros Casos de Usos**

## **Casos de Uso de Inclusao**

Efetuar Login

## **Casos de Uso de Extensao**

Controlar Disponibilidade de Veiculo

# **Requisitos Especiais**

O sistema deve impedir duplicidade de placa e chassi.

# **Cenarios**

| ID | Nome | Possiveis caminhos do caso de uso |  |  |
| :---- | ----- | ----- | :---- | :---- |
| C1 | Cadastro de veiculo com acessorios | Fluxo Basico |  |  |
| C2 | Falha por duplicidade | Fluxo Basico | Fluxo Alternativo 1 |  |

# **Caso de Uso 005**

## **Nome**

Controlar Disponibilidade de Veiculo

## **Descricao**

Este caso de uso descreve o controle de status da frota, indicando se o veiculo esta disponivel, alugado, em negociacao para venda ou vendido.

## **Atores Envolvidos**

Equipe de Frota, Atendente, Gerente

## **Exemplo**

Status possiveis: Disponivel, Alugado, Em negociacao para venda, Vendido.

## **Pre-condicoes**

- Veiculo cadastrado;
- Usuario autenticado.

## **Pos-condicao**

- Status do veiculo atualizado e visivel para consulta.

# **Fluxos de Eventos**

## **Fluxo Basico**

1. Acessar tela de frota.
2. Selecionar veiculo.
3. Atualizar status do veiculo.
4. Confirmar alteracao.
5. O sistema disponibiliza novo status para todos os perfis autorizados.

## **Fluxos Alternativos**

1. Veiculo indisponivel para locacao por regra de uso.
1.1 O sistema identifica veiculo com mais de 80.000 km ou mais de 4 anos de uso.
1.2 O sistema bloqueia status de Disponivel para locacao.

# **Relacionamento com Outros Casos de Usos**

## **Casos de Uso de Inclusao**

Cadastrar Veiculo e Acessorios

## **Casos de Uso de Extensao**

Realizar Locacao

# **Requisitos Especiais**

Veiculos com mais de 80.000 km ou mais de 4 anos de uso nao podem ser locados.

# **Cenarios**

| ID | Nome | Possiveis caminhos do caso de uso |  |  |
| :---- | ----- | ----- | :---- | :---- |
| C1 | Atualizacao de status valida | Fluxo Basico |  |  |
| C2 | Bloqueio por regra da frota | Fluxo Basico | Fluxo Alternativo 1 |  |

# **Caso de Uso 006**

## **Nome**

Realizar Locacao de Veiculo

## **Descricao**

Este caso de uso descreve o processo de locação de um veículo para cliente apto, incluindo prazo, forma de pagamento e registro da quilometragem inicial.

## **Atores Envolvidos**

- Ator primário: Atendente
- Ator secundário: Cliente (fornece dados para a locação, sem interação direta com o sistema)

## **Prototipo**

Nao se aplica.

## **Pré-condições**

- Cliente cadastrado;
- Veículo com status disponível;
- Cliente sem outra locação ativa;
- Veículo apto para locação conforme regras de quilometragem e tempo de uso.

## **Pós-condição**

- Locação registrada com sucesso;
- Status do veículo alterado para Alugado;
- Quilometragem inicial registrada.

# **Fluxos de Eventos**

## **Fluxo Básico**

1. Atendente acessa a tela de locação.
2. Atendente seleciona um cliente cadastrado.
3. Sistema verifica se o cliente não possui locação ativa.
4. Atendente seleciona um veículo disponível.
5. Atendente informa o período da locação e a forma de pagamento.
6. Sistema calcula o valor total e apresenta o resumo da locação.
7. Atendente confirma a locação.
8. Sistema registra a locação, a quilometragem inicial e altera o status do veículo para Alugado.

## **Fluxos Alternativos**

1. Cliente já possui locação ativa.
1.1 Sistema informa que o cliente já possui locação em aberto.
1.2 Sistema impede a conclusão da locação.

2. Veículo não apto para locação.
2.1 Sistema identifica violação de regra (km > 80.000 ou uso > 4 anos).
2.2 Sistema impede a conclusão da locação.

# **Relacionamento com Outros Casos de Usos**

## **Casos de Uso de Inclusão**

Efetuar Login

Cadastrar Cliente (PF e PJ)

Controlar Disponibilidade de Veículo

## **Casos de Uso de Extensão**

Registrar Devolução de Veículo

# **Requisitos Especiais**

- Deve existir no máximo uma locação ativa por cliente;
- O valor da locação deve ser calculado automaticamente.

# **Cenários**

| ID | Nome | Possiveis caminhos do caso de uso |  |  |
| :---- | ----- | ----- | :---- | :---- |
| C1 | Locação concluída com sucesso | Fluxo Básico |  |  |
| C2 | Bloqueio por locação ativa | Fluxo Básico | Fluxo Alternativo 1 |  |
| C3 | Bloqueio por regra da frota | Fluxo Básico | Fluxo Alternativo 2 |  |

# **Caso de Uso 007**

## **Nome**

Registrar Devolucao de Veiculo

## **Descricao**

Este caso de uso descreve o registro da devolucao do veiculo e a gravacao da quilometragem final para encerramento da locacao.

## **Atores Envolvidos**

Atendente, Cliente

## **Exemplo**

Registrar km final e encerrar contrato de locacao ativo.

## **Pre-condicoes**

- Existir locacao ativa para o cliente e veiculo.

## **Pos-condicao**

- Locacao encerrada;
- Quilometragem final registrada;
- Veiculo retorna para status disponivel (se apto).

# **Fluxos de Eventos**

## **Fluxo Basico**

1. Atendente localiza locacao ativa.
2. Informa quilometragem final do veiculo.
3. Sistema valida consistencia da quilometragem.
4. Sistema encerra locacao.
5. Sistema atualiza status do veiculo.

## **Fluxos Alternativos**

1. Quilometragem final invalida.
1.1 Sistema identifica valor menor que quilometragem inicial.
1.2 Sistema exibe erro e solicita correcao.

# **Relacionamento com Outros Casos de Usos**

## **Casos de Uso de Inclusao**

Realizar Locacao de Veiculo

## **Casos de Uso de Extensao**

Controlar Disponibilidade de Veiculo

# **Requisitos Especiais**

O sistema deve impedir registro de quilometragem final menor que a inicial.

# **Cenarios**

| ID | Nome | Possiveis caminhos do caso de uso |  |  |
| :---- | ----- | ----- | :---- | :---- |
| C1 | Devolucao registrada com sucesso | Fluxo Basico |  |  |
| C2 | Erro de quilometragem | Fluxo Basico | Fluxo Alternativo 1 |  |

# **Caso de Uso 008**

## **Nome**

Emitir Relatorios Gerenciais

## **Descricao**

Este caso de uso descreve a geracao de relatorios para apoio a gestao da locadora, incluindo dados de clientes, veiculos, locacoes e pagamentos.

## **Atores Envolvidos**

Gerente, Administrativo

## **Prototipo**

Nao se aplica.

## **Pre-condicoes**

- Usuario autenticado com permissao de acesso a relatorios;
- Existencia de dados cadastrados no sistema.

## **Pos-condicao**

- Relatorio emitido com as informacoes solicitadas.

# **Fluxos de Eventos**

## **Fluxo Basico**

1. Acessar modulo de relatorios.
2. Selecionar tipo de relatorio.
3. Informar filtros desejados.
4. Solicitar emissao.
5. Sistema gera e apresenta relatorio.

## **Fluxos Alternativos**

1. Nenhum dado encontrado.
1.1 Sistema informa ausencia de registros para os filtros escolhidos.

# **Relacionamento com Outros Casos de Usos**

## **Casos de Uso de Inclusao**

Efetuar Login

## **Casos de Uso de Extensao**

Nao possui.

# **Requisitos Especiais**

As consultas de relatorio devem ser processadas em ate 3 segundos em condicoes normais.

# **Cenarios**

| ID | Nome | Possiveis caminhos do caso de uso |  |  |
| :---- | ----- | ----- | :---- | :---- |
| C1 | Emissao de relatorio com dados | Fluxo Basico |  |  |
| C2 | Relatorio sem resultados | Fluxo Basico | Fluxo Alternativo 1 |  |
