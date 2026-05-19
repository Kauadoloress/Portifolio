---
# Relatório de Incidente de Segurança Cibernética: Análise de Tráfego de Rede
|**Parte 1: Forneça um resumo do problema encontrado no log de tráfego DNS e ICMP**|
|---|
|**O protocolo UDP revela que** a pacote não pode ser entregue na porta 53 no servido DNS. **Isso se baseia nos resultados da análise de rede, que mostram que a resposta de eco ICMP (echo reply) retornou a seguinte mensagem de erro **udp port 53 unreachable.**A porta observada na mensagem de erro é usada para **o serviço DNS.**O problema mais provável é que servidor esta inacessivel.**|
|**Parte 2: Explique sua análise dos dados e forneça pelo menos uma causa do incidente**|
|---|
|**Hora em que o incidente ocorreu  ****ás **13h24.     **Explique como a equipe de TI tomou conhecimento do incidente:** A equipe teve oo conhecimento após vário clientes relataram que não estava conseguindo acessar o site e ciram o erro de "porta de destino inalcamçável". após esperar a pagina carregar.**Explique as ações tomadas pelo departamento de TI para investigar o incidente:** As ações tomadas foram utilizar a ferramenta de analise de protocolo de rede tcpdump.**Observe as principais conclusões da investigação do departamento de TI (ex: detalhes relacionados à porta afetada, servidor DNS, etc.):** Com base na mensagem de erro que mostra ,que a porta esta inacessível, podemos dizer que a solicitação sequer chegou ao servido DNS. **Aponte uma causa provável para o incidente: **Ataque de inundação de ICMP.|
---
