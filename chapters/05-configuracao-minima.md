# 05 – Configurar o serviço de forma mínima e segura

## Objetivo
Manter o serviço o mais simples possível, usando apenas o necessário e aproveitando as proteções nativas do Render.

## O que foi configurado

| Item                    | Configuração                     | Motivo |
|-------------------------|----------------------------------|--------|
| Runtime                 | Node                             | App é Node.js |
| Porta                   | 3000 (padrão do app)             | Render detecta automaticamente |
| HTTPS                   | Automático                       | Fornecido pelo Render |
| Variáveis de ambiente   | Nenhuma sensível                 | App não precisa de secrets |
| Auto-Deploy             | Ativado                          | Deploy a cada push |

## Comandos / configuração usada

No painel do Render:
- Root Directory: `app`
- Build Command: `npm install`
- Start Command: `node server.js`

No código do app:
```js
const PORT = process.env.PORT || 3000;
```
O Render injeta a variável `PORT` automaticamente.

## Proteções nativas aproveitadas
- HTTPS obrigatório
- Isolamento de container
- Deploy apenas a partir do repositório autorizado
- Logs disponíveis no painel

## Evidências
![App respondendo](../images/app-no-ar.png)

## Fontes consultadas
- Documentação do Render
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
O serviço está configurado de forma mínima e segura, aproveitando os recursos nativos do Render sem adicionar complexidade desnecessária.
