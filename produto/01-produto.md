# 🧩 DPP — Parte 1: Produto
> **[NOME DO PROJETO]** — Versão `1.0` | Status: `Em Elaboração`

> 🧭 **Responsável por este arquivo:** Assessores de Produtos · **Valida:** Gerente de Produtos
> 🌿 **Branch de preenchimento:** `dpp/<ano>-<cliente>/produto` (ver `MANUAL-GIT.md`)
>
> ⚡ **Prioridade de preenchimento:** as seções 3 (Escopo) e 4 (Funcionalidades — ao menos a lista de IDs) destravam o trabalho paralelo de Design e Desenvolvimento. Preencha-as primeiro.

---

## 📌 Sumário

1. [Visão Geral do Projeto](#1-visão-geral-do-projeto)
2. [Stakeholders e Usuários](#2-stakeholders-e-usuários)
3. [Escopo do Projeto](#3-escopo-do-projeto)
4. [Funcionalidades Requeridas](#4-funcionalidades-requeridas)
5. [DON'Ts — O que NÃO será feito](#5-donts--o-que-não-será-feito)
6. [Regras de Negócio](#6-regras-de-negócio)
7. [Riscos e Premissas de Negócio](#7-riscos-e-premissas-de-negócio)
8. [Glossário de Negócio](#8-glossário-de-negócio)

---

## 1. Visão Geral do Projeto

### 1.1 Problema a Ser Resolvido

> Descreva com clareza o problema central que esse projeto resolve. Foque no problema, não na solução. Responda: **o que dói hoje para o cliente/usuário?**

```
[Exemplo: O cliente gerencia os agendamentos dos clientes via WhatsApp e planilhas,
o que gera conflitos de horário, perda de informações e experiência ruim para o usuário final.]
```

### 1.2 Objetivo do Projeto

> Descreva **o que** será entregue e **por quê**. Evite descrever o "como".

```
[Exemplo: Desenvolver uma plataforma web de agendamentos online que permita ao
cliente gerenciar sua agenda e aos usuários finais marcar serviços de forma autônoma.]
```

### 1.3 Objetivo de Negócio (Resultado Esperado)

> Qual métrica de sucesso o cliente espera mover com esse projeto?

| Métrica                        | Situação Atual | Meta             |
|-------------------------------|----------------|-----------------|
| [Ex: Tempo médio de agendamento] | [Ex: 15 min]  | [Ex: < 2 min]   |
| [Ex: Conflitos de horário/mês]   | [Ex: ~10]     | [Ex: 0]         |

### 1.4 Contexto e Motivação

> Background do cliente, mercado em que atua, e por que o projeto é relevante agora.

```
[Descreva o contexto do negócio do cliente, histórico relevante e o que motivou
a contratação deste projeto neste momento.]
```

---

## 2. Stakeholders e Usuários

### 2.1 Stakeholders

| Nome / Papel             | Responsabilidade no Projeto              | Contato          |
|--------------------------|------------------------------------------|-----------------|
| [Ex: João — Dono do negócio] | Aprovação final e validação de requisitos | joao@email.com  |
| [Ex: Maria — Gerente]       | Ponto focal para dúvidas de negócio      | maria@email.com |

### 2.2 Perfis de Usuário (Personas)

> Liste os tipos de usuário que vão interagir com o sistema.
> ⚠️ Nenhuma persona deve ser preenchida sem a participação dos assessores de Design.

#### Persona 1: [Nome da Persona]
- **Quem é:** [Ex: Atendente da recepção, 25-40 anos, baixa familiaridade com tecnologia]
- **Objetivo principal:** [Ex: Visualizar e confirmar agendamentos do dia]
- **Frustração atual:** [Ex: Precisa consultar 3 ferramentas diferentes para ver a agenda]
- **Permissões no sistema:** [Ex: Admin / Operador / Leitura]

#### Persona 2: [Nome da Persona]
- **Quem é:** [...]
- **Objetivo principal:** [...]
- **Frustração atual:** [...]
- **Permissões no sistema:** [...]

---

## 3. Escopo do Projeto

> O escopo define as fronteiras do projeto. É a "lei" do que entra e o que não entra. Ambiguidades de escopo são a principal causa de retrabalho.

### 3.1 O que ESTÁ no escopo

```
✅ [Módulo ou funcionalidade 1] — [breve descrição]
✅ [Módulo ou funcionalidade 2] — [breve descrição]
✅ [Módulo ou funcionalidade 3] — [breve descrição]
✅ [Módulo ou funcionalidade 4] — [breve descrição]
```

### 3.2 Entregáveis do Projeto

| Entregável                       | Descrição                              | Responsável       |
|----------------------------------|----------------------------------------|------------------|
| [Ex: Código-fonte do backend]    | API REST documentada e testada         | Time de Dev      |
| [Ex: Código-fonte do frontend]   | Interface web responsiva               | Time de Dev      |
| [Ex: Banco de dados configurado] | Scripts de migration e seed            | Time de Dev      |
| [Ex: Documentação de deploy]     | README com instruções de configuração  | Tech Lead        |

### 3.3 Módulos do Sistema

> Mapa visual das grandes áreas do sistema. Detalhe em seções seguintes.

```
Sistema [Nome]
│
├── Módulo de Autenticação
│   ├── Login / Logout
│   └── Recuperação de senha
│
├── Módulo de [Nome]
│   ├── [Funcionalidade A]
│   └── [Funcionalidade B]
│
└── Módulo de [Nome]
    ├── [Funcionalidade A]
    └── [Funcionalidade B]
```

---

## 4. Funcionalidades Requeridas

> Cada funcionalidade deve responder: **O que faz? Para quem? Qual o critério de aceite?**
> Prioridade: `P0` = Bloqueante (MVP) | `P1` = Importante | `P2` = Desejável
>
> ⚠️ Os IDs `F0X` definidos aqui são referenciados pelos documentos de Design, Backend e Frontend. **Nunca renumere uma funcionalidade já publicada** — se uma for removida, mantenha o ID aposentado.

---

### 4.1 [Nome do Módulo — ex: Autenticação]

#### F01 — [Nome da Funcionalidade — ex: Login de usuário]

| Campo               | Descrição                                               |
|---------------------|---------------------------------------------------------|
| **Prioridade**      | P0                                                      |
| **Usuário(s)**      | [Persona(s) que usa essa funcionalidade]                |
| **Descrição**       | [O que a funcionalidade faz em linguagem clara]         |
| **Fluxo principal** | [Passo a passo do caminho feliz]                        |
| **Fluxos alternativos** | [O que acontece se der errado, e-mail não encontrado, senha incorreta etc.] |

**Critérios de Aceite:**
- [ ] Dado que `[contexto]`, quando `[ação]`, então `[resultado esperado]`
- [ ] Dado que `[contexto]`, quando `[ação]`, então `[resultado esperado]`
- [ ] Dado que `[contexto]`, quando `[ação]`, então `[resultado esperado]`

---

#### F02 — [Nome da Funcionalidade — ex: Recuperação de senha]

| Campo               | Descrição                                               |
|---------------------|---------------------------------------------------------|
| **Prioridade**      | P1                                                      |
| **Usuário(s)**      | [Persona(s)]                                            |
| **Descrição**       | [Descrição]                                             |
| **Fluxo principal** | [Passo a passo]                                         |
| **Fluxos alternativos** | [Cenários de erro]                                  |

**Critérios de Aceite:**
- [ ] Dado que `[contexto]`, quando `[ação]`, então `[resultado esperado]`
- [ ] Dado que `[contexto]`, quando `[ação]`, então `[resultado esperado]`

---

### 4.2 [Nome do Módulo — ex: Agendamentos]

#### F03 — [Nome da Funcionalidade]

| Campo               | Descrição                                               |
|---------------------|---------------------------------------------------------|
| **Prioridade**      | P0                                                      |
| **Usuário(s)**      | [Persona(s)]                                            |
| **Descrição**       | [Descrição]                                             |
| **Fluxo principal** | [Passo a passo]                                         |
| **Fluxos alternativos** | [Cenários de erro]                                  |

**Critérios de Aceite:**
- [ ] Dado que `[contexto]`, quando `[ação]`, então `[resultado esperado]`

> ➕ *Repita o bloco acima para cada funcionalidade identificada.*

---

### 4.3 Mapa de Funcionalidades por Prioridade

| ID  | Funcionalidade               | Módulo          | Prioridade | Persona       |
|-----|------------------------------|-----------------|------------|--------------|
| F01 | [Nome]                       | [Módulo]        | P0         | [Persona]    |
| F02 | [Nome]                       | [Módulo]        | P0         | [Persona]    |
| F03 | [Nome]                       | [Módulo]        | P1         | [Persona]    |
| F04 | [Nome]                       | [Módulo]        | P2         | [Persona]    |

---

## 5. DON'Ts — O que NÃO será feito

> Esta seção é tão importante quanto o escopo positivo. Evita que o cliente ou o time assuma entregas que não foram acordadas. Registre aqui tudo que foi explicitamente discutido e descartado.

### 5.1 Fora do Escopo Técnico

```
❌ [Ex: App mobile nativo (iOS/Android)] — Motivo: fora do orçamento e prazo acordados
❌ [Ex: Integração com sistema legado X] — Motivo: API do sistema não disponível
❌ [Ex: Modo offline] — Motivo: fora do escopo desta versão
❌ [Ex: Relatórios em PDF] — Motivo: será avaliado em fase futura
```

### 5.2 Fora do Escopo de Negócio

```
❌ [Ex: Módulo financeiro / emissão de notas fiscais]
❌ [Ex: Multitenancy (suporte a múltiplas empresas na mesma instância)]
❌ [Ex: Envio de SMS] — apenas e-mail está no escopo
```

### 5.3 Decisões Tomadas e Justificativas

| Decisão                          | Motivo                             | Data       | Aprovado por   |
|----------------------------------|------------------------------------|------------|----------------|
| [Ex: Não usar React Native]      | [Custo e prazo inviáveis]          | DD/MM/AAAA | [Nome]         |
| [Ex: Banco de dados PostgreSQL]  | [Equipe tem mais experiência]      | DD/MM/AAAA | [Nome]         |

---

## 6. Regras de Negócio

> Regras de negócio são restrições, políticas e lógicas que o sistema **obrigatoriamente** deve respeitar. Toda RN deve ser verificável e testável.
>
> ⚠️ Os IDs `RN-00X` definidos aqui são referenciados pelas especificações técnicas de Backend. **Nunca renumere uma regra já publicada.**

---

### RN-001 — [Nome da Regra — ex: Limite de agendamentos simultâneos]

- **Contexto:** [Em qual situação essa regra se aplica]
- **Regra:** [Descrição precisa da regra. Ex: "Um profissional não pode ter mais de 1 agendamento ativo no mesmo horário."]
- **Exceção:** [Existe alguma exceção? Se sim, quando e como]
- **Consequência do descumprimento:** [O que o sistema deve fazer ao violar a regra — bloquear, alertar, registrar log]
- **Funcionalidades relacionadas:** F01, F03

---

### RN-002 — [Nome da Regra — ex: Cancelamento de agendamento]

- **Contexto:** [...]
- **Regra:** [Ex: "O cancelamento só é permitido com no mínimo 2 horas de antecedência do horário agendado."]
- **Exceção:** [Ex: "Administradores podem cancelar sem restrição de prazo."]
- **Consequência do descumprimento:** [Bloquear a ação e exibir mensagem de erro ao usuário]
- **Funcionalidades relacionadas:** F04

---

### RN-003 — [Nome da Regra]

- **Contexto:** [...]
- **Regra:** [...]
- **Exceção:** [...]
- **Consequência do descumprimento:** [...]
- **Funcionalidades relacionadas:** [...]

---

### 6.1 Tabela Consolidada de Regras de Negócio

| ID     | Regra (resumo)                          | Módulo          | Prioridade |
|--------|-----------------------------------------|-----------------|------------|
| RN-001 | [Resumo da regra]                       | [Módulo]        | Alta       |
| RN-002 | [Resumo da regra]                       | [Módulo]        | Alta       |
| RN-003 | [Resumo da regra]                       | [Módulo]        | Média      |

---

## 7. Riscos e Premissas de Negócio

> Riscos **técnicos** (indisponibilidade de API, dívida de infraestrutura etc.) são documentados em `desenvolvimento/04-backend.md`. Aqui ficam os riscos e premissas de negócio e de relacionamento com o cliente.

### 7.1 Premissas

> Condições assumidas como verdadeiras, mas que não estão totalmente garantidas.

- [ ] O cliente irá fornecer conteúdo (textos, imagens, dados) até `DD/MM/AAAA`
- [ ] O ambiente de produção será provisionado pelo cliente até `DD/MM/AAAA`
- [ ] Os requisitos documentados aqui estão alinhados com todos os stakeholders
- [ ] [Outra premissa]

### 7.2 Riscos Identificados

| # | Risco                                   | Probabilidade | Impacto | Mitigação                            |
|---|-----------------------------------------|---------------|---------|--------------------------------------|
| 1 | [Ex: Requisitos mudarem no meio do projeto] | Alta      | Alto    | [Validação semanal com cliente]      |
| 2 | [Ex: Atraso na entrega de conteúdo]         | Alta      | Médio   | [Definir prazo claro no contrato]    |
| 3 | [Ex: Rotatividade no time]                  | Média     | Alto    | [Documentação atualizada, pair programming] |

### 7.3 Dependências do Cliente

| Dependência               | Responsável    | Prazo       | Impacto se não disponível          |
|---------------------------|----------------|-------------|-------------------------------------|
| [Ex: Credenciais SMTP]    | [Nome]         | DD/MM/AAAA  | Envio de e-mails indisponível       |
| [Ex: Textos e imagens]    | [Nome]         | DD/MM/AAAA  | Telas entregues com conteúdo provisório |

---

## 8. Glossário de Negócio

> Padroniza o vocabulário usado no projeto. Evita ambiguidades entre cliente, PM e dev. Termos **técnicos** ficam no glossário de `desenvolvimento/03-arquitetura.md`.

| Termo              | Definição                                                    |
|--------------------|--------------------------------------------------------------|
| **Agendamento**    | [Ex: Reserva de um horário por um usuário final]            |
| **Profissional**   | [Ex: Colaborador que recebe agendamentos]                   |
| **Admin**          | [Ex: Usuário com acesso total ao sistema de gestão]         |
| **MVP**            | Minimum Viable Product — versão mínima funcional do projeto |
| **P0 / P1 / P2**   | Prioridade: P0 = bloqueante, P1 = importante, P2 = desejável|
| **RN**             | Regra de Negócio                                            |
| **[Outro termo]**  | [Definição]                                                 |
