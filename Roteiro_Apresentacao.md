# Roteiro de Apresentação — Super Veículos
**Teste e Qualidade de Software | Prof. Leonardo Pol | Grupo Nº 1**
**Enzo Nardelli Ribeiro & Camila Bontempo Sidersky**
**Duração: até 50 minutos**

---

## SLIDE 1 — Capa

**O que escrever no slide:**
> Super Veículos — Pacote de Testes  
> Sistema de Gestão para Locadora de Veículos  
> Enzo Nardelli Ribeiro | Camila Bontempo Sidersky — Grupo Nº 1  
> Teste e Qualidade de Software — Prof. Leonardo Pol  
> Junho de 2026

**O que falar:**
Bom dia/boa tarde professor. Somos o Grupo Nº 1, Enzo e Camila. Hoje vamos apresentar o pacote completo de artefatos de teste desenvolvido para o sistema Super Veículos, um sistema de gestão de locadora de veículos. Ao longo da apresentação vamos percorrer os seis artefatos produzidos, explicando as decisões tomadas e como eles se conectam entre si.

---

## SLIDE 2 — Visão Geral do Processo

**O que escrever no slide:**
```
Requisitos (A01)
      ↓
Casos de Uso (A02)
      ↓
Plano de Teste (A03)
      ↓
Cenários de Teste (A04)
      ↓
Roteiro de Execução (A05)
      ↓
Casos de Teste (A06)
```

**O que falar:**
O trabalho segue o fluxo clássico de teste de software. Partimos do levantamento de requisitos, modelamos os casos de uso, planejamos os testes, definimos os cenários, detalhamos o roteiro de execução e finalizamos com a especificação dos casos de teste. Cada artefato alimenta o próximo, garantindo rastreabilidade de ponta a ponta. Vamos seguir essa ordem na apresentação.

---

## SLIDE 3 — Artefato 01: Contexto do Sistema

**O que escrever no slide:**
> **Sistema:** Super Veículos — Gestão de Locadora  
> **Problema resolvido:** Controle centralizado de funcionários, clientes, frota e locações  
> **Usuários do sistema:**  
> - Atendente  
> - Gerente  
> - Administrativo  
> - Equipe de Frota

**O que falar:**
O sistema Super Veículos foi criado para digitalizar e centralizar os processos de uma locadora de veículos. Antes do sistema, o controle era manual e sujeito a erros. O sistema atende quatro perfis de usuário, cada um com permissões diferentes: o Atendente realiza locações e cadastros de clientes, o Gerente acessa relatórios e tem visão geral, o Administrativo cuida do cadastro de funcionários, e a Equipe de Frota gerencia os veículos.

---

## SLIDE 4 — Artefato 01: Requisitos Funcionais

**O que escrever no slide:**
| ID | Funcionalidade |
|---|---|
| RF001 | Autenticação de Usuários |
| RF002–RF005 | CRUD de Funcionários |
| RF006–RF009 | CRUD de Clientes (PF e PJ) |
| RF010–RF013 | CRUD de Veículos e Disponibilidade |
| RF014–RF016 | Realizar Locação |
| RF017–RF018 | Registrar Devolução |
| RF019 | Cálculo Automático: Dias × Diária |
| RF020 | Restrição: 1 locação ativa por cliente |
| RF021 | Bloqueio: km > 80.000 |
| RF022 | Bloqueio: uso > 4 anos |
| RF023 | Emissão de Relatórios |

**O que falar:**
Foram levantados 23 requisitos funcionais. Para facilitar a visualização, agrupamos por tema. As regras de negócio mais críticas são a RF019 — cálculo automático do valor da locação como Dias multiplicado pelo valor da diária —, a RF020 — que impede um cliente de ter duas locações ativas ao mesmo tempo —, e as RF021 e RF022, que bloqueiam a locação de veículos com mais de 80.000 quilômetros rodados ou com mais de 4 anos de uso. Essas quatro regras são as que mais geraram casos de teste.

---

## SLIDE 5 — Artefato 01: Requisitos Não Funcionais

