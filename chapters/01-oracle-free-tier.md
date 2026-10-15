# 01 – Entender o Oracle Cloud Free Tier

## Objetivo
Pesquisar e compreender o que é realmente gratuito no Oracle Cloud Free Tier, quais recursos são Always Free, os limites e os riscos de cobrança.

## O que foi feito
- Leitura da documentação oficial da Oracle
- Análise dos recursos Always Free (compute, storage, network)
- Identificação dos principais riscos de cobrança
- Comparação com outro provedor de nuvem (AWS)

## Resumo do Free Tier

O Oracle Cloud Free Tier é composto por duas partes distintas:

1. **Always Free** – recursos que permanecem gratuitos **indefinidamente**, desde que a conta esteja ativa e em conformidade com os termos.
2. **Free Trial** – crédito de **US$ 300** válido por **30 dias** para testar praticamente todos os serviços da Oracle Cloud.

Quando o período de trial termina:
- Todos os recursos que **não** forem Always Free são automaticamente excluídos.
- Os recursos Always Free continuam funcionando normalmente.

## Tabela dos recursos Always Free (valores atuais – 2026)

| Recurso                  | Tipo / Shape                      | Limite Always Free                          | Observação |
|--------------------------|-----------------------------------|---------------------------------------------|----------|
| Compute AMD              | VM.Standard.E2.1.Micro            | 2 instâncias                                | 1/8 OCPU + 1 GB RAM cada |
| Compute ARM (Ampere A1)  | VM.Standard.A1.Flex               | 1.500 OCPU-hours + 9.000 GB-hours por mês  | Equivale a **2 OCPUs + 12 GB RAM** contínuos |
| Block Volume             | Armazenamento em bloco            | 200 GB no total                             | Mínimo ~47 GB por boot volume |
| Object Storage           | Bucket                            | 20 GB                                       | |
| Outbound Data Transfer   | Transferência de saída            | 10 TB / mês                                 | |
| Load Balancer            | Flexible                          | 1 instância (10 Mbps)                       | |
| Autonomous Database      | ATP / ADW / JSON                  | 2 bancos (20 GB cada)                       | |
| VCN                      | Rede virtual                      | 2 VCNs                                      | |

> **Fonte oficial**: [Always Free Resources](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier_topic-Always_Free_Resources.htm)

**Nota importante (2026):** O limite de ARM foi reduzido. Antigamente era 4 OCPUs / 24 GB. Atualmente é **2 OCPUs / 12 GB** no total.

## Riscos de cobrança e como evitá-los

### Principais armadilhas
- Criar instâncias com shapes que **não** são elegíveis a Always Free
- Aumentar o disco além de 200 GB
- Criar Load Balancer, Autonomous Database ou outros serviços e esquecer de apagar
- Fazer upgrade para Pay As You Go e depois criar recursos pagos sem controle
- Deixar recursos do trial rodando após o crédito acabar

### Como se proteger
1. Ativar **Budget Alert** com valor baixo (US$ 1) logo no início
2. Sempre verificar se o recurso está marcado como **Always Free-eligible** antes de criar
3. Preferir os shapes `VM.Standard.A1.Flex` (ARM) ou `VM.Standard.E2.1.Micro` (AMD)
4. Revisar periodicamente a lista de recursos na conta
5. Não fazer upgrade para Pay As You Go a menos que realmente precise

## Comparação com AWS Free Tier

| Critério                | Oracle Always Free                      | AWS Free Tier                              |
|-------------------------|-----------------------------------------|--------------------------------------------|
| Duração                 | Para sempre                             | Maioria dos serviços: 12 meses             |
| Compute                 | 2× Micro AMD ou 2 OCPU ARM              | 750 horas/mês de t2.micro / t3.micro       |
| Armazenamento           | 200 GB                                  | 30 GB EBS                                  |
| Transferência de saída  | 10 TB/mês                               | 100 GB/mês                                 |
| Banco de dados          | 2× Autonomous (20 GB)                   | RDS 750h + 20 GB                           |
| Facilidade de uso       | Mais trabalhoso                         | Mais simples e documentado                 |
| Risco de cobrança       | Médio (principalmente se errar o shape) | Alto (muita gente esquece recursos ligados)|
| Capacidade garantida    | Não (pode faltar host capacity)         | Mais estável                               |

## Evidências
![Página oficial dos recursos Always Free](../images/01-always-free.png)

> **Ação necessária**: Tire o print da página oficial e salve como `images/01-always-free.png`.

## Problemas encontrados e soluções
- Nenhum problema técnico neste capítulo (apenas pesquisa documental).

## Fontes consultadas
- [Oracle Always Free Resources](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier_topic-Always_Free_Resources.htm)
- [Oracle Cloud Free Tier](https://www.oracle.com/cloud/free/)
- [Oracle Free Tier FAQ](https://www.oracle.com/cloud/free/faq/)
- [Service Limits](https://docs.oracle.com/en-us/iaas/Content/General/Concepts/servicelimits.htm)
- Uso de IA: Grok (xAI) para estruturação, pesquisa e orientação do capítulo

## Conclusão do capítulo
Compreendi a diferença clara entre Always Free e o crédito de teste, os limites atuais (especialmente a redução do ARM para 2 OCPUs/12 GB), os riscos de cobrança e como evitá-los. Estou preparado para criar a conta com as devidas proteções no próximo capítulo.
