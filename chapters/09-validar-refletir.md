# 09 – Validar e refletir

## Objetivo
Comprovar que os três objetivos principais foram alcançados e fazer uma reflexão final sobre o trabalho.

## Checklist dos três objetivos

| Objetivo                                      | Status | Evidência |
|-----------------------------------------------|--------|-----------|
| App rodando em servidor próprio               | ✅     | ![App no ar](../images/09-app-no-ar.png) |
| Deploy automático a cada push no GitHub       | ✅     | ![Deploy automático](../images/09-deploy-automatico.png) |
| Documentação completa em 9 capítulos + PDF   | ✅     | Este repositório + `trabalho-devops.pdf` |

## Limitações do ambiente gratuito
- Capacidade de CPU/RAM limitada (especialmente no shape Micro)
- Possível falta de capacidade em algumas regiões (ARM)
- Sem balanceador de carga de alto desempenho
- Transferência limitada a 10 TB/mês (mais que suficiente para este trabalho)

## Riscos de segurança que restam e melhorias possíveis
- SSH aberto para 0.0.0.0/0 → melhorar com IP restrito ou VPN
- Falta de HTTPS (certificado Let's Encrypt)
- Usuário de deploy com permissões elevadas demais
- Monitoramento e alertas básicos ainda não implementados

## Aprendizados pessoais
_Escrever um texto curto e sincero sobre o que aprendeu durante o trabalho._

## Fontes consultadas
- Todos os capítulos anteriores
- Uso de IA: Grok (xAI) para orientação geral

## Conclusão final
Trabalho concluído com sucesso. O ciclo completo — da pesquisa à entrega automática — foi realizado.
