# 01 – Entender o ambiente gratuito (Render Free Tier)

## Objetivo
Pesquisar e compreender o que é realmente gratuito no Render Free Tier, quais são os limites e os riscos envolvidos.

## Por que escolhi o Render

Inicialmente o trabalho foi planejado para ser realizado no Oracle Cloud Free Tier, conforme a proposta original. No entanto, durante a etapa de criação da conta, encontrei um obstáculo importante: a Oracle exige cartão de crédito ou débito real para verificação de identidade, mesmo no plano gratuito. Como eu não tinha um cartão disponível no momento, precisei buscar uma alternativa que permitisse cumprir os mesmos objetivos do trabalho.

Depois de pesquisar opções de ambientes gratuitos que não exigissem cartão, optei pelo **Render**. As principais razões foram:

- Não exige cartão de crédito na maioria dos casos
- Possui plano Free permanente
- Oferece deploy automático direto a partir do GitHub
- Suporta aplicações Node.js de forma simples
- Gera HTTPS automaticamente
- Permite demonstrar o ciclo completo de “código → push → aplicação no ar”

Embora o Render não ofereça o mesmo nível de controle de um servidor tradicional (como SSH, configuração de VCN e Security Lists), ele atende plenamente aos três objetivos centrais do trabalho:

1. Ter um aplicativo rodando em um ambiente próprio
2. Atualizar automaticamente a cada push no GitHub
3. Documentar todo o processo

Além disso, o uso do Render evidenciou um ponto importante em DevOps: nem sempre a ferramenta ideal é a mais complexa. Às vezes, a melhor escolha é aquela que permite entregar valor de forma rápida, segura e viável dentro das restrições reais do momento.

Por esses motivos, a decisão de migrar do Oracle Cloud para o Render foi tomada de forma consciente e documentada.

## Resumo do Free Tier do Render

O Render oferece um plano **Free** permanente com as seguintes características:

- Web Services gratuitos
- 750 horas de instância por mês (suficiente para 1 serviço 24/7)
- SSL automático
- Deploy automático a partir do GitHub
- Geralmente não exige cartão de crédito

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
- [Oracle Cloud Free Tier](https://www.oracle.com/cloud/free/)
- Uso de IA: Grok (xAI) para orientação e estruturação

## Conclusão do capítulo
O Render Free Tier atende perfeitamente ao objetivo do trabalho (app no ar + deploy automático), com a vantagem de não exigir cartão. As limitações (principalmente o cold start) foram compreendidas e documentadas.
