---
title: "Segurança e privacidade para gerenciamento de aplicativos | System Center Configuration Manager"
description: "Práticas recomendadas de segurança e privacidade para gerenciamento de aplicativos no System Center Configuration Manager."
ms.custom: na
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-app
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 4d26deed-3b16-4116-b640-f618f2c20f5a
caps.latest.revision: 8
author: robstackmsft
ms.author: robstack
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: 1134bb2f04152288e72d40b1b1083f415cb4e900
ms.openlocfilehash: 2c954d2e0244536d74fe85ab98b0d581f7a8167f


---
# <a name="security-and-privacy-for-application-management-in-system-center-configuration-manager"></a>Segurança e privacidade para gerenciamento de aplicativos no System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*


##  <a name="security-best-practices-for-application-management"></a>Práticas recomendadas de segurança para gerenciamento de aplicativos  

|Prática recomendada de segurança|Mais informações|  
|----------------------------|----------------------|  
|Configurar os pontos do catálogo de aplicativos para usar conexões HTTPS e instruir os usuários sobre os perigos de sites mal-intencionados.|Configure o ponto de sites da Web do catálogo de aplicativos e o ponto de serviços Web do catálogo de aplicativos para aceitar conexões HTTPS para que o servidor seja autenticado para usuários e os dados transmitidos sejam protegidos contra violação e exibição. Ajude a evitar ataques de engenharia social ensinando os usuários a se conectar apenas a sites confiáveis.<br /><br /> Não use as opções de configuração de identidade visual que exibem o nome da sua organização no catálogo de aplicativos como prova de identidade quando você não usa HTTPS.|  
|Usar separação de funções e instalar o ponto de sites da Web do catálogo de aplicativos e o ponto de serviços do catálogo de aplicativos em servidores separados.|Se o ponto de sites da Web do catálogo de aplicativos estiver comprometido, instale-o em um servidor separado para o ponto de serviços Web do catálogo de aplicativos. Isso ajudará a proteger os clientes e a infraestrutura do Configuration Manager. Isso é particularmente importante se o ponto de sites da Web do catálogo de aplicativos aceita conexões de cliente da Internet, pois essa configuração deixa o servidor vulnerável a ataques.|  
|Treinar os usuários para fechar a janela do navegador quando terminarem de usar o catálogo de aplicativos.|Se os usuários navegarem para um site externo na mesma janela do navegador que usaram para o catálogo de aplicativos, o navegador continuará usando as configurações de segurança adequadas para sites confiáveis na intranet.|  
|Especificar manualmente a afinidade de dispositivo de usuário em vez de permitir que usuários identifiquem seu dispositivo primário; e não habilitar a configuração baseada em uso.|Não considere as informações coletadas dos usuários ou do dispositivo para autorização. Se você implantar software usando a afinidade de dispositivo de usuário não especificada por um usuário administrativo confiável, o software poderá ser instalado em computadores e em usuários não autorizados a receber esse software.|  
|Sempre configurar implantações para baixar conteúdo dos pontos de distribuição em vez de executar de pontos de distribuição.|Quando você configura implantações para baixar conteúdo de um ponto de distribuição e executar localmente, o cliente do Configuration Manager verifica o hash do pacote depois de baixar o conteúdo e descarta o pacote se o hash não corresponde ao hash na política. Em comparação, se você configurar a implantação para ser executada diretamente de um ponto de distribuição, o cliente do Configuration Manager não verificará o hash do pacote, o que significa que o cliente do Configuration Manager pode instalar software violado.<br /><br /> Se precisar executar implantações diretamente de pontos de distribuição, use o mínimo de permissões NTFS nos pacotes nos pontos de distribuição e use IPsec para proteger o canal entre o cliente e os pontos de distribuição e entre os pontos de distribuição e o servidor do site.|  
|Não permitir que usuários interajam com programas se a opção **Executar com direitos administrativos** for necessária.|Ao configurar um programa, você pode definir a opção **Permitir que os usuários interajam com este programa** para que os usuários possam responder a quaisquer solicitações na interface do usuário. Se o programa também estiver configurado para **Executar com direitos administrativos**, um invasor no computador que executa o programa poderá usar a interface do usuário para escalar privilégios no computador cliente.<br /><br /> Use programas de instalação baseados no Windows Installer com privilégios elevados por usuário para implantações de software que exigem credenciais administrativas, mas que devem ser executadas no contexto de um usuário que não tem credenciais administrativas. Os privilégios elevados por usuário do Windows Installer fornecem a maneira mais segura para implantar aplicativos que têm esse requisito.|  
|Restringir se os usuários podem instalar software interativamente usando a configuração do cliente **Permissões de instalação** .|Defina o dispositivo de cliente **Agente de Computador** configurando **Permissões de instalação** para restringir os tipos de usuários que podem instalar software usando o catálogo de aplicativos ou o Centro de Software. Por exemplo, crie uma configuração personalizada do cliente com as **Permissões de instalação** definidas como **Somente administradores**. Depois, aplique essa configuração do cliente a uma coleção de servidores para evitar que usuários sem permissões administrativas instalem software nesses computadores.|  
|Para dispositivos móveis, implantar somente os aplicativos assinados|Implante aplicativos de dispositivos móveis somente se eles têm assinatura por código de uma CA (autoridade de certificação) confiável pelo dispositivo móvel. Por exemplo:<br /><br /> – Um aplicativo de um fornecedor, que é assinado por uma AC já conhecida, como a VeriSign.<br /><br /> – Um aplicativo interno que você assina independentemente do Configuration Manager, usando a AC interna.<br /><br /> – Um aplicativo interno que você assina usando o Configuration Manager ao criar o tipo de aplicativo e usar um certificado de autenticação.|  
|Se você assinar aplicativos de dispositivos móveis usando o **Assistente para Criar Aplicativo** no Configuration Manager, proteja o local do certificado de autenticação e o canal de comunicação.|Para ajudar a proteger contra elevação de privilégios e ataques de falsificação, armazene o arquivo do certificado de autenticação em uma pasta protegida e use IPsec ou SMB entre os computadores a seguir:<br /><br /> – O computador que executa o console do Configuration Manager.<br /><br /> – O computador que armazena o arquivo do certificado de autenticação.<br /><br /> – O computador que armazena os arquivos de origem do aplicativo.<br /><br /> Como alternativa, assine o aplicativo independentemente do Configuration Manager e antes de executar o **Assistente para Criar Aplicativo**.|  
|Implementar controles de acesso para proteger computadores de referência.|Quando um usuário administrativo configura o método de detecção em um tipo de implantação navegando para um computador de referência, verifique se o computador não foi comprometido.|  
|Restringir e monitorar os usuários administrativos que recebem as funções de segurança baseadas em funções que estão relacionadas ao gerenciamento de aplicativos:<br /><br /> - **Administrador de Aplicativos**<br>- **Autor de Aplicativos**<br>- **Gerenciador de Implantação de Aplicativos**|Mesmo quando você configura a administração baseada em funções, os usuários administrativos que criar e implantam aplicativos podem ter mais permissões do que você imagina. Por exemplo, quando os usuários administrativos criam ou modificam um aplicativo, eles podem selecionas aplicativos dependentes que  não estão em seu escopo de segurança.|  
|Ao configurar ambientes virtuais do Microsoft Application Virtualization (App-V), selecione aplicativos no ambiente virtual que tem o mesmo nível de confiança.|Como os aplicativos em um ambiente virtual do App-V podem compartilhar recursos, como a área de transferência, configure o ambiente virtual de modo que os aplicativos selecionados tenham o mesmo nível de confiança.<br /><br /> Para mais informações, confira [Criar ambientes virtuais App-V](../../apps/deploy-use/create-app-v-virtual-environments.md).|  
|Se você implantar aplicativos em computadores Mac, verifique se os arquivos de origem são de uma fonte confiável.|A ferramenta CMAppUtil não valida a assinatura do pacote de origem, então, verifique se ele é originário de uma fonte confiável. A ferramenta CMAppUtil não é capaz de detectar se os arquivos foram violados.|  
|Se você implantar aplicativos para computadores Mac, proteja o local do arquivo **.cmmac** e proteja o canal de comunicação ao importá-lo no Configuration Manager.|Como o arquivo **.cmmac** que a ferramenta CMAppUtil gera e que você importa no Configuration Manager não está assinado nem validado, para ajudar a evitar a violação desse arquivo, armazene-o em uma pasta protegida e use IPsec ou SMB entre os computadores a seguir:<br /><br /> – O computador que executa o console do Configuration Manager.<br /><br /> – O computador que armazena o arquivo **.cmmac**.|  
|Se for configurar um tipo de implantação de aplicativo Web, use HTTPS, em vez de HTTP, para proteger a conexão.|Se você implantar um aplicativo web usando um link HTTP em vez de um link HTTPS, o dispositivo poderá ser redirecionado a um servidor não autorizado e os dados transferidos entre o dispositivo e o servidor poderão ser violados.|  

