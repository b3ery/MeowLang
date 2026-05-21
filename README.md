# 🐱 MeowLang — Linguagem Esotérica Felina

<div align="center">

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Analisador Léxico](https://img.shields.io/badge/Analisador-Léxico-00e5ff?style=flat-square)

> **MeowLang** é uma linguagem de programação esotérica com tema felino, desenvolvida como trabalho prático da disciplina de **Linguagens Formais e Autômatos**. O projeto implementa um **analisador léxico completo** com interpretador, tabela de símbolos, detecção de erros e log de compilação animado.

</div>

---

## 👥 Equipe

| Nome | RA |
|------|-----|
| Andressa Rabêlo   | 823213904 |
| Júlia Oliveira    | 823214680 |
| Lucas Marzocca    | 823116813 |
| Marcos V. Santos  | 82327399  |
| Matheus H. F.     | 823141914 |
| Mylena Soares     | 824144075 |

**Disciplina:** Linguagens Formais e Autômatos — Universidade São Judas Tadeu · 2026

---

## 🚀 Como Executar

Sem dependências externas. Apenas abra o arquivo no navegador:

```bash
# Clone o repositório
git clone https://github.com/seu-grupo/meowlang.git
cd meowlang

# Abra no navegador
open meowlang.html
# ou arraste o arquivo para o navegador
```

---

## 🐱 Gramática MeowLang

### Tipos de Variáveis

| Palavra-chave | Equivalente | Descrição |
|---|---|---|
| `psiu` | `var` | Variável genérica |
| `psiu_int` | `int` | Número inteiro |
| `psiu_float` | `float` | Número decimal |
| `psiu_string` | `string` | Texto |
| `psiu_bool` | `bool` | Booleano |
| `psiu_lista` | `array` | Lista |
| `ronrom` | `true` | Verdadeiro |
| `bufar` | `false` | Falso |
| `dormindo` | `null` | Nulo |

### Comandos

| Palavra-chave | Equivalente | Descrição |
|---|---|---|
| `miar` | `print` | Imprime no console |
| `se_miar` | `if` | Condicional |
| `hiss` | `else` | Alternativa |
| `cacar` | `while` | Laço com condição |
| `cada_pelo` | `for` | Laço com init; cond; incr |
| `arranhar` | `return` | Retorna valor |
| `ronronar` | `function` | Declara função |
| `gatil` | `class` | Declara classe |

### Comentários

```
# comentário de linha
// também funciona
/* comentário
   de bloco */
```

---

## 📝 Exemplos de Código

### Variáveis e Print
```
psiu_string nome  = "Whiskers"
psiu_int    vidas = 9
psiu_bool   ativo = ronrom

miar("Nome: "  + nome)
miar("Vidas: " + vidas)
```

### Condicional
```
se_miar (vidas > 0) {
  miar("😸 O gato está vivo!")
} hiss {
  miar("😿 Sem vidas...")
}
```

### Loop While
```
psiu_int i = 0
cacar (i < 3) {
  miar("Vida " + i)
  psiu_int i = i + 1
}
```

### Loop For
```
cada_pelo (psiu_int n = 1; n < 6; psiu_int n = n + 1) {
  psiu_int r = n * 3
  miar(n + " x 3 = " + r)
}
```

### Função
```
ronronar saudacao(nome) {
  miar("Olá, " + nome + "! Miau!")
  arranhar ronrom
}

saudacao("Garfield")
```

### Classe
```
gatil Gato {
  psiu_string nome  = "Sem nome"
  psiu_int    vidas = 9

  ronronar apresentar(apelido) {
    miar("Eu sou " + apelido)
  }
}
```

---

## ⚙️ Funcionalidades do Analisador

| Funcionalidade | Status |
|---|---|
| Tokenização completa | ✅ |
| Eliminação de espaços em branco | ✅ |
| Eliminação de comentários (`#` `//` `/* */`) | ✅ |
| Detecção de erro léxico com número de linha | ✅ |
| Detecção de erro sintático (chaves, parênteses, strings) | ✅ |
| Tela de erro animada "Errou e Molhou o Gato 😿" | ✅ |
| Tabela de símbolos — variáveis | ✅ |
| Tabela de símbolos — funções | ✅ |
| Tabela de símbolos — classes | ✅ |
| Interpretação de `psiu` / tipos | ✅ |
| Verificação de tipo em tempo de execução | ✅ |
| Interpretação de `miar` (print) | ✅ |
| Interpretação de `se_miar` / `hiss` | ✅ |
| Interpretação de `cacar` (while) | ✅ |
| Interpretação de `cada_pelo` (for) | ✅ |
| Interpretação de `ronronar` (função) com chamada | ✅ |
| Interpretação de `gatil` (classe) | ✅ |
| Log de compilação animado (8 segundos, 15 etapas) | ✅ |

---

## 🧠 Conceitos Teóricos Implementados

### Análise Léxica
O tokenizer lê o código-fonte caractere por caractere e classifica cada sequência em um dos seguintes tipos de token:

- `KEYWORD` — palavras reservadas da linguagem
- `IDENTIFICADOR` — nomes criados pelo programador
- `NUMERO` — literais numéricos (inteiros e decimais)
- `STRING` — literais de texto entre aspas
- `OPERADOR` — operadores aritméticos e lógicos
- `DELIMITADOR` — parênteses, chaves, vírgulas
- `BOOLEAN` — `ronrom` / `bufar`
- `COMENTARIO` — removidos durante a análise

### Autômato Finito
O reconhecimento de tokens segue um autômato finito implícito: lê um caractere, decide o estado (início de palavra, número, string, operador) e avança até reconhecer o token completo.

### Tabela de Símbolos
Registra todos os identificadores encontrados — variáveis com nome, tipo e valor; funções com parâmetros e corpo; classes com atributos e métodos.

### Eliminação de Ruído
Espaços, tabs, quebras de linha e comentários são identificados e removidos antes da análise dos tokens, exatamente como compiladores reais fazem no pré-processamento.

---

## 📁 Estrutura do Projeto

```
meowlang/
├── meowlang.html              # Implementação completa (HTML + CSS + JS)
├── pesquisa_analisador_lexico.pdf  # Pesquisa teórica (item 1 do trabalho)
└── README.md                  # Este arquivo
```

---

<div align="center">
Feito com 🐾 e muito <code>miar()</code>
</div>
