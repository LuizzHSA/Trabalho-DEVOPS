# 04 – Criar a instância e acessar por SSH

## Objetivo
Criar a instância Always Free e acessá-la exclusivamente por chave SSH.

## Configuração escolhida e justificação

| Item              | Escolha                     | Justificativa                     |
|-------------------|-----------------------------|-----------------------------------|
| Sistema Operacional | Ubuntu 22.04 / Oracle Linux | _preencher_                       |
| Shape             | VM.Standard.A1.Flex ou E2.1.Micro | Always Free + recursos suficientes |
| OCPU / Memória    | _preencher_                 |                                   |
| Disco (Boot Volume) | 50 GB (ou até 200 GB)     | Dentro do limite Always Free      |

## Explicação de chave pública e privada
- **Chave privada**: fica **somente** na sua máquina local (nunca sobe para o GitHub ou servidor).
- **Chave pública**: é colocada na instância no momento da criação.

Local da chave privada: `~/.ssh/id_rsa` (ou o nome que você escolheu).

## Evidências
![Instância em execução](../images/04-instancia-running.png)
![Acesso SSH funcionando](../images/04-ssh-acesso.png)

## Problemas encontrados e soluções
- _registrar aqui_ (ex: falta de capacidade na região, erro de chave, etc.)

## Fontes consultadas
- Documentação oficial Oracle Compute
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
_A ser preenchido._
