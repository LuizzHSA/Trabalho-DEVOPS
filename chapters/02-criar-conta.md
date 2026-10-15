# 02 – Criar a conta com segurança e controle de gastos

## Objetivo
Criar a conta no Oracle Cloud com proteções de login ativadas, definir a Home Region corretamente e configurar alertas de gasto para evitar qualquer cobrança indesejada.

## O que foi feito
- Criação da conta Oracle Cloud Free Tier
- Escolha cuidadosa da Home Region
- Ativação de autenticação multifator (MFA)
- Configuração de Budget Alert com valor baixo

## Região escolhida e justificação

**Região escolhida:** South America East (São Paulo) — `sa-saopaulo-1`

**Justificativa:**
- Menor latência para acesso a partir do Brasil
- Disponibilidade de recursos Always Free
- A Home Region **não pode ser alterada** depois da criação da conta
- Recursos Always Free só podem ser criados na Home Region

> **Atenção crítica**: A escolha da Home Region é permanente. Escolher errado pode impossibilitar a criação de instâncias Always Free por falta de capacidade.

## Medidas de segurança ativadas

1. **Autenticação Multifator (MFA)** ativada via aplicativo autenticador
2. Senha forte e única
3. Budget Alert configurado com valor de US$ 1,00 (alerta precoce de qualquer gasto)

### Como configurar o Budget Alert
1. Menu → **Governance & Administration** → **Budgets**
2. Create Budget
3. Scope: **Tenancy**
4. Amount: **1** (um dólar)
5. Reset Period: Monthly
6. Adicionar Alert Rules:
   - Actual Spend ≥ 50%
   - Actual Spend ≥ 100%

## Evidências

![Conta criada (sem dados pessoais)](../images/02-conta-criada.png)

![Alerta de gasto configurado](../images/02-budget-alert.png)

![MFA e medidas de segurança ativadas](../images/02-seguranca-mfa.png)

> **Ação necessária**: Substituir os prints acima pelos prints reais da sua conta (sem expor e-mail, nome completo ou números de cartão).

## Problemas encontrados e soluções

- **Problema**: Necessidade de cartão de crédito/débito real para verificação de identidade.
- **Solução**: A Oracle não aceita cartões virtuais ou pré-pagos. É necessário um cartão real (mesmo que seja apenas para a autorização temporária).

## Fontes consultadas
- [Oracle Cloud Free Tier](https://www.oracle.com/cloud/free/)
- [Oracle Free Tier FAQ](https://www.oracle.com/cloud/free/faq/)
- Documentação de Budgets da Oracle
- Uso de IA: Grok (xAI) para orientação e estruturação

## Conclusão do capítulo
A conta foi criada com as proteções básicas de segurança e com alerta de gasto configurado. A Home Region foi escolhida de forma consciente, sabendo que não poderá ser alterada. O próximo passo é montar a rede de forma segura.
