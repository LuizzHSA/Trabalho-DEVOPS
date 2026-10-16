# 06 – Escolher o app pronto

## Objetivo
Escolher um aplicativo simples, com licença permissiva, adequado para rodar no Render Free Tier.

## Nome, origem e licença do app

- **Nome**: devops-app
- **Origem**: criado neste repositório (`app/`)
- **Licença**: MIT

## Motivo da escolha
- Extremamente leve (Node.js puro, sem dependências pesadas)
- Roda perfeitamente no plano Free do Render
- Fácil de entender e de modificar
- Permite demonstrar deploy automático com clareza
- Licença MIT permite uso livre

## Requisitos para rodar

| Item                  | Valor                    |
|-----------------------|--------------------------|
| Runtime               | Node.js 18+              |
| Porta                 | 3000 (ou process.env.PORT)|
| Banco de dados        | Nenhum                   |
| Variáveis de ambiente | Nenhuma obrigatória      |
| Memória               | Muito baixa (< 50 MB)    |

## Plano de publicação
1. Código já está no repositório
2. Conectar o repositório ao Render
3. Definir Root Directory = `app`
4. Build: `npm install`
5. Start: `node server.js`

## Evidências
O código do app e a licença MIT estão disponíveis na pasta `app/` deste repositório.

## Fontes consultadas
- Este repositório
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
Foi escolhido um aplicativo mínimo, leve e com licença permissiva, ideal para o ambiente gratuito do Render.
