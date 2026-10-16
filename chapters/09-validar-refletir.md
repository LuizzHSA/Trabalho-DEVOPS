# 09 – Validar e refletir

## Objetivo
Comprovar que os três objetivos principais foram alcançados e fazer uma reflexão final.

## Checklist dos três objetivos

| Objetivo                                      | Status | Evidência |
|-----------------------------------------------|--------|-----------|
| App rodando em ambiente próprio (Render)      | ✅     | https://devops-app-x1r7.onrender.com/ |
| Deploy automático a cada push no GitHub       | ✅     | Auto-Deploy do Render ativado |
| Documentação completa em 9 capítulos         | ✅     | Este repositório |

## Limitações do ambiente gratuito (Render)

- Cold start de 30–60 segundos após 15 minutos de inatividade
- Recursos limitados (512 MB RAM / 0.1 CPU)
- Sem acesso SSH / shell
- Sem IP público fixo
- 750 horas de instância por mês

## Riscos de segurança que restam e melhorias possíveis

| Risco / Limitação              | Melhoria possível                     |
|--------------------------------|---------------------------------------|
| Cold start                     | Plano pago (sempre ligado)            |
| Recursos baixos                | Upgrade de instância                  |
| Sem SSH                        | Usar plataforma com VPS (Oracle etc.) |
| Dependência de um único provedor | Adicionar domínio próprio + monitor |

## Aprendizados pessoais e reflexão sobre a escolha do Render

Durante o trabalho foi possível vivenciar o ciclo completo de publicação de um aplicativo: pesquisa de ambientes gratuitos, criação de conta, escolha do app, publicação manual e, principalmente, a automatização do deploy.

A troca do Oracle Cloud pelo Render (devido à necessidade de cartão) mostrou que existem caminhos alternativos viáveis para cumprir os mesmos objetivos pedagógicos, mesmo com trade-offs diferentes (simplicidade vs controle total).

A escolha do Render não foi por comodidade, e sim por necessidade prática. Ela reforçou um princípio importante de DevOps: a melhor ferramenta é aquela que permite entregar o resultado dentro das restrições reais do momento, documentando claramente as decisões tomadas.

## Fontes consultadas
- Todos os capítulos anteriores
- Documentação do Render
- Uso de IA: Grok (xAI) para orientação e estruturação de todo o trabalho

## Conclusão final

Os três objetivos foram cumpridos:
1. O app está no ar
2. O deploy acontece automaticamente a cada push
3. Todo o processo está documentado em nove capítulos

Trabalho concluído com sucesso.
