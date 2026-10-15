# Da pesquisa à entrega automática: do seu repositório ao ar

Trabalho prático de DevOps usando **Render Free Tier** + deploy automático via GitHub.

## Objetivo
Ter um aplicativo rodando em um servidor próprio (Render), atualizado automaticamente a cada `git push`, documentado em 9 capítulos.

## App em produção
**https://devops-app-x1r7.onrender.com/**

## Status dos capítulos

| Capítulo | Título                                      | Status          |
|----------|---------------------------------------------|-----------------|
| 01       | Entender o ambiente gratuito (Render)       | ✅ Completo     |
| 02       | Criar a conta com segurança                 | ✅ Completo     |
| 03       | Entender a infraestrutura do Render         | ✅ Completo     |
| 04       | Criar o serviço e fazer o primeiro deploy   | ✅ Completo     |
| 05       | Configurar o serviço de forma mínima e segura | ✅ Completo   |
| 06       | Escolher o app pronto                       | ✅ Completo     |
| 07       | Publicar o app manualmente                  | ✅ Completo     |
| 08       | Montar o CI/CD com GitHub + Render          | ✅ Completo     |
| 09       | Validar e refletir                          | ✅ Completo     |

## Links importantes
- **Aplicação em produção**: [https://devops-app-x1r7.onrender.com/](https://devops-app-x1r7.onrender.com/)
- **Repositório**: [https://github.com/LuizzHSA/Trabalho-DEVOPS](https://github.com/LuizzHSA/Trabalho-DEVOPS)
- **PDF final**: `trabalho-devops.pdf` (gerado a partir dos capítulos)

## Estrutura do repositório
```text
chapters/          → capítulos em Markdown
images/            → todos os prints de tela
app/               → código do aplicativo
.github/workflows/ → (opcional) workflows adicionais
```

## Como gerar o PDF final
```bash
pandoc chapters/*.md -o trabalho-devops.pdf --toc --toc-depth=2 -V geometry:margin=2cm
```
