# Lição 4 — Repositório local e remoto

## Objetivo

Entender a diferença entre o histórico no computador e o histórico compartilhado no GitHub.

## Nomes importantes

- `origin` é o nome convencional do repositório remoto.
- `main` é uma branch local.
- `origin/main` é a última visão local conhecida da branch `main` no remoto.

Veja a configuração atual:

```bash
git remote -v
git branch -vv
```

## Fetch, pull e push

Baixar informações sem integrar mudanças:

```bash
git fetch origin
```

Baixar e integrar a branch correspondente:

```bash
git pull --ff-only
```

Publicar commits locais:

```bash
git push
```

Ao publicar uma branch pela primeira vez:

```bash
git push -u origin lesson/<seu-nome>
```

O `-u` registra a relação entre a branch local e a remota, permitindo usar apenas `git push` e `git pull` nas próximas vezes.

## Exercício em dupla

1. A pessoa A cria um commit em sua branch e executa `git push`.
2. A pessoa B executa `git fetch origin`.
3. A pessoa B inspeciona a branch sem modificar seu próprio trabalho.

```bash
git log --oneline --all --graph
git diff main...origin/lesson/<nome-da-pessoa-a>
```

4. A pessoa B cria uma branch local a partir da remota:

```bash
git switch -c review/<nome> origin/lesson/<nome-da-pessoa-a>
```

## Verificação antes de sincronizar

Use sempre:

```bash
git status -sb
```

Ele mostra a branch atual e se ela está à frente ou atrás da branch remota relacionada.

## Perguntas para discussão

- `git fetch` altera os arquivos de trabalho?
- Um commit local já está disponível para o colega?
- Qual relação o `-u` cria no primeiro push?