**O que escrever no slide:**
| ID | Categoria | Requisito |
|---|---|---|
| RNF001 | Segurança | Autenticação por usuário e senha |
| RNF002 | Controle de Acesso | Permissões por perfil |
| RNF003 | Integridade | Validação antes de gravar |
| RNF004 | Desempenho | Consultas em até 3 segundos |
| RNF005 | Disponibilidade | 99% no horário comercial |
| RNF006 | Usabilidade | Interface intuitiva |
| RNF007 | Backup | Backup diário automático |
| RNF008 | Compatibilidade | Navegadores modernos |
| RNF009 | Confiabilidade | Sem CPF/CNPJ/CNH/Placa duplicados |
| RNF010 | Manutenibilidade | Atualizações sem impacto |

**O que falar:**
Além dos funcionais, definimos 10 requisitos não funcionais. Os mais relevantes para os testes são o RNF004 — desempenho com resposta em até 3 segundos —, o RNF008 — compatibilidade com navegadores —, e o RNF009 — que impede duplicidade de documentos como CPF, CNPJ, CNH e placa. No Artefato 03, descrevemos como esses três RNFs seriam testados mesmo em um contexto teórico.

---

## SLIDE 6 — Artefato 02: Casos de Uso — Visão Geral

**O que escrever no slide:**
| UC | Nome | Ator Principal |
|---|---|---|
| UC001 | Efetuar Login | Atendente, Gerente, Administrativo, Equipe de Frota |
| UC002 | Cadastrar Funcionário | Administrativo, Gerente |
| UC003 | Cadastrar Cliente (PF e PJ) | Atendente |
| UC004 | Cadastrar Veículo e Acessórios | Equipe de Frota, Gerente |
| UC005 | Controlar Disponibilidade | Equipe de Frota |
| UC006 | **Realizar Locação** | **Atendente** (Cliente: secundário) |
| UC007 | Registrar Devolução | Atendente |
| UC008 | Emitir Relatórios | Gerente |

**O que falar:**
O Artefato 02 modela os 8 casos de uso do sistema. Um ponto importante é o UC006, Realizar Locação: definimos o Atendente como ator primário, pois é ele quem opera o sistema. O Cliente é ator secundário — ele fornece os dados verbalmente ao atendente, mas não interage diretamente com o sistema. Essa distinção é importante para alinhar os testes à realidade do processo.

---

## SLIDE 7 — Artefato 02: UC006 em Detalhe

**O que escrever no slide:**
**UC006 — Realizar Locação**

**Pré-condições:**
- Cliente cadastrado e sem locação ativa
- Veículo disponível, apto (km ≤ 80.000 e uso ≤ 4 anos)

**Fluxo básico:** Atendente seleciona cliente → seleciona veículo → informa período e pagamento → sistema calcula valor → confirma → sistema registra km inicial e altera status para "Alugado"

**Exceções:**
- Cliente com locação ativa → bloqueio
- Veículo fora das regras → bloqueio

**O que falar:**
O UC006 é o caso de uso central do sistema e por isso recebeu atenção especial nos artefatos 04 e 05. As pré-condições são rigorosas: o cliente não pode ter outra locação em aberto e o veículo precisa estar dentro dos limites de quilometragem e tempo de uso. O fluxo básico termina com o sistema registrando a quilometragem inicial — dado essencial para o cálculo final na devolução. Dois fluxos de exceção bloqueiam a operação quando as regras de negócio não são atendidas.

---

## SLIDE 8 — Artefato 03: Plano de Teste

**O que escrever no slide:**
**Identificador:** LOCADORA-PTF-01

**8 funcionalidades planejadas para teste:**
1. Efetuar Login
2. Cadastrar Funcionário
3. Cadastrar Cliente PF e PJ
4. Cadastrar Veículo e Acessórios
5. Controlar Disponibilidade
6. Realizar Locação
7. Registrar Devolução
8. Emitir Relatórios

**Abordagem:** testes positivos, negativos, validação de campos e regras de negócio

