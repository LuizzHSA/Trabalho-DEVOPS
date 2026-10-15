# Da pesquisa à entrega automática: do seu repositório ao ar

Trabalho prático de DevOps usando **Oracle Cloud Free Tier** + servidor mínimo + **GitHub Actions**.

## Objetivo
Ter um aplicativo rodando em um servidor próprio na Oracle Cloud, atualizado automaticamente a cada `git push`, documentado em 9 capítulos.

## Status dos capítulos

| Capítulo | Título                                      | Status          |
|----------|---------------------------------------------|-----------------|
| 01       | Entender o Oracle Cloud Free Tier           | ✅ Completo     |
| 02       | Criar a conta com segurança e controle de gastos | 🟡 Aguardando cartão |
| 03       | Entender e montar a rede                    | ✅ Conteúdo pronto |
| 04       | Criar a instância e acessar por SSH         | ✅ Conteúdo pronto |
| 05       | Deixar o servidor mínimo e seguro           | ✅ Conteúdo pronto |
| 06       | Escolher o app pronto                       | ✅ Completo     |
| 07       | Publicar o app manualmente                  | ✅ Conteúdo pronto |
| 08       | Montar o CI/CD com GitHub                   | ✅ Conteúdo pronto |
| 09       | Validar e refletir                          | ✅ Conteúdo pronto |

## Links importantes
- **Aplicação em produção**: _ainda não publicado_
- **Repositório**: [https://github.com/LuizzHSA/Trabalho-DEVOPS](https://github.com/LuizzHSA/Trabalho-DEVOPS)
- **PDF final**: `trabalho-devops.pdf` (gerado a partir dos capítulos)

## Estrutura do repositório
```text
chapters/          → capítulos em Markdown
images/            → todos os prints de tela
app/               → código do aplicativo
.github/workflows/ → pipeline de CI/CD
```

## Como gerar o PDF final
```bash
# Com pandoc (recomendado)
pandoc chapters/*.md -o trabalho-devops.pdf --toc --toc-depth=2 -V geometry:margin=2cm
```