##  <a name="security-issues-for-application-management"></a>Problemas de segurança para gerenciamento de aplicativos  

-   Usuários com direitos limitados podem copiar arquivos do cache de cliente no computador cliente.  

     Os usuários podem ler o cache de cliente, mas não podem gravá-lo. Com permissões de leitura, um usuário pode copiar arquivos de instalação do aplicativo de um computador para outro.  

-   Usuários com direitos limitados podem modificar os arquivos que registram o histórico de implantação de software no computador cliente.  

     Como as informações do histórico do aplicativo não estão protegidas, um usuário pode modificar arquivos que informam se um aplicativo é instalado.  

-   Pacotes do App-V não são assinados.  

     Os pacotes do App-V no Configuration Manager não dão suporte à assinatura para verificar se o conteúdo é proveniente de uma fonte confiável e se ele não foi alterado em trânsito. Não há migração para este problema de segurança; siga a prática recomendada de segurança para baixar o conteúdo de uma fonte confiável e de um local seguro.  

-   Aplicativos publicados do App-V podem ser instalados por todos os usuários no computador.  

     Quando um aplicativo do App-V é publicado em um computador, todos os usuários que fizerem logon nesse computador poderão instalar o aplicativo. Isso significa que você não pode restringir quais usuários podem instalar o aplicativo após a publicação.  

