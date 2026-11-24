# 📋 Documentação Pré-Projeto — Controle
> **[NOME DO PROJETO]** — Versão `1.0` | Status: `Em Elaboração`

> 🧭 **Responsável por este arquivo:** Gerente de Projeto · **Aprova:** Diretor de Projetos
> 🌿 **Branch de preenchimento:** `dpp/<ano>-<cliente>/controle` (ver `MANUAL-GIT.md`)

---

## 🗂️ Controle do Documento

| Campo              | Informação                        |
|--------------------|-----------------------------------|
| **Projeto**        | Market Finder                 |
| **Cliente**        | Projeto interno       |
| **Responsável**    | Tadashi  |
| **Data de Início** | 24/11/2026                        |
| **Prazo Estimado** | Não estimado                        |
| **Versão**         | 1.0                               |
| **Revisado por**   | [Nome]                            |
| **Aprovado por**   | [Nome do Cliente]                 |

### Histórico de Revisões

| Versão | Data       | Autor  | Descrição da Alteração         |
|--------|------------|--------|-------------------------------|
| 1.0    | 24/11/2026 | Tadashi | Criação do documento          |
| 1.1    | DD/MM/AAAA | [Nome] | [Descrição da alteração]      |

---

> ⚠️ **Como usar esta documentação**
>
> A DPP é dividida em **partes por área**, para que Produtos, Design e Desenvolvimento preencham em paralelo. Este arquivo é o **hub**: ele registra o controle do documento, o status de cada parte e o checklist de validação final. Antes de tomar qualquer decisão de desenvolvimento, produto ou negócio, consulte a parte correspondente. Caso algo não esteja coberto, registre a dúvida e alinhe com o Gerente de Projeto antes de prosseguir. Esse documento é vivo — atualizações devem ser versionadas e comunicadas ao time.

---

## 📌 Partes da Documentação

| # | Parte            | Arquivo                               | Elabora                         | Valida                    | Status            |
|---|------------------|---------------------------------------|---------------------------------|---------------------------|-------------------|
| 0 | Controle         | `00-controle.md`                      | Gerente de Projeto              | Diretor de Projetos       | `Em elaboração`   |
| 1 | Produto          | `produto/01-produto.md`               | Assessores de Produtos          | Gerente de Produtos       | `Em elaboração`   |
| 2 | Design           | `design/02-design.md`                 | Assessores de Design            | Gerente de Design         | `Em elaboração`   |
| 3 | Arquitetura      | `desenvolvimento/03-arquitetura.md`   | Assessores de Dev + Tech Lead   | Gerente de Desenvolvimento| `Em elaboração`   |
| 4 | Backend          | `desenvolvimento/04-backend.md`       | Assessores de Dev               | Gerente de Desenvolvimento| `Em elaboração`   |
| 5 | Frontend         | `desenvolvimento/05-frontend.md`      | Assessores de Dev               | Gerente de Desenvolvimento| `Em elaboração`   |

> Status possíveis: `Em elaboração` → `Em validação` → `Aprovado` ✅
> O Gerente de Projeto atualiza esta tabela conforme os PRs de cada área são mergeados e validados.

---

## 🔀 Ordem de Preenchimento e Dependências

O paralelismo entre as áreas depende de **uma única entrega inicial**: a lista de funcionalidades com IDs (`F0X`) e o escopo, no documento de Produto. Todo o restante roda em paralelo.

```
Fase 1 (curta)     Produto: Escopo + lista de Funcionalidades (só IDs e descrições)
                   Dev: 03-arquitetura.md (stack + padrões)
                          │
Fase 2 (paralela)  ┌──────┼────────────┬─────────────────┐
                   Produto detalha     Design faz         Backend modela banco
                   critérios de        jornadas e         e define a TABELA DE
                   aceite e RNs        wireframes         ENDPOINTS (contrato)
                          │                │                    │
Fase 3             Frontend preenche o mapa tela↔endpoint↔wireframe
                   (consome os três anteriores, mas o contrato de endpoints
                    permite começar antes do banco estar 100% detalhado)
```

**Regras de referência cruzada entre as partes:**

- IDs de funcionalidade (`F0X`) e de regra de negócio (`RN-00X`) **nascem** no documento de Produto. As demais partes apenas os referenciam — nunca criam IDs novos.
- Nenhuma tela entra no documento de Frontend sem o wireframe correspondente linkado no documento de Design.
- Nenhum endpoint entra no documento de Frontend sem estar especificado no documento de Backend.

---

## ✅ Checklist de Validação do Documento

> A ser preenchido pelo Gerente de Projeto antes de iniciar o desenvolvimento.

### Geral

- [ ] Todas as partes estão com status `Aprovado` na tabela acima
- [ ] O controle do documento tem GP, Tech Lead e data-limite preenchidos
- [ ] O histórico de revisões está atualizado com todas as versões

### Produto (`produto/01-produto.md`)

- [ ] O cliente leu e aprovou o escopo
- [ ] Os DON'Ts foram comunicados e aceitos pelo cliente
- [ ] Todas as regras de negócio foram validadas com o cliente
- [ ] Os riscos foram comunicados ao cliente
- [ ] O glossário cobre todos os termos ambíguos de negócio

### Design (`design/02-design.md`)

- [ ] Identidade visual aprovada pelo cliente
- [ ] Wireframes das telas do MVP concluídos e linkados
- [ ] Critérios de aceite de design definidos para as telas principais

### Desenvolvimento (`desenvolvimento/`)

- [ ] A stack técnica foi aprovada pelo time (03-arquitetura)
- [ ] O diagrama ER foi revisado pelo Tech Lead (04-backend)
- [ ] Todas as funcionalidades P0 e P1 têm especificação técnica (04-backend)
- [ ] O mapa tela ↔ endpoint ↔ wireframe cobre todas as telas do MVP (05-frontend)

### Finalização

- [ ] O documento foi versionado e salvo no repositório do projeto
- [ ] O cliente recebeu o documento, leu e sinalizou aprovação por escrito

---

*Documento elaborado por Tadashi Bello Nagashima · Versão 1.0 · 24/11/2026*
