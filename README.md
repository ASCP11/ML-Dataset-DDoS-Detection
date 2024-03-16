# Sobre o dataset
Este conjunto de dados representa um desafio significativo no segmento das telecomunicações: os ataques de negação de serviço (DDoS). Mais importante do que a capacidade de processamento é a capacidade de classificar se uma determinada conexão está envolvida em um ataque ou não.
O conjunto de dados foi compilado com base em observações(capturas de tráfego) de ataques direcionados à indústria de jogos. durante o final de 2023 e início de 2024, essa indústria enfrentou uma considerável quantidade de ataques, conforme documentado pela Cloudflare em seu Relatório de Ameaças DDoS de 2023 Q4 (https://blog.cloudflare.com/ddos-threat-report-2023-q4). Todos os dados presentes nesse 
Foi introduzida uma etapa de pré-processamento dado a sensibilidade dos endereços IP e as dificuldades associadas ao seu uso em modelos de aprendizado, optou-se por transformar essa feature em duas outras: país de origem e ASN de origem. ASN, ou Número de Sistema Autônomo, é uma identificação numérica atribuída a uma entidade na Internet, representando uma organização que controla um ou mais blocos de endereços IP. Por exemplo, cada provedor de serviços de Internet (ISP) possui seu próprio ASN, que abrange uma variedade de endereços IP associados. Essa transformação facilita a manipulação, enriquece dados e preserva a privacidade de informações sensíveis.
Cada amostra neste conjunto de dados representa um pacote de rede. Contendo as seguintes features:


## Features
- Src_ip_country: Pais do ip de origem
- Src_ip_asn: ASN do ip de origem
- Src_port: Porta de origem da conexão
- Ttl: é um campo numérico presente no header de um pacote. Ele especifica o número máximo de roteadores que um pacote pode atravessar antes de ser descartado pela rede. Cada roteador decrementa o valor do TTL à medida que o pacote passa por ele. Se o valor do TTL atingir zero, o pacote é descartado.
- Payload_size: Refere-se à quantidade de dados úteis contidos no pacote, excluindo os cabeçalhos do protocolo UDP
- class: Classificação binaria 1 representa que determinado pacote é legitimo e 0 representa que faz parte de um ataque
