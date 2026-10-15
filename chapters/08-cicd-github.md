# 08 – Montar o CI/CD com GitHub

## Objetivo
Configurar um pipeline com GitHub Actions que, a cada push, faça o deploy automático do aplicativo no servidor.

## Link do repositório
[https://github.com/LuizzHSA/Trabalho-DEVOPS](https://github.com/LuizzHSA/Trabalho-DEVOPS)

## Diagrama do fluxo

```text
[git push] 
    ↓
GitHub Actions (workflow)
    ↓
  Build / Testes (opcional)
    ↓
  Deploy via SSH
    ↓
Servidor Oracle Cloud
    ↓
App atualizado
```

## Descrição de cada etapa do workflow

| Etapa              | Função                                      |
|--------------------|----------------------------------------------|
| Checkout           | Baixa o código do repositório               |
| Setup runtime      | Prepara Node/Python/etc.                     |
| Install & Build    | Instala dependências e faz build (se houver) |
| Deploy via SSH     | Conecta no servidor e atualiza o app         |

## Segredos usados e como foram protegidos
- `SSH_PRIVATE_KEY` → chave exclusiva para o pipeline (nunca a chave pessoal)
- `HOST` → IP público do servidor
- `USER` → usuário de deploy

Todos armazenados em **Settings → Secrets and variables → Actions**.

## Evidências
![Execução com sucesso na aba Actions](../images/08-actions-sucesso.png)
![Falha tratada na aba Actions](../images/08-actions-falha.png)
![App antes do push](../images/08-app-antes.png)
![App depois do push](../images/08-app-depois.png)

## Problemas encontrados e soluções
- _registrar aqui_

## Fontes consultadas
- Documentação GitHub Actions
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
_A ser preenchido._
