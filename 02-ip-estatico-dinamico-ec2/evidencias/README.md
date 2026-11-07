# 02 - IP Estático e Dinâmico em Instâncias EC2

## Descrição

Neste laboratório foi analisado o comportamento dos endereços IP em instâncias Amazon EC2 e investigado um problema reportado por um cliente cuja instância alterava seu endereço IP público sempre que era interrompida e iniciada novamente.

A solução implementada consistiu na criação e associação de um Elastic IP (EIP), garantindo um endereço IP público estático e persistente.

---

## Objetivos

- Compreender a diferença entre IP estático e IP dinâmico.
- Reproduzir o problema relatado pelo cliente.
- Validar o comportamento dos endereços IPv4 público e privado.
- Configurar um Elastic IP (EIP).
- Garantir persistência do endereço IP público.

---

## Serviços Utilizados

- Amazon EC2
- Amazon VPC
- Elastic IP (EIP)
- Security Groups

---

## Etapa 1 - Criação da Instância EC2

Foi criada uma instância Amazon Linux 2 do tipo t3.micro na VPC do laboratório com atribuição automática de IP público.

![Instância Criada](imagens/01-instancia-criada.png)

---

## Etapa 2 - Identificação dos Endereços IP

Após a criação da instância, foram identificados os endereços IPv4 público e privado atribuídos pela AWS.

![IPs Iniciais](imagens/02-ip-inicial.png)

---

## Etapa 3 - Parada da Instância

A instância foi interrompida para verificar o comportamento dos endereços IP após o desligamento.

![Instância Parada](imagens/03-instancia-parada.png)

---

## Etapa 4 - Reinicialização da Instância

Após iniciar novamente a instância, foi possível observar que o endereço IPv4 público foi alterado, enquanto o IPv4 privado permaneceu o mesmo.

![IP Público Alterado](imagens/04-ip-publico-alterado.png)

---

## Etapa 5 - Comparação dos Endereços IP

Foi realizada uma comparação entre os endereços IP antes e depois da reinicialização da instância.

Observação:

- O IPv4 Público mudou.
- O IPv4 Privado permaneceu inalterado.

![Comparação de IPs](imagens/05-comparacao-ips.png)

---

## Etapa 6 - Criação do Elastic IP

Foi criado um Elastic IP (EIP), recurso utilizado para fornecer um endereço IP público estático para instâncias EC2.

![Elastic IP Criado](imagens/06-eip-criado.png)

---

## Etapa 7 - Associação do Elastic IP

O Elastic IP foi associado à instância EC2 criada durante o laboratório.

![Associação do EIP](imagens/07-associacao-eip.png)

---

## Etapa 8 - Elastic IP Associado

Após a associação, o endereço IPv4 público da instância passou a ser o Elastic IP.

![EIP Associado](imagens/08-eip-associado.png)

---

## Etapa 9 - Validação da Solução

A instância foi novamente parada e iniciada para validar a persistência do endereço IP.

O Elastic IP permaneceu o mesmo, comprovando que o endereço se tornou estático.

![Teste Final](imagens/09-teste-final.png)

---

## Resultados Obtidos

Durante os testes foi possível comprovar que:

- O endereço IPv4 público padrão da EC2 é dinâmico.
- O endereço IPv4 privado permanece constante dentro da VPC.
- O Elastic IP fornece um endereço IPv4 público estático.
- O Elastic IP continua associado à instância mesmo após reinicializações.

---

## Conclusão

O problema relatado pelo cliente foi causado pela utilização de um endereço IPv4 público dinâmico fornecido automaticamente pela AWS. Como consequência, o endereço era alterado sempre que a instância era interrompida e iniciada novamente.

A solução implementada foi a criação e associação de um Elastic IP (EIP), garantindo um endereço IPv4 público estático e persistente. Após os testes realizados, foi comprovado que o endereço permaneceu inalterado mesmo após novas reinicializações da instância, resolvendo definitivamente o problema.

---

## Autor

**João Victor Bezerra de Araújo**

Escola da Nuvem | AWS Cloud Computing
