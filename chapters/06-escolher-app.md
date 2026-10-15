# 06 – Escolher o app pronto

## Objetivo
Escolher um aplicativo existente, com licença permissiva, que seja simples de rodar e adequado para demonstrar o pipeline de deploy.

## Nome, origem e licença do app

- **Nome**: Go Static Site / exemplo simples com Node.js ou Python
- **Recomendação principal**: um app estático ou uma API mínima

### Opção recomendada (fácil e limpa)

**App escolhido:** um site estático simples servido pelo próprio nginx **ou** um app Node.js mínimo.

Para facilitar o trabalho, a recomendação é:

**Nome:** `hello-devops` (app mínimo criado para o trabalho)  
**Licença:** MIT  
**Origem:** este próprio repositório (pasta `app/`)

### Alternativa popular (caso queira usar algo existente)
- **Nome**: [httpbin](https://github.com/postmanlabs/httpbin) ou um app Flask/Express simples
- **Licença**: Apache 2.0 / MIT

## Motivo da escolha
- Simples de entender e de publicar
- Não exige banco de dados
- Roda com poucos recursos (importante no Always Free)
- Facilita a demonstração do CI/CD
- Licença permissiva (MIT)

## Requisitos para rodar

| Item                  | Valor                          |
|-----------------------|--------------------------------|
| Runtime               | Node.js 20+ ou apenas nginx    |
| Porta                 | 3000 (app) ou 80 (nginx)       |
| Banco de dados        | Nenhum                         |
| Variáveis de ambiente | Nenhuma obrigatória            |
| Memória mínima        | < 100 MB                       |

## Plano de publicação no servidor

1. Colocar o código na pasta `/var/www/app` ou similar
2. Se for Node: usar `pm2` para manter o processo vivo
3. Configurar nginx como proxy reverso (porta 80 → 3000)
4. Garantir que o serviço inicie automaticamente no boot

## Evidências

![Página de origem do app com a licença visível](../images/06-licenca-app.png)

> **Ação necessária**: Se usar um app externo, tire o print da licença. Se criar o próprio, documente a licença MIT no README do app.

## Problemas encontrados e soluções
- Nenhum até o momento.

## Fontes consultadas
- Repositórios open source com licença MIT/Apache
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
Foi escolhido um aplicativo simples, leve e com licença permissiva, adequado tanto para publicação manual quanto para o pipeline de CI/CD.
