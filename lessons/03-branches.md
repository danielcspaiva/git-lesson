# Lição 3 — Branches

## Objetivo

Entender como branches permitem desenvolver ideias separadamente sem duplicar o repositório.

## Modelo mental

Uma branch é um nome móvel que aponta para um commit. Ao criar novos commits, a branch atual avança.

```text
main:       A──B
                \
feature:         C──D
```

## Comandos essenciais

Listar branches e identificar a atual:

```bash
git branch
```

Criar uma branch e mudar para ela:

```bash
git switch -c lesson/<seu-nome>
```

Voltar para uma branch existente:

```bash
git switch main
```

## Exercício em dupla

Cada participante deve começar a partir de `main` e criar sua própria branch:

```bash
git switch main
git pull --ff-only
git switch -c lesson/<seu-nome>
```

Depois:

1. Crie um arquivo chamado `<seu-nome>.md`.
2. Escreva três fatos sobre você.
3. Faça um commit.
4. Compare sua branch com `main`.

```bash
git add <seu-nome>.md
git commit -m "Add <seu-nome> introduction"
git diff main...HEAD
```

## Integrando o trabalho

Para praticar localmente:

```bash
git switch main
git merge lesson/<seu-nome>
```

Em trabalho compartilhado, prefira abrir um pull request. Isso cria um espaço para revisão e conversa antes da integração.

## Perguntas para discussão

- Criar uma branch copia todos os arquivos?
- Por que `main` não muda quando você faz commits em outra branch?
- O que acontece com a branch depois que seu trabalho é integrado?
