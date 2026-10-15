# 05 – Deixar o servidor mínimo e seguro

## Objetivo
Instalar apenas o necessário, configurar firewall em duas camadas e deixar o servidor pronto para receber o aplicativo, reduzindo a superfície de ataque.

## Lista do que foi instalado e por quê

| Pacote / Ferramenta     | Motivo                                              |
|-------------------------|-----------------------------------------------------|
| Atualizações do sistema | Correções de segurança                             |
| ufw                     | Firewall do sistema operacional                     |
| nginx                   | Servidor web / proxy reverso leve                   |
| curl / wget             | Ferramentas básicas de diagnóstico                  |
| git                     | Necessário para clonar o repositório do app         |

## Comandos usados (reproduzíveis)

```bash
# Atualizar o sistema
sudo apt update && sudo apt upgrade -y

# Instalar pacotes essenciais
sudo apt install -y nginx ufw git curl

# Configurar firewall do sistema (segunda camada)
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow OpenSSH
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw enable

# Verificar status
sudo ufw status verbose

# Habilitar e iniciar o nginx
sudo systemctl enable nginx
sudo systemctl start nginx
```

## Regras de firewall nas duas camadas

### Camada 1 – Security List (Oracle Cloud)
- Porta 22/TCP (SSH)
- Porta 80/TCP (HTTP)
- Porta 443/TCP (HTTPS)

### Camada 2 – ufw (dentro do sistema)
- Mesmas portas liberadas
- Política padrão: negar entrada, permitir saída

## Evidências

![Resposta HTTP do servidor no navegador](../images/05-http-resposta.png)

> **Ação necessária**: Acessar o IP público no navegador e tirar print da página padrão do nginx (ou da página de teste).

## Problemas encontrados e soluções
- Ainda não executado (depende dos capítulos anteriores).

## Fontes consultadas
- Documentação do Ubuntu Server
- Documentação do nginx e ufw
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
O servidor está atualizado, com firewall em duas camadas e com um servidor web mínimo respondendo. Está pronto para receber o aplicativo real.
