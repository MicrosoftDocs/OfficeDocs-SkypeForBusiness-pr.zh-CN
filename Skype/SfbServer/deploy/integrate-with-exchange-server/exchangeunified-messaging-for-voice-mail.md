---
title: 为 Skype for Business Server 语音邮件配置 Exchange Server 统一消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/11/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 摘要： 配置 Exchange Server 统一消息的 Skype Business Server 语音邮件。
ms.openlocfilehash: 76a73c396657d98871a0238fe840e08016bccf13
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894342"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>为 Skype for Business Server 语音邮件配置 Exchange Server 统一消息
 
**摘要：** 配置 Exchange Server 统一消息的 Skype Business Server 语音邮件。
  
Skype 业务服务器，您可以在 Exchange Server 2016 或 Exchange Server 2013; 中存储的语音邮件然后，这些语音邮件消息将显示为用户的收件箱中的电子邮件。 

> [!NOTE]
> Exchange 统一消息为以前已知不再可用在 Exchange 2019，但您可以仍使用电话系统中的记录的语音邮件，然后用户的 Exchange 邮箱中保留录制。 有关详细信息，请参阅[规划语音邮件云服务](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)。
  
如果您已配置的业务服务器和 Exchange Server 2016 或 Exchange Server 2013 的 Skype 之间的服务器到服务器身份验证，则表明已准备好安装统一消息。 为此，必须首先创建，并将新的统一消息拨号计划分配 Exchange 服务器上。 例如，（在 Exchange 命令行管理程序从运行） 这两个命令为 Exchange 配置新 3 位数字拨号计划：
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

在第一个命令，该示例的 VoIPSecurity 参数，并参数值"Secured"指示通过使用传输层安全性 (TLS) 进行加密的信号通道。 URIType“SipName”指示将使用 SIP 协议发送和接收消息，CountryOrRegionCode 为 1 指示拨号计划适用于美国。
  
在第二个命令中，传递给 ConfiguredInCountryOrRegionGroups 参数的参数值指定可在此拨号计划中使用的国家/地区组。 参数值"Anywhere，\*，\*，\*"设置以下：
  
- 组名 ("Anywhere")
    
- AllowedNumberString (\*，指示允许任意数字字符串的通配符)
    
- DialNumberString (\*，指示允许任意已拨的号码的通配符)
    
- TextComment (\*，指示允许任意文本命令的通配符)
    
> [!NOTE]
> 创建新的拨号计划也会创建一条默认邮箱策略。 
  
在创建和配置新拨号计划后，必须将新拨号计划添加至统一消息服务器中，然后修改该服务器的启动模式；特别需要指出的是，必须将启动模式设置为“双”。 您可以执行两项任务从 Exchange 命令行管理程序中：
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

配置统一消息服务器后，接下来应该运行 Enable-exchangecertificate cmdlet，以确保您的 Exchange 证书于统一消息服务：
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

在正确分配证书后，接下来必须在统一消息服务器上停止并重新启动 MsExchangeUM 服务。只要更改启动模式，就必须停止并重新启动此服务。
  
配置完统一消息服务器后，接下来可以配置 UM 调用路由器：
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

由于启动模式已更改，因此您必须在承载 UM 调用路由器的计算机上停止并重新启动 MsExchangeUMCR 服务。
  
要完成统一消息设置，接下来需要创建 UM 邮箱策略，然后使用该策略为用户启用统一消息。可使用类似如下的命令创建邮箱策略：
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

您可以使用类似如下的命令为用户启用统一消息：
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

在前一个命令中，Extensions 参数表示用户的电话分机号。在该示例中，用户的分机号为 100。
  