**O que falar:**
O Artefato 03 é o plano de teste funcional. Ele define o escopo — as 8 funcionalidades que serão testadas — e a abordagem adotada. Para cada funcionalidade, testamos o fluxo feliz, o fluxo de erro e as validações de campos obrigatórios. Os critérios de sucesso exigem que todos os casos de teste sejam executados, que os resultados batam com o esperado, e que nenhuma duplicidade de documentos seja permitida.

---

## SLIDE 9 — Artefato 03: Massa de Dados e Testes Não Funcionais

**O que escrever no slide:**
**Massa de dados padronizada (usada em todos os artefatos):**

| Entidade | Valor Válido | Valor Inválido |
|---|---|---|
| CPF | 987.654.321-00 | 111.111.111-11 |
| CNPJ | 11.222.333/0001-99 | 00.000.000/0000-00 |
| Placa | ABC1D23 | ABC-1234 |
| Quilometragem | 25.000 km | 82.000 km |
| Locação | 3 dias × R$ 150,00 = **R$ 450,00** | — |

**Testes não funcionais (teóricos):**
- RNF004: relatório com 1.000 registros → tempo ≤ 3s
- RNF008: CT001 e CT005 nos navegadores Chrome, Firefox e Edge
- RNF009: cadastro com CPF duplicado → segundo bloqueado

**O que falar:**
Um cuidado importante que tomamos foi padronizar a massa de dados usada em todos os artefatos. Isso garante que quando o CT003 do A04 cita "3 dias a R$150", o CT007 do A06 usa exatamente os mesmos valores. A quilometragem de bloqueio é 82.000 km em todo o pacote. Para os testes não funcionais, descrevemos como cada um seria executado em teoria, já que o sistema não está implementado — esse é um requisito de completude do plano.

---

## SLIDE 10 — Artefato 04: Cenários de Teste (UC006)

**O que escrever no slide:**
**Escopo:** UC006 — Realizar Locação de Veículo

| Cenário | Caso de Teste | Situação |
|---|---|---|
| Cenário 1 | CT001 | Abrir tela de locação |
| Cenário 1 | CT002 | Locação realizada com sucesso |
| Cenário 1 | CT003 | Cálculo: 3 dias × R$ 150 = R$ 450 |
| Cenário 2 | CT004 | Cancelar antes de confirmar |
| Cenário 3 | CT005 | Bloqueio: cliente com locação ativa |
| Cenário 4 | CT006 | Bloqueio: veículo com 82.000 km |
| Cenário 4 | CT007 | Bloqueio: veículo com mais de 4 anos |

**O que falar:**
O Artefato 04 foca especificamente no UC006 porque ele é o processo mais complexo e crítico do sistema. A técnica usada foi o levantamento dos fluxos de eventos — básico e alternativos — e o cruzamento desses caminhos para derivar os cenários. Chegamos a 4 cenários e 7 casos de teste. O CT003 valida a regra de cálculo: 3 dias multiplicado por R$150 deve resultar em exatamente R$450. Qualquer desvio nesse resultado seria um defeito.

---

## SLIDE 11 — Artefato 05: Roteiro de Execução

**O que escrever no slide:**
**Identificador:** LOC-RTF-001/2026  
**Escopo:** UC006 — Realizar Locação de Veículo

**Exemplo — CT002: Locação com sucesso**

| Passo/Verificação | Ação |
|---|---|
| P1 | Atendente acessa a tela de locação |
| P2 | Atendente seleciona cliente cadastrado |
| V1 | Sistema confirma: cliente sem locação ativa |
| P3 | Atendente seleciona veículo disponível |
| V2 | Sistema confirma: veículo apto |
| P4 | Atendente informa período e forma de pagamento |
| V3 | Sistema calcula valor total e exibe resumo |
| P5 | Atendente confirma |
| V4–V7 | Locação registrada, km inicial gravado, status → Alugado, mensagem de sucesso |

**O que falar:**
O Artefato 05 transforma os cenários em um roteiro passo a passo que um testador consegue seguir sem conhecer o sistema. Cada passo é uma ação do testador e cada verificação é o que o sistema deve responder. Padronizamos as pré-condições em todos os casos de teste de locação: o atendente precisa estar autenticado, o cliente cadastrado e o veículo disponível. Essa padronização evita ambiguidade na execução.

