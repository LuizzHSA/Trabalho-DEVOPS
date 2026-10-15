# 04 – Criar a instância e acessar por SSH

## Objetivo
Criar a instância Always Free e acessá-la exclusivamente por chave SSH (nunca por senha).

## Configuração escolhida e justificação

| Item                 | Escolha                          | Justificativa                                      |
|----------------------|----------------------------------|----------------------------------------------------|
| Sistema Operacional  | Ubuntu 22.04 Minimal             | Leve, bem documentado e amplamente usado           |
| Shape                | VM.Standard.A1.Flex (ARM)        | Melhor custo-benefício dentro do Always Free       |
| OCPU / Memória       | 2 OCPU / 12 GB                   | Usa todo o limite Always Free de ARM               |
| Disco (Boot Volume)  | 50 GB                            | Dentro do limite de 200 GB e suficiente            |
| Rede                 | Subnet pública criada no cap. 03 | Necessária para ter IP público                     |
| Chave SSH            | Par de chaves gerado localmente  | Acesso seguro sem senha                            |

## Explicação de chave pública e privada

- **Chave privada** (`.pem` ou `id_rsa`): fica **somente** na sua máquina local. Nunca deve ser enviada para o GitHub, para o servidor ou compartilhada.
- **Chave pública** (`.pub`): é colocada na instância no momento da criação. O servidor usa ela para autenticar quem possui a chave privada correspondente.

Local da chave privada (exemplo):
```bash
~/.ssh/oracle_devops_key
```

Comando para gerar o par de chaves:
```bash
ssh-keygen -t ed25519 -f ~/.ssh/oracle_devops_key -C "oracle-devops"
```

## Evidências

![Instância em execução no console](../images/04-instancia-running.png)

![Acesso SSH funcionando](../images/04-ssh-acesso.png)

> **Ação necessária**: Tirar os prints após a instância estar Running e após conseguir conectar via SSH.

## Problemas encontrados e soluções

Problemas comuns neste capítulo:
- **Out of host capacity**: falta de capacidade na região para o shape ARM. Solução: tentar outro Availability Domain, reduzir para 1 OCPU ou tentar em outro horário.
- Erro de permissão na chave: `chmod 400 ~/.ssh/oracle_devops_key`

## Fontes consultadas
- Documentação oficial Oracle Compute
- Man pages do ssh-keygen
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
A instância foi criada dentro dos limites Always Free e o acesso é feito exclusivamente por chave SSH. O servidor está pronto para ser endurecido no próximo capítulo.