在启用其邮箱后，用户 kenmyer@litwareinc.com 应该能够使用 Exchange 统一消息。 您可以验证用户可以连接到 Exchange UM 由运行 Business Server 命令行管理程序中 Skype [Test-csexumconnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet:
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

如果已为第二个用户启用了统一消息，则可使用 [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet 验证第二个用户是否可为第一个用户留下语音邮件。
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>配置 Microsoft Exchange Server 统一消息 
> [!IMPORTANT]
> 如果您想要使用 Exchange 统一消息 (UM) 来提供呼叫应答、 Outlook Voice Access 或自动助理服务为企业语音用户，阅读[Plan for Business 的 Skype 中的 Exchange 统一消息集成](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)，并按本部分中的说明。 

若要配置 Exchange 统一消息 (UM) 与企业语音一起工作，您需要执行以下任务：

- 在运行 Exchange 统一消息 (UM) 服务的服务器上配置证书
  > [!NOTE]
  > 将所有客户端访问和邮箱服务器添加到所有 UM SIP URI 拨号计划。 如果没有，出站呼叫路由不能作为预期。 
- 创建一个或多个 UM SIP URI 拨号计划，订阅者访问电话号码，以及根据需要，然后创建相应 L 拨号计划。

- 使用 exchucutil.ps1 脚本执行以下操作：
    - 创建 UM IP 网关。
    - 创建 UM 智能寻线。
    - 授予 Skype Business Server 权限读取 UM Active Directory 域服务对象。
- 创建 UM 自动助理对象。
- 创建订阅者访问对象。
- 为创建一个 SIP URI 每个用户和将用户与 UM SIP URI 拨号计划。

### <a name="requirements-and-recommendations"></a>要求与建议

在开始之前，本节中的文档假定您已部署以下 Exchange 角色： 客户端访问和邮箱。 在 Microsoft Exchange Server Exchange UM 作为服务运行在这些服务器上。

此外请注意以下情况：
- 如果 Exchange UM 安装在多个林中，则必须在每个 UM 林执行 Exchange Server 集成步骤。 此外，每个 UM 林必须配置为信任的林在其中部署了 Skype 业务服务器，则和 whichSkype 中的为林的部署业务服务器必须配置为信任每个 UM 林。
- 在其中运行的统一消息服务，这两个 Exchange 服务器角色和业务服务器运行 Skype 的服务器上执行集成步骤。 执行的 Lync Server 2013 集成步骤之前，应执行的 Exchange Server 统一消息集成步骤。
  > [!NOTE]
  > 若要查看在哪些服务器上并且由哪些管理员角色执行哪些集成步骤，请参阅[集成的部署过程概述在本地统一消息和 Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)。 

必须在每台服务器运行 Exchange UM 上提供以下工具：
- Exchange 命令行管理程序
- 脚本 exchucutil.ps1，它将执行以下任务：
    - 业务服务器，请为每个 Skype 上创建一个 UM IP 网关。
    - 创建每个网关的智能寻线组。 每个智能寻线的引导标识符指定由前端池或 Standard Edition 服务器与网关相关联的 UM SIP URI 拨号计划。
    - 授予 Skype 的业务 Server 读取 Active Directory 域服务中的 Exchange UM 对象的权限。



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1 

当您正在为业务 Server 与 Exchange 统一消息 (UM) 集成 Microsoft Skype 时，您必须在命令行管理程序中运行 ExchUcUtil.ps1 脚本。 ExchUcUtil.ps1 脚本执行以下操作：

- 为每个 Skype 业务服务器池创建一个 UM IP 网关。

> [!IMPORTANT]
> ExchUcUtil.ps1 脚本将创建一个或多个 UM IP 网关。 您必须禁用上创建脚本的一个网关除外的所有 UM IP 网关的传出呼叫。 这包括禁用上运行脚本之前创建的 UM IP 网关的传出呼叫。 

- 创建 UM 智能寻每个 UM IP 网关。 每个智能寻线的引导标识符指定 Skype 用于业务 Server 前端池或 Standard Edition server 的与 UM IP 网关相关联的 UM SIP URI 拨号计划。
- 业务 Server 读取 Active Directory UM 容器对象，例如 UM 拨号计划、 自动助理、 UM IP 网关和 UM 智能寻权限的授予 Skype。
  > [!IMPORTANT]
  > 必须将每个 UM 林配置为信任的林顺序 Skype 业务服务器部署，并在其中部署业务 Server 2013 的 Skype 林必须配置为信任每个 UM 林。 如果 Exchange UM 安装在多个林中，则必须为每个 UM 林执行 Exchange Server 集成步骤或您必须指定 Skype Business Server 域。 例如，ExchUcUtil.ps1 – 林： <lync-域-控制器-fqdn>。 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>使用命令行管理程序运行 ExchUcUtil.ps1 脚本

在组织中的同一作为 Skype 的企业服务器拓扑中任何 Exchange 服务器上运行 ExchUcUtil.ps1 脚本。 您可以从邮箱服务器使用命令行管理程序中运行该脚本，也可以运行的客户端访问服务器上使用远程 Windows PowerShell 脚本。 如果您在组织中的客户端访问服务器上运行该脚本，客户端访问服务器将代理到组织中的邮箱服务器的远程 Windows PowerShell 会话。
> [!IMPORTANT]
> ExchUcUtil.ps1 脚本将创建一个或多个 UM IP 网关。 您必须禁用上创建脚本的一个网关除外的所有 UM IP 网关的传出呼叫。 这包括禁用上运行脚本之前创建的 UM IP 网关的传出呼叫。 若要禁用 UM IP 网关的传出呼叫，请参阅禁用传出呼叫的 UM IP 网关。 
> [!IMPORTANT]
> 您必须具有 Exchange Organization Management 角色的权限或者是要运行脚本的 Exchange Organization Administrators 安全组的成员。 

1. 打开 Exchange Management Shell。
2. 在 C:\Windows\System32 提示符处，键入**cd\<驱动器 letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts>。ExchUcUtil.ps1**，然后按 Enter。

#### <a name="how-do-you-know-this-worked"></a>您如何知道这样可行？

若要验证成功完成 ExchUcUtul.ps1 脚本，请执行以下操作：
- 使用 Get-umipgateway cmdlet 或 EAC 查看新 UM IP 网关或已创建的网关。
- 使用 Get-umhuntgroup cmdlet 或 EAC 查看新 UM 智能寻线组或已创建的组。

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>在运行 Exchange Server 统一消息的服务器上配置证书
 
如果您已规划中的业务服务器规划文档中的 Skype 的 Exchange 统一消息集成中所述部署 Exchange 统一消息 (UM)，并且想要提供 Exchange UM 中的企业语音用户的功能您组织可以使用以下过程在运行 Exchange UM 服务器上配置证书。

> [!IMPORTANT]
> 对于内部证书，运行 Skype 业务服务器的服务器和运行 Microsoft Exchange 的服务器必须拥有受信任相互受信任的根证书颁发机构证书。 证书颁发机构 (CA) 可以是相同，或不同的证书颁发机构，只要服务器具有其受信任的根证书颁发机构证书存储中注册的证书颁发机构的根证书。 

Exchange Server 必须配置了服务器证书，才能连接到 Skype 业务服务器：
1. 为 Exchange Server 下载 CA 证书。
2. 为 Exchange Server 安装 CA 证书。
3. 确认该 CA 的 Exchange 服务器的受信任的根 Ca 列表中。
4. 为 Exchange Server 创建证书请求并安装证书。 
5. 为 Exchange Server 分配证书。


**若要下载 CA 证书：**

1. 在运行 Exchange UM 服务器上，单击**开始**，单击**运行**类型**http://\<颁发 CA Server>/certsrv 名称**，然后单击**确定**。
2. 在选择任务下，单击**下载 CA 证书、 证书链或 CRL**。
3. 在**下载 CA 证书、 证书链或 CRL**下选择**Base 64 编码方式**，，然后单击**下载 CA 证书**。
   > [!NOTE]
   > 您还可以指定在此步骤的可分辨编码规则 (DER) 编码。 如果选择 DER 编码，此过程的下一步的文件类型和在步骤 10 个**到安装 CA 证书**是.p7b 而不是非.cer。 
4. 在**文件下载**对话框中，单击**保存**，然后将文件保存到硬盘上，在服务器上。 （文件会为.cer 或.p7b 文件扩展名，具体取决于您在上一步中选择的编码。）

**安装 CA 证书：**

1. 在运行 Exchange UM 服务器上，通过单击**启动**、**运行**，在打开框中键入**mmc** ，然后单击**确定**打开 Microsoft 管理控制台 (MMC)。
2. 在**文件**菜单中，单击**添加/删除管理单元**，然后单击**添加**。
3. 在**添加独立管理单元**框中，单击**证书**，然后单击**添加**。
4. 在“**证书管理单元**”对话框中，单击“**计算机帐户**”，然后单击“**下一步**”。
5. 在**选择计算机**对话框中，确认**本地计算机: （运行这个控制台的计算机）** 复选框处于选中状态，然后单击**完成**。
6. 单击**关闭**，然后单击**确定**。 
7. 在控制台树中，展开**证书 （本地计算机）**，展开**受信任的根证书颁发机构**，，然后单击**证书**。
8. 右键单击**证书**，单击**所有任务**，然后单击**导入**。
9. 单击" **下一步**"。 
10. 单击**浏览**找到文件，，，然后单击**下一步**。 （该文件将具有为.cer 或.p7b 文件扩展名，具体取决于您的**下载 CA 证书**的步骤 3 中选择的编码。
11. 单击**将所有证书放**入下列存储。
12. 单击**浏览**，然后选择**受信任的根证书颁发机构**。 
13. 单击**下一步**来验证设置，，，然后单击**完成**。 


**验证 CA 位于受信任根 Ca 的列表：**

1. 在运行 Exchange UM 服务器上，在 MMC 展开证书 （本地计算机）、 受信任根证书颁发机构，然后单击证书。
2. 在细节窗格中，确认您的 CA 位于受信任的 Ca 列表。


