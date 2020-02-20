---
title: 管理受信任的应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 受信任的应用程序是基于 Microsoft 统一通信托管 API （UCMA） 3.0 Core SDK （受 Skype for Business Server 信任）的应用程序。
ms.openlocfilehash: c5c1a62440ebb98974cee5771c13cf0e5acc55c7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151222"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>在 Skype for Business Server 中管理受信任的应用程序

*受信任的应用程序*是基于 Microsoft 统一通信托管 API （UCMA） 3.0 Core SDK （受 Skype For business Server 信任）的应用程序。 有关 UCMA 应用程序的详细信息，请参阅中的 "统一通信托管 API 3.0 https://go.microsoft.com/fwlink/p/?linkId=210320核心 SDK 文档"。

若要在添加或删除服务器角色时成功发布、启用或禁用拓扑，应以 RTCUniversalServerAdmins 和 Domain Admins 组成员的用户身份登录。 

使用此文章可了解如何配置新的受信任应用程序服务器、查看受信任的应用程序列表以及查看受信任的应用程序信息。 

## <a name="configure-a-new-trusted-application-server"></a>配置新的受信任应用程序服务器

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **skype for business server**"，然后单击 " **skype for business server 拓扑生成器**"。

3.  选择“从现有部署下载拓扑”****，然后单击“确定”****。

4.  在 "**将拓扑另存为**" 对话框中，单击要使用的拓扑生成器文件，然后单击 "**保存**"。

5.  在左窗格中，右键单击 "**受信任的应用程序服务器**"，然后单击 "**新建受信任的应用程序池**"。

6.  输入受信任应用程序池的“池 FQDN”****，选择该池是单服务器池还是多服务器池，然后单击“下一步”****。

7.  在 "**选择下一个跃点**" 页上的列表中，选择 "Skype For Business Server 前端池"。

8.  单击“完成”****。

9.  选择最上面的节点**Skype For Business Server**，然后从 "**操作**" 菜单中单击 "**发布拓扑**"。
    
    应成功创建**受信任的应用程序池**，并将其与正确的前端池关联。


## <a name="view-a-list-of-trusted-applications"></a>查看受信任的应用程序列表

您可以使用 Skype for Business Server 控制面板查看您在 Skype for business Server 环境中部署的受信任应用程序的列表。 受信任的应用程序是基于 Microsoft 统一通信托管 API （UCMA） 3.0 Core SDK （受 Skype for Business Server 信任）的应用程序。 以下列表概述了此信任关系：

  - 受信任的应用程序不会受到 Skype for Business Server 的身份验证的挑战。

  - Skype for Business Server 不会限制受信任的应用程序的 SIP 事务、连接或传出的 Internet 协议（VoIP）呼叫。

  - 受信任应用程序可模拟任何用户，并能在不出现在名单中的情况下参加会议。

  - 受信任应用程序具有高可用性和恢复能力。

在 Skype for Business Server 控制面板中，可以看到应用程序的名称、运行的池以及它们所使用的端口。


### <a name="to-view-a-list-of-trusted-applications"></a>查看受信任应用程序列表

1.  从分配给 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的用户帐户中，登录到内部部署中的任何计算机。 有关 Skype for Business Server 中可用的预定义管理角色的详细信息，请参阅[基于角色的访问控制（RBAC）](../plan-your-deployment/security/role-based-access-control-rbac.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。

3.  在左侧导航栏中，单击 "**拓扑**"，然后单击 "**受信任的应用程序**"。

4.  在“受信任应用程序”**** 页上，单击某个列标题对应用程序进行排序（如果需要）。


## <a name="view-trusted-application-information"></a>查看受信任的应用程序信息

您可以使用 Windows PowerShell 和**CsTrustedApplication** cmdlet 查看有关受信任的应用程序的信息。 此 cmdlet 可从 Skype for Business Server 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 


### <a name="to-view-trusted-applications"></a>查看受信任应用程序

若要查看所有受信任的应用程序，请在 Skype for Business Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsConferenceDisclaimer
    
   此命令将为每个受信任应用程序返回类似于下面的信息：
    
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
    
   有关详细信息，请参阅 [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)。
