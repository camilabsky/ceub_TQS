

![][image1]

**Artefato 01**  
**Requisitos do Sistema**  
**Disciplina: Teste e Qualidade de Software Prof. Leonardo Pol**

**Levantamento de Requisitos**

Alunos Participantes: Enzo Nardelli Ribeiro

                               Camila Bontempo Sidersky  
                 
                    

| Versão: |  1.1 |
| ----- | :---- |
| Data: |  01 /06/2026      |
|  |  |
|  |  |
|  |  |

|  |  Documento de levantamento de requisitos do sistema da locadora.  |  |  |
| :---- | :---: | :---- | :---- |
| Cliente: | Locadora de Veículos | Projeto: | Super Veículos |
| Assunto:  | Levantamento de requisitos | Sistema: | Sistema de Gestão para Locadora de Veículos |
| Responsável:  | Grupo Nº 1 | Status:  | Finalizado |

1. **Introdução**

   1. Propósito

Este documento especifica os requisitos do sistema de gestão de uma locadora de veículos, com foco em agilizar o atendimento aos clientes e melhorar os processos internos da empresa. O software permitirá controle centralizado de funcionários, clientes, frota, locações e vendas, reduzindo falhas operacionais e aumentando a confiabilidade das informações.

2. Público Alvo

Equipe de atendimento da locadora, setor administrativo, gerência, responsáveis pelo cadastro de clientes e funcionários, e equipe responsável pela operação de locação e venda dos veículos.

3. Escopo

A locadora de veículos necessita de um sistema para facilitar o atendimento a seus clientes e tornar os processos realizados na empresa mais ágeis. Para controle dos funcionários, o sistema precisa registrar os dados do funcionário, como CPF, nome, RG, endereço do funcionário, telefone, gênero e data de nascimento. Clientes a serem gerenciados devem ser do tipo pessoa física e pessoa jurídica, e para pessoa física deve ser informado nome, sexo, CPF, RG, data nascimento, dados da CNH e endereço. Para pessoa jurídica deve ser registrado nome fantasia, razão social, CNPJ e endereço. A frota da empresa deve ter as informações de placa do veículo, marca, modelo, chassi, cor, combustível, quilometragem e tipo de câmbio. O carro deve possuir sua lista de acessórios para complementar o veículo e facilitar a consulta do veículo no perfil desejável pelo cliente. O sistema deve informar quais carros estão disponíveis para locação, quais estão em negociação para venda ou quais já foram vendidos. No ato da locação o cliente deve escolher o veículo, informar a quantidade de dias na qual ficará com o veículo e a forma de pagamento. O cliente só poderá efetuar a locação de um veículo por vez, não existindo a possibilidade de existir mais de um veículo alugado em seu nome ao mesmo tempo. Após selecionar o veículo, deve ser registrada a quilometragem inicial do veículo na locação, ou seja, a quilometragem atual do veículo e no ato da entrega deve ser registrada a quilometragem final, ou seja, a quilometragem no momento da entrega. O pagamento do aluguel será a quantidade de dias vezes o valor da diária. A frota não pode ser disponibilizada para locação quando o veículo ultrapassar os 80.000 km rodados ou 4 anos de uso.  

2. # **Visão Geral do Produto**

O sistema será utilizado no ambiente da locadora para automatizar o ciclo completo de cadastro, consulta, locação, devolução e controle da frota. A plataforma apoiará a tomada de decisão com dados atualizados sobre disponibilidade de veículos, histórico de locações e situação da frota.

Entrada

\- Dados de funcionários

\- Dados de clientes Pessoa Física

\- Dados de clientes Pessoa Jurídica

\- Dados dos veículos

\- Lista de acessórios

\- Quantidade de dias de locação

\- Quilometragem inicial e final

\- Forma de pagamento

Saída

\- Situação do veículo (disponível, em negociação, vendido)

\- Contrato e valor da locação

\- Histórico de locações por cliente

\- Relatórios de controle da frota

\- Relatórios de quilometragem e tempo de uso

1. ## Descrição dos usuários

   

Atendente

\- Realiza cadastro de clientes e consulta disponibilidade de veículos.

\- Registra processos de locação e devolução.

Gerente

\- Acessa todas as informações operacionais do sistema.

\- Acompanha relatórios de frota, locações e vendas.

Administrativo

\- Realiza cadastro e manutenção dos dados de funcionários.

\- Mantém dados cadastrais gerais do sistema.

Cliente

\- Informa dados para cadastro e seleciona veículo para locação.

\- Define período de locação e forma de pagamento.

Equipe de frota

\- Atualiza status dos veículos e dados técnicos da frota.

\- Registra quilometragem e controla restrições de disponibilidade.

3. # **Requisitos Funcionais**

**Exemplos** 

3.1\<RF001\>\<Autenticação de Usuários\>

O sistema deverá permitir que usuários realizem login utilizando usuário e senha. 

3.2\<RF002\>\<Cadastro de Funcionários\>

O sistema deverá permitir cadastrar funcionários contendo:

* CPF;  
* Nome;  
* RG;  
* Endereço;  
* Telefone;  
* Gênero;  
* Data de nascimento.

3.3\<RF003\>\<Consulta de Funcionários\>

O sistema deverá permitir consultar funcionários cadastrados. 

3.4\<RF004\>\<Alteração de Funcionários\>

O sistema deverá permitir alterar dados de funcionários cadastrados. 

3.5\<RF005\>\<Exclusão de Funcionários\>

O sistema deverá permitir excluir funcionários cadastrados. 

3.6\<RF006\>\<Cadastro de Cliente Pessoa Física\> 

O sistema deverá permitir cadastrar clientes pessoa física contendo:

* Nome;  
* Sexo;  
* CPF;  
* RG;  
* Data de nascimento;  
* Dados da CNH;  
* Endereço.

3.7\<RF007\>\<Cadastro de Cliente Pessoa Jurídica\>

O sistema deverá permitir cadastrar clientes pessoa jurídica contendo:

* Nome fantasia;  
* Razão social;  
* CNPJ;  
* Endereço.

3.8\<RF008\>\<Consulta de Clientes\>

O sistema deverá permitir consultar clientes cadastrados. 

3.9\<RF009\>\<Alteração de Clientes\>

O sistema deverá permitir alterar dados de clientes cadastrados.

3.10\<RF010\>\<Cadastro de Veículos\>

O sistema deverá permitir cadastrar veículos contendo:

* Placa;  
* Marca;  
* Modelo;  
* Chassi;  
* Cor;  
* Combustível;  
* Quilometragem;  
* Tipo de câmbio.

3.11\<RF011\>\<Cadastro de Acessórios\>

O sistema deverá permitir associar acessórios aos veículos. 

3.12\<RF012\>\<Consulta de Veículos\>

O sistema deverá permitir consultar veículos cadastrados. 

3.13\<RF013\>\<Controle de Disponibilidade\>

O sistema deverá informar se o veículo está:

* Disponível;  
* Alugado;  
* Em negociação para venda;  
* Vendido.

3.14\<RF014\>\<Realizar Locação\>

O sistema deverá permitir registrar uma locação de veículo. 

3.15\<RF015\>\<Seleção de Forma de Pagamento\>

O sistema deverá permitir informar a forma de pagamento da locação. 

3.16\<RF016\>\<Registro de Quilometragem Inicial\>

O sistema deverá registrar a quilometragem inicial do veículo no momento da locação. 

3.17\<RF017\>\<Registro de Devolução \>

O sistema deverá permitir registrar a devolução do veículo. 

3.18\<RF018\>\<Registro de Quilometragem Final \>

O sistema deverá registrar a quilometragem final do veículo no momento da devolução. 

3.19\<RF019\>\<Cálculo do Valor da Locação \>

O sistema deverá calcular automaticamente o valor da locação utilizando:

Valor Total \= Quantidade de Dias × Valor da Diária 

3.20\<RF020\>\<Restrição de Locação Simultânea \>

O sistema deverá impedir que um cliente possua mais de uma locação ativa simultaneamente. 

3.21\<RF021\>\<Restrição por Quilometragem \>

O sistema deverá impedir a locação de veículos com quilometragem superior a 80.000 km. 

3.22\<RF022\>\<Restrição por Tempo de Uso \>

O sistema deverá impedir a locação de veículos com mais de 4 anos de uso. 

3.23\<RF023\>\<Emissão de Relatórios \>

O sistema deverá gerar relatórios gerenciais sobre:

* Clientes;  
* Veículos;  
* Locações;  
* Pagamentos.

4. # **Requisitos Não Funcionais**

   **Exemplos:**

   

1. Segurança: Monitorará os caminhões via satélite, fará backup dos dados automaticamente, além de pedir usuário e senha fará um reconhecimento do usuário através de impressão digital.  
     
2. Performance: As telas terão um tempo de resposta estimado em 20s, tanto em consulta em banco de dados quanto em outros dados solicitados pelo usuário.  
     
     
3. Usabilidade: Descreve os requisitos não-funcionais associados à facilidade de uso do sistema.  
     
4. Confiabilidade: executará uma busca para detectar duplicidade nos dados, erros no sistema, não proibirá o usuário de cadastrar uma determinada quantidade de clientes, avisa aos usuários do sistema quando houver um atraso na entrega da mercadoria, quando tiver mudanças na rota dos veículos, pois cada veículo terá um chip de identificação.  
     
     
5. Padrões: Terá padrão ANSI e ISO 9001\.  
     
6. Hardware e Software: Funcionará com Windows 98/2000/NT/XP e Linux, o computador tem que ter no mínimo 2GB de memória RAM, um HDD 120GB, placa de rede, placa de vídeo, processador Pentium 4, deverá ter um servidor para disponibilizar o software para mais de um usuário.

   1. ## \<RNF001\>\<Segurança \>

*O acesso ao sistema deverá ocorrer mediante autenticação por usuário e senha.* 

2. ## \<RNF002\>\<Controle de Acesso \>

*Cada usuário deverá possuir permissões compatíveis com seu perfil.* 

3. ## \<RNF003\>\<Integridade dos Dados \>

*O sistema deverá validar informações obrigatórias antes da gravação.* 

4. ## \<RNF004\>\<Desempenho \>

*As consultas deverão ser processadas em até 3 segundos em condições normais de uso.* 

5. ## \<RNF005\>\<Disponibilidade \>

*O sistema deverá possuir disponibilidade mínima de 99% durante o horário comercial.* 

6. ## \<RNF006\>\<Usabilidade \>

*A interface deverá ser intuitiva e de fácil utilização pelos funcionários.* 

7. ## \<RNF007\>\<Backup \>

*O sistema deverá realizar backup diário das informações armazenadas.* 

8. ## \<RNF008\>\<Compatibilidade \>

*O sistema deverá funcionar nos principais navegadores modernos.* 

9. ## \<RNF009\>\<Confiabilidade \>

*O sistema deverá impedir registros duplicados de CPF, CNPJ, CNH e Placa.* 

10. ## \<RNF010\>\<Manutenibilidade \>

*O sistema deverá permitir futuras atualizações sem comprometer as funcionalidades existentes.* 

[image1]: <data:image/png;base64,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>