# 🎨 DPP — Parte 2: Design
> **[NOME DO PROJETO]** — Versão `1.0` | Status: `Em Elaboração`

> 🧭 **Responsável por este arquivo:** Assessores de Design · **Valida:** Gerente de Design
> 🌿 **Branch de preenchimento:** `dpp/<ano>-<cliente>/design` (ver `MANUAL-GIT.md`)
>
> 🔗 **Referências cruzadas:** as jornadas e critérios por tela referenciam as funcionalidades (`F0X`) definidas em `produto/01-produto.md`. O documento de Frontend (`desenvolvimento/05-frontend.md`) consome os wireframes, estados e tokens definidos aqui.

---

## 📌 Sumário

1. [Identidade Visual e Referências](#1-identidade-visual-e-referências)
2. [Jornada do Usuário](#2-jornada-do-usuário)
3. [Protótipo e Wireframes](#3-protótipo-e-wireframes)
4. [Componentes e Design System](#4-componentes-e-design-system)
5. [Estados das Interfaces](#5-estados-das-interfaces)
6. [Responsividade](#6-responsividade)
7. [Acessibilidade](#7-acessibilidade)
8. [Critérios de Aceite de Design](#8-critérios-de-aceite-de-design)

---

## 1. Identidade Visual e Referências

> Registre aqui as diretrizes visuais do cliente e referências de estilo acordadas. Caso o cliente já tenha uma identidade visual estabelecida, documente-a. Caso não tenha, registre as referências aprovadas nas reuniões. Os valores apresentados entre `[Ex: ...]` são apenas exemplos de preenchimento e devem ser substituídos pelos valores definidos para cada projeto.

### 1.1 Paleta de Cores

| Uso                  | Nome / Token          | Hex       |
|---------------------|-----------------------|-----------|
| Cor primária | `--color-primary` | `[Ex: #2563EB]` |
| Cor secundária | `--color-secondary` | `[Ex: #64748B]` |
| Cor de fundo | `--color-background` | `[Ex: #FFFFFF]` |
| Cor de texto | `--color-text` | `[Ex: #1E293B]` |
| Cor de destaque | `--color-accent` | `[Ex: #F59E0B]` |
| Cor de erro | `--color-error` | `[Ex: #DC2626]` |
| Cor de sucesso | `--color-success` | `[Ex: #16A34A]` |

### 1.2 Tipografia

| Uso              | Fonte             | Peso(s)         | Tamanho base |
|-----------------|-------------------|-----------------|--------------|
| Títulos | `[Ex: Inter]` | `600, 700` | `[Ex: 32px]` |
| Corpo de texto | `[Ex: Inter]` | `400` | `[Ex: 16px]` |
| Labels / UI | `[Ex: Inter]` | `500` | `[Ex: 14px]` |

### 1.3 Tom e Estilo Visual

> Descreva em poucas frases a direção estética acordada com o cliente. Ex: limpo e corporativo, vibrante e jovem, minimalista, etc.

```
[Ex: Interface limpa e profissional, com uso moderado de cor primária apenas em
elementos de ação. Ícones simples, espaçamento generoso, sem elementos decorativos excessivos.]
```

### 1.4 Referências Visuais

| Referência                   | Link / Descrição                                      |
|-----------------------------|-------------------------------------------------------|
| [Ex: Site concorrente A]    | [URL ou descrição do que foi aproveitado como ref]    |
| [Ex: Moodboard aprovado]    | [Link do Figma / Miro / Drive]                        |

---

## 2. Jornada do Usuário

> Descreva o caminho que cada persona percorre dentro do sistema, do ponto de entrada até o objetivo final. Isso guia tanto o Design quanto o Desenvolvimento na hora de priorizar o que deve funcionar sem atrito. As personas são definidas em `produto/01-produto.md` (seção 2.2).

### Jornada: [Nome da Persona]

```
[Ponto de entrada] → [Tela/ação 1] → [Tela/ação 2] → [Objetivo alcançado]

Ex:
Acessa o link → Tela de login → Dashboard → Clica em "Novo agendamento"
→ Escolhe serviço → Escolhe data e hora → Confirma → Recebe e-mail de confirmação ✅
```

**Pontos de fricção identificados:**
- [Ex: O usuário pode não saber a diferença entre os tipos de serviço disponíveis]
- [Ex: A confirmação precisa ser clara o suficiente para evitar dúvidas]

---

### Jornada: [Nome da Persona 2]

```
[Ponto de entrada] → [Tela/ação 1] → [Tela/ação 2] → [Objetivo alcançado]

Ex:
Realiza login → Dashboard → Acessa módulo desejado → Preenche formulário → Envia informações
→ Recebe confirmação de processamento ✅
```

**Pontos de fricção identificados:**
- [Ex: Formulários muito extensos podem aumentar a taxa de abandono]
- [Ex: Campos obrigatórios precisam estar claramente identificados]

---

## 3. Protótipo e Wireframes

> Links para os artefatos de Design. Devem ser atualizados conforme o projeto avança. Nunca desenvolva uma tela sem que o wireframe ou protótipo correspondente esteja linkado aqui e aprovado.

| Artefato                    | Status              | Link                        | Aprovado pelo cliente? |
|-----------------------------|---------------------|-----------------------------|------------------------|
| Wireframes de baixa fidelidade | [Ex: Concluído]  | [Link Figma]                | [ ] Sim / [ ] Não      |
| Protótipo navegável         | [Ex: Em andamento]  | [Link Figma]                | [ ] Sim / [ ] Não      |
| Guia de estilos (Style Guide) | [Ex: Pendente]   | —                           | [ ] Sim / [ ] Não      |

---

## 4. Componentes e Design System

> Esta seção documenta os componentes reutilizáveis do sistema e os padrões definidos para sua utilização. O objetivo é garantir consistência visual e comportamental entre as telas, além de facilitar a implementação e manutenção do produto.

### 4.1 Biblioteca de Componentes

| Componente | Origem | Variantes | Observações |
|------------|---------|------------|-------------|
| Button | [Ex: HeroUI, Shadcn] | Primary, Secondary, Danger | Utilizar variante primária para ações principais |
| Input | [Ex: HeroUI, Shadcn] | Text, Password, Email | Todos os campos devem possuir label |
| Select | [Ex: HeroUI, Shadcn] | Single, Multiple | Exibir placeholder quando vazio |
| Modal | [Ex: HeroUI, Shadcn] | Default, Confirmation | Utilizar confirmação para ações destrutivas |
| Table | [Ex: Customizado, HeroUI, Shadcn] | Padrão | Deve possuir tratamento para estados vazios |

### 4.2 Padrões de Utilização

- Componentes devem ser reutilizados sempre que possível.
- Evitar a criação de componentes duplicados com a mesma finalidade.
- Alterações visuais em componentes compartilhados devem ser avaliadas pelo time de Design.
- Componentes devem seguir os tokens definidos na seção 1 deste documento.
- Sempre documentar novas variantes adicionadas ao Design System.

### 4.3 Tokens Utilizados

| Categoria | Token | Valor |
|------------|--------|--------|
| Cor Primária | `--color-primary` | `[Ex: #2563EB]` |
| Cor Secundária | `--color-secondary` | `[Ex: #64748B]` |
| Espaçamento Pequeno | `--spacing-sm` | `[Ex: 8px]` |
| Espaçamento Médio | `--spacing-md` | `[Ex: 16px]` |
| Espaçamento Grande | `--spacing-lg` | `[Ex: 24px]` |
| Raio Pequeno | `--border-radius-sm` | `[Ex: 4px]` |
| Raio Médio | `--border-radius-md` | `[Ex: 8px]` |

### 4.4 Biblioteca de Ícones

| Item | Valor |
|------|-------|
| Biblioteca | [Ex: Heroicons, Lucide, Material Symbols] |
| Estilo | [Ex: Outline, Filled] |
| Tamanho padrão | [Ex: 20px] |
| Tamanho alternativo | [Ex: 24px] |

---

## 5. Estados das Interfaces

> Todas as telas e componentes devem prever seus estados de interação e carregamento. Isso reduz ambiguidades durante o desenvolvimento e melhora a experiência do usuário em situações excepcionais.

### 5.1 Estados Obrigatórios

| Estado | Descrição |
|----------|----------|
| Default | Estado padrão da interface |
| Hover | Estado ao passar o cursor |
| Focus | Estado de foco para navegação e acessibilidade |
| Disabled | Estado desabilitado |
| Loading | Estado de carregamento |
| Success | Operação concluída com sucesso |
| Error | Erro de validação ou processamento |
| Empty State | Ausência de dados para exibição |

### 5.2 Checklist de Estados

- [ ] Todos os botões possuem estados de hover e disabled.
- [ ] Campos de formulário possuem estados de foco e erro.
- [ ] Listagens possuem tratamento para ausência de dados.
- [ ] Processos assíncronos possuem indicador visual de carregamento.
- [ ] Mensagens de sucesso e erro estão definidas.
- [ ] Modais possuem comportamento documentado para confirmação e cancelamento.

### Observações

> Sempre que uma tela consumir dados externos (API, banco de dados ou integrações), devem ser previstos os estados de carregamento, erro e ausência de dados.

---

## 6. Responsividade

> Esta seção define como a interface deve se adaptar a diferentes tamanhos de tela. O objetivo é garantir uma experiência consistente entre dispositivos desktop, tablet e mobile.

### 6.1 Breakpoints

| Dispositivo | Faixa de Largura |
|-------------|------------------|
| Mobile | 360px – 767px |
| Tablet | 768px – 1023px |
| Desktop | 1024px ou superior |

### 6.2 Diretrizes Gerais

- Priorizar abordagem Mobile First sempre que aplicável.
- Evitar rolagem horizontal.
- Garantir área mínima de toque adequada para dispositivos móveis.
- Manter legibilidade dos textos em todos os tamanhos de tela.
- Preservar hierarquia visual e espaçamentos definidos no Design System.

### 6.3 Comportamentos Esperados

| Elemento | Desktop | Mobile |
|-----------|----------|---------|
| Menu de navegação | Barra lateral ou superior | Menu hambúrguer |
| Formulários | Múltiplas colunas quando necessário | Coluna única |
| Tabelas | Exibição completa | Scroll horizontal ou visualização adaptada |
| Cards | Grid com múltiplas colunas | Uma coluna por linha |

### 6.4 Critérios de Aceite

- [ ] Todas as telas possuem versão mobile validada.
- [ ] Todos os componentes funcionam corretamente em diferentes resoluções.
- [ ] Não há sobreposição de elementos em telas menores.
- [ ] Os fluxos principais podem ser executados em dispositivos móveis.
- [ ] Imagens e mídias se adaptam proporcionalmente ao espaço disponível.

---

## 7. Acessibilidade

> Esta seção define requisitos mínimos de acessibilidade para garantir que a interface seja utilizável pelo maior número possível de usuários.

### 7.1 Diretrizes

- Todos os campos de formulário devem possuir label.
- O contraste entre texto e fundo deve garantir legibilidade.
- Informações não devem depender exclusivamente de cor para serem compreendidas.

### 7.2 Critérios de Aceite

- [ ] Todos os campos possuem identificação clara.
- [ ] Contraste visual atende aos padrões definidos.
- [ ] Mensagens de erro são compreensíveis e acessíveis.

---

## 8. Critérios de Aceite de Design

> Assim como as funcionalidades têm critérios de aceite técnicos, o Design tem os seus. Nenhuma tela deve ser considerada pronta sem que estes critérios sejam verificados.

### 8.1 Critérios Globais (aplicam-se a todas as telas)

- [ ] Todas as telas seguem a paleta de cores definida na seção 1
- [ ] Todos os textos usam as fontes e tamanhos definidos na seção 1
- [ ] A interface atende aos requisitos de responsividade definidos na seção 6
- [ ] Todos os componentes possuem estados documentados conforme a seção 5
- [ ] Mensagens de erro são exibidas em linguagem clara, próximas ao campo que gerou o erro
- [ ] Ícones têm significado consistente em todo o sistema

### 8.2 Critérios por Tela / Funcionalidade

> Para funcionalidades com requisitos visuais específicos, adicione critérios individuais abaixo, referenciando o ID da funcionalidade (`F0X`).

**Tela: [Nome da tela — ex: Login] (F01)**
- [ ] [Ex: O botão de ação principal usa a cor primária e tem estado de loading]
- [ ] [Ex: O campo de senha tem opção de mostrar/ocultar]

**Tela: [Nome da tela — ex: Listagem de Registros] (F03)**
- [ ] [Ex: A tabela possui tratamento para estado vazio]
- [ ] [Ex: Filtros e campo de busca permanecem visíveis durante a navegação]
- [ ] [Ex: Ações principais estão acessíveis sem necessidade de rolagem horizontal]
- [ ] [Ex: O estado de carregamento é exibido enquanto os dados são buscados]
