# 🛡️ Avaliação de Risco de Segurança: Hardening de Rede e Remediação Pós-Incidente

## 📝 Visão Geral do Cenário
* **Organização:** Plataforma de Mídia Social (Pequena/Média Empresa)
* **Incidente:** Violação massiva de dados que comprometeu as Informações Pessoais Identificáveis (PII) dos clientes, especificamente nomes e endereços.
* **Objetivo:** Realizar uma avaliação de segurança com base nas vulnerabilidades de rede identificadas e fornecer recomendações estratégicas de *hardening* para evitar futuras exfiltrações de dados.

---

## 🔍 Identificação de Vulnerabilidades

Durante a inspeção da rede realizada após o incidente, foram descobertas quatro falhas críticas na postura de segurança:
1. **Credenciais Compartilhadas:** Os funcionários partilhavam senhas ativamente, destruindo a responsabilização individual (não-repúdio).
2. **Configurações Padrão:** A senha do administrador do banco de dados permaneceu com a configuração de fábrica (padrão).
3. **Ausência de Regras de Firewall:** Os firewalls estavam ativos, mas não possuíam regras de filtragem para tráfego de entrada (*ingress*) e de saída (*egress*).
4. **Ausência de Autenticação Forte:** A Autenticação Multifator (MFA) não estava implementada em nenhum dos sistemas corporativos.

---

## 🛠️ Recomendações de Hardening e Mitigação

Para corrigir as falhas encontradas e estabelecer uma postura robusta de defesa em profundidade, os três métodos de *hardening* de rede a seguir foram selecionados para implementação imediata e contínua:

### 1. Filtragem de Portas e Otimização de Regras de Firewall
* **Eficácia Técnica:** Diante da falta de restrição de tráfego, a **Filtragem de Portas** atua como a primeira barreira digital. Ao implementar regras estritas de entrada e saída no firewall, a organização passa a inspecionar o cabeçalho dos pacotes e a bloquear protocolos não autorizados. Restringir ou fechar portas não utilizadas minimiza a superfície de ataque, impedindo diretamente que atores maliciosos realizem o reconhecimento da rede (*port scanning*) e explorem serviços expostos desnecessariamente.
* **Frequência de Implementação:** A base de regras inicial deve ser implantada **imediatamente** como remediação pós-incidente. A partir daí, as regras do firewall devem passar por **revisões mensais contínuas** ou sempre que ocorrerem mudanças na infraestrutura, aderindo estritamente ao Princípio do Menor Privilégio.

### 2. Criptografia de Dados (Padrões Modernos)
* **Eficácia Técnica:** Uma vez que as PII dos clientes (nomes e endereços) foram expostas, a segurança dos dados em repouso e em trânsito tornou-se uma prioridade crítica. A implementação de **Padrões Avançados de Criptografia (como AES-256 para armazenamento e TLS 1.3 para tráfego de rede)** garante que, mesmo que um atacante consiga burlar os firewalls de perímetro e exfiltrar os ficheiros do banco de dados novamente, os dados permanecerão completamente ilegíveis e inúteis sem as chaves criptográficas adequadas.
* **Frequência de Implementação:** Os protocolos de criptografia devem ser aplicados **imediatamente** em todos os bancos de dados de produção. Esta técnica exige **avaliações anuais regulares** para verificar se os padrões atuais permanecem seguros contra vetores de ameaças emergentes e técnicas modernas de quebra de criptografia.
