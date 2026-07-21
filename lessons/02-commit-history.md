# Lição 2 — Commits e histórico

## Objetivo

Aprender a criar commits pequenos e a investigar o histórico do projeto.

## O que é um commit?

Um commit é um ponto identificável no histórico. Ele registra uma versão preparada dos arquivos, uma mensagem, um autor e a referência ao commit anterior.

Um bom commit representa uma única intenção. Por exemplo, corrigir um texto e adicionar uma funcionalidade devem ser commits diferentes.

## Explorando o histórico

Veja uma versão compacta e visual:

```bash
git log --oneline --graph --decorate --all
```

Inspecione um commit específico:

```bash
git show <hash-do-commit>
```

Compare dois pontos do histórico:

```bash
git diff <hash-antigo> <hash-novo>
```

## Exercício

1. Corrija uma frase no `README.md`.
2. Prepare e confirme somente essa correção.
3. Acrescente uma nova frase.
4. Crie um segundo commit.
5. Use `git log` e `git show` para explicar a diferença entre eles.

```bash
git add README.md
git commit -m "Fix lesson description"

# faça a segunda alteração
git add README.md
git commit -m "Add lesson objective"

git log --oneline -5
git show HEAD
git show HEAD~1
```

## Desafio

Encontre quem alterou cada linha de um arquivo:

```bash
git blame README.md
```

O objetivo de `blame` não é procurar culpados. Ele ajuda a encontrar o contexto e o commit que introduziu uma linha.

## Perguntas para discussão

- A mensagem explica o motivo ou apenas repete o conteúdo da mudança?
- Seria possível reverter esse commit sem remover trabalho não relacionado?
- O commit é pequeno o suficiente para ser revisado com facilidade?
