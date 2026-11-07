# Roteamento e Conectividade em uma Amazon VPC

## Objetivo

Criar uma infraestrutura de rede funcional na AWS utilizando uma Amazon VPC, configurando os recursos necessários para permitir a comunicação entre uma instância EC2 e a Internet.

---

## Cenário

Uma startup entrou em contato com o suporte da AWS informando que sua infraestrutura de rede não possuía conectividade com a Internet. Apesar de possuir uma VPC criada, a comunicação externa não funcionava corretamente.

O objetivo deste laboratório foi criar e configurar todos os componentes necessários para tornar a VPC roteável, incluindo sub-rede pública, tabela de rotas, Internet Gateway, Network ACL, Security Group e uma instância Amazon EC2 para validação da conectividade.

---

# Evidências

## 1. VPC Criada

![VPC Criada](evidencias/01-vpc-criada.png)

---

## 2. Sub-rede Pública Criada

![Sub-rede Pública](evidencias/02-subrede-publica.png)

---

## 3. Tabela de Rotas Criada

![Tabela de Rotas](evidencias/03-tabela-rotas.png)

---

## 4. Internet Gateway Criado

![Internet Gateway](evidencias/04-internet-gateway-criado.png)

---

## 5. Internet Gateway Associado à VPC

![IGW Associado](evidencias/05-igw-anexado-vpc.png)

---

## 6. Rota para a Internet Configurada

![Rota para Internet](evidencias/06-rota-para-internet.png)

---

## 7. Associação da Sub-rede à Tabela de Rotas

![Associação da Sub-rede](evidencias/07-associacao-subrede-route-table.png)

---

## 8. Network ACL Criada

![NACL Criada](evidencias/08-nacl-criada.png)

---

## 9. Regra de Entrada da NACL

![Regra de Entrada](evidencias/09-nacl-regra-entrada.png)

---

## 10. Regra de Saída da NACL

![Regra de Saída](evidencias/10-nacl-regra-saida.png)

---

## 11. Associação da NACL à Sub-rede

![Associação NACL](evidencias/11-associacao-nacl-subrede.png)

---

## 12. Security Group Configurado

![Security Group](evidencias/12-security-group-configurado.png)

---

## 13. Instância EC2 em Execução

![Instância Running](evidencias/13-instancia-running.png)

---

## 14. Teste de Conectividade com a Internet

![Ping Google](evidencias/14-ping-google-sucesso.png)

---

# Análise

Durante a implementação da solução foi necessário configurar todos os componentes responsáveis pela conectividade e segurança da rede.

| Recurso | Finalidade |
|----------|------------|
| Amazon VPC | Ambiente de rede isolado |
| Sub-rede Pública | Hospedagem da instância EC2 |
| Route Table | Direcionamento do tráfego |
| Internet Gateway | Acesso à Internet |
| Network ACL | Controle de tráfego na sub-rede |
| Security Group | Firewall da instância |
| Amazon EC2 | Validação da conectividade |

A rota padrão `0.0.0.0/0` foi adicionada à tabela de rotas e apontada para o Internet Gateway, permitindo que o tráfego destinado à Internet pudesse sair da VPC.

Além disso, as regras da Network ACL foram configuradas para permitir tráfego de entrada e saída, enquanto o Security Group permitiu conexões SSH, HTTP e HTTPS.

A validação final foi realizada através do comando:

```bash
ping google.com
```

O recebimento das respostas confirmou que a instância EC2 possuía conectividade com a Internet e que a configuração da infraestrutura estava correta.

---

# Conclusão

O problema apresentado pelo cliente foi solucionado através da criação de uma arquitetura de rede completa dentro da Amazon VPC.

O laboratório demonstrou na prática a importância do relacionamento entre VPC, sub-redes, tabelas de rotas, Internet Gateway, Network ACLs e Security Groups para o funcionamento da comunicação de rede na AWS.

Ao final, a instância EC2 conseguiu acessar recursos externos com sucessoux 2023
- SSH
- ICMP (Ping)
- IPv4
