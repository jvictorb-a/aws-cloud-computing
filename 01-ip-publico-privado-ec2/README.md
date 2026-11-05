# Protocolos da Internet - Endereços IP Públicos e Privados

## Objetivos

- Investigar o ambiente do cliente.
- Analisar a diferença entre endereços IP públicos e privados.
- Identificar a causa do problema de conectividade.
- Desenvolver uma solução para o cliente.

## Status

✅ Concluído

## Evidências

As evidências deste laboratório estão disponíveis na pasta `evidencias`.

## Conclusão

A Instância A não possuía endereço IPv4 público, impossibilitando o acesso externo via SSH.

A Instância B possuía endereço IPv4 público, permitindo comunicação com a Internet e acesso remoto.

Também foi identificado que o uso de blocos públicos como CIDR da VPC não é recomendado. O ideal é utilizar intervalos privados definidos pela RFC 1918.
