---
title: Comunicação entre pontos de extremidade
titleSuffix: Configuration Manager
description: Saiba como os componentes e sistemas de sites do Configuration Manager se comunicam em uma rede.
ms.date: 10/25/2018
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: conceptual
ms.assetid: 68fe0e7e-351e-4222-853a-877475adb589
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5ebe37bb97c4a1e231bfaf94f420f7f0471f30f6
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56141952"
---
# <a name="communications-between-endpoints-in-configuration-manager"></a>Comunicação entre pontos de extremidade no Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Este artigo descreve como os clientes e sistemas de sites do Configuration Manager se comunicam pela sua rede. Ele inclui as seguintes seções:  

- [Comunicações entre os sistemas de sites em um site](#Planning_Intra-site_Com)  
    - [Do servidor do site para o ponto de distribuição](#bkmk_site2dp)  

- [Comunicações de clientes para serviços e sistemas de sites](#Planning_Client_to_Site_System)  
    - [Comunicação do cliente para o ponto de gerenciamento](#bkmk_client2mp)  
    - [Comunicação do cliente para o ponto de distribuição](#bkmk_client2dp)  
    - [Considerações sobre a comunicação do cliente da Internet ou de uma floresta não confiável](#BKMK_clientspan)  
    - [Sobre os sistemas de sites para a Internet](#bkmk_internetfacing)  

- [Comunicações entre florestas do Active Directory](#Plan_Com_X-Forest)  
    - [Suporte a computadores de domínio em uma floresta que não é confiável para a floresta do seu servidor do site](#bkmk_noforesttrust)  
    - [Suporte a computadores de um grupo de trabalho](#bkmk_workgroup)  
    - [Cenários compatíveis com um site ou hierarquia que abrange vários domínios e florestas](#bkmk_span)  



##  <a name="Planning_Intra-site_Com"></a> Comunicações entre os sistemas de sites em um site  

 Quando os sistemas de sites ou componentes do Configuration Manager se comunicam pela rede com outros sistemas de sites ou componentes no site, eles usam um dos seguintes protocolos, dependendo de como você configura o site:  

-   Protocolo SMB  

-   HTTP  

-   HTTPS  

Com exceção da comunicação entre o servidor do site e um ponto de distribuição, as comunicações de servidor para servidor em um site podem ocorrer a qualquer momento. Essas comunicações não usam mecanismos para controlar a largura de banda de rede. Como não é possível controlar a comunicação entre os sistemas de sites, não deixe de instalar servidores do sistema de sites em localizações que têm redes rápidas e bem conectadas.  


### <a name="bkmk_site2dp"></a> Do servidor do site para o ponto de distribuição 

Use as seguintes estratégias para ajudá-lo a gerenciar a transferência de conteúdo do servidor do site para os pontos de distribuição:  

-   Configurar o ponto de distribuição para agendamento e controle de largura de banda da rede. Esses controles lembram as configurações que são usadas por endereços entre sites. Use essa configuração em vez de instalar outro site do Configuration Manager quando a transferência de conteúdo para localizações remotas da rede for sua consideração principal de largura de banda.  

-   Você pode instalar um ponto de distribuição como um ponto de distribuição em pré-teste. Um ponto de distribuição em pré-teste permite que você use o conteúdo que é colocado manualmente no servidor de ponto de distribuição e remove a necessidade de transferir arquivos de conteúdo pela rede.  

Para obter mais informações, consulte [Manage network bandwidth for content management](manage-network-bandwidth.md) (Gerenciar largura de banda de rede para gerenciamento de conteúdo).



##  <a name="Planning_Client_to_Site_System"></a> Comunicações de clientes para serviços e sistemas de sites  

Os clientes iniciam a comunicação com as funções do sistema de sites, o Active Directory Domain Services e os serviços online. Para habilitar essas comunicações, os firewalls devem permitir o tráfego de rede entre clientes e o ponto de extremidade de suas comunicações. Para obter mais informações sobre as portas e os protocolos usados pelos clientes quando eles se comunicam com esses pontos de extremidade, confira [Portas usadas no Configuration Manager](/sccm/core/plan-design/hierarchy/ports).  

Antes que um cliente possa se comunicar com uma função do sistema de sites, o cliente usa a localização do serviço para localizar uma função que dá suporte ao protocolo do cliente (HTTP ou HTTPS). Por padrão, os clientes usam o método mais seguro disponível para eles. Para obter mais informações, confira [Entender como os clientes encontram serviços e recursos do site](/sccm/core/plan-design/hierarchy/understand-how-clients-find-site-resources-and-services).  

Para usar HTTPS, configure uma das seguintes opções:  

- Usar uma PKI (infraestrutura de chave pública) e instalar certificados PKI em clientes e servidores. Para obter informações sobre como usar certificados, confira [Requisitos de certificado de PKI](/sccm/core/plan-design/network/pki-certificate-requirements).  

- Começando na versão 1806, configure o site para **usar os certificados gerados pelo Configuration Manager para sistemas de sites HTTP**. Para obter mais informações, confira [HTTP aprimorado](/sccm/core/plan-design/hierarchy/enhanced-http).  

Quando você implanta uma função de sistema de site que usa o Internet Information Services (IIS) oferece suporte à comunicação de clientes, você deve especificar se os clientes conectam ao sistema de site usando HTTP ou HTTPS. Se você usar HTTP, também deve considerar as opções de assinatura e criptografia. Para obter mais informações, confira [Planejando a assinatura e a criptografia](/sccm/core/plan-design/security/plan-for-security#BKMK_PlanningForSigningEncryption).  


### <a name="bkmk_client2mp"></a> Comunicação do cliente para o ponto de gerenciamento

Há dois estágios quando um cliente se comunica com um ponto de gerenciamento: autenticação (transporte) e autorização (mensagem). Esse processo varia de acordo com os seguintes fatores: 
- Configuração do site: HTTP, HTTPS ou HTTP aprimorado
- Configuração do ponto de gerenciamento: Somente HTTPS ou permite HTTP ou HTTPS
- Identidade do dispositivo para cenários centrados em dispositivos
- Identidade do dispositivo para cenários centrados em usuários

Use a tabela a seguir para entender como este processo funciona:  

| Tipo de MP  | Autenticação de cliente  | Autorização do cliente<br>Identidade do dispositivo  | Autorização do cliente<br>Identidade do usuário  |
|----------|---------|---------|---------|
| HTTP     | Anônima<br>Com o HTTP aprimorado, o site verifica o token do *usuário* ou do *dispositivo* do Azure AD. | Solicitação de localização: Anônima<br>Pacote do cliente: Anônima<br>Registro, usando um dos seguintes métodos para provar a identidade do dispositivo:<br> – Anônimo (aprovação manual)<br> – Autenticação integrada ao Windows<br> – Token do *dispositivo* do Azure AD (HTTP aprimorado)<br>Após o registro, o cliente usa assinatura da mensagem para comprovar a identidade do dispositivo | Para cenários centrados no usuário, usando um dos seguintes métodos para provar a identidade do usuário:<br> – Autenticação integrada ao Windows<br> – Token do *usuário* do Azure AD (HTTP aprimorado) |
| HTTPS    | Use um dos métodos a seguir:<br> – Certificado PKI<br> – Autenticação integrada ao Windows<br> – Token do *usuário* ou do *dispositivo* do Azure AD | Solicitação de localização: Anônima<br>Pacote do cliente: Anônima<br>Registro, usando um dos seguintes métodos para provar a identidade do dispositivo:<br> – Anônimo (aprovação manual)<br> – Autenticação integrada ao Windows<br> – Certificado PKI<br> – Token do *usuário* ou do *dispositivo* do Azure AD<br>Após o registro, o cliente usa assinatura da mensagem para comprovar a identidade do dispositivo | Para cenários centrados no usuário, usando um dos seguintes métodos para provar a identidade do usuário:<br> – Autenticação integrada ao Windows<br> – Token do *usuário* do Azure AD |

> [!Tip]  
> Para obter mais informações sobre a configuração do ponto de gerenciamento para tipos de identidade do dispositivo diferentes e com o gateway de gerenciamento de nuvem, confira [Habilitar o ponto de gerenciamento para HTTPS](/sccm/core/clients/manage/cmg/certificates-for-cloud-management-gateway#bkmk_mphttps).  


### <a name="bkmk_client2dp"></a> Comunicação do cliente para o ponto de distribuição

Quando um cliente se comunica com um ponto de distribuição, ele só precisa autenticar antes de baixar o conteúdo. Use a tabela a seguir para entender como este processo funciona:


| Tipo de DP  | Autenticação de cliente  |
|----------|---------|
| HTTP     | – Anônimo, se permitido<br>– Autenticação integrada ao Windows com conta de computador ou conta de acesso à rede<br> – Token de acesso ao conteúdo (HTTP aprimorado) |
| HTTPS    | – Certificado PKI<br> – Autenticação integrada ao Windows com conta de computador ou conta de acesso à rede<br> – Token de acesso ao conteúdo |


###  <a name="BKMK_clientspan"></a> Considerações sobre a comunicação do cliente da Internet ou de uma floresta não confiável  

As funções do sistema de sites a seguir instaladas em sites primários dão suporte a conexões de clientes que estão em localizações não confiáveis, como a Internet ou uma floresta não confiável. (Sites secundários não dão suporte a conexões de cliente de localizações não confiáveis.) 

-   Ponto de site da Web do Catálogo de Aplicativos  

-   Módulo de política do Configuration Manager (NDES) 

-   Ponto de distribuição   

-   Ponto de distribuição baseado em nuvem (requer HTTPS)

-   Ponto proxy do registro  

-   Ponto de status de fallback  

-   Ponto de gerenciamento  

-   Ponto de atualização de software  

-   Gateway de gerenciamento de nuvem (requer HTTPS)


### <a name="bkmk_internetfacing"></a> Sobre os sistemas de sites para a Internet

> [!Note]  
> A seção a seguir é sobre os cenários de gerenciamento de clientes baseado na Internet. Não se aplica a cenários de gateway de gerenciamento de nuvem. Para obter mais informações, veja [Gerenciar clientes na Internet](/sccm/core/clients/manage/manage-clients-internet).  

Não há nenhum requisito para haver uma relação de confiança entre a floresta do cliente e a do servidor do sistema de sites. No entanto, quando a floresta que contém um sistema de sites para a Internet confia na floresta que contém as contas de usuário, essa configuração dá suporte a políticas baseadas no usuário para dispositivos na Internet ao habilitar, em **Política do Cliente**, a configuração do cliente **Habilitar solicitações da política de usuário de clientes da Internet**.  

Por exemplo, as configurações seguintes ilustram quando o gerenciamento de cliente baseado na Internet dá suporte a políticas de usuário para dispositivos na Internet:  

-   O ponto de gerenciamento baseado na Internet é na rede de perímetro em que um controlador de domínio somente leitura reside, para autenticar o usuário e um firewall intermediário permite pacotes do Active Directory.  

-   A conta do usuário está na Floresta A (a intranet) e o ponto de gerenciamento baseado na Internet está na Floresta B (a rede de perímetro). A floresta B confia na Floresta A e um firewall intermediário permite pacotes de autenticação.  

-   A conta de usuário e o ponto de gerenciamento baseados na Internet estão na Floresta A (intranet). O ponto de gerenciamento é publicado na Internet usando um servidor proxy da Web (como o Forefront Threat Management Gateway).  

> [!NOTE]  
>  Se a autenticação Kerberos falhar, a autenticação NTLM será tentada automaticamente.  

Como mostra o exemplo anterior, você pode colocar os sistemas de áreas baseados na Internet na intranet quando são publicados na Internet por meio de um servidor proxy da Web. Esses sistemas de sites podem ser configurados apenas para conexão de cliente pela Internet ou para conexões de cliente pela Internet e intranet. Ao usar um servidor proxy da Web, é possível configurá-lo para uma ponte do protocolo SSL para SSL (mais seguro) ou túnel SSL da seguinte maneira:  

-   **Ponte SSL para SSL:**   
    A configuração recomendada ao usar servidores proxy da Web para o gerenciamento de clientes baseado na Internet é a ponte SSL para SSL, que usa a terminação SSL com autenticação. Computadores cliente devem ser autenticados usando a autenticação do computador e os clientes herdados de dispositivos móveis são autenticados usando a autenticação do usuário. Os dispositivos móveis registrados pelo Configuration Manager não dão suporte à ponte SSL.  

     O benefício da terminação de SSL no servidor proxy Web é que os pacotes da Internet estão sujeitos a inspeção antes de serem encaminhados à rede interna. O servidor proxy Web autentica a conexão do cliente, termina a conexão e depois abre uma nova conexão autenticada com os sistemas de área baseados na Internet. Quando os clientes do Configuration Manager usam um servidor Web proxy, a identidade do cliente (GUID do cliente) fica protegida no conteúdo do pacote para que o ponto de gerenciamento não considere o servidor Web proxy como o cliente. Não há suporte para ponte no Configuration Manager com HTTP para HTTPS ou de HTTPS para HTTP.  

-   **Túnel**:   
    Se o servidor Web proxy não conseguir dar suporte aos requisitos da ponte SSL ou se desejar configurar o suporte da Internet para dispositivos móveis registrados pelo Configuration Manager, também haverá suporte para o túnel SSL. É uma opção menos segura, pois os pacotes de SSL da Internet são encaminhados para os sistemas de site sem terminação SSL, para que não possam ser inspecionados quanto a conteúdo malicioso. Quando você usa o túnel SSL, não existem requisitos de certificado do servidor proxy da Web.  



##  <a name="Plan_Com_X-Forest"></a> Comunicações entre florestas do Active Directory  

O Configuration Manager dá suporte a sites e hierarquias que abrangem florestas do Active Directory. Ele também dá suporte a computadores de domínio que não estão na mesma floresta do Active Directory que o servidor do site e a computadores de grupos de trabalho.  


### <a name="bkmk_noforesttrust"></a> Suporte a computadores de domínio em uma floresta que não é confiável para a floresta do seu servidor do site 

-   Instalar funções de sistema de sites nessa floresta não confiável, com a opção de publicar informações do site na floresta do Active Directory  

-   Gerenciar esses computadores como se fossem computadores de grupo de trabalho  

Ao instalar servidores do sistema de sites em uma floresta não confiável do Active Directory, a comunicação de cliente para servidor dos clientes da floresta é mantida na floresta e o Configuration Manager pode autenticar o computador usando o Kerberos. Ao publicar informações do site na floresta do cliente, os clientes se beneficiam da recuperação das informações do site, como uma lista de pontos de gerenciamento disponíveis da floresta do Active Directory, em vez de baixar essas informações de seu ponto de gerenciamento atribuído.  

> [!NOTE]  
>  Para gerenciar dispositivos na Internet, você pode instalar funções do sistema de áreas baseado na Internet em sua rede de perímetro, quando os servidores do sistema de site estiverem em uma floresta do Active Directory. Esse cenário não exige uma relação de confiança bidirecional entre a rede de perímetro e a floresta do servidor do site.  


### <a name="bkmk_workgroup"></a> Suporte a computadores de um grupo de trabalho  

-   Aprovar manualmente computadores do grupo de trabalho quando eles usarem conexões de cliente HTTP com funções de sistema de sites. O Configuration Manager não pode autenticar esses computadores usando o Kerberos.  

-   Configurar os clientes do grupo de trabalho para usar a Conta de Acesso à Rede para que esses computadores possam recuperar conteúdo de pontos de distribuição.  

-   Fornecer um mecanismo alternativo para os clientes do grupo de trabalho localizarem pontos de gerenciamento. Use a publicação DNS, WINS ou atribua diretamente um ponto de gerenciamento. Esses clientes não podem recuperar informações do site do Active Directory Domain Services.  

Para obter mais informações, consulte os seguintes artigos:  

-   [Gerenciar registros conflitantes](/sccm/core/clients/manage/manage-clients#BKMK_ConflictingRecords)  

-   [Conta de acesso de rede](/sccm/core/plan-design/hierarchy/fundamental-concepts-for-content-management#accounts-used-for-content-management)  

-   [Como instalar clientes do Configuration Manager em computadores do grupo de trabalho](/sccm/core/clients/deploy/deploy-clients-to-windows-computers#BKMK_ClientWorkgroup)  


###  <a name="bkmk_span"></a> Cenários compatíveis com um site ou hierarquia que abrange vários domínios e florestas  

#### <a name="scenario-1-communication-between-sites-in-a-hierarchy-that-spans-forests"></a>Cenário 1: Comunicação entre sites em uma hierarquia que abrange florestas  
Esse cenário exige uma relação de confiança de floresta bidirecional que dá suporte à autenticação Kerberos.  Se você não tiver uma relação de confiança de floresta bidirecional que dá suporte à autenticação Kerberos, o Configuration Manager não dará suporte a um site filho na floresta remota.  

O Configuration Manager dá suporte à instalação de um site filho em uma floresta remota que tem a relação de confiança bidirecional necessária com a floresta do site pai. Por exemplo, é possível colocar um site secundário em uma floresta diferente de seu site pai primário, contanto que a relação de confiança necessária exista.  

> [!NOTE]  
>  Um site filho pode ser um site primário (em que o site de administração central é o site pai) ou um site secundário.  

A comunicação entre sites no Configuration Manager usa replicação de banco de dados e transferências baseadas em arquivo. Ao instalar um site, é necessário especificar uma conta com a qual o site será instalado no servidor designado. Essa conta também estabelece e mantém a comunicação entre os sites. Depois que o site é instalado com êxito e inicia transferências baseadas em arquivos e replicação de banco de dados, não é necessário configurar mais nada para a comunicação com o site.  

Quando existe uma relação de confiança bidirecional na floresta, o Configuration Manager não necessita de nenhuma etapa adicional de configuração.  

Por padrão, quando você instala um novo site filho, o Configuration Manager configura os seguintes componentes:  

-   Uma rota de replicação baseada em arquivo entre sites em cada site que usa a conta de computador do servidor do site. O Configuration Manager adiciona a conta de computador de cada computador ao grupo **SMS_SiteToSiteConnection_&lt;sitecode\>** no computador de destino.  

-   Replicação de banco de dados entre os SQL Servers em cada site.  

Defina também as seguintes configurações:  

-   Firewalls e dispositivos de rede intermediários devem permitir os pacotes de rede de que o Configuration Manager necessita.  

-   A resolução de nomes deve funcionar entre as florestas.  

-   Para instalar um site ou de função do sistema do site, você deve especificar uma conta que tenha permissões de administrador local no computador especificado.  

#### <a name="scenario-2-communication-in-a-site-that-spans-forests"></a>Cenário 2: Comunicação em um site que abrange florestas  
Esse cenário não requer uma relação de confiança de floresta bidirecional.  

Sites primários oferecem suporte à instalação de funções do sistema de site em computadores em florestas remotas.  

-   O Ponto de Serviços Web do Catálogo de Aplicativos é a única exceção.  Ele só é compatível na mesma floresta que o servidor do site.  

-   Quando a função do sistema de site aceita conexões da Internet, como uma prática recomendada de segurança, instale as funções do sistema de site em uma localização em que o limite da floresta forneça proteção para o servidor de site (por exemplo, em uma rede de perímetro).  

Para instalar uma função do sistema de site em um computador em uma floresta não confiável:  

- Especifique uma **Conta de Instalação do Sistema de Site**, que o site usa para instalar a função do sistema de sites. (Essa conta deve ter credenciais administrativas locais à qual se conectar.) Em seguida, instale as funções do sistema de sites no computador especificado.  

- Selecione a opção do sistema de site **Exigir que o servidor do site inicie conexões com este sistema de site**. Essa configuração exige que o servidor do site estabeleça conexões com o servidor do sistema de site para transferir dados. Essa configuração impede que o computador na localização não confiável inicie contato com o servidor do site que está na rede confiável. Essas conexões usam a **Conta de Instalação do Sistema de Site**.  

Para usar uma função de sistema de sites que foi instalada em uma floresta não confiável, os firewalls devem permitir o tráfego de rede, mesmo quando o servidor do site iniciar a transferência de dados.  

Além disso, as seguintes funções de sistema de site exigem acesso direto ao banco de dados do site. Portanto, os firewalls devem permitir o tráfego aplicável da floresta não confiável para o SQL Server do site:  

-   Ponto de sincronização do Asset Intelligence  

-   Ponto do Endpoint Protection  

-   Ponto de registro  

-   Ponto de gerenciamento  

-   Ponto de serviço de relatório  

-   Ponto de migração de estado  

Para obter mais informações, confira [Portas usadas no Configuration Manager](/sccm/core/plan-design/hierarchy/ports).  

Você pode precisar configurar o acesso do ponto de gerenciamento e do ponto de registro ao banco de dados do site.

-   Por padrão, quando você instala essas funções, o Configuration Manager configura a conta de computador do novo servidor do sistema de sites como a conta de conexão para a função do sistema de sites. Depois ele adiciona a conta à função de banco de dados do SQL Server apropriada.  

-   Quando você instala essas funções do sistema de site em um domínio não confiável, configure a conta de conexão da função do sistema de site para habilitá-la a obter informações do banco de dados.  

Se você configurar uma conta de usuário de domínio como uma conta de conexão para essas funções do sistema, verifique se a conta de usuário do domínio tem acesso adequado ao banco de dados do SQL Server naquele site:  

-   Ponto de gerenciamento: **Conta de Conexão de Banco de Dados do Ponto de Gerenciamento**  

-   Ponto de registro: **Conta de conexão do ponto de registro**  

Ao planejar funções do sistema de site em outras florestas, considere as seguintes informações adicionais:  

-   Se você executar o Firewall do Windows, configure os perfis de firewall aplicáveis ​​para passar a comunicação entre o servidor de banco de dados do site e os computadores instalados com as funções do sistema de sites remoto.   

-   Quando o ponto de gerenciamento com base em Internet tem uma relação de confiança com a floresta que contém as contas do usuário, as políticas do usuário têm suporte. Quando não existe uma relação de confiança, somente as políticas do computador têm suporte.  

#### <a name="scenario-3-communication-between-clients-and-site-system-roles-when-the-clients-arent-in-the-same-active-directory-forest-as-their-site-server"></a>Cenário 3: comunicação entre clientes e funções do sistema de sites quando os clientes não estão na mesma floresta do Active Directory que o servidor do site  
O Configuration Manager dá suporte aos seguintes cenários para os clientes que não estão na mesma floresta que o servidor do site:  

-   Há uma relação de confiança de floresta bidirecional entre a floresta do cliente e a floresta do servidor do site.  

-   O servidor da função do sistema de sites está localizado na mesma floresta que o cliente.  

-   O cliente está em um computador de domínio que não tem uma relação de confiança de floresta bidirecional com o servidor do site e as funções do sistema de sites não estão instaladas na floresta do cliente.  

-   O cliente está em um computador de grupo de trabalho.  

Os clientes em um computador ingressado em domínio podem usar o Active Directory Domain Services como o local do serviço quando seu site é publicado na floresta do Active Directory.  

Para publicar informações do site em outra floresta do Active Directory:  

-   Especificar a floresta e, em seguida, habilitar a publicação nessa floresta no nó **Florestas do Active Directory** do workspace **Administração**.  

-   Configurar cada site para publicar seus dados nos Serviços de Domínio Active Directory. Essa configuração permite que os clientes nessa floresta recuperem informações do site e localizem pontos de gerenciamento. Para clientes que não podem usar o Active Directory Domain Services na localização de serviço, é possível usar DNS, WINS ou o ponto de gerenciamento atribuído do cliente.  


####  <a name="bkmk_xchange"></a> Cenário 4: Colocar o conector do Exchange Server em uma floresta remota  

Para dar suporte a esse cenário, verifique se a resolução de nomes funciona entre as florestas. Por exemplo, configure encaminhamentos de DNS. Quando você configura o conector do Exchange Server, especifique o FQDN do Exchange Server da intranet. Para saber mais, confira [Gerenciar dispositivos móveis com o Configuration Manager e o Exchange](/sccm/mdm/deploy-use/manage-mobile-devices-with-exchange-activesync).  



## <a name="see-also"></a>Consulte também

- [Planejar a segurança](/sccm/core/plan-design/security/plan-for-security)  

- [Segurança e privacidade para clientes do Configuration Manager](/sccm/core/clients/deploy/plan/security-and-privacy-for-clients)  

