---
title: 管理受信任的应用程序
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 受信任的应用程序是基于 Microsoft Unified Communications 托管 API (UCMA) 3.0 核心 SDK 的应用程序，受Skype for Business Server信任。
ms.openlocfilehash: 909ade1fbb44410d6b2acb695b8111e43d766e50
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674534"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>在Skype for Business Server中管理受信任的应用程序

*受信任的应用程序* 是基于 Microsoft Unified Communications 托管 API (UCMA) 3.0 核心 SDK 的应用程序，受Skype for Business Server信任。 有关 UCMA 应用程序的详细信息，请参阅“统一通信托管 API 3.0 核心 SDK 文档”https://go.microsoft.com/fwlink/p/?linkId=210320

若要在添加或删除服务器角色时成功发布、启用或禁用拓扑，应以 RTCUniversalServerAdmins 和 Domain Admins 组成员的用户身份登录。 

使用本文了解如何配置新的受信任应用程序服务器、查看受信任应用程序列表以及查看受信任的应用程序信息。 

## <a name="configure-a-new-trusted-application-server"></a>配置新的受信任应用程序服务器

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  "开始"菜单拓扑生成器：单击 **"开始"菜单**，单击 **“所有程序**”，单击 **Skype for Business Server**，然后单击 **Skype for Business Server拓扑生成器**。

3.  选择“从现有部署下载拓扑”，然后单击“确定”。

4.  在 **“将拓扑另存为** ”对话框中，单击要使用的拓扑生成器文件，然后单击“ **保存**”。

5.  在左窗格中，右键单击 **“受信任的应用程序服务器**”，然后单击 **“新建受信任的应用程序池**”。

6.  输入受信任应用程序池的“池 FQDN”，选择该池是单服务器池还是多服务器池，然后单击“下一步”。

7.  在 **“选择下一跃点**”页上，从列表中选择Skype for Business Server前端池。

8.  单击“完成”。

9.  选择顶部节 **点Skype for Business Server**，然后从 **“操作”** 菜单中单击 **“发布拓扑**”。
    
    应成功创建 **受信任的应用程序池** ，并与正确的前端池相关联。


## <a name="view-a-list-of-trusted-applications"></a>查看受信任应用程序的列表

可以使用Skype for Business Server 控制面板查看已在Skype for Business Server环境中部署的受信任应用程序的列表。 受信任的应用程序是基于 Microsoft Unified Communications 托管 API (UCMA) 3.0 核心 SDK 的应用程序，受Skype for Business Server信任。 以下列表概述了此信任关系：

  - Skype for Business Server不会对受信任的应用程序进行身份验证。

  - 对于 SIP 事务、连接或通过 Internet 的传出语音协议 (VoIP) 调用，Skype for Business Server不会限制受信任的应用程序。

  - 受信任应用程序可模拟任何用户，并能在不出现在名单中的情况下参加会议。

  - 受信任应用程序具有高可用性和恢复能力。

在Skype for Business Server 控制面板中，可以看到应用程序的名称、运行位置的池及其使用的端口。


### <a name="to-view-a-list-of-trusted-applications"></a>查看受信任应用程序列表

1.  从分配给 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的用户帐户登录到内部部署中的任何计算机。 有关Skype for Business Server中提供的预定义管理角色的详细信息，请[参阅基于角色的访问控制 (RBAC) ](../plan-your-deployment/security/role-based-access-control-rbac.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开Skype for Business Server 控制面板。

3.  在左侧导航栏中，单击 **拓扑**，然后单击 **“受信任的应用程序**”。

4.  在“受信任应用程序”页上，单击某个列标题对应用程序进行排序（如果需要）。


## <a name="view-trusted-application-information"></a>查看受信任的应用程序信息

可以使用 Windows PowerShell 和 **Get-CsTrustedApplication** cmdlet 查看有关受信任应用程序的信息。 此 cmdlet 可以从 Skype for Business Server Management Shell 运行，也可以从远程Windows PowerShell会话运行。 


### <a name="to-view-trusted-applications"></a>查看受信任应用程序

若要查看所有受信任的应用程序，请在 Skype for Business Server Management Shell 中键入以下命令，然后按 Enter：
    
   **Get-CsConferenceDisclaimer**
    
   此命令将为每个受信任应用程序返回类似于下面的信息：
    
   标识：CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9}，CN=应用程序联系人，CN=RTC 服务，CN=Services，CN=Configuration，DC=litware，DC=com<br/>
   RegistrarPool： 487279971<br/>
   HomeServer： CN=Lc Services，CN=Microsoft，CN=co1：2，CN=Pools，CN=RTC Service，CN=Services，CN=Configuration，DC=litware，DC=com OwnerUrn： urn：application：helpdesk<br/>
   SipAddress： sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com<br/>
   DisplayName：<br/>
   DisplayNumber：<br/>
   LineURI：<br/>
   PrimaryLanguage ： 0<br/>
   SecondaryLanguages： {}<br/>
   EnterpriseVoiceEnabled： True<br/>
   ExUmEnabled： False<br/>
   已启用： True<br/>
    
   有关详细信息，请参阅 [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication)。