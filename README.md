# Bootcamp_Arquitetura_Azure
Este repositório fala um pouco sobre o que aprendi durante o modulo Arquiteturas no Azure do Bootcamp Microsoft Azure Essentials da Dio.

# Vamos falar um pouco sobre Arquiteturas no Azure

### O que são Regiões?
- **Descrição**: No contexto da Azure, uma **região** é uma localização geográfica que contém pelo menos um datacenter, conectado a uma rede de baixa latência e alta redundância. Cada região oferece uma combinação de serviços Azure, desde computação até armazenamento e banco de dados, permitindo aos clientes implantar suas soluções geograficamente próximas aos seus usuários ou requisitos de conformidade.
- As regiões permitem que os clientes escolham onde seus dados e recursos são implantados, ajudando a minimizar a latência e a cumprir requisitos de conformidade de dados, como as leis locais de proteção de dados.

### Exemplos de Regiões:
- **East US**
- **West Europe**
- **Southeast Asia**

### Como escolher uma região:
- **Latência**: Escolher a região mais próxima dos seus usuários para melhorar o desempenho.
- **Conformidade**: Algumas organizações precisam garantir que os dados estejam dentro de uma região específica devido a regulamentações legais.
- **Disponibilidade de Serviços**: Nem todos os serviços do Azure estão disponíveis em todas as regiões, portanto, é importante verificar a disponibilidade de serviços na região escolhida.

---

##  Pares de Regiões do Azure
- **Descrição**: Um **par de regiões** é uma estratégia de design da Microsoft Azure que vincula duas regiões dentro da mesma geografia. Essas regiões são emparelhadas para garantir que em cenários de falhas ou desastres naturais, os dados possam ser replicados de forma segura e os serviços continuem funcionando com o mínimo de interrupção.
- Em caso de um grande incidente que afete uma região, a região emparelhada é configurada para assumir as cargas críticas. Isso é crucial para garantir a **alta disponibilidade** e **recuperação de desastres**.

### Benefícios dos Pares de Regiões:
- **Recuperação de Desastres**: Serviços como o Azure Storage replicam dados de forma assíncrona entre as regiões emparelhadas, garantindo a recuperação em caso de falha regional.
- **Manutenção Programada**: Quando atualizações de software são necessárias, a manutenção é realizada em uma região por vez, minimizando o impacto para os clientes.
- **Isolamento Geográfico**: As regiões emparelhadas geralmente estão localizadas em áreas geográficas separadas, garantindo redundância física em caso de desastres naturais ou falhas sistêmicas.

### Exemplos de Pares de Regiões:
- **East US** e **West US**
- **North Europe** e **West Europe**
- **Southeast Asia** e **East Asia**

---

##  Regiões Soberanas do Azure
- **Descrição**: As **regiões soberanas** do Azure são instâncias separadas da nuvem pública do Azure, criadas para atender a requisitos específicos de regulamentação, segurança e soberania de dados em algumas jurisdições. Essas regiões garantem que os dados sejam processados e armazenados apenas dentro do território nacional ou sob controle governamental.
- Regiões soberanas atendem a necessidades específicas de conformidade e regulamentação, permitindo que governos e organizações em determinados países ou setores com altos requisitos de segurança utilizem os serviços de nuvem sem violar leis locais.

### Tipos de Regiões Soberanas:
1. **Azure Government**:
   - **Descrição**: Disponível apenas para entidades governamentais dos EUA, a região Azure Government é dedicada a cumprir os requisitos rigorosos de conformidade e segurança.
   - **Disponibilidade**: Exclusivo para uso por agências governamentais e seus parceiros nos EUA.
   
2. **Azure China**:
   - **Descrição**: Operado pela 21Vianet, o Azure China é uma instância separada do Azure, projetada para cumprir as regulamentações e leis de soberania de dados da China.
   - **Disponibilidade**: Exclusivo para entidades dentro da China, com serviços e suporte operados localmente.


---
##  Zonas de Disponibilidade e Datacenters do Azure

### Zonas de Disponibilidade (Availability Zones)
- **Descrição**: Zonas de Disponibilidade são localizações fisicamente separadas dentro de uma região do Azure. Cada zona é composta por um ou mais datacenters independentes, com infraestrutura de energia, refrigeração e rede próprias, o que aumenta a resiliência de serviços críticos.
- As Zonas de Disponibilidade protegem suas aplicações e dados de falhas no datacenter, interrupções regionais ou desastres naturais. São usadas para garantir alta disponibilidade e recuperação de desastres.

