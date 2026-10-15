# 03 – Entender e montar a rede

## Objetivo
Compreender e configurar a rede (VCN, subnet, security list e gateways) de forma segura e funcional para o servidor, liberando apenas as portas realmente necessárias.

## Conceitos explicados com minhas palavras

### Compartment
É como uma pasta ou departamento dentro da conta Oracle. Serve para organizar recursos e aplicar políticas de permissão. No início usamos o compartment raiz (root).

### VCN (Virtual Cloud Network)
É a rede virtual privada da sua conta. Equivale a uma VPC na AWS. Dentro dela ficam as subnets, roteadores e regras de segurança.

### Subnet pública
É uma subdivisão da VCN que possui rota para a Internet (através do Internet Gateway). Instâncias dentro de uma subnet pública podem ter IP público.

### Internet Gateway
Componente que permite que recursos dentro da VCN se comuniquem com a Internet (entrada e saída).

### Security List
É o firewall da rede na camada da Oracle. Define quais portas e protocolos são permitidos (regras de entrada e de saída).

### Diferença entre regra de entrada e de saída
- **Entrada (Ingress)**: tráfego que chega de fora para a instância (ex: alguém acessando a porta 80).
- **Saída (Egress)**: tráfego que sai da instância para a Internet (ex: a instância baixando pacotes ou fazendo atualização).

## Diagrama da rede montada

```text
                    Internet
                       |
               Internet Gateway
                       |
                     VCN
                       |
              Subnet Pública
                       |
              Security List
             (portas 22, 80, 443)
                       |
                   Instância
```

## Tabela das regras de entrada

| Porta | Protocolo | Origem      | Motivo                              |
|-------|-----------|-------------|-------------------------------------|
| 22    | TCP       | 0.0.0.0/0   | SSH – acesso administrativo         |
| 80    | TCP       | 0.0.0.0/0   | HTTP – acesso ao aplicativo web     |
| 443   | TCP       | 0.0.0.0/0   | HTTPS – acesso seguro (futuro)      |

> Em produção real, a porta 22 deveria ser restrita ao seu IP. Para o trabalho, 0.0.0.0/0 é aceitável desde que documentado.

## Evidências

![VCN criada](../images/03-vcn.png)

![Subnet pública](../images/03-subnet.png)

![Security List com as regras](../images/03-security-list.png)

> **Ação necessária**: Tirar os prints reais após criar a VCN, a subnet e a security list.

## Problemas encontrados e soluções
- Ainda não executado (aguardando criação da conta).

## Fontes consultadas
- Documentação oficial Oracle Networking / VCN
- Uso de IA: Grok (xAI)

## Conclusão do capítulo
A rede foi planejada de forma mínima e segura: apenas as portas necessárias foram liberadas. O próximo passo é criar a instância dentro dessa rede.
