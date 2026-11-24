# 🏗️ DPP — Parte 3: Arquitetura e Padrões
> **[NOME DO PROJETO]** — Versão `1.0` | Status: `Em Elaboração`

> 🧭 **Responsável por este arquivo:** Assessores de Desenvolvimento + Tech Lead · **Valida:** Gerente de Desenvolvimento
> 🌿 **Branch de preenchimento:** `dpp/<ano>-<cliente>/arquitetura` (ver `MANUAL-GIT.md`)
>
> ⚡ **Prioridade de preenchimento:** este arquivo deve ser preenchido **antes** dos documentos de Backend e Frontend — as decisões daqui (stack, padrões) valem para os dois. É um documento curto: resolva-o na Fase 1.

---

## 📌 Sumário

1. [Stack Tecnológica](#1-stack-tecnológica)
2. [Arquitetura do Sistema](#2-arquitetura-do-sistema)
3. [Padrões de Desenvolvimento](#3-padrões-de-desenvolvimento)
4. [Glossário Técnico](#4-glossário-técnico)

---

## 1. Stack Tecnológica

| Camada         | Tecnologia                  | Versão   | Justificativa                        |
|----------------|-----------------------------|----------|--------------------------------------|
| Backend        | [Ex: Node.js / Python]      | [Ex: 20] | [Experiência do time]                |
| Framework      | [Ex: Express / FastAPI]     | [...]    | [...]                                |
| Frontend       | [Ex: React / Vue]           | [...]    | [...]                                |
| Banco de Dados | [Ex: PostgreSQL / MySQL]    | [...]    | [...]                                |
| ORM            | [Ex: Prisma / TypeORM]      | [...]    | [...]                                |
| Autenticação   | [Ex: JWT / OAuth]           | [...]    | [...]                                |
| Hospedagem     | [Ex: Railway / Vercel / AWS]| [...]    | [...]                                |
| Versionamento  | Git + GitHub                | —        | Padrão da empresa                    |

> Decisões de stack descartadas (e o motivo) devem ser registradas na tabela de decisões em `produto/01-produto.md` (seção 5.3).

---

## 2. Arquitetura do Sistema

> Descreva brevemente como as partes do sistema se comunicam.

```
[Frontend]  ──HTTP/REST──►  [Backend API]  ──ORM──►  [Banco de Dados]
                                  │
                                  ├──► [Serviço de E-mail]
                                  └──► [Serviço de Storage]
```

---

## 3. Padrões de Desenvolvimento

> Estes padrões valem para **todo o time de desenvolvimento** (backend e frontend).

| Categoria            | Padrão adotado                                             |
|----------------------|------------------------------------------------------------|
| Branches             | `main`, `develop`, `feat/nome`, `fix/nome`, `hotfix/nome` |
| Commits              | Conventional Commits (`feat:`, `fix:`, `docs:`, `refactor:`) |
| Code Review          | PR obrigatório com ao menos 1 aprovação antes de merge     |
| Variáveis de ambiente| Usar `.env` — nunca commitar secrets no repositório        |
| Tratamento de erros  | Sempre retornar JSON com `{ error: true, message, code }`  |
| Paginação            | Padrão: `page` + `limit`, máx. 100 itens por página       |
| Logs                 | [Ferramenta: ex: Winston / console.log estruturado]        |

---

## 4. Glossário Técnico

> Termos técnicos usados nos documentos de Backend e Frontend. Termos de **negócio** ficam no glossário de `produto/01-produto.md`.

| Termo              | Definição                                                    |
|--------------------|--------------------------------------------------------------|
| **API REST**       | [Ex: Interface de comunicação entre frontend e backend via HTTP] |
| **JWT**            | [Ex: JSON Web Token — token de autenticação do usuário]     |
| **ORM**            | [Ex: Camada que traduz objetos do código em registros do banco] |
| **DER**            | Diagrama Entidade-Relacionamento                            |
| **[Outro termo]**  | [Definição]                                                 |
