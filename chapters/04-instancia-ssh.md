# 04 – Criar o serviço e fazer o primeiro deploy

## Objetivo
Criar o Web Service no Render e realizar o primeiro deploy a partir do repositório GitHub.

## Configuração escolhida e justificação

| Item              | Escolha                          | Justificativa                              |
|-------------------|----------------------------------|--------------------------------------------|
| Tipo de serviço   | Web Service                      | Adequado para aplicação Node.js            |
| Runtime           | Node                             | App escrito em Node.js                     |
| Root Directory    | `app`                            | Código fica dentro da pasta app/           |
| Build Command     | `npm install`                    | Instala dependências                       |
| Start Command     | `node server.js`                 | Inicia o servidor                          |
| Plano             | Free                             | Atende ao requisito de ambiente gratuito   |

## Acesso ao serviço

Diferente do Oracle Cloud, não existe SSH. O acesso é feito exclusivamente via HTTPS pelo link gerado pelo Render.

**URL do serviço:** https://devops-app-x1r7.onrender.com/

## Evidências
![Serviço criado e em execução](../images/04-servico-render.png)
![Primeiro deploy com sucesso](../images/04-primeiro-deploy.png)
![App respondendo no navegador](../images/04-app-no-ar.png)

## Problemas encontrados e soluções
- Nenhum problema relevante. O deploy foi bem-sucedido na primeira tentativa.

## Fontes consultadas
- Documentação do Render (Web Services)
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
O serviço foi criado e o aplicativo está acessível publicamente. O próximo passo é garantir que o ambiente esteja mínimo e documentar o processo.
