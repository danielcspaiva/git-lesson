# Lição 1 — Área de preparação (staging area)

## Objetivo

Entender como escolher exatamente quais alterações entrarão no próximo commit.

## Modelo mental

Uma alteração passa por três lugares locais:

```text
arquivo modificado → staging area → histórico de commits
                  git add       git commit
```

`git add` não salva definitivamente uma alteração. Ele apenas prepara uma versão do arquivo para o próximo commit.

## Exercício

1. Acrescente duas linhas diferentes ao arquivo `hello.md`.
2. Observe todas as alterações:

   ```bash
   git diff
   ```

3. Prepare o arquivo:

   ```bash
   git add hello.md
   ```

4. Compare o que ainda está fora e o que já está dentro da staging area:

   ```bash
   git diff
   git diff --staged
   ```

5. Faça mais uma alteração em `hello.md` e execute os dois comandos novamente.

## Desafio

Crie um commit contendo somente parte do que foi alterado:

```bash
git add -p hello.md
git diff --staged
git commit -m "Improve greeting"
```

## Como desfazer com segurança

Retirar um arquivo da staging area, mantendo a alteração:

```bash
git restore --staged hello.md
```

Descartar uma alteração que ainda não foi preparada:

```bash
git restore hello.md
```

Antes de cada ação, use `git status` e explique onde cada alteração está.
