# 01 – Entender o ambiente gratuito (Render Free Tier)

## Objetivo
Pesquisar e compreender o que é realmente gratuito no Render Free Tier, quais são os limites e os riscos envolvidos.

## O que foi feito
- Pesquisa da documentação oficial do Render
- Análise dos recursos do plano Free
- Identificação das limitações (cold start, horas mensais)
- Comparação com Oracle Cloud Free Tier e outras opções

## Resumo do Free Tier do Render

O Render oferece um plano **Free** permanente com as seguintes características:

- Web Services gratuitos
- 750 horas de instância por mês (suficiente para 1 serviço 24/7)
- SSL automático
- Deploy automático a partir do GitHub
- **Não exige cartão de crédito** na maioria dos casos

### Limitações importantes
- O serviço **dorme** após 15 minutos sem tráfego
- Ao receber uma nova requisição, demora cerca de 30–60 segundos para “acordar” (cold start)
- 512 MB de RAM e 0.1 CPU no plano Free

## Tabela dos recursos Free

| Recurso              | Limite Free                          | Observação |
|----------------------|--------------------------------------|----------|
| Web Service          | 1 instância                          | Dorme após 15 min idle |
| Horas de instância   | 750 horas/mês                        | Suficiente para 1 app 24/7 |
| RAM                  | 512 MB                               | |
| CPU                  | 0.1                                  | |
| Build minutes        | 500/mês                              | |
| Bandwidth            | ~100 GB/mês                          | |
| SSL                  | Grátis e automático                  | |
| Deploy do GitHub     | Sim, automático                      | |

## Riscos e como evitá-los

- Ultrapassar as 750 horas (improvável com 1 serviço)
- Exceder bandwidth (raro em trabalho acadêmico)
- Dependência do cold start (documentar essa limitação)

## Comparação com Oracle Cloud Always Free

| Critério              | Render Free                     | Oracle Always Free              |
|-----------------------|---------------------------------|---------------------------------|
| Cartão necessário     | Geralmente não                  | Sim                             |
| SSH / controle total  | Não                             | Sim                             |
| Cold start            | Sim (15 min)                    | Não                             |
| Facilidade de deploy  | Muito alta                      | Média                           |
| Recursos de compute   | Baixos                          | Altos (2 OCPU / 12 GB)          |
| Ideal para            | Apps web simples + CI/CD        | Servidor completo + aprendizado |

## Evidências
![Página oficial do Render Free](../images/01-render-free.png)

## Fontes consultadas
- [Render Documentation](https://render.com/docs)
- [Render Pricing](https://render.com/pricing)
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
O Render Free Tier atende perfeitamente ao objetivo do trabalho (app no ar + deploy automático), com a vantagem de não exigir cartão. As limitações (principalmente o cold start) foram compreendidas e serão documentadas.