-   Você não pode restringir as permissões de instalação para o portal da empresa.  

     Embora seja possível configurar uma definição de cliente para restringir as permissões de instalação, como por exemplo, a usuários primários do dispositivo ou somente administradores locais, essa definição não funciona no portal da empresa. Isso poderia resultar em uma elevação de privilégios porque um usuário poderia instalar um aplicativo que ele não deveria ter permissão para tal ação.  

##  <a name="certificates-for-microsoft-silverlight-5-and-elevated-trust-mode-required-for-the-application-catalog"></a>Certificados para o Microsoft Silverlight 5 e modo de confiança elevada necessários para o catálogo de aplicativos  
 Os clientes do Configuration Manager exigem o Microsoft Silverlight 5, que deve ser executado em modo de confiança elevada para que os usuários instalem o software do Catálogo de Aplicativos. Por padrão, os aplicativos Silverlight são executados no modo de confiança parcial para impedir que os aplicativos acessem dados do usuário. O Configuration Manager instalará automaticamente o Microsoft Silverlight 5 em clientes se ele ainda não estiver instalado e, por padrão, definirá a configuração de cliente **Permitir que aplicativos Silverlight sejam executados no modo de confiança elevada** do Agente de Computador como **Sim**. Essa configuração permite que os aplicativos Silverlight assinados e confiáveis solicitem o modo de confiança elevada.  

 Quando você instala a função do sistema de site do ponto de sites da Web do catálogo de aplicativos, o cliente também instala um certificado de autenticação da Microsoft no repositório de certificados do computador de Editores Confiáveis em cada computador cliente do Configuration Manager. Este certificado permite que aplicativos Silverlight assinados por este cerificado sejam executados no modo de confiança elevada que os computadores exigem para instalar software do catálogo de aplicativos. O Configuration Manager gerencia automaticamente este certificado de assinatura. Para garantir a continuidade do serviço, não exclua manualmente nem mova esse certificado de autenticação da Microsoft.  

