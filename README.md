# Alpine.js: Guia Completo para Iniciantes

**Um framework JavaScript minimalista para adicionar interatividade ao seu HTML**

---

## Índice

1. [Introdução](#1-introdução)
   - [O que é Alpine.js?](#o-que-é-alpinejs)
   - [Por que usar Alpine.js?](#por-que-usar-alpinejs)
   - [Quando usar Alpine.js?](#quando-usar-alpinejs)

2. [Primeiros Passos](#2-primeiros-passos)
   - [Instalação](#instalação)
   - [Seu Primeiro Componente](#seu-primeiro-componente)
   - [Como Alpine.js Funciona](#como-alpinejs-funciona)

3. [Conceitos Fundamentais](#3-conceitos-fundamentais)
   - [x-data: Definindo Estado](#x-data-definindo-estado)
   - [x-text e x-html: Exibindo Conteúdo](#x-text-e-x-html-exibindo-conteúdo)
   - [@click e Eventos: Interatividade](#click-e-eventos-interatividade)
   - [x-show e x-if: Controle de Visibilidade](#x-show-e-x-if-controle-de-visibilidade)
   - [x-model: Binding Bidirecional](#x-model-binding-bidirecional)

4. [Exemplos Práticos](#4-exemplos-práticos)
   - [Exemplo 1: Contador Simples](#exemplo-1-contador-simples)
   - [Exemplo 2: Toggle de Visibilidade](#exemplo-2-toggle-de-visibilidade)
   - [Exemplo 3: Formulário com Validação](#exemplo-3-formulário-com-validação)
   - [Exemplo 4: Lista de Tarefas (To-Do)](#exemplo-4-lista-de-tarefas-to-do)
   - [Exemplo 5: Tabs/Abas](#exemplo-5-tabsabas)
   - [Exemplo 6: Modal/Diálogo](#exemplo-6-modaldiálogo)

5. [Diretivas Avançadas](#5-diretivas-avançadas)
   - [x-for: Iteração em Listas](#x-for-iteração-em-listas)
   - [x-bind: Atributos Dinâmicos](#x-bind-atributos-dinâmicos)
   - [x-on: Ouvindo Eventos](#x-on-ouvindo-eventos)
   - [x-transition: Animações](#x-transition-animações)
   - [x-cloak: Evitando Flash de Conteúdo](#x-cloak-evitando-flash-de-conteúdo)

6. [Propriedades Mágicas](#6-propriedades-mágicas)
   - [$el: Elemento Atual](#el-elemento-atual)
   - [$refs: Referências a Elementos](#refs-referências-a-elementos)
   - [$watch: Observando Mudanças](#watch-observando-mudanças)
   - [$dispatch: Eventos Customizados](#dispatch-eventos-customizados)
   - [$nextTick: Próximo Ciclo do DOM](#nexttick-próximo-ciclo-do-dom)

7. [Estado Global](#7-estado-global)
   - [Alpine.store(): Gerenciamento de Estado](#alpinestore-gerenciamento-de-estado)
   - [Compartilhando Dados Entre Componentes](#compartilhando-dados-entre-componentes)

8. [Boas Práticas](#8-boas-práticas)
   - [Organização do Código](#organização-do-código)
   - [Performance](#performance)
   - [Acessibilidade](#acessibilidade)
   - [Quando NÃO Usar Alpine.js](#quando-não-usar-alpinejs)

9. [Integração e Ecosistema](#9-integração-e-ecosistema)
   - [Alpine.js com Laravel](#alpinejs-com-laravel)
   - [Alpine.js com Rails](#alpinejs-com-rails)
   - [Plugins Úteis](#plugins-úteis)

10. [Recursos e Referências](#10-recursos-e-referências)
    - [Documentação Oficial](#documentação-oficial)
    - [Tutoriais e Cursos](#tutoriais-e-cursos)
    - [Comunidade](#comunidade)

---

## 1. Introdução

### O que é Alpine.js?

Alpine.js é um framework JavaScript leve e minimalista, criado por Caleb Porzio, que oferece a reatividade e a estrutura declarativa de frameworks maiores como Vue.js ou React, mas com uma sintaxe muito mais simples e um tamanho extremamente reduzido (apenas ~15kb compactado).

**Documentação oficial:** https://alpinejs.dev/

Alpine.js é frequentemente descrito como "jQuery moderno" ou "Tailwind CSS para JavaScript" porque você escreve a lógica diretamente no HTML usando atributos especiais (diretivas), sem precisar criar arquivos JavaScript separados para funcionalidades simples.

### Por que usar Alpine.js?

**Vantagens principais:**

1. **Simplicidade**: Sintaxe intuitiva que você aprende em minutos
2. **Leveza**: Apenas 15kb compactado, ideal para performance
3. **Sem Build Step**: Não precisa de Webpack, Vite ou outras ferramentas de build
4. **Declarativo**: Escreve a lógica diretamente no HTML
5. **Reativo**: Atualiza automaticamente o DOM quando os dados mudam
6. **Progressivo**: Adicione onde precisar, sem reescrever tudo
7. **Sem Virtual DOM**: Manipula o DOM diretamente para melhor performance em casos simples

**Comparação com outros frameworks:**

| Característica | Alpine.js | Vue.js | React | jQuery |
|----------------|-----------|---------|--------|---------|
| Tamanho | ~15kb | ~33kb | ~40kb | ~30kb |
| Curva de aprendizado | Baixa | Média | Média-Alta | Baixa |
| Reatividade | ✓ | ✓ | ✓ | ✗ |
| Build necessário | ✗ | Opcional | ✓ | ✗ |
| Virtual DOM | ✗ | ✓ | ✓ | ✗ |

### Quando usar Alpine.js?

**Casos de uso ideais:**

- Adicionar interatividade a sites estáticos ou aplicações server-side
- Componentes simples: menus dropdown, modais, tabs, accordions
- Formulários com validação e interatividade
- Dashboards administrativos simples
- Protótipos rápidos
- Quando você não quer a complexidade de um framework completo

**Quando considerar alternativas:**

- Aplicações de página única (SPA) muito complexas
- Precisa de roteamento sofisticado
- Gerenciamento de estado muito complexo
- Grandes equipes que precisam de padrões mais rigorosos

---

## 2. Primeiros Passos

### Instalação

Existem várias formas de incluir Alpine.js no seu projeto:

#### Opção 1: CDN (mais simples para começar)

```html
<!DOCTYPE html>
<html>
<head>
    <title>Meu Primeiro App Alpine.js</title>
    <!-- Incluir Alpine.js via CDN -->
    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
</head>
<body>
    <!-- Seu código aqui -->
</body>
</html>
```

**Nota:** Use `defer` para garantir que o script carregue após o HTML.

**Referência:** https://alpinejs.dev/essentials/installation

#### Opção 2: NPM (para projetos com build)

```bash
npm install alpinejs
```

```javascript
import Alpine from 'alpinejs'

window.Alpine = Alpine

Alpine.start()
```

#### Opção 3: Download direto

Baixe o arquivo do repositório oficial: https://github.com/alpinejs/alpine

### Seu Primeiro Componente

Vamos criar um exemplo simples de "Olá Mundo":

```html
<!DOCTYPE html>
<html>
<head>
    <title>Olá Alpine.js</title>
    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
</head>
<body>
    <div x-data="{ mensagem: 'Olá, Alpine.js!' }">
        <p x-text="mensagem"></p>
        <button @click="mensagem = 'Você clicou no botão!'">
            Clique aqui
        </button>
    </div>
</body>
</html>
```

**O que está acontecendo:**

1. `x-data`: Define um componente Alpine com estado inicial
2. `x-text`: Exibe o valor da variável `mensagem`
3. `@click`: Ouve o evento de clique e atualiza a mensagem

### Como Alpine.js Funciona

Alpine.js funciona através de **diretivas** (atributos especiais que começam com `x-`) que você adiciona aos elementos HTML. Quando a página carrega:

1. Alpine.js escaneia o DOM procurando por elementos com `x-data`
2. Inicializa cada componente com seu estado
3. Processa todas as diretivas e estabelece ligações reativas
4. Quando os dados mudam, o DOM é atualizado automaticamente

**Fluxo de reatividade:**

```
Estado (x-data) → Mudança → Alpine detecta → Atualiza DOM automaticamente
```

---

## 3. Conceitos Fundamentais

### x-data: Definindo Estado

A diretiva `x-data` é o coração do Alpine.js. Ela define o escopo de um componente e seu estado inicial.

**Sintaxe básica:**

```html
<div x-data="{ count: 0, nome: 'João' }">
    <!-- Aqui você pode acessar count e nome -->
</div>
```

**Com funções e métodos:**

```html
<div x-data="{
    count: 0,
    incrementar() {
        this.count++
    },
    decrementar() {
        this.count--
    }
}">
    <span x-text="count"></span>
    <button @click="incrementar()">+</button>
    <button @click="decrementar()">-</button>
</div>
```

**Componentes reutilizáveis:**

```html
<script>
    document.addEventListener('alpine:init', () => {
        Alpine.data('contador', () => ({
            count: 0,
            incrementar() {
                this.count++
            }
        }))
    })
</script>

<!-- Usar em qualquer lugar -->
<div x-data="contador">
    <span x-text="count"></span>
    <button @click="incrementar()">+</button>
</div>
```

**Referência:** https://alpinejs.dev/directives/data

### x-text e x-html: Exibindo Conteúdo

**x-text**: Define o conteúdo de texto de um elemento

```html
<div x-data="{ titulo: 'Bem-vindo!' }">
    <h1 x-text="titulo"></h1>
    <!-- Resultado: <h1>Bem-vindo!</h1> -->
</div>
```

**x-html**: Insere HTML (use com cuidado - risco de XSS!)

```html
<div x-data="{ conteudo: '<strong>Texto em negrito</strong>' }">
    <div x-html="conteudo"></div>
    <!-- Resultado: <div><strong>Texto em negrito</strong></div> -->
</div>
```

**⚠️ Aviso de Segurança:** Nunca use `x-html` com conteúdo não confiável ou fornecido pelo usuário, pois pode causar ataques XSS (Cross-Site Scripting).

**Referência:** https://alpinejs.dev/directives/text

### @click e Eventos: Interatividade

A sintaxe `@` é um atalho para `x-on:` e permite ouvir eventos do DOM.

**Eventos comuns:**

```html
<div x-data="{ mensagem: '' }">
    <!-- Click -->
    <button @click="mensagem = 'Clicou!'">Click</button>
    
    <!-- Submit de formulário -->
    <form @submit.prevent="mensagem = 'Enviado!'">
        <button type="submit">Enviar</button>
    </form>
    
    <!-- Hover (mouseenter/mouseleave) -->
    <div @mouseenter="mensagem = 'Mouse entrou'"
         @mouseleave="mensagem = 'Mouse saiu'">
        Passe o mouse aqui
    </div>
    
    <!-- Tecla pressionada -->
    <input @keyup.enter="mensagem = 'Enter pressionado!'" 
           placeholder="Pressione Enter">
    
    <p x-text="mensagem"></p>
</div>
```

**Modificadores úteis:**

- `.prevent`: Previne comportamento padrão (`event.preventDefault()`)
- `.stop`: Para propagação (`event.stopPropagation()`)
- `.once`: Executa apenas uma vez
- `.debounce`: Adiciona debounce ao evento
- `.throttle`: Adiciona throttle ao evento

```html
<!-- Debounce: espera 500ms após última digitação -->
<input @input.debounce.500ms="buscar()" placeholder="Buscar...">

<!-- Throttle: executa no máximo uma vez a cada 1000ms -->
<div @scroll.throttle.1000ms="verificarScroll()">
    Conteúdo com scroll...
</div>
```

**Referência:** https://alpinejs.dev/directives/on

### x-show e x-if: Controle de Visibilidade

**x-show**: Oculta/mostra elemento com CSS (display: none)

```html
<div x-data="{ aberto: false }">
    <button @click="aberto = !aberto">Toggle</button>
    
    <div x-show="aberto">
        Este conteúdo pode ser ocultado
    </div>
</div>
```

**x-if**: Remove/adiciona elemento do DOM

```html
<div x-data="{ existe: false }">
    <button @click="existe = !existe">Toggle</button>
    
    <template x-if="existe">
        <div>Este elemento é removido do DOM</div>
    </template>
</div>
```

**Diferenças importantes:**

| x-show | x-if |
|--------|------|
| Usa CSS (display: none) | Remove do DOM |
| Mais rápido para alternar | Melhor para conteúdo pesado |
| Elemento sempre existe no DOM | Elemento é criado/destruído |
| Não requer `<template>` | Requer `<template>` |

**Quando usar cada um:**

- **x-show**: Para elementos que alternam frequentemente (menus, dropdowns)
- **x-if**: Para conteúdo condicional que raramente muda ou é pesado

**Referência:** 
- x-show: https://alpinejs.dev/directives/show
- x-if: https://alpinejs.dev/directives/if

### x-model: Binding Bidirecional

`x-model` cria uma ligação bidirecional entre um input e uma variável.

**Inputs de texto:**

```html
<div x-data="{ nome: '' }">
    <input type="text" x-model="nome" placeholder="Digite seu nome">
    <p>Olá, <span x-text="nome"></span>!</p>
</div>
```

**Checkboxes:**

```html
<div x-data="{ aceito: false }">
    <label>
        <input type="checkbox" x-model="aceito">
        Aceito os termos
    </label>
    <p x-show="aceito">Obrigado por aceitar!</p>
</div>
```

**Radio buttons:**

```html
<div x-data="{ escolha: '' }">
    <label><input type="radio" x-model="escolha" value="a"> Opção A</label>
    <label><input type="radio" x-model="escolha" value="b"> Opção B</label>
    <label><input type="radio" x-model="escolha" value="c"> Opção C</label>
    
    <p>Você escolheu: <span x-text="escolha"></span></p>
</div>
```

**Select:**

```html
<div x-data="{ cidade: 'sp' }">
    <select x-model="cidade">
        <option value="sp">São Paulo</option>
        <option value="rj">Rio de Janeiro</option>
        <option value="mg">Minas Gerais</option>
    </select>
    
    <p>Cidade selecionada: <span x-text="cidade"></span></p>
</div>
```

**Modificadores:**

```html
<!-- .lazy: atualiza apenas no blur, não a cada tecla -->
<input x-model.lazy="valor">

<!-- .number: converte para número -->
<input type="number" x-model.number="idade">

<!-- .debounce: adiciona debounce -->
<input x-model.debounce.500ms="busca">
```

**Referência:** https://alpinejs.dev/directives/model

---

## 4. Exemplos Práticos

### Exemplo 1: Contador Simples

Um contador é o "Hello World" dos frameworks reativos.

```html
<!DOCTYPE html>
<html>
<head>
    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
    <style>
        .contador {
            text-align: center;
            padding: 2rem;
            font-family: Arial, sans-serif;
        }
        .numero {
            font-size: 3rem;
            font-weight: bold;
            color: #2c3e50;
            margin: 1rem 0;
        }
        button {
            padding: 0.5rem 1rem;
            font-size: 1rem;
            margin: 0.5rem;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="contador" x-data="{ 
        count: 0,
        incrementar() {
            this.count++
        },
        decrementar() {
            this.count--
        },
        resetar() {
            this.count = 0
        }
    }">
        <h2>Contador Simples</h2>
        <div class="numero" x-text="count"></div>
        
        <button @click="decrementar()">-</button>
        <button @click="resetar()">Reset</button>
        <button @click="incrementar()">+</button>
        
        <!-- Mensagem condicional -->
        <p x-show="count > 10" style="color: green;">
            🎉 Você passou de 10!
        </p>
        <p x-show="count < 0" style="color: red;">
            ⚠️ Número negativo!
        </p>
    </div>
</body>
</html>
```

**Conceitos demonstrados:**
- x-data com métodos
- x-text para exibir valores
- @click para eventos
- x-show para condicionalidade

### Exemplo 2: Toggle de Visibilidade

Controle de visibilidade é muito comum em interfaces modernas.

```html
<!DOCTYPE html>
<html>
<head>
    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
    <style>
        .conteudo {
            padding: 1rem;
            background: #f0f0f0;
            border-radius: 8px;
            margin-top: 1rem;
        }
        button {
            padding: 0.5rem 1rem;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div x-data="{ mostrar: false }">
        <h2>Toggle de Visibilidade</h2>
        
        <button @click="mostrar = !mostrar">
            <span x-text="mostrar ? 'Ocultar' : 'Mostrar'"></span> Conteúdo
        </button>
        
        <!-- Usando x-show -->
        <div x-show="mostrar" class="conteudo">
            <h3>Conteúdo Revelado!</h3>
            <p>Este conteúdo pode ser mostrado ou ocultado.</p>
        </div>
    </div>
    
    <hr style="margin: 2rem 0;">
    
    <!-- Versão com transição -->
    <div x-data="{ aberto: false }">
        <h2>Toggle com Transição</h2>
        
        <button @click="aberto = !aberto">
            Toggle Suave
        </button>
        
        <div x-show="aberto" 
             x-transition
             class="conteudo">
            <h3>Com animação suave!</h3>
            <p>A transição torna a experiência mais agradável.</p>
        </div>
    </div>
</body>
</html>
```

**Conceitos demonstrados:**
- Operador ternário em expressões
- x-transition para animações
- Binding de texto dinâmico

### Exemplo 3: Formulário com Validação

Validação de formulários é essencial em aplicações web.

```html
<!DOCTYPE html>
<html>
<head>
    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
    <style>
        .formulario {
            max-width: 400px;
            margin: 2rem auto;
            padding: 2rem;
            border: 1px solid #ddd;
            border-radius: 8px;
        }
        .campo {
            margin-bottom: 1rem;
        }
        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: bold;
        }
        input {
            width: 100%;
            padding: 0.5rem;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        input.erro {
            border-color: #e74c3c;
        }
        .mensagem-erro {
            color: #e74c3c;
            font-size: 0.875rem;
            margin-top: 0.25rem;
        }
        .sucesso {
            background: #d4edda;
            color: #155724;
            padding: 1rem;
            border-radius: 4px;
            margin-top: 1rem;
        }
        button {
            width: 100%;
            padding: 0.75rem;
            background: #3498db;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 1rem;
        }
        button:disabled {
            background: #95a5a6;
            cursor: not-allowed;
        }
    </style>
</head>
<body>
    <div class="formulario" x-data="{
        nome: '',
        email: '',
        senha: '',
        confirmaSenha: '',
        enviado: false,
        
        get nomeValido() {
            return this.nome.length >= 3
        },
        get emailValido() {
            return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(this.email)
        },
        get senhaValida() {
            return this.senha.length >= 6
        },
        get senhasConferem() {
            return this.senha === this.confirmaSenha && this.senha !== ''
        },
        get formularioValido() {
            return this.nomeValido && 
                   this.emailValido && 
                   this.senhaValida && 
                   this.senhasConferem
        },
        
        enviar() {
            if (this.formularioValido) {
                this.enviado = true
                // Aqui você faria o envio real dos dados
                console.log('Dados:', {
                    nome: this.nome,
                    email: this.email
                })
            }
        }
    }">
        <h2>Cadastro de Usuário</h2>
        
        <form @submit.prevent="enviar()">
            <!-- Nome -->
            <div class="campo">
                <label>Nome completo:</label>
                <input 
                    type="text" 
                    x-model="nome"
                    :class="{ 'erro': nome && !nomeValido }"
                    placeholder="Digite seu nome">
                <div x-show="nome && !nomeValido" class="mensagem-erro">
                    Nome deve ter pelo menos 3 caracteres
                </div>
            </div>
            
            <!-- Email -->
            <div class="campo">
                <label>E-mail:</label>
                <input 
                    type="email" 
                    x-model="email"
                    :class="{ 'erro': email && !emailValido }"
                    placeholder="seu@email.com">
                <div x-show="email && !emailValido" class="mensagem-erro">
                    E-mail inválido
                </div>
            </div>
            
            <!-- Senha -->
            <div class="campo">
                <label>Senha:</label>
                <input 
                    type="password" 
                    x-model="senha"
                    :class="{ 'erro': senha && !senhaValida }"
                    placeholder="Mínimo 6 caracteres">
                <div x-show="senha && !senhaValida" class="mensagem-erro">
                    Senha deve ter pelo menos 6 caracteres
                </div>
            </div>
            
            <!-- Confirmar Senha -->
            <div class="campo">
                <label>Confirmar senha:</label>
                <input 
                    type="password" 
                    x-model="confirmaSenha"
                    :class="{ 'erro': confirmaSenha && !senhasConferem }"
                    placeholder="Digite a senha novamente">
                <div x-show="confirmaSenha && !senhasConferem" class="mensagem-erro">
                    As senhas não conferem
                </div>
            </div>
            
            <button 
                type="submit" 
                :disabled="!formularioValido">
                Cadastrar
            </button>
        </form>
        
        <!-- Mensagem de sucesso -->
        <div x-show="enviado" class="sucesso">
            ✓ Cadastro realizado com sucesso!
        </div>
    </div>
</body>
</html>
```

**Conceitos demonstrados:**
- Getters computados (get)
- Validação em tempo real
- Classes condicionais com :class
- Desabilitar botão com :disabled
- @submit.prevent

### Exemplo 4: Lista de Tarefas (To-Do)

Um clássico exemplo para demonstrar manipulação de arrays.

```html
<!DOCTYPE html>
<html>
<head>
    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
    <style>
        .todo-app {
            max-width: 500px;
            margin: 2rem auto;
            padding: 2rem;
            background: #f8f9fa;
            border-radius: 8px;
        }
        .adicionar {
            display: flex;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }
        .adicionar input {
            flex: 1;
            padding: 0.75rem;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        .adicionar button {
            padding: 0.75rem 1.5rem;
            background: #28a745;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        .tarefas {
            list-style: none;
            padding: 0;
        }
        .tarefa {
            background: white;
            padding: 1rem;
            margin-bottom: 0.5rem;
            border-radius: 4px;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        .tarefa.completa {
            opacity: 0.6;
            text-decoration: line-through;
        }
        .tarefa input[type="checkbox"] {
            width: 20px;
            height: 20px;
        }
        .tarefa span {
            flex: 1;
        }
        .tarefa button {
            padding: 0.25rem 0.75rem;
            background: #dc3545;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        .estatisticas {
            margin-top: 1rem;
            padding: 1rem;
            background: white;
            border-radius: 4px;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="todo-app" x-data="{
        novaTarefa: '',
        tarefas: [
            { id: 1, texto: 'Aprender Alpine.js', completa: false },
            { id: 2, texto: 'Criar um projeto', completa: false }
        ],
        proximoId: 3,
        
        adicionar() {
            if (this.novaTarefa.trim() !== '') {
                this.tarefas.push({
                    id: this.proximoId++,
                    texto: this.novaTarefa,
                    completa: false
                })
                this.novaTarefa = ''
            }
        },
        
        remover(id) {
            this.tarefas = this.tarefas.filter(t => t.id !== id)
        },
        
        get totalTarefas() {
            return this.tarefas.length
        },
        
        get tarefasCompletas() {
            return this.tarefas.filter(t => t.completa).length
        },
        
        get tarefasPendentes() {
            return this.totalTarefas - this.tarefasCompletas
        }
    }">
        <h2>📝 Lista de Tarefas</h2>
        
        <!-- Adicionar nova tarefa -->
        <div class="adicionar">
            <input 
                type="text" 
                x-model="novaTarefa"
                @keyup.enter="adicionar()"
                placeholder="Digite uma nova tarefa...">
            <button @click="adicionar()">Adicionar</button>
        </div>
        
        <!-- Lista de tarefas -->
        <ul class="tarefas">
            <template x-for="tarefa in tarefas" :key="tarefa.id">
                <li class="tarefa" :class="{ 'completa': tarefa.completa }">
                    <input 
                        type="checkbox" 
                        x-model="tarefa.completa">
                    <span x-text="tarefa.texto"></span>
                    <button @click="remover(tarefa.id)">Remover</button>
                </li>
            </template>
        </ul>
        
        <!-- Mensagem quando não há tarefas -->
        <div x-show="tarefas.length === 0" style="text-align: center; padding: 2rem;">
            <p>Nenhuma tarefa ainda. Adicione uma acima! 👆</p>
        </div>
        
        <!-- Estatísticas -->
        <div class="estatisticas">
            <strong>Total:</strong> <span x-text="totalTarefas"></span> |
            <strong>Completas:</strong> <span x-text="tarefasCompletas"></span> |
            <strong>Pendentes:</strong> <span x-text="tarefasPendentes"></span>
        </div>
    </div>
</body>
</html>
```

**Conceitos demonstrados:**
- x-for para listas
- Manipulação de arrays
- :key para identificação única
- Getters computados para estatísticas

### Exemplo 5: Tabs/Abas

Sistema de abas é um padrão comum em interfaces.

```html
<!DOCTYPE html>
<html>
<head>
    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
    <style>
        .tabs-container {
            max-width: 600px;
            margin: 2rem auto;
        }
        .tabs-header {
            display: flex;
            border-bottom: 2px solid #ddd;
        }
        .tab-button {
            padding: 1rem 1.5rem;
            background: none;
            border: none;
            cursor: pointer;
            font-size: 1rem;
            position: relative;
            transition: all 0.3s;
        }
        .tab-button:hover {
            background: #f0f0f0;
        }
        .tab-button.ativa {
            color: #3498db;
            font-weight: bold;
        }
        .tab-button.ativa::after {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 0;
            right: 0;
            height: 2px;
            background: #3498db;
        }
        .tab-content {
            padding: 2rem;
            background: #f8f9fa;
            border-radius: 0 0 8px 8px;
        }
    </style>
</head>
<body>
    <div class="tabs-container" x-data="{ abaAtiva: 'perfil' }">
        <h2>Configurações da Conta</h2>
        
        <!-- Botões das abas -->
        <div class="tabs-header">
            <button 
                class="tab-button"
                :class="{ 'ativa': abaAtiva === 'perfil' }"
                @click="abaAtiva = 'perfil'">
                👤 Perfil
            </button>
            <button 
                class="tab-button"
                :class="{ 'ativa': abaAtiva === 'seguranca' }"
                @click="abaAtiva = 'seguranca'">
                🔒 Segurança
            </button>
            <button 
                class="tab-button"
                :class="{ 'ativa': abaAtiva === 'notificacoes' }"
                @click="abaAtiva = 'notificacoes'">
                🔔 Notificações
            </button>
        </div>
        
        <!-- Conteúdo das abas -->
        <div class="tab-content">
            <!-- Aba Perfil -->
            <div x-show="abaAtiva === 'perfil'">
                <h3>Informações do Perfil</h3>
                <p>Atualize suas informações pessoais aqui.</p>
                <input type="text" placeholder="Nome completo" style="width: 100%; padding: 0.5rem; margin: 0.5rem 0;">
                <input type="email" placeholder="E-mail" style="width: 100%; padding: 0.5rem; margin: 0.5rem 0;">
            </div>
            
            <!-- Aba Segurança -->
            <div x-show="abaAtiva === 'seguranca'">
                <h3>Configurações de Segurança</h3>
                <p>Gerencie sua senha e opções de segurança.</p>
                <button style="padding: 0.5rem 1rem; margin: 0.5rem 0;">Alterar Senha</button>
                <br>
                <button style="padding: 0.5rem 1rem; margin: 0.5rem 0;">Ativar 2FA</button>
            </div>
            
            <!-- Aba Notificações -->
            <div x-show="abaAtiva === 'notificacoes'">
                <h3>Preferências de Notificações</h3>
                <p>Escolha como deseja receber notificações.</p>
                <label style="display: block; margin: 0.5rem 0;">
                    <input type="checkbox"> E-mail de marketing
                </label>
                <label style="display: block; margin: 0.5rem 0;">
                    <input type="checkbox" checked> Atualizações do produto
                </label>
                <label style="display: block; margin: 0.5rem 0;">
                    <input type="checkbox"> Newsletter semanal
                </label>
            </div>
        </div>
    </div>
</body>
</html>
```

**Conceitos demonstrados:**
- Estado simples para controle de abas
- Classes condicionais
- Múltiplos x-show

### Exemplo 6: Modal/Diálogo

Modais são essenciais para interações que requerem foco do usuário.

```html
<!DOCTYPE html>
<html>
<head>
    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 2rem;
        }
        .overlay {
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.5);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
        }
        .modal {
            background: white;
            padding: 2rem;
            border-radius: 8px;
            max-width: 500px;
            width: 90%;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
        }
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
        }
        .modal-header h3 {
            margin: 0;
        }
        .close-btn {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            padding: 0;
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .modal-actions {
            display: flex;
            gap: 0.5rem;
            justify-content: flex-end;
            margin-top: 1.5rem;
        }
        button {
            padding: 0.75rem 1.5rem;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 1rem;
        }
        .btn-primary {
            background: #3498db;
            color: white;
        }
        .btn-secondary {
            background: #95a5a6;
            color: white;
        }
        .btn-danger {
            background: #e74c3c;
            color: white;
        }
    </style>
</head>
<body x-data="{ 
    modalAberto: false,
    tipoModal: '',
    
    abrirModal(tipo) {
        this.tipoModal = tipo
        this.modalAberto = true
    },
    
    fecharModal() {
        this.modalAberto = false
    },
    
    confirmar() {
        alert('Ação confirmada!')
        this.fecharModal()
    }
}">
    <h1>Exemplos de Modal</h1>
    
    <button class="btn-primary" @click="abrirModal('info')">
        Abrir Modal Informativo
    </button>
    
    <button class="btn-danger" @click="abrirModal('confirmacao')">
        Abrir Modal de Confirmação
    </button>
    
    <!-- Overlay do Modal -->
    <div 
        x-show="modalAberto"
        x-transition.opacity
        class="overlay"
        @click.self="fecharModal()">
        
        <!-- Modal Informativo -->
        <div 
            x-show="tipoModal === 'info'"
            x-transition
            class="modal"
            @click.away="fecharModal()">
            
            <div class="modal-header">
                <h3>ℹ️ Informação</h3>
                <button class="close-btn" @click="fecharModal()">×</button>
            </div>
            
            <p>Este é um modal informativo. Você pode colocar qualquer conteúdo aqui.</p>
            <p>Alpine.js torna muito fácil criar modais reativos!</p>
            
            <div class="modal-actions">
                <button class="btn-primary" @click="fecharModal()">
                    Entendi
                </button>
            </div>
        </div>
        
        <!-- Modal de Confirmação -->
        <div 
            x-show="tipoModal === 'confirmacao'"
            x-transition
            class="modal">
            
            <div class="modal-header">
                <h3>⚠️ Confirmação</h3>
                <button class="close-btn" @click="fecharModal()">×</button>
            </div>
            
            <p>Tem certeza que deseja executar esta ação?</p>
            <p>Esta operação não pode ser desfeita.</p>
            
            <div class="modal-actions">
                <button class="btn-secondary" @click="fecharModal()">
                    Cancelar
                </button>
                <button class="btn-danger" @click="confirmar()">
                    Confirmar
                </button>
            </div>
        </div>
    </div>
</body>
</html>
```

**Conceitos demonstrados:**
- x-transition para animações suaves
- @click.self (clica apenas no próprio elemento)
- @click.away (clica fora do elemento)
- Múltiplos modais gerenciados por estado

---

## 5. Diretivas Avançadas

### x-for: Iteração em Listas

`x-for` permite iterar sobre arrays para criar múltiplos elementos.

**Sintaxe básica:**

```html
<template x-for="item in items" :key="item.id">
    <div x-text="item.nome"></div>
</template>
```

**⚠️ Importante:** 
- Sempre use dentro de `<template>`
- Sempre defina `:key` para performance e estabilidade

**Iterando com índice:**

```html
<div x-data="{ frutas: ['Maçã', 'Banana', 'Laranja'] }">
    <ul>
        <template x-for="(fruta, index) in frutas" :key="index">
            <li>
                <span x-text="index + 1"></span>. 
                <span x-text="fruta"></span>
            </li>
        </template>
    </ul>
</div>
```

**Iterando objetos:**

```html
<div x-data="{ 
    usuario: {
        nome: 'João',
        email: 'joao@example.com',
        idade: 30
    }
}">
    <ul>
        <template x-for="(valor, chave) in usuario" :key="chave">
            <li>
                <strong x-text="chave"></strong>: 
                <span x-text="valor"></span>
            </li>
        </template>
    </ul>
</div>
```

**Range numérico:**

```html
<div x-data="{}">
    <template x-for="i in 5" :key="i">
        <div x-text="'Item ' + i"></div>
    </template>
    <!-- Resultado: Item 1, Item 2, Item 3, Item 4, Item 5 -->
</div>
```

**Referência:** https://alpinejs.dev/directives/for

### x-bind: Atributos Dinâmicos

`x-bind` (ou `:` como atalho) vincula atributos HTML a dados reativos.

**Sintaxe:**

```html
<!-- Forma completa -->
<img x-bind:src="imagemUrl" x-bind:alt="descricao">

<!-- Atalho (preferido) -->
<img :src="imagemUrl" :alt="descricao">
```

**Exemplos comuns:**

```html
<div x-data="{
    imagemUrl: 'foto.jpg',
    linkUrl: 'https://example.com',
    desabilitado: false,
    classeDinamica: 'ativo'
}">
    <!-- Imagens -->
    <img :src="imagemUrl" alt="Foto">
    
    <!-- Links -->
    <a :href="linkUrl">Visitar site</a>
    
    <!-- Atributos booleanos -->
    <button :disabled="desabilitado">Clique</button>
    
    <!-- Classes (várias formas) -->
    <div :class="classeDinamica"></div>
    <div :class="{ 'ativo': true, 'inativo': false }"></div>
    <div :class="['classe1', 'classe2', classeDinamica]"></div>
    
    <!-- Estilos -->
    <div :style="{ color: 'red', fontSize: '20px' }"></div>
</div>
```

**Binding de múltiplos atributos:**

```html
<div x-data="{ 
    atributos: {
        id: 'meuElemento',
        class: 'destaque',
        'data-info': 'importante'
    }
}">
    <div x-bind="atributos">Conteúdo</div>
    <!-- Resultado: <div id="meuElemento" class="destaque" data-info="importante"> -->
</div>
```

**Referência:** https://alpinejs.dev/directives/bind

### x-on: Ouvindo Eventos

`x-on` (ou `@` como atalho) escuta eventos do DOM.

**Eventos nativos do navegador:**

```html
<div x-data="{ mensagem: '' }">
    <!-- Mouse events -->
    <button @click="mensagem = 'Clicou'">Click</button>
    <div @mouseenter="mensagem = 'Mouse entrou'"
         @mouseleave="mensagem = 'Mouse saiu'">
        Área sensível ao mouse
    </div>
    
    <!-- Keyboard events -->
    <input @keydown="console.log('Tecla pressionada')"
           @keyup.enter="mensagem = 'Enter!'">
    
    <!-- Form events -->
    <form @submit.prevent="mensagem = 'Formulário enviado'">
        <input type="text">
        <button type="submit">Enviar</button>
    </form>
    
    <!-- Window events -->
    <div @resize.window="console.log('Janela redimensionada')">
        Conteúdo
    </div>
    
    <p x-text="mensagem"></p>
</div>
```

**Modificadores de eventos:**

```html
<div x-data="{}">
    <!-- .prevent: event.preventDefault() -->
    <form @submit.prevent="console.log('Sem reload')">
        <button type="submit">Enviar</button>
    </form>
    
    <!-- .stop: event.stopPropagation() -->
    <div @click="console.log('Externo')">
        <button @click.stop="console.log('Só botão')">Clique</button>
    </div>
    
    <!-- .self: apenas se o evento originou do próprio elemento -->
    <div @click.self="console.log('Clicou no div, não nos filhos')">
        <button>Não dispara</button>
    </div>
    
    <!-- .once: executa apenas uma vez -->
    <button @click.once="console.log('Só uma vez')">Clique</button>
    
    <!-- .debounce: aguarda tempo sem eventos -->
    <input @input.debounce.500ms="console.log('Parou de digitar')">
    
    <!-- .throttle: limita frequência de execução -->
    <div @scroll.throttle.1000ms="console.log('Scroll')">
        Conteúdo com scroll
    </div>
    
    <!-- .passive: melhora performance de scroll -->
    <div @touchstart.passive="console.log('Touch iniciado')">
        Área touch
    </div>
    
    <!-- .camel: converte evento para camelCase -->
    <div @my-event.camel="console.log('myEvent disparado')">
        Conteúdo
    </div>
</div>
```

**Modificadores de teclas:**

```html
<div x-data="{}">
    <!-- Teclas específicas -->
    <input @keyup.enter="console.log('Enter')">
    <input @keyup.escape="console.log('Escape')">
    <input @keyup.space="console.log('Espaço')">
    <input @keyup.tab="console.log('Tab')">
    <input @keyup.delete="console.log('Delete')">
    <input @keyup.backspace="console.log('Backspace')">
    <input @keyup.arrow-up="console.log('Seta para cima')">
    <input @keyup.arrow-down="console.log('Seta para baixo')">
    
    <!-- Modificadores de teclado -->
    <input @keyup.ctrl.enter="console.log('Ctrl + Enter')">
    <input @keyup.shift.a="console.log('Shift + A')">
    <input @keyup.alt.s="console.log('Alt + S')">
    <input @keyup.meta.k="console.log('Cmd/Win + K')">
</div>
```

**Referência:** https://alpinejs.dev/directives/on

### x-transition: Animações

`x-transition` adiciona transições CSS suaves quando elementos aparecem/desaparecem.

**Transição simples:**

```html
<div x-data="{ aberto: false }">
    <button @click="aberto = !aberto">Toggle</button>
    
    <div x-show="aberto" x-transition>
        Conteúdo com transição suave
    </div>
</div>
```

**Transições customizadas:**

```html
<div x-data="{ mostrar: false }">
    <button @click="mostrar = !mostrar">Toggle</button>
    
    <!-- Apenas opacity -->
    <div x-show="mostrar" x-transition.opacity>
        Fade in/out
    </div>
    
    <!-- Apenas scale -->
    <div x-show="mostrar" x-transition.scale>
        Zoom in/out
    </div>
    
    <!-- Com duração customizada -->
    <div x-show="mostrar" x-transition.duration.500ms>
        Transição de 500ms
    </div>
    
    <!-- Entrada e saída diferentes -->
    <div x-show="mostrar"
         x-transition:enter="transition ease-out duration-300"
         x-transition:enter-start="opacity-0 transform scale-90"
         x-transition:enter-end="opacity-100 transform scale-100"
         x-transition:leave="transition ease-in duration-200"
         x-transition:leave-start="opacity-100 transform scale-100"
         x-transition:leave-end="opacity-0 transform scale-90">
        Transição customizada completa
    </div>
</div>
```

**Exemplo prático - Notificação:**

```html
<div x-data="{ 
    notificacao: false,
    mostrarNotificacao() {
        this.notificacao = true
        setTimeout(() => this.notificacao = false, 3000)
    }
}">
    <button @click="mostrarNotificacao()">
        Mostrar Notificação
    </button>
    
    <div x-show="notificacao"
         x-transition:enter="transition ease-out duration-300"
         x-transition:enter-start="opacity-0 transform translate-y-4"
         x-transition:enter-end="opacity-100 transform translate-y-0"
         x-transition:leave="transition ease-in duration-200"
         x-transition:leave-start="opacity-100 transform translate-y-0"
         x-transition:leave-end="opacity-0 transform translate-y-4"
         style="position: fixed; bottom: 20px; right: 20px; background: #28a745; color: white; padding: 1rem; border-radius: 4px;">
        ✓ Ação realizada com sucesso!
    </div>
</div>
```

**Referência:** https://alpinejs.dev/directives/transition

### x-cloak: Evitando Flash de Conteúdo

`x-cloak` oculta elementos até Alpine.js inicializar, evitando que usuários vejam código não processado.

**Problema sem x-cloak:**

```html
<!-- Usuário pode ver "{{ mensagem }}" antes do Alpine carregar -->
<div x-data="{ mensagem: 'Olá!' }">
    <p x-text="mensagem"></p>
</div>
```

**Solução com x-cloak:**

```html
<style>
    [x-cloak] { display: none !important; }
</style>

<div x-data="{ mensagem: 'Olá!' }" x-cloak>
    <p x-text="mensagem"></p>
</div>
```

**Quando Alpine inicializar, o atributo `x-cloak` é removido automaticamente.**

**Referência:** https://alpinejs.dev/directives/cloak

---

## 6. Propriedades Mágicas

Alpine.js oferece propriedades especiais prefixadas com `$` que fornecem funcionalidades úteis.

### $el: Elemento Atual

`$el` referencia o elemento DOM atual do componente.

```html
<div x-data="{ cor: 'red' }">
    <button @click="$el.style.background = cor">
        Pintar botão de vermelho
    </button>
    
    <button @click="console.log($el.offsetWidth)">
        Ver largura do botão
    </button>
</div>
```

**Referência:** https://alpinejs.dev/magics/el

### $refs: Referências a Elementos

`$refs` permite acessar elementos marcados com `x-ref`.

```html
<div x-data="{
    focar() {
        this.$refs.input.focus()
    },
    obterValor() {
        console.log(this.$refs.input.value)
    }
}">
    <input x-ref="input" type="text" placeholder="Digite algo">
    
    <button @click="focar()">Focar no input</button>
    <button @click="obterValor()">Ver valor</button>
</div>
```

**Exemplo prático - Scroll automático:**

```html
<div x-data="{
    mensagens: ['Olá', 'Como vai?'],
    novaMensagem: '',
    
    enviar() {
        if (this.novaMensagem.trim()) {
            this.mensagens.push(this.novaMensagem)
            this.novaMensagem = ''
            
            // Scroll até o final
            this.$nextTick(() => {
                this.$refs.chat.scrollTop = this.$refs.chat.scrollHeight
            })
        }
    }
}">
    <div x-ref="chat" style="height: 200px; overflow-y: auto; border: 1px solid #ddd; padding: 1rem;">
        <template x-for="msg in mensagens" :key="msg">
            <div x-text="msg" style="margin: 0.5rem 0;"></div>
        </template>
    </div>
    
    <input x-model="novaMensagem" @keyup.enter="enviar()" placeholder="Digite uma mensagem">
    <button @click="enviar()">Enviar</button>
</div>
```

**Referência:** https://alpinejs.dev/magics/refs

### $watch: Observando Mudanças

`$watch` permite reagir a mudanças em propriedades específicas.

```html
<div x-data="{
    nome: '',
    email: '',
    
    init() {
        this.$watch('nome', valor => {
            console.log('Nome mudou para:', valor)
        })
        
        this.$watch('email', (novoValor, valorAntigo) => {
            console.log('Email mudou de', valorAntigo, 'para', novoValor)
        })
    }
}">
    <input x-model="nome" placeholder="Nome">
    <input x-model="email" placeholder="E-mail">
</div>
```

**Observando objetos aninhados:**

```html
<div x-data="{
    usuario: {
        nome: 'João',
        idade: 30
    },
    
    init() {
        // Observa apenas 'nome'
        this.$watch('usuario.nome', valor => {
            console.log('Nome do usuário mudou:', valor)
        })
        
        // Observa qualquer mudança no objeto
        this.$watch('usuario', valor => {
            console.log('Usuário mudou:', valor)
        })
    }
}">
    <input x-model="usuario.nome">
    <input x-model.number="usuario.idade" type="number">
</div>
```

**Referência:** https://alpinejs.dev/magics/watch

### $dispatch: Eventos Customizados

`$dispatch` dispara eventos customizados que podem ser ouvidos por outros componentes.

```html
<div @notificacao.window="alert($event.detail.mensagem)">
    <div x-data="{}">
        <button @click="$dispatch('notificacao', { mensagem: 'Olá do componente filho!' })">
            Disparar Evento
        </button>
    </div>
</div>
```

**Comunicação entre componentes:**

```html
<div x-data="{ mensagens: [] }"
     @nova-mensagem.window="mensagens.push($event.detail)">
    
    <h3>Mensagens recebidas:</h3>
    <ul>
        <template x-for="msg in mensagens" :key="msg">
            <li x-text="msg"></li>
        </template>
    </ul>
</div>

<div x-data="{ texto: '' }">
    <input x-model="texto" placeholder="Digite uma mensagem">
    <button @click="$dispatch('nova-mensagem', texto); texto = ''">
        Enviar
    </button>
</div>
```

**Modificadores:**

```html
<!-- .window: dispara no objeto window -->
<button @click="$dispatch('evento', {}, { bubbles: false })">
    Não propaga
</button>

<!-- .self: evento não propaga além do elemento atual -->
<div @evento.self="console.log('Apenas neste elemento')">
```

**Referência:** https://alpinejs.dev/magics/dispatch

### $nextTick: Próximo Ciclo do DOM

`$nextTick` executa código após Alpine atualizar o DOM.

```html
<div x-data="{
    items: ['A', 'B', 'C'],
    
    adicionar() {
        this.items.push('D')
        
        // Executado ANTES do DOM atualizar
        console.log('Elementos antes:', this.$refs.lista.children.length)
        
        // Executado DEPOIS do DOM atualizar
        this.$nextTick(() => {
            console.log('Elementos depois:', this.$refs.lista.children.length)
        })
    }
}">
    <ul x-ref="lista">
        <template x-for="item in items" :key="item">
            <li x-text="item"></li>
        </template>
    </ul>
    
    <button @click="adicionar()">Adicionar Item</button>
</div>
```

**Caso de uso comum - Focar em elemento adicionado:**

```html
<div x-data="{
    mostrarInput: false,
    
    revelarInput() {
        this.mostrarInput = true
        this.$nextTick(() => {
            this.$refs.novoInput.focus()
        })
    }
}">
    <button @click="revelarInput()" x-show="!mostrarInput">
        Adicionar campo
    </button>
    
    <input x-show="mostrarInput" x-ref="novoInput" placeholder="Digite aqui">
</div>
```

**Referência:** https://alpinejs.dev/magics/nextTick

---

## 7. Estado Global

### Alpine.store(): Gerenciamento de Estado

Para compartilhar estado entre múltiplos componentes, use `Alpine.store()`.

**Definindo uma store:**

```html
<script>
    document.addEventListener('alpine:init', () => {
        Alpine.store('carrinho', {
            items: [],
            
            adicionar(produto) {
                this.items.push(produto)
            },
            
            remover(index) {
                this.items.splice(index, 1)
            },
            
            get total() {
                return this.items.reduce((sum, item) => sum + item.preco, 0)
            },
            
            get quantidade() {
                return this.items.length
            }
        })
    })
</script>
```

**Acessando a store:**

```html
<!-- Componente 1: Adicionar ao carrinho -->
<div x-data="{
    produto: { nome: 'Livro Alpine.js', preco: 50 }
}">
    <button @click="$store.carrinho.adicionar(produto)">
        Adicionar ao Carrinho
    </button>
</div>

<!-- Componente 2: Exibir carrinho -->
<div x-data>
    <h3>Carrinho (<span x-text="$store.carrinho.quantidade"></span>)</h3>
    
    <ul>
        <template x-for="(item, index) in $store.carrinho.items" :key="index">
            <li>
                <span x-text="item.nome"></span> - 
                R$ <span x-text="item.preco"></span>
                <button @click="$store.carrinho.remover(index)">X</button>
            </li>
        </template>
    </ul>
    
    <p>Total: R$ <strong x-text="$store.carrinho.total"></strong></p>
</div>
```

**Referência:** https://alpinejs.dev/globals/alpine-store

### Compartilhando Dados Entre Componentes

**Exemplo completo - Sistema de notificações:**

```html
<!DOCTYPE html>
<html>
<head>
    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
    <style>
        .notificacoes {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 1000;
            width: 300px;
        }
        .notificacao {
            background: white;
            border-left: 4px solid #3498db;
            padding: 1rem;
            margin-bottom: 0.5rem;
            border-radius: 4px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        .notificacao.sucesso { border-color: #28a745; }
        .notificacao.erro { border-color: #e74c3c; }
        .notificacao.aviso { border-color: #f39c12; }
    </style>
</head>
<body>
    <script>
        document.addEventListener('alpine:init', () => {
            Alpine.store('notificacoes', {
                items: [],
                proximoId: 1,
                
                adicionar(mensagem, tipo = 'info') {
                    const id = this.proximoId++
                    this.items.push({ id, mensagem, tipo })
                    
                    // Remove automaticamente após 5 segundos
                    setTimeout(() => this.remover(id), 5000)
                },
                
                remover(id) {
                    this.items = this.items.filter(item => item.id !== id)
                },
                
                sucesso(mensagem) {
                    this.adicionar(mensagem, 'sucesso')
                },
                
                erro(mensagem) {
                    this.adicionar(mensagem, 'erro')
                },
                
                aviso(mensagem) {
                    this.adicionar(mensagem, 'aviso')
                }
            })
        })
    </script>
    
    <!-- Componente de notificações (sempre visível) -->
    <div class="notificacoes" x-data>
        <template x-for="notif in $store.notificacoes.items" :key="notif.id">
            <div 
                class="notificacao"
                :class="notif.tipo"
                x-transition:enter="transition ease-out duration-300"
                x-transition:enter-start="opacity-0 transform translate-x-full"
                x-transition:enter-end="opacity-100 transform translate-x-0">
                <div x-text="notif.mensagem"></div>
                <button @click="$store.notificacoes.remover(notif.id)" 
                        style="float: right; background: none; border: none; cursor: pointer;">
                    ×
                </button>
            </div>
        </template>
    </div>
    
    <!-- Componentes que disparam notificações -->
    <div style="padding: 2rem;">
        <h2>Sistema de Notificações</h2>
        
        <button @click="$store.notificacoes.sucesso('Operação concluída!')">
            Notificação de Sucesso
        </button>
        
        <button @click="$store.notificacoes.erro('Erro ao processar!')">
            Notificação de Erro
        </button>
        
        <button @click="$store.notificacoes.aviso('Atenção necessária!')">
            Notificação de Aviso
        </button>
        
        <button @click="$store.notificacoes.adicionar('Informação geral')">
            Notificação Info
        </button>
    </div>
</body>
</html>
```

---

## 8. Boas Práticas

### Organização do Código

**1. Mantenha componentes pequenos e focados:**

```html
<!-- ❌ Evite: componente gigante com muita lógica -->
<div x-data="{ /* 50 linhas de lógica */ }">
    <!-- Conteúdo complexo -->
</div>

<!-- ✅ Prefira: componentes menores e reutilizáveis -->
<script>
    document.addEventListener('alpine:init', () => {
        Alpine.data('formularioUsuario', () => ({
            // Lógica isolada e reutilizável
        }))
    })
</script>

<div x-data="formularioUsuario">
    <!-- Conteúdo -->
</div>
```

**2. Use Alpine.data() para componentes reutilizáveis:**

```javascript
document.addEventListener('alpine:init', () => {
    // Componente dropdown reutilizável
    Alpine.data('dropdown', () => ({
        aberto: false,
        toggle() {
            this.aberto = !this.aberto
        },
        fechar() {
            this.aberto = false
        }
    }))
})
```

**3. Separe lógica complexa em funções:**

```html
<div x-data="{
    usuarios: [],
    carregando: false,
    erro: null,
    
    async buscarUsuarios() {
        this.carregando = true
        this.erro = null
        
        try {
            const response = await fetch('/api/usuarios')
            this.usuarios = await response.json()
        } catch (e) {
            this.erro = 'Erro ao carregar usuários'
        } finally {
            this.carregando = false
        }
    },
    
    init() {
        this.buscarUsuarios()
    }
}">
    <!-- Template -->
</div>
```

### Performance

**1. Use x-if para conteúdo pesado:**

```html
<!-- ❌ x-show mantém no DOM (pode ser lento com muito conteúdo) -->
<div x-show="mostrar">
    <!-- 1000 linhas de conteúdo -->
</div>

<!-- ✅ x-if remove do DOM completamente -->
<template x-if="mostrar">
    <div>
        <!-- 1000 linhas de conteúdo -->
    </div>
</template>
```

**2. Use debounce/throttle para eventos frequentes:**

```html
<!-- ❌ Evite: executa a cada tecla -->
<input @input="buscarAPI()">

<!-- ✅ Melhor: aguarda pausa na digitação -->
<input @input.debounce.500ms="buscarAPI()">

<!-- ✅ Para scroll: limita frequência -->
<div @scroll.throttle.100ms="verificarPosicao()">
```

**3. Memoize cálculos complexos com getters:**

```html
<div x-data="{
    items: [...],
    
    // ❌ Evite: recalcula toda vez
    filtrados() {
        return this.items.filter(/* lógica complexa */)
    },
    
    // ✅ Melhor: usa getter (Alpine cacheia automaticamente)
    get filtrados() {
        return this.items.filter(/* lógica complexa */)
    }
}">
```

**4. Use :key corretamente em x-for:**

```html
<!-- ❌ Evite: índice pode causar problemas -->
<template x-for="(item, index) in items" :key="index">

<!-- ✅ Melhor: use ID único -->
<template x-for="item in items" :key="item.id">
```

### Acessibilidade

**1. Mantenha HTML semântico:**

```html
<!-- ❌ Evite -->
<div @click="enviar()">Enviar</div>

<!-- ✅ Melhor -->
<button @click="enviar()">Enviar</button>
```

**2. Use atributos ARIA quando necessário:**

```html
<div x-data="{ aberto: false }">
    <button 
        @click="aberto = !aberto"
        :aria-expanded="aberto"
        aria-controls="conteudo">
        Toggle
    </button>
    
    <div 
        id="conteudo"
        x-show="aberto"
        role="region">
        Conteúdo
    </div>
</div>
```

**3. Gerencie foco adequadamente:**

```html
<div x-data="{ modalAberto: false }">
    <button @click="modalAberto = true">Abrir Modal</button>
    
    <div x-show="modalAberto"
         x-trap="modalAberto">
        <!-- x-trap mantém foco dentro do modal -->
        <button @click="modalAberto = false">Fechar</button>
    </div>
</div>
```

**Referência:** https://alpinejs.dev/directives/trap

### Quando NÃO Usar Alpine.js

Alpine.js é ótimo, mas não é ideal para tudo:

**Considere alternativas quando:**

1. **SPA complexa com roteamento:** Use Vue, React ou Svelte
2. **Precisa de SSR (Server-Side Rendering):** Next.js, Nuxt, SvelteKit
3. **Aplicação muito grande:** Frameworks maiores têm melhor estrutura
4. **Precisa de ecosistema robusto:** React/Vue têm mais bibliotecas
5. **Time grande precisa de padrões rígidos:** Frameworks opinativos ajudam

**Alpine.js é perfeito para:**
- Adicionar interatividade a sites existentes
- Protótipos rápidos
- Dashboards admin simples
- Componentes isolados
- Quando você quer simplicidade

---

## 9. Integração e Ecosistema

### Alpine.js com Laravel

Laravel e Alpine.js são uma combinação perfeita, especialmente com Livewire.

**Instalação em projeto Laravel:**

```bash
npm install alpinejs
```

**app.js:**

```javascript
import Alpine from 'alpinejs'

window.Alpine = Alpine

Alpine.start()
```

**Blade template:**

```blade
<div x-data="{ aberto: false }">
    <button @click="aberto = !aberto">Toggle</button>
    <div x-show="aberto">Conteúdo</div>
</div>
```

**Com Livewire:**

```blade
<div>
    @livewire('meu-componente')
</div>

<script>
    // Alpine funciona perfeitamente com Livewire
    Alpine.data('dropdown', () => ({
        aberto: false
    }))
</script>
```

**Referência:** https://laravel-livewire.com/docs/alpine-js

### Alpine.js com Rails

**Via importmap (Rails 7+):**

```ruby
# config/importmap.rb
pin "alpinejs", to: "https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/module.esm.js"
```

```javascript
// app/javascript/application.js
import Alpine from 'alpinejs'

window.Alpine = Alpine
Alpine.start()
```

**ERB templates:**

```erb
<div x-data="{ count: 0 }">
    <button @click="count++">Incrementar</button>
    <span x-text="count"></span>
</div>
```

### Plugins Úteis

**1. Alpine.js Persist** - Persiste estado em localStorage

```html
<script defer src="https://cdn.jsdelivr.net/npm/@alpinejs/persist@3.x.x/dist/cdn.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>

<div x-data="{ 
    tema: $persist('light'),
    contador: $persist(0)
}">
    <button @click="tema = tema === 'light' ? 'dark' : 'light'">
        Alternar Tema: <span x-text="tema"></span>
    </button>
    
    <button @click="contador++">
        Contador: <span x-text="contador"></span>
    </button>
</div>
```

**Referência:** https://alpinejs.dev/plugins/persist

**2. Alpine.js Focus** - Gerenciamento avançado de foco

```html
<script defer src="https://cdn.jsdelivr.net/npm/@alpinejs/focus@3.x.x/dist/cdn.min.js"></script>

<div x-data="{ aberto: false }">
    <button @click="aberto = true">Abrir Menu</button>
    
    <div x-show="aberto" x-trap="aberto">
        <input type="text">
        <button>Item 1</button>
        <button @click="aberto = false">Fechar</button>
    </div>
</div>
```

**Referência:** https://alpinejs.dev/plugins/focus

**3. Alpine.js Collapse** - Animações de colapso

```html
<script defer src="https://cdn.jsdelivr.net/npm/@alpinejs/collapse@3.x.x/dist/cdn.min.js"></script>

<div x-data="{ expandido: false }">
    <button @click="expandido = !expandido">Toggle</button>
    
    <div x-show="expandido" x-collapse>
        Conteúdo que colapsa suavemente
    </div>
</div>
```

**Referência:** https://alpinejs.dev/plugins/collapse

**4. Alpine.js Mask** - Máscaras de input

```html
<script defer src="https://cdn.jsdelivr.net/npm/@alpinejs/mask@3.x.x/dist/cdn.min.js"></script>

<div x-data>
    <input x-mask="(999) 999-9999" placeholder="(555) 555-5555">
    <input x-mask="99/99/9999" placeholder="12/31/2024">
    <input x-mask="$999,999.99" placeholder="$123,456.78">
</div>
```

**Referência:** https://alpinejs.dev/plugins/mask

**5. Alpine.js Morph** - Morphing de DOM

Útil para atualizar DOM preservando estado (usado com Livewire).

```javascript
Alpine.morph(elemento, novoHTML)
```

**Referência:** https://alpinejs.dev/plugins/morph

---

## 10. Recursos e Referências

### Documentação Oficial

**Site principal:**
https://alpinejs.dev/

**Documentação essencial:**
- Getting Started: https://alpinejs.dev/essentials/installation
- Directives: https://alpinejs.dev/directives/data
- Magics: https://alpinejs.dev/magics/el
- Globals: https://alpinejs.dev/globals/alpine-data
- Plugins: https://alpinejs.dev/plugins/persist

**GitHub:**
https://github.com/alpinejs/alpine

### Tutoriais e Cursos

**Tutoriais gratuitos:**

1. **Alpine.js Crash Course** (YouTube)
   - Canal: Traversy Media
   - Link: https://www.youtube.com/results?search_query=alpine+js+crash+course

2. **Learn Alpine.js** (Scrimba)
   - Curso interativo gratuito
   - Link: https://scrimba.com/

3. **Alpine.js Tutorial** (freeCodeCamp)
   - Tutoriais completos e projetos
   - Link: https://www.freecodecamp.org/

**Cursos pagos:**

1. **Alpine.js Essentials** (Laracasts)
   - Focado em integração com Laravel
   - Link: https://laracasts.com/

2. **Advanced Alpine.js** (Frontend Masters)
   - Conceitos avançados e padrões
   - Link: https://frontendmasters.com/

### Comunidade

**Discord:**
- Alpine.js Official Discord
- Link disponível no GitHub: https://github.com/alpinejs/alpine

**Twitter:**
- Criador: @calebporzio
- Hashtag: #alpinejs

**Reddit:**
- r/alpinejs
- r/laravel (muita discussão sobre Alpine + Laravel)

**Stack Overflow:**
- Tag: [alpine.js]
- Link: https://stackoverflow.com/questions/tagged/alpine.js

**Newsletter:**
- Laravel News (cobre Alpine.js frequentemente)
- Link: https://laravel-news.com/

**Blogs recomendados:**
- Blog do Caleb Porzio: https://calebporzio.com/
- Alpine Toolbox: https://www.alpinetoolbox.com/
- Codewithhugo: https://codewithhugo.com/tags/alpinejs/

---

## Conclusão

Alpine.js é uma ferramenta poderosa e elegante que traz reatividade moderna para o desenvolvimento web sem a complexidade de frameworks maiores. Com apenas 15kb e uma sintaxe intuitiva, você pode criar interfaces interativas e responsivas diretamente no HTML.

**Pontos-chave para lembrar:**

✓ Alpine.js é perfeito para adicionar interatividade progressiva
✓ A sintaxe é declarativa e fácil de aprender
✓ Use x-data para definir estado, x-show/x-if para visibilidade, x-model para inputs
✓ Propriedades mágicas ($refs, $watch, $dispatch) expandem as capacidades
✓ Alpine.store() permite compartilhar estado entre componentes
✓ Plugins oficiais adicionam funcionalidades específicas
✓ Integra perfeitamente com Laravel, Rails e outros frameworks backend

**Próximos passos sugeridos:**

1. Pratique recriando os exemplos deste guia
2. Construa um projeto pequeno (to-do list, calculadora, formulário)
3. Explore os plugins oficiais
4. Integre Alpine.js em um projeto existente
5. Contribua para a comunidade compartilhando seus aprendizados

**Lembre-se:** A melhor forma de aprender é praticando. Comece pequeno, experimente, quebre coisas e se divirta construindo interfaces reativas!

---

**Sobre este eBook:**

Este guia foi criado como material fundamental para iniciantes em Alpine.js. Todas as informações foram baseadas na documentação oficial e nas melhores práticas da comunidade.

**Última atualização:** Outubro 2025
**Versão do Alpine.js:** 3.x

Para atualizações e correções, visite: https://alpinejs.dev/

---

## Apêndice: Referência Rápida

### Diretivas Principais

| Diretiva | Descrição | Exemplo |
|----------|-----------|---------|
| x-data | Define componente e estado | `x-data="{ count: 0 }"` |
| x-text | Define conteúdo de texto | `x-text="mensagem"` |
| x-html | Define conteúdo HTML | `x-html="conteudo"` |
| x-show | Mostra/oculta com CSS | `x-show="aberto"` |
| x-if | Adiciona/remove do DOM | `x-if="existe"` |
| x-for | Loop em arrays | `x-for="item in items"` |
| x-model | Binding bidirecional | `x-model="nome"` |
| x-bind / : | Bind de atributo | `:class="classe"` |
| x-on / @ | Ouve eventos | `@click="fn()"` |
| x-transition | Adiciona transições | `x-transition` |
| x-cloak | Oculta até inicializar | `x-cloak` |
| x-ref | Cria referência | `x-ref="input"` |

### Propriedades Mágicas

| Propriedade | Descrição | Uso |
|-------------|-----------|-----|
| $el | Elemento atual | `$el.classList.add('ativo')` |
| $refs | Referências a elementos | `$refs.input.focus()` |
| $watch | Observa mudanças | `$watch('nome', fn)` |
| $dispatch | Dispara eventos | `$dispatch('evento', data)` |
| $nextTick | Próximo ciclo DOM | `$nextTick(() => {})` |
| $store | Acessa store global | `$store.carrinho.items` |

### Modificadores de Eventos

| Modificador | Descrição |
|-------------|-----------|
| .prevent | preventDefault() |
| .stop | stopPropagation() |
| .self | Apenas no próprio elemento |
| .once | Executa uma vez |
| .debounce | Adiciona debounce |
| .throttle | Adiciona throttle |
| .window | Ouve no window |
| .document | Ouve no document |

### Modificadores de Teclas

| Modificador | Tecla |
|-------------|-------|
| .enter | Enter |
| .escape | Escape |
| .space | Espaço |
| .tab | Tab |
| .delete | Delete/Backspace |
| .arrow-up | Seta cima |
| .arrow-down | Seta baixo |
| .ctrl | Ctrl |
| .shift | Shift |
| .alt | Alt |
| .meta | Cmd/Win |

---

**FIM DO EBOOK**

Bons estudos e feliz codificação com Alpine.js! 🚀
