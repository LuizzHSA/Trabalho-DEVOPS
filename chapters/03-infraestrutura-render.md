# 03 – Entender a infraestrutura do Render

## Objetivo
Compreender como o Render organiza a infraestrutura (em contraste com VCN, subnet e security list do Oracle Cloud) e quais controles de rede existem no plano Free.

## Conceitos explicados com minhas palavras

### Web Service
É o equivalente a uma “instância” no Render. Você define o runtime (Node, Python, etc.), o comando de start e o Render cuida do restante.

### Deploy automático
A cada push no repositório conectado, o Render detecta a mudança, faz o build e publica uma nova versão automaticamente.

### Cold Start
Como o plano Free coloca o serviço para dormir após 15 minutos sem tráfego, a primeira requisição depois disso demora alguns segundos para “acordar” o container.

### SSL / HTTPS
O Render fornece certificado SSL gratuito e automático para todos os serviços.

### Domínio
Todo serviço recebe um subdomínio `*.onrender.com`.

## Diagrama da infraestrutura

```text
GitHub (push)
     |
     v
Render Build
     |
     v
Web Service (container)
     |
     +---> HTTPS (SSL automático)
     |
     v
Internet (usuários)
```

## Regras de exposição

| Item                | Comportamento no Render Free      |
|---------------------|-----------------------------------|
| Porta exposta       | Definida pelo Start Command (3000)|
| HTTPS               | Obrigatório e automático          |
| Firewall            | Gerenciado pelo Render            |
| Acesso SSH          | Não disponível no Free            |
| IP público fixo     | Não (usa load balancer do Render) |

## Evidências
![Dashboard do serviço no Render](../images/deploy.png)

## Fontes consultadas
- Documentação oficial do Render
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
Embora o Render não exponha VCN, Security List ou SSH, a infraestrutura é suficiente e muito mais simples para o objetivo do trabalho: ter o app no ar com deploy automático.
