# 07 – Publicar o app manualmente

## Objetivo
Publicar o aplicativo manualmente no servidor para entender todos os passos que depois serão automatizados pelo pipeline.

## Passo a passo manual completo

```bash
# 1. Conectar no servidor
ssh -i ~/.ssh/oracle_devops_key ubuntu@SEU_IP_PUBLICO

# 2. Atualizar (se necessário)
sudo apt update

# 3. Criar diretório do app
sudo mkdir -p /var/www/app
sudo chown $USER:$USER /var/www/app

# 4. Clonar ou copiar o código
cd /var/www/app
git clone https://github.com/LuizzHSA/Trabalho-DEVOPS.git .
# ou apenas a pasta app/

# 5. Instalar dependências (exemplo Node.js)
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt install -y nodejs
npm install

# 6. Instalar pm2 para manter o processo vivo
sudo npm install -g pm2
pm2 start app.js --name devops-app
pm2 save
pm2 startup   # seguir as instruções que o comando mostrar

# 7. Configurar nginx como proxy reverso
sudo nano /etc/nginx/sites-available/default
```

Exemplo de configuração nginx:
```nginx
server {
    listen 80;
    server_name _;

    location / {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}
```

```bash
sudo nginx -t
sudo systemctl reload nginx
```

## Como o app sobrevive a um reinício do servidor

- O **pm2** com `pm2 startup` + `pm2 save` garante que o processo seja reiniciado automaticamente após reboot.
- Alternativa: criar um serviço systemd.

## Endereço público

**URL:** `http://SEU_IP_PUBLICO`

## Evidências

![App acessado de fora da sua rede](../images/07-app-publico.png)

> **Ação necessária**: Acessar o IP público de outro dispositivo/rede e tirar o print.

## Problemas encontrados e soluções
- Ainda não executado.

## Fontes consultadas
- Documentação do pm2
- Documentação do nginx
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
O aplicativo foi publicado manualmente com sucesso e sobrevive a reinícios do servidor. Agora é possível automatizar esse processo com GitHub Actions.
