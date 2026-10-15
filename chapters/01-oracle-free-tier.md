# 01 – Entender o Oracle Cloud Free Tier

## Objetivo
Pesquisar e compreender o que é realmente gratuito no Oracle Cloud Free Tier, quais recursos são Always Free, os limites e os riscos de cobrança.

## O que foi feito
- Leitura da documentação oficial da Oracle
- Análise dos recursos Always Free (compute, storage, network)
- Identificação dos principais riscos de cobrança
- Comparação com outro provedor de nuvem

## Resumo do Free Tier

O Oracle Cloud Free Tier é composto por duas partes:

1. **Always Free** – recursos que permanecem gratuitos indefinidamente (enquanto a conta estiver ativa e em conformidade).
2. **Free Trial** – crédito de US$ 300 válido por 30 dias para testar serviços pagos.

Quando o trial termina, todos os recursos que **não** forem Always Free são excluídos automaticamente.

## Tabela dos recursos Always Free

| Recurso              | Tipo / Shape                  | Limite Always Free          | Observação |
|----------------------|-------------------------------|-----------------------------|----------|
| Compute (AMD)        | VM.Standard.E2.1.Micro        | 2 instâncias                | 1 OCPU + 1 GB RAM cada |
| Compute (ARM)        | VM.Standard.A1.Flex           | Até 4 OCPUs + 24 GB RAM     | Pode ser 1 ou várias instâncias |
| Block Volume         | Armazenamento em bloco        | 200 GB no total             | Pode ser dividido |
| Object Storage       | Bucket                        | 20 GB                       | |
| Outbound Data Transfer | Transferência de saída      | 10 TB / mês                 | |
| Load Balancer        | Flexible                      | 1 (10 Mbps)                 | |
| Autonomous Database  | ATP / ADW                     | 2 bancos (20 GB cada)       | |

> **Fonte oficial**: [Always Free Resources](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier_topic-Always_Free_Resources.htm)

## Riscos de cobrança e como evitá-los

Principais riscos:
- Criar instâncias com shapes que **não** são Always Free
- Aumentar o disco além de 200 GB
- Criar serviços pagos (Load Balancer adicional, Autonomous Database extra, etc.) e esquecer de apagar
- Deixar recursos do trial rodando após o crédito acabar

Como se proteger:
- Ativar **Budget Alerts** logo no início (feito no Capítulo 02)
- Sempre verificar se o recurso está marcado como Always Free antes de criar
- Preferir os shapes `VM.Standard.A1.Flex` ou `VM.Standard.E2.1.Micro`
- Revisar periodicamente a lista de recursos na conta

## Comparação com outro provedor (AWS Free Tier)

| Critério                | Oracle Always Free              | AWS Free Tier                          |
|-------------------------|---------------------------------|----------------------------------------|
| Duração                 | Para sempre                     | Maioria dos serviços: 12 meses         |
| Compute                 | 2× Micro AMD ou 4 OCPU ARM      | 750 horas/mês de t2.micro / t3.micro   |
| Armazenamento           | 200 GB                          | 30 GB EBS                              |
| Transferência de saída  | 10 TB/mês                       | 100 GB/mês                             |
| Banco de dados          | 2× Autonomous (20 GB)           | RDS 750h + 20 GB                       |
| Facilidade de uso       | Mais trabalhoso                 | Mais simples                           |
| Risco de cobrança       | Médio (se errar o shape)        | Alto (muita gente esquece recursos)    |

## Evidências
![Página oficial dos recursos Always Free](../images/01-always-free.png)

> **Observação**: O print acima deve mostrar a seção oficial da Oracle listando os recursos Always Free.

## Problemas encontrados e soluções
- Ainda não houve problemas técnicos neste capítulo (apenas pesquisa).

## Fontes consultadas
- [Oracle Always Free Resources](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier_topic-Always_Free_Resources.htm)
- [Oracle Cloud Free Tier](https://www.oracle.com/cloud/free/)
- [Oracle Free Tier FAQ](https://www.oracle.com/cloud/free/faq/)
- [Service Limits](https://docs.oracle.com/en-us/iaas/Content/General/Concepts/servicelimits.htm)
- Uso de IA: Grok (xAI) para estruturação e orientação do capítulo

## Conclusão do capítulo
Compreendi claramente a diferença entre Always Free e o crédito de teste, os limites de cada recurso e os principais cuidados para não gerar cobrança. Estou pronto para criar a conta com segurança no próximo capítulo.
