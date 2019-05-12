---
title: 管理受信任应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 受信任的应用程序是基于受 Business Server Skype 的 Microsoft 统一通信托管 API (UCMA) 3.0 核心 SDK 的应用程序。
ms.openlocfilehash: 0f483cc0a1a3a9e7dad881fc40819a9c27dacdec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911866"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>管理业务服务器中 Skype 的受信任应用程序

*受信任应用程序*是基于受 Business Server Skype 的 Microsoft 统一通信托管 API (UCMA) 3.0 核心 SDK 的应用程序。 有关 UCMA 应用程序的详细信息，请参阅"统一通信托管 API 3.0 Core SDK 文档"在http://go.microsoft.com/fwlink/p/?linkId=210320。

若要成功发布、 启用或禁用拓扑时添加或删除服务器角色，应以 RTCUniversalServerAdmins 和 Domain Admins 组成员的用户身份登录。 

使用本文以了解如何配置新的受信任应用程序服务器、 查看受信任的应用程序的列表和查看受信任应用程序的信息。 

## <a name="configure-a-new-trusted-application-server"></a>配置新的受信任应用程序服务器

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  启动拓扑生成器： 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server 拓扑生成器**。

3.  选择**下载从现有部署的拓扑**，，然后单击**确定**。

4.  在**将拓扑另存为**对话框中，单击您想要使用，该拓扑生成器文件，然后单击**保存**。

5.  在左窗格中，右键单击**受信任应用程序服务器**，然后单击**新建受信任应用程序池**。

6.  是它将包含单服务器还是多服务器，然后单击**下一步**，请输入的受信任应用程序池中，选择的**池 FQDN** 。

7.  在**选择下一个跃点**页上，从列表中，选择 Business Server 前端池的 Skype。

8.  单击“**完成**”。

9.  选择顶层节点**Skype 业务服务器**，，然后单击从**操作**菜单的**发布拓扑**。
    
    **受信任应用程序池**应已成功创建且与正确的前端池相关联。


## <a name="view-a-list-of-trusted-applications"></a>查看受信任应用程序的列表

您可以使用业务 Server Control Panel Skype 查看已在您 Skype 业务服务器环境中部署的受信任应用程序的列表。 受信任的应用程序是基于受 Business Server Skype 的 Microsoft 统一通信托管 API (UCMA) 3.0 核心 SDK 的应用程序。 以下列表概述了此信任关系：

  - 受信任应用程序不会要求进行身份验证 Skype 业务服务器。

  - 受信任应用程序不会限制进行 Skype 业务服务器的 SIP 事务、 连接或传出语音 (Voip) 呼叫。

  - 受信任应用程序可模拟任何用户，并可以加入会议而不出现在名单中。

  - 受信任应用程序是高可用性和恢复能力。

在业务 Server 控制面板的 Skype，您可以看到应用程序名称、 它们运行时所在的池以及它们使用的端口。


### <a name="to-view-a-list-of-trusted-applications"></a>若要查看的受信任应用程序列表

1.  使用分配给 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 有关业务服务器 Skype 中提供的预定义管理角色的详细信息，请参阅[基于角色的访问控制 (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md)。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。

3.  在左侧的导航栏中，单击**拓扑**，，然后单击**受信任应用程序**。

4.  在**受信任应用程序**页上，单击某个列标题进行排序的应用程序中，如果需要。


## <a name="view-trusted-application-information"></a>查看受信任应用程序信息

您可以使用 Windows PowerShell 和**Get-cstrustedapplication** cmdlet 查看有关受信任的应用程序的信息。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 


### <a name="to-view-trusted-applications"></a>若要查看受信任应用程序

若要查看所有受信任应用程序，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:
    
        Get-CsConferenceDisclaimer
    
   此命令将返回类似于每个受信任的应用程序的以下信息：
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   有关详细信息，请参阅[Get-cstrustedapplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)。