> [!WARNING]  
>  Quando habilitada, a configuração do cliente **Permitir que os aplicativos Silverlight sejam executados no modo de confiança elevada** permite que todos os aplicativos Silverlight assinados por certificados no repositório de certificados de Editores Confiáveis no repositório do computador ou do usuário sejam executados em modo de confiança elevada. A configuração do cliente não pode habilitar o modo de confiança elevada especificamente para o catálogo de aplicativos do Configuration Manager ou para o repositório de certificados de Editores Confiáveis no repositório do computador. Se um malware adicionar um certificado não autorizado ao repositório de Editores Confiáveis, por exemplo, no repositório do usuário, o malware que usa seu próprio aplicativo Silverlight também poderá ser executado em modo de confiança elevada.  

 Se você definir a configuração do cliente **Permitir que os aplicativos Silverlight sejam executados no modo de confiança elevada** como **Não**, isso não removerá o certificado de autenticação da Microsoft dos clientes.  

 Para obter mais informações sobre aplicativos confiáveis no Silverlight, consulte [Trusted Applications (Aplicativos confiáveis)](http://go.microsoft.com/fwlink/p/?LinkId=252842).  

##  <a name="privacy-information-for-application-management"></a>Informações de privacidade sobre gerenciamento de aplicativos  
 O gerenciamento de aplicativos permite executar qualquer aplicativo, programa ou script em qualquer computador cliente ou dispositivo móvel cliente na hierarquia. O Configuration Manager não tem controle sobre quais tipos de aplicativos, programas ou scripts são executados ou quais tipos de informações eles transmitem. Durante o processo de implantação do aplicativo, o Configuration Manager pode transmitir informações entre clientes e servidores que identificam o dispositivo e as contas de logon.  

 O Configuration Manager mantém informações de status sobre o processo de implantação de software. As informações sobre o status da implantação de software não são criptografadas durante a transmissão, a menos que o cliente se comunica usando HTTPS. As informações de status não são armazenadas de forma criptografada no banco de dados.  

 O uso da instalação do aplicativo Configuration Manager para instalar software de modo remoto, interativo ou silencioso em clientes pode estar sujeito aos termos de licença para software desse software e está separado dos Termos de Licença para Software do System Center Configuration Manager. Sempre leia e concorde com os Termos de Licença para Software antes de implantar software usando o Configuration Manager.  

 A implantação do aplicativo não acontece por padrão e requer várias etapas de configuração.  

 Dois recursos opcionais que ajudam na implantação de software eficiente são a afinidade de dispositivo de usuário e o catálogo de aplicativos:  

-   A afinidade de dispositivo de usuário mapeia um usuário para dispositivos de modo que um administrador do Configuration Manager possa implantar software em um usuário, e o software seja instalado automaticamente em um ou mais computadores usados pelos usuários com mais frequência.  

-   O catálogo de aplicativos é um site que permite aos usuários solicitar o software a ser instalado.  

 Exiba as seguintes seções para obter informações de privacidade sobre a afinidade de dispositivo de usuário e o catálogo de aplicativos.  

 Para poder configurar o gerenciamento de aplicativos, considere seus requisitos de privacidade.  

##  <a name="user-device-affinity"></a>Afinidade de dispositivo do usuário  
-  O Configuration Manager pode transmitir informações entre clientes e sistemas de sites do ponto de gerenciamento que identificam o computador e a conta de logon, além do uso resumido das contas de logon.  
-  As informações transmitidas entre o cliente e o servidor não são criptografadas, a não ser que o ponto de gerenciamento esteja configurado para requerer que os clientes se comuniquem usando HTTPS.  
-  As informações do computador e de uso da conta de logon, usadas para mapear um usuário para um dispositivo, são armazenadas em computadores cliente, enviadas aos pontos de gerenciamento e então armazenadas no banco de dados do Configuration Manager. As informações antigas são excluídas do banco de dados por padrão após 90 dias. O comportamento de exclusão é configurável, definindo a tarefa de manutenção do site **Excluir Dados Antigos de Afinidade de Dispositivo de Usuário** .
-  O Configuration Manager mantém informações de status sobre afinidade de dispositivo de usuário. As informações de status não são criptografadas durante a transmissão, a menos que os clientes sejam configurados para se comunicar com pontos de gerenciamento usando HTTPS. As informações de status não são armazenadas de forma criptografada no banco de dados.  
-  Informações sobre uso do computador, da conta de logon e de status não são enviadas à Microsoft.  
-  Informações de uso do computador e logon, usadas para estabelecer afinidade de dispositivo e de usuário, estão sempre habilitadas. Além disso, os usuários e os usuários administrativos podem fornecer informações de afinidade de dispositivo de usuário.  

##  <a name="application-catalog"></a>Catálogo de aplicativos  
-  O catálogo de aplicativos permite que o administrador do Configuration Manager publique qualquer aplicativo, programa ou script para os usuários executarem. O Configuration Manager não tem controle sobre quais tipos de programas ou scripts são publicados no catálogo ou quais tipos de informações eles transmitem.    
-  O Configuration Manager pode transmitir informações entre clientes e as funções do sistema de sites do catálogo de aplicativos que identificam o computador e as contas de logon. As informações transmitidas entre o cliente e os servidores não são criptografadas, a não ser que essas funções do sistema de site sejam configuradas para requerer que os clientes se conectem usando HTTPS.  
-  As informações sobre a solicitação de aprovação do aplicativo são armazenadas no banco de dados do Configuration Manager. As solicitações canceladas ou negadas são excluídas por padrão após 30 dias, junto com as entradas de histórico de solicitação correspondentes. O comportamento de exclusão é configurável, definindo a tarefa de manutenção do site **Excluir Dados Antigos de Solicitação de Aplicativo** . As solicitações de aprovação de aplicativo que estão em estados aprovado e pendente nunca são excluídas.  
-  Informações enviadas para e a partir do catálogo de aplicativos não são enviadas à Microsoft.  
-  O catálogo de aplicativos não está instalado por padrão. Essa instalação requer várias etapas de configuração.  



<!--HONumber=Nov16_HO1-->

