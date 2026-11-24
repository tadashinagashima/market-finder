# 🖥️ DPP — Parte 5: Frontend
> **[NOME DO PROJETO]** — Versão `1.0` | Status: `Em Elaboração`

> 🧭 **Responsável por este arquivo:** Assessores de Desenvolvimento · **Valida:** Gerente de Desenvolvimento
> 🌿 **Branch de preenchimento:** `dpp/<ano>-<cliente>/frontend` (ver `MANUAL-GIT.md`)
>
> 🔗 **Referências cruzadas:** este documento é o ponto de encontro das outras partes. Cada tela referencia a funcionalidade (`F0X`) de `produto/01-produto.md`, o wireframe de `design/02-design.md` e os endpoints de `desenvolvimento/04-backend.md`. **Nenhuma tela deve ser especificada aqui sem wireframe linkado e endpoint definido.**
>
> ⚡ **Quando começar:** assim que o documento de Backend tiver a tabela de endpoints (o contrato) — não é preciso esperar o detalhamento completo de request/response.

---

## 📌 Sumário

1. [Mapa de Telas](#1-mapa-de-telas)
2. [Rotas e Navegação](#2-rotas-e-navegação)
3. [Especificação por Tela](#3-especificação-por-tela)
4. [Autenticação e Sessão no Frontend](#4-autenticação-e-sessão-no-frontend)
5. [Requisitos Não Funcionais de Frontend](#5-requisitos-não-funcionais-de-frontend)

---

## 1. Mapa de Telas

> A tabela abaixo é o **coração deste documento**: conecta cada tela à funcionalidade, ao wireframe e aos endpoints que ela consome. É por ela que o time verifica se nada ficou órfão — funcionalidade sem tela, tela sem wireframe, ou tela sem endpoint.

| Tela                    | Funcionalidade(s) | Wireframe (link)   | Endpoint(s) consumidos                  | Acesso            |
|-------------------------|-------------------|--------------------|------------------------------------------|-------------------|
| [Ex: Login]             | F01               | [Link Figma]       | `POST /api/auth/login`                   | Público           |
| [Ex: Dashboard]         | F03, F04          | [Link Figma]       | `GET /api/appointments`                  | Autenticado       |
| [Ex: Novo Agendamento]  | F03               | [Link Figma]       | `GET /api/services`, `POST /api/appointments` | Autenticado  |
| [Ex: Gestão de Usuários]| F05               | [Link Figma]       | `GET /api/users`, `PATCH /api/users/:id` | Admin             |

**Checklist de consistência (verificar antes da validação):**
- [ ] Toda funcionalidade P0 e P1 do documento de Produto tem ao menos uma tela neste mapa
- [ ] Toda tela tem wireframe linkado e aprovado no documento de Design
- [ ] Todo endpoint listado existe na especificação do documento de Backend

---

## 2. Rotas e Navegação

> Defina as rotas da aplicação e as regras de acesso de cada uma.

| Rota                  | Tela                     | Permissão            | Redirecionamento se não autorizado |
|-----------------------|--------------------------|----------------------|-------------------------------------|
| `/login`              | [Ex: Login]              | Público              | — (se já logado → `/dashboard`)     |
| `/dashboard`          | [Ex: Dashboard]          | Autenticado          | `/login`                            |
| `/agendamentos/novo`  | [Ex: Novo Agendamento]   | Autenticado          | `/login`                            |
| `/admin/usuarios`     | [Ex: Gestão de Usuários] | Admin                | `/dashboard`                        |

**Estrutura de navegação:**

```
[Ex:
/login
/dashboard
├── /agendamentos
│   ├── /agendamentos/novo
│   └── /agendamentos/:id
└── /admin
    └── /admin/usuarios          (visível apenas para Admin)
]
```

---

## 3. Especificação por Tela

> Para cada tela do Mapa de Telas, documente os dados consumidos, os estados previstos e as validações client-side. Os estados obrigatórios estão definidos em `design/02-design.md` (seção 5) — aqui você documenta **como cada tela os aplica**.

---

### Tela: [Nome da Tela — ex: Login] (F01)

**Dados consumidos / enviados:**

| Ação do usuário         | Endpoint                | Quando é chamado              |
|-------------------------|-------------------------|-------------------------------|
| Submeter formulário     | `POST /api/auth/login`  | Ao clicar em "Entrar"         |

**Validações client-side (antes de chamar a API):**

| Campo     | Regra                                  | Mensagem de erro                     |
|-----------|----------------------------------------|--------------------------------------|
| `email`   | Obrigatório, formato de e-mail válido  | "Informe um e-mail válido"           |
| `password`| Obrigatório, mínimo [X] caracteres     | "A senha deve ter ao menos [X] caracteres" |

**Estados da tela:**

| Estado   | Comportamento esperado                                                  |
|----------|--------------------------------------------------------------------------|
| Loading  | [Ex: Botão "Entrar" desabilitado com spinner durante a requisição]       |
| Error    | [Ex: Mensagem de erro da API exibida acima do formulário, campos mantidos] |
| Success  | [Ex: Redireciona para `/dashboard`]                                      |

**Tratamento dos erros da API:**

| Código de erro (API)   | O que a tela exibe                                   |
|------------------------|-------------------------------------------------------|
| `INVALID_CREDENTIALS`  | [Ex: "E-mail ou senha incorretos"]                    |
| `USER_INACTIVE`        | [Ex: "Usuário desativado. Fale com o administrador"]  |
| `SERVER_ERROR` / rede  | [Ex: "Erro inesperado. Tente novamente" + opção de retry] |

---

### Tela: [Nome da Tela — ex: Dashboard] (F03, F04)

**Dados consumidos / enviados:**

| Ação do usuário         | Endpoint                | Quando é chamado              |
|-------------------------|-------------------------|-------------------------------|
| [Carregar a tela]       | [...]                   | [Ao montar a tela]            |
| [...]                   | [...]                   | [...]                         |

**Validações client-side:**

| Campo     | Regra       | Mensagem de erro |
|-----------|-------------|-------------------|
| [...]     | [...]       | [...]             |

**Estados da tela:**

| Estado      | Comportamento esperado                        |
|-------------|------------------------------------------------|
| Loading     | [...]                                          |
| Empty State | [Ex: Ilustração + botão "Criar primeiro registro"] |
| Error       | [...]                                          |

> ➕ *Repita o bloco acima para cada tela do Mapa de Telas.*

---

## 4. Autenticação e Sessão no Frontend

> Como o frontend gerencia a sessão do usuário. Deve ser consistente com a estratégia de autenticação definida em `desenvolvimento/03-arquitetura.md`.

| Item                          | Definição                                                        |
|-------------------------------|-------------------------------------------------------------------|
| Armazenamento do token        | [Ex: Cookie httpOnly / localStorage — justifique a escolha]       |
| Expiração da sessão           | [Ex: Ao receber 401, limpar sessão e redirecionar para `/login`]  |
| Renovação do token            | [Ex: Refresh token / re-login manual]                             |
| Controle de acesso por perfil | [Ex: Rotas de admin verificam `role` antes de renderizar]         |

---

## 5. Requisitos Não Funcionais de Frontend

> Requisitos de performance, segurança e disponibilidade da API ficam em `desenvolvimento/04-backend.md`.

### 5.1 Compatibilidade

- **Web:** Navegadores modernos (Chrome, Firefox, Safari, Edge — últimas 2 versões)
- **Mobile:** Design responsivo conforme os breakpoints definidos em `design/02-design.md` (seção 6)
- **Resolução mínima:** 360px de largura

### 5.2 Usabilidade

- Feedback visual para todas as ações do usuário (loading, sucesso, erro)
- Mensagens de erro escritas em linguagem clara para o usuário final
- Nenhuma ação destrutiva sem modal de confirmação (conforme `design/02-design.md`, seção 4)
- [Seguir WCAG AA de acessibilidade — se aplicável]

### 5.3 Performance Percebida

- [Ex: Primeira renderização visível em < 3s em conexão 4G]
- [Ex: Feedback de loading para qualquer operação que leve mais de 300ms]
- [Ex: Imagens otimizadas e carregadas sob demanda (lazy loading)]
