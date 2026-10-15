# 08 – Montar o CI/CD com GitHub

## Objetivo
Configurar um pipeline com GitHub Actions que, a cada push na branch main, faça o deploy automático do aplicativo no servidor Oracle Cloud.

## Link do repositório
[https://github.com/LuizzHSA/Trabalho-DEVOPS](https://github.com/LuizzHSA/Trabalho-DEVOPS)

## Diagrama do fluxo

```text
Desenvolvedor
     |
  git push
     |
     v
GitHub Repository
     |
     v
GitHub Actions (workflow)
     |
     +---> Checkout do código
     +---> (opcional) Build / Testes
     +---> Deploy via SSH
              |
              v
        Servidor Oracle
              |
              v
         App atualizado
```

## Descrição de cada etapa do workflow

| Etapa              | Função                                                |
|--------------------|--------------------------------------------------------|
| trigger (on: push) | Dispara o pipeline a cada push na main                 |
| checkout           | Baixa o código mais recente                            |
| setup-node         | Prepara o ambiente Node.js (se necessário)             |
| deploy             | Conecta via SSH e atualiza o código + reinicia o app   |

## Segredos usados e como foram protegidos

| Segredo            | Conteúdo                              | Onde fica                          |
|--------------------|---------------------------------------|------------------------------------|
| `SSH_PRIVATE_KEY`  | Chave privada exclusiva do pipeline   | GitHub → Settings → Secrets        |
| `HOST`             | IP público do servidor                | GitHub → Settings → Secrets        |
| `USERNAME`         | Usuário SSH (ubuntu ou outro)         | GitHub → Settings → Secrets        |

**Importante:** Nunca usar a chave SSH pessoal no pipeline. Gerar uma chave específica só para o deploy.

## Exemplo de workflow (`.github/workflows/deploy.yml`)

```yaml
name: Deploy to Oracle Cloud

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Deploy via SSH
        uses: appleboy/ssh-action@v1.0.3
        with:
          host: ${{ secrets.HOST }}
          username: ${{ secrets.USERNAME }}
          key: ${{ secrets.SSH_PRIVATE_KEY }}
          script: |
            cd /var/www/app
            git pull origin main
            # npm install --production   # se for Node
            pm2 restart devops-app || pm2 start app.js --name devops-app
```

## Evidências

![Execução com sucesso na aba Actions](../images/08-actions-sucesso.png)

![Falha tratada na aba Actions](../images/08-actions-falha.png)

![App antes do push](../images/08-app-antes.png)

![App depois do push](../images/08-app-depois.png)

> **Ação necessária**: Após configurar o pipeline, fazer um push de teste e capturar os prints.

## Problemas encontrados e soluções
- Ainda não executado.

## Fontes consultadas
- Documentação oficial do GitHub Actions
- Ação `appleboy/ssh-action`
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
O pipeline de CI/CD foi configurado. Agora qualquer push na branch main atualiza automaticamente o aplicativo no servidor.
