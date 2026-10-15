# 05 – Deixar o servidor mínimo e seguro

## Objetivo
Instalar apenas o necessário, configurar firewall em duas camadas e deixar o servidor pronto para receber o aplicativo.

## Lista do que foi instalado e por quê

| Pacote / Ferramenta | Motivo                              |
|---------------------|-------------------------------------|
| updates do sistema  | Segurança e correções             |
| ufw / firewalld     | Firewall do sistema operacional     |
| nginx ou caddy      | Servir a aplicação web             |
| _outros_            |                                     |

## Comandos usados (reproduzíveis)

```bash
# Atualizar o sistema
sudo apt update && sudo apt upgrade -y

# Criar usuário para o app
sudo adduser appuser

# Configurar firewall do sistema
sudo ufw allow OpenSSH
sudo ufw allow 80/tcp
sudo ufw enable

# Instalar e testar servidor web mínimo
sudo apt install nginx -y
sudo systemctl enable nginx
```

## Regras de firewall nas duas camadas

### Camada 1 – Security List (Oracle Cloud)
- Porta 22 (SSH)
- Porta 80 (HTTP)
- Porta 443 (HTTPS)

### Camada 2 – Firewall do sistema (ufw)
- Mesmas portas liberadas

## Evidências
![Resposta HTTP do servidor no navegador](../images/05-http-resposta.png)

## Problemas encontrados e soluções
- _registrar aqui_

## Fontes consultadas
- Documentação Ubuntu / Nginx
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
_A ser preenchido._