### Datacenters do Azure
- **Descrição**: Os datacenters são instalações físicas onde a infraestrutura de nuvem do Azure é hospedada. Cada datacenter contém servidores e equipamentos de rede que armazenam e processam os dados.
- Cada datacenter é parte de uma região e está interligado com baixa latência a outros datacenters dentro da mesma região. Eles garantem escalabilidade, segurança e redundância para os serviços do Azure.

---

## 2. Recursos e Grupos de Recursos do Azure

### Recursos do Azure
- **Descrição**: Um **recurso** no Azure é qualquer instância de um serviço que você cria e gerencia, como máquinas virtuais, redes virtuais, bancos de dados, contas de armazenamento, etc. 
- Os recursos são os componentes essenciais que compõem qualquer solução no Azure. Eles são provisionados, configurados e gerenciados conforme necessário para atender aos requisitos de uma aplicação.

### Grupos de Recursos (Resource Groups)
- **Descrição**: Um **Grupo de Recursos** é um container lógico que agrupa vários recursos do Azure para que eles possam ser gerenciados como uma unidade. Todos os recursos de um grupo compartilham o mesmo ciclo de vida e podem ser criados, atualizados e excluídos juntos.
- O agrupamento de recursos em grupos facilita a organização e gerenciamento. Ele ajuda a aplicar políticas, controlar o acesso e monitorar o uso de forma eficiente.

### Práticas Recomendadas para Grupos de Recursos:
1. **Organização**: Agrupe recursos que compartilham o mesmo ciclo de vida, como todos os recursos relacionados a uma aplicação.
2. **Gestão de Custo**: Facilita o controle de gastos, pois você pode ver o custo total dos recursos dentro de um grupo.
3. **Controle de Acesso**: Use o controle de acesso baseado em função (RBAC) para gerenciar permissões nos grupos de recursos.

---

##  Assinaturas e Grupos de Gerenciamento

### Assinaturas (Subscriptions)
- **Descrição**: Uma **assinatura** no Azure é um container que agrupa serviços e recursos. Ela define os limites de faturamento e controle de acesso para os recursos criados nela. Todos os recursos no Azure devem estar associados a uma assinatura.
- As assinaturas são usadas para separar ambientes, projetos ou divisões dentro de uma organização, ajudando a gerenciar e monitorar os custos de cada unidade separadamente.
- Cada assinatura tem limites em termos de recursos que podem ser criados, como o número de VMs, discos, e recursos de armazenamento.

### Grupos de Gerenciamento (Management Groups)
- **Descrição**: Os **Grupos de Gerenciamento** são containers que ajudam a organizar múltiplas assinaturas dentro de uma hierarquia. Eles facilitam a aplicação de políticas, o controle de acesso e a governança em várias assinaturas.
- Permitem que grandes organizações gerenciem e apliquem políticas de forma centralizada, garantindo consistência entre as assinaturas e melhorando a governança.

### Exemplo de Uso de Grupos de Gerenciamento:
- Um grupo de gerenciamento pode conter várias assinaturas que são usadas para desenvolvimento, teste e produção. Isso permite que políticas de segurança e conformidade sejam aplicadas de forma uniforme a todos os ambientes.

---

## 4. Hierarquia de Grupos de Recursos, Assinaturas e Grupos de Gerenciamento

### Estrutura Hierárquica:
1. **Grupos de Gerenciamento**: Estão no topo da hierarquia. Eles podem conter múltiplas assinaturas e permitem a gestão centralizada de várias assinaturas de forma eficiente.
2. **Assinaturas**: Ficam abaixo dos grupos de gerenciamento. Cada assinatura contém um conjunto de recursos e define limites de faturamento e controle de acesso.
3. **Grupos de Recursos**: Ficam abaixo das assinaturas. São containers que agrupam recursos como máquinas virtuais, bancos de dados e redes que compartilham o mesmo ciclo de vida.
4. **Recursos**: Estão na base da hierarquia. São instâncias específicas de serviços do Azure, como VMs, redes, contas de armazenamento, etc.

### Exemplo de Hierarquia:
- **Empresa ABC** (Grupo de Gerenciamento)
  - **Desenvolvimento** (Assinatura)
    - **App Web Dev** (Grupo de Recursos)
      - Máquina Virtual
      - Banco de Dados
  - **Produção** (Assinatura)
    - **App Web Prod** (Grupo de Recursos)
      - Máquina Virtual
      - Banco de Dados

---

