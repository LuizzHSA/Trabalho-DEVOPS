# 03 – Entender e montar a rede

## Objetivo
Compreender e configurar a rede (VCN, subnet, security list, gateways) de forma segura e funcional para o servidor.

## Conceitos explicados com minhas palavras

### Compartment
_Explicar_

### VCN (Virtual Cloud Network)
_Explicar_

### Subnet pública
_Explicar_

### Internet Gateway
_Explicar_

### Security List
_Explicar_

### Diferença entre regra de entrada e de saída
_Explicar_

## Diagrama da rede montada
```text
[Internet] 
    |
Internet Gateway
    |
   VCN
    |
Subnet Pública ── Security List (portas liberadas)
    |
  Instância
```

## Tabela das regras de entrada

| Porta | Protocolo | Origem     | Motivo                          |
|-------|-----------|------------|---------------------------------|
| 22    | TCP       | 0.0.0.0/0  | SSH (acesso administrativo)     |
| 80    | TCP       | 0.0.0.0/0  | HTTP (aplicação web)           |
| 443   | TCP       | 0.0.0.0/0  | HTTPS (futuro)                  |

## Evidências
![VCN criada](../images/03-vcn.png)
![Subnet](../images/03-subnet.png)
![Security List](../images/03-security-list.png)

## Problemas encontrados e soluções
- _registrar aqui_

## Fontes consultadas
- Documentação oficial Oracle Networking
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
_A ser preenchido._