---

## SLIDE 12 — Artefato 06: Rastreabilidade (Matriz RF)

**O que escrever no slide:**
**De RF001 a RF023 — todos cobertos:**

| RFs | CTs correspondentes |
|---|---|
| RF001 | CT012 — Login Válido |
| RF002–RF005 | CT013–CT016 — CRUD Funcionários |
| RF006–RF007 | CT001–CT002 — Cadastro de Clientes |
| RF008–RF009 | CT017–CT018 — Consulta e Alteração |
| RF010–RF013 | CT003–CT004, CT019, CT020 |
| RF014–RF016 | CT005 — Realizar Locação |
| RF015 | CT021 — Forma de Pagamento |
| RF017–RF018 | CT006 — Registrar Devolução |
| RF019 | CT007 — Cálculo do Valor |
| RF020–RF022 | CT008–CT010 — Restrições |
| RF023 | CT011 — Relatórios |

**O que falar:**
A matriz de rastreabilidade é a prova de que nenhum requisito ficou sem teste. O artefato 06 na versão final tem 21 casos de teste, cobrindo todos os 23 requisitos funcionais. Requisitos como RF001, RF002 a RF005, RF008, RF009, RF011, RF013 e RF015 não tinham cobertura na versão anterior — foram adicionados nesta revisão exatamente para fechar essa lacuna.

---

## SLIDE 13 — Artefato 06: Exemplos de Casos de Teste

**O que escrever no slide:**
**CT001 — Cadastro de Cliente PF**
- Campos: nome, **sexo, CPF, RG, data de nascimento, CNH** e endereço (todos obrigatórios conforme RF006)

**CT005 — Realizar Locação (fluxo principal)**
- Passo 08 corrigido: sistema altera status para "Alugado" *(removida referência à impressão de contrato — funcionalidade não prevista em requisito)*

**CT007 — Validar Cálculo**
- 3 dias × R$ 150,00 = **R$ 450,00** *(alinhado com A03, A04 e A05)*

**CT010 — Bloqueio por Tempo de Uso**
- Pré-condição: veículo com ano de fabricação **2020** *(valor fixo, sem ambiguidade)*

**O que falar:**
Quatro ajustes importantes foram feitos nos casos de teste. Primeiro, o CT001 agora lista todos os campos obrigatórios do RF006, inclusive sexo, RG, data de nascimento e CNH, que estavam ausentes. Segundo, o CT005 teve removido o passo de impressão de contrato, que não existe em nenhum requisito. Terceiro, o CT007 foi corrigido de 5 dias para 3 dias, alinhando com todos os outros artefatos. E o CT010 passou a usar um ano fixo de fabricação — 2020 — em vez de uma referência relativa que mudaria com o tempo.

---

## SLIDE 14 — Encerramento

**O que escrever no slide:**
**Resumo do pacote entregue:**

| Artefato | Conteúdo |
|---|---|
| A01 | 23 RFs + 10 RNFs |
| A02 | 8 Casos de Uso |
| A03 | Plano de Teste — 8 funcionalidades + testes NF teóricos |
| A04 | 4 Cenários + 7 CTs para UC006 |
| A05 | Roteiro de execução passo a passo para UC006 |
| A06 | 21 Casos de Teste — cobertura RF001–RF023 |

**Rastreabilidade garantida: Requisito → Caso de Uso → Plano → Cenário → Roteiro → Caso de Teste**

**O que falar:**
Para encerrar, o pacote entregue cobre o ciclo completo de teste. Partimos de 23 requisitos funcionais, modelamos 8 casos de uso, planejamos 8 funcionalidades para teste, derivamos 7 cenários focados no processo principal, detalhamos o roteiro de execução e finalizamos com 21 casos de teste rastreados. Todos os requisitos têm ao menos um caso de teste correspondente. Ficamos à disposição para perguntas.

---

*Apresentação — Teste e Qualidade de Software | CEUB | Junho 2026*
