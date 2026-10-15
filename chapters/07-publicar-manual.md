# 07 – Publicar o app manualmente

## Objetivo
Publicar o aplicativo manualmente no servidor para entender todo o processo antes de automatizar.

## Passo a passo manual completo

1. Conectar via SSH
2. Atualizar o sistema (se necessário)
3. Clonar o repositório do app
4. Instalar dependências
5. Configurar variáveis de ambiente
6. Iniciar o aplicativo (com pm2 ou systemd)
7. Configurar nginx como proxy reverso
8. Testar o acesso público

```bash
# Exemplos de comandos (ajustar conforme o app)
git clone https://github.com/...
cd app
npm install   # ou pip install -r requirements.txt
pm2 start app.js --name meu-app
pm2 save
pm2 startup
```

## Como o app sobrevive a um reinício do servidor
- Usando **pm2** com `pm2 startup` + `pm2 save`
- Ou criando um serviço **systemd**

## Endereço público
- **URL**: `http://SEU-IP-PUBLICO`

## Evidências
![App acessado de fora da rede](../images/07-app-publico.png)

## Problemas encontrados e soluções
- _registrar aqui_

## Fontes consultadas
- Documentação do app escolhido
- Documentação pm2 / systemd
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
_A ser preenchido._
