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
description: 受信任的应用程序是基于 Microsoft 统一通信托管 API （UCMA） 3.0 Core SDK 受 Skype for Business Server 信任的应用程序。
ms.openlocfilehash: b2a257ad197d573beccb187ef49e41b3864c1a58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817073"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>在 Skype for Business 服务器中管理受信任的应用程序

*受信任的应用程序*是基于 Microsoft 统一通信托管 API （UCMA） 3.0 Core SDK 受 Skype For business Server 信任的应用程序。 有关 UCMA 应用程序的详细信息，请参阅 "统一通信托管 API 3.0 核心 SDK http://go.microsoft.com/fwlink/p/?linkId=210320文档"。

若要在添加或删除服务器角色时成功发布、启用或禁用拓扑，您应以 RTCUniversalServerAdmins 和域管理员组成员的用户身份登录。 

使用本文了解如何配置新的受信任的应用程序服务器、查看受信任的应用程序列表以及查看受信任的应用程序信息。 

## <a name="configure-a-new-trusted-application-server"></a>配置新的受信任的应用程序服务器

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 "skype for business**服务器**"，然后单击 " **skype for business 服务器拓扑生成器**"。

3.  选择 "**从现有部署下载拓扑**"，然后单击 **"确定"**。

4.  在 "**将拓扑另存为**" 对话框中，单击要使用的拓扑生成器文件，然后单击 "**保存**"。

5.  在左窗格中，右键单击 "**受信任的应用程序服务器**"，然后单击 "**新建受信任的应用程序池**"。

6.  输入受信任的应用程序池的**池 FQDN** ，选择它是单服务器还是多服务器，然后单击 "**下一步**"。

7.  在 "**选择下一个跃点**" 页面上，从列表中选择 "Skype For Business 服务器前端池"。

8.  单击“**完成**”。

9.  选择顶部节点**Skype for Business 服务器**，然后从 "**操作**" 菜单中单击 "**发布拓扑**"。
    
    **受信任的应用程序池**应已成功创建并与正确的前端池关联。


## <a name="view-a-list-of-trusted-applications"></a>查看受信任的应用程序列表

您可以使用 Skype for Business 服务器控制面板查看您在 Skype for business 服务器环境中部署的受信任的应用程序的列表。 受信任的应用程序是基于 Microsoft 统一通信托管 API （UCMA） 3.0 Core SDK 受 Skype for Business Server 信任的应用程序。 下表总结了此信任关系：

  - 受信任的应用程序不会受到 Skype for Business 服务器的身份验证的挑战。

  - Skype for Business Server 不会阻止受信任的应用程序进行 SIP 交易、连接或通过 Internet 协议（VoIP）呼叫发出语音。

  - 受信任的应用程序可以模拟任何用户，并且可以加入会议，而无需出现在海报中。

  - 受信任的应用程序高度可用且具有弹性。

在 Skype for Business 服务器控制面板中，你可以看到应用程序的名称、运行的池以及它们使用的端口。


### <a name="to-view-a-list-of-trusted-applications"></a>查看受信任的应用程序列表

1.  使用分配给 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 有关 Skype for Business Server 中可用的预定义管理角色的详细信息，请参阅[基于角色的访问控制（RBAC）](../plan-your-deployment/security/role-based-access-control-rbac.md)。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。

3.  在左侧导航栏中，单击 "**拓扑**"，然后单击 "**受信任的应用程序**"。

4.  如果需要，请在 "**受信任的应用程序**" 页面上，单击列标题以对应用程序进行排序。


## <a name="view-trusted-application-information"></a>查看受信任的应用程序信息

你可以使用 Windows PowerShell 和**CsTrustedApplication** cmdlet 查看有关你的受信任的应用程序的信息。 此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 


### <a name="to-view-trusted-applications"></a>查看受信任的应用程序

若要查看所有受信任的应用程序，请在 Skype for Business Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsConferenceDisclaimer
    
   此命令针对每个受信任的应用程序返回类似于以下内容的信息：
    
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
    
   有关详细信息，请参阅[CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)。
