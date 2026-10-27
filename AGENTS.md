# APEX — Marca Pessoal · site institucional

Instruções do projeto. Quem abrir esta pasta lê isto automaticamente, de qualquer
máquina e de qualquer conta — é o que faz duas pessoas trabalharem igual sem
combinar por mensagem.

Atualize junto com o código: decisão que não está escrita aqui some na primeira
troca de mão.

---

## O que é

Landing page institucional, **HTML estático**. Sem build, sem framework, sem
dependência: abre do disco com dois cliques.

```
index.html          monta a página
sections/*.html     uma seção por arquivo
```

As seções, na ordem em que entram: `hero`, `manifesto`, `metodologia`,
`servicos`, `diferenciais`, `digital-pr`, `conexao`, `sobre`, `contato`.

**Para mudar uma seção, edite o arquivo dela em `sections/`** — não o
`index.html`. O `index.html` só monta; mexer nele para alterar conteúdo quebra a
separação que torna a página editável por quem não é programador.

## O que este projeto não tem, de propósito

Não há servidor, banco de dados nem etapa de build. **Nenhuma página grava dado
nenhum.** Se algo pedir formulário que persiste, é projeto novo, não é esta
página — e a decisão de onde ele mora vem antes do código.

## A regra que explica a estrutura

**Transferência não é migração.** Este projeto foi montado para trocar de dono, e
não para ser exportado e remontado do outro lado.

Disso vem a regra mais importante: **um repositório por projeto, nunca um
repositório só para tudo.** É o que permite um projeto sair sem levar o histórico
do vizinho. Projeto novo nasce como pasta irmã desta, com `git init` próprio —
nunca como subpasta deste repositório.

## Como contribuir sem atropelar o deploy

O deploy sai do Git do titular. Push direto no branch de produção **publica sem
ninguém ver**.

```
git switch -c <autor>/<o-que-mudou>
git push -u origin <autor>/<o-que-mudou>
gh pr create
```

O Pull Request é o ponto de entrega: quem é dono revisa e faz o merge, e **o
merge é que publica**. Vale para colaborador externo e para quem é titular.

## O que nunca entra em commit

`.env` e variantes, `node_modules/`, `.vercel/` — já cobertos pelo `.gitignore`.
Chave de API, token e senha não entram neste repositório em hipótese nenhuma:
ele é pequeno, estático e feito para trocar de mão, então tudo que entra aqui
viaja junto para sempre.

`.claude/settings.local.json` é pessoal de cada máquina e também fica de fora.
Já `AGENTS.md` e `.claude/skills/` são para compartilhar — é o que faz o projeto
ser entendido do mesmo jeito por quem chegar depois.

⚠ **Este repositório é público.** Então o que entra em `.claude/skills/` aqui é só
o que diz respeito a esta página. O método da casa — nomenclatura, abertura de
cliente, padrões de trabalho — mora no repositório `contexto`, que é privado.
Regra da casa escrita aqui fica legível por qualquer pessoa, e fechar o
repositório depois não apaga o que já foi lido ou clonado.
