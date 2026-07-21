# Lição 5 — Conflitos de merge

## Objetivo

Aprender por que conflitos acontecem, como resolvê-los e como cancelar uma tentativa de merge com segurança.

## Quando surge um conflito?

Git normalmente combina mudanças automaticamente. Um conflito ocorre quando mudanças diferentes atingem a mesma região e Git não consegue decidir qual resultado representa a intenção da equipe.

Os marcadores têm esta aparência:

```text
| <<<<<<< HEAD
conteúdo da branch atual
| =======
conteúdo que está chegando
| >>>>>>> outra-branch
```

O caractere `|` foi acrescentado apenas para que o próprio Git não interprete este exemplo como um conflito ainda não resolvido.

Esses marcadores não escolhem um vencedor. Eles delimitam a decisão que precisa ser tomada por uma pessoa.

## Exercício em dupla

1. As duas pessoas criam branches a partir do mesmo `main`.
2. Cada uma substitui a primeira linha de `receita-de-bolo.md` por um texto diferente.
3. Ambas criam um commit.
4. Integre a primeira branch em `main`.
5. Tente integrar a segunda.

```bash
git switch main
git merge lesson/pessoa-a
git merge lesson/pessoa-b
```

## Resolvendo o conflito

Primeiro, identifique os arquivos:

```bash
git status
```

Abra o arquivo, remova os marcadores e escreva o conteúdo final acordado pela dupla. Depois:

```bash
git add receita-de-bolo.md
git commit
```

Confira o resultado:

```bash
git log --oneline --graph --all
git show --stat HEAD
```

## Cancelando a tentativa

Se ainda não houver uma decisão correta, volte ao estado anterior ao início do merge:

```bash
git merge --abort
```

Isso é diferente de escolher uma das versões: o merge inteiro é cancelado.

## Perguntas para discussão

- Qual foi a intenção de cada alteração?
- O resultado correto pode combinar as duas versões?
- Quem tem contexto suficiente para decidir?
- Por que remover apenas os marcadores não garante uma resolução correta?
