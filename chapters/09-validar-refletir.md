# 09 – Validar e refletir

## Objetivo
Comprovar que os três objetivos principais foram alcançados e fazer uma reflexão final sobre o que foi construído e aprendido.

## Checklist dos três objetivos

| Objetivo                                      | Status | Evidência |
|-----------------------------------------------|--------|-----------|
| App rodando em servidor próprio (Oracle)      | ✅     | ![App no ar](../images/09-app-no-ar.png) |
| Deploy automático a cada push no GitHub       | ✅     | ![Deploy automático](../images/09-deploy-automatico.png) |
| Documentação completa em 9 capítulos + PDF   | ✅     | Este repositório + arquivo `trabalho-devops.pdf` |

## Limitações do ambiente gratuito

- Capacidade de CPU/RAM limitada (especialmente após a redução do ARM para 2 OCPUs / 12 GB)
- Possibilidade de erro "Out of host capacity" em regiões concorridas
- Sem SLA (nível de serviço garantido)
- Recursos ociosos podem ser reclamados pela Oracle após longos períodos de inatividade
- Ausência de recursos avançados de balanceamento e alta disponibilidade no Always Free

## Riscos de segurança que restam e melhorias possíveis

| Risco                              | Melhoria recomendada                          |
|------------------------------------|-----------------------------------------------|
| SSH aberto para 0.0.0.0/0          | Restringir ao IP pessoal ou usar VPN/bastion  |
| Ausência de HTTPS                  | Configurar certificado Let's Encrypt          |
| Usuário com muitos privilégios     | Criar usuário específico com permissões mínimas |
| Falta de monitoramento             | Adicionar alertas básicos (uptime, disco, CPU)|
| Chave SSH única                    | Rotacionar chaves periodicamente              |

## Aprendizados pessoais

Durante este trabalho foi possível vivenciar o ciclo completo de publicação de um aplicativo: desde a pesquisa dos limites da nuvem gratuita, passando pela criação segura da conta, montagem da rede, hardenização do servidor, publicação manual e, finalmente, a automatização com GitHub Actions.

Os principais aprendizados foram:
- A importância de entender os limites reais do Free Tier antes de criar recursos
- A necessidade de proteger a conta desde o primeiro momento (MFA + Budget Alert)
- A diferença prática entre fazer o deploy manual e automatizá-lo
- Que documentar cada passo é tão importante quanto fazer o processo funcionar

## Fontes consultadas
- Todos os capítulos anteriores
- Documentação oficial Oracle Cloud e GitHub Actions
- Uso de IA: Grok (xAI) para orientação, estruturação e revisão de todo o trabalho

## Conclusão final

O ciclo completo — da pesquisa à entrega automática — foi realizado. O aplicativo está no ar, o deploy acontece a cada push e toda a jornada está documentada. O trabalho atende aos três objetivos propostos.
