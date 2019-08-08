---
title: 为 Skype for Business Server 语音邮件配置 Exchange Server 统一消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: '摘要: 为 Skype for business 服务器语音邮件配置 Exchange Server 统一消息。'
ms.openlocfilehash: 514b2159c3836aee4bd6bcfad2b85311280277c4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238003"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>为 Skype for Business Server 语音邮件配置 Exchange Server 统一消息
 
**摘要:** 为 Skype for business 服务器语音邮件配置 Exchange Server 统一消息。
  
Skype for Business 服务器使你能够将语音邮件消息存储在 Exchange Server 2016 或 Exchange Server 2013 中;这些语音邮件将以电子邮件形式显示在用户的收件箱中。 

> [!NOTE]
> Exchange 2019 中不再提供 exchange 统一消息, 但您仍然可以使用 "电话系统" 录制语音邮件, 然后将录制内容保留在用户的 Exchange 邮箱中。 有关详细信息, 请参阅[规划云语音邮件服务](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)。
  
如果您已在 Skype for Business 服务器与 Exchange Server 2016 或 Exchange Server 2013 之间配置了服务器到服务器的身份验证, 则可以设置统一消息。 若要执行此操作, 必须首先在 Exchange 服务器上创建并分配新的统一邮件拨号计划。 例如, 这两个命令 (从 Exchange 命令行管理程序中运行) 为 Exchange 配置新的3位数拨号计划:
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

在示例中的第一个命令中, VoIPSecurity 参数和参数值 "受保护" 表示使用传输层安全 (TLS) 加密信号信道。 URIType“SipName”指示将使用 SIP 协议发送和接收消息，CountryOrRegionCode 为 1 指示拨号计划适用于美国。
  
在第二个命令中，传递给 ConfiguredInCountryOrRegionGroups 参数的参数值指定可在此拨号计划中使用的国家/地区组。 参数值 "Anywhere,\*,"\*,\*"设置以下各项:
  
- 组名 ("Anywhere")
    
- AllowedNumberString (\*, 通配符表示允许使用任何数字字符串)
    
- DialNumberString (\*, 表示允许任何拨出号码的通配符)
    
- TextComment (\*, 表示允许使用任何文本命令的通配符)
    
> [!NOTE]
> 创建新的拨号计划也会创建一条默认邮箱策略。 
  
在创建和配置新拨号计划后，必须将新拨号计划添加至统一消息服务器中，然后修改该服务器的启动模式；特别需要指出的是，必须将启动模式设置为“双”。 你可以从 Exchange 管理外壳程序中执行这两个任务:
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

配置统一消息服务器之后, 您应该下一步运行 ExchangeCertificate cmdlet 以确保 Exchange 证书应用于统一消息服务:
  
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
  
在启用其邮箱后，用户 kenmyer@litwareinc.com 应该能够使用 Exchange 统一消息。 你可以通过在 Skype for Business Server Management Shell 中运行[CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet 来验证用户是否可以连接到 Exchange UM:
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

如果已为第二个用户启用了统一消息，则可使用 [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet 验证第二个用户是否可为第一个用户留下语音邮件。
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>在 Microsoft Exchange Server 上配置统一消息 
> [!IMPORTANT]
> 如果要使用 Exchange 统一消息 (UM) 为企业语音用户提供呼叫应答、Outlook Voice Access 或自动助理服务, 请阅读[Skype For business 中 Exchange 统一消息集成的计划](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md), 然后按照本部分中的说明。 

要将 Exchange 统一消息 (UM) 配置为使用企业语音, 你需要执行以下任务:

- 在运行 Exchange 统一消息 (UM) 服务的服务器上配置证书
  > [!NOTE]
  > 将所有客户端访问和邮箱服务器添加到所有 UM SIP URI 拨号计划。 如果不是, 则出站呼叫路由不会按预期工作。 
- 创建一个或多个 UM SIP URI 拨号计划, 以及订阅者按需访问电话号码, 然后创建相应的 L 拨号计划。

- 使用 exchucutil 脚本执行以下操作:
    - 创建 UM IP 网关。
    - 创建 UM 查寻组。
    - 授予 Skype for Business 服务器读取 UM Active Directory 域服务对象的权限。
- 创建 UM 自动助理对象。
- 创建订阅者访问对象。
- 为每个用户创建 SIP URI 并将用户与 UM SIP URI 拨号计划相关联。

### <a name="requirements-and-recommendations"></a>要求与建议

开始之前, 本部分中的文档假定你已部署以下 Exchange 角色: 客户端访问和邮箱。 在 Microsoft Exchange Server 中, Exchange UM 在这些服务器上作为一项服务运行。

另请注意以下事项:
- 如果 Exchange UM 安装在多个林中, 则必须为每个 UM 林执行 Exchange Server 集成步骤。 此外, 必须将每个 UM 林配置为信任在其中部署 Skype for Business 服务器的林, 并且部署 whichSkype for Business Server 中的林必须配置为信任每个 UM 林。
- 在运行统一消息服务的 Exchange 服务器角色上以及运行 Skype for business 服务器的服务器上执行集成步骤。 在执行 Lync Server 2013 集成步骤之前, 应执行 Exchange Server 统一消息集成步骤。
  > [!NOTE]
  > 若要查看在哪些服务器及其管理员角色上执行哪些集成步骤, 请参阅[集成本地统一消息和 Skype for business 的部署过程概述](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)。 

以下工具必须在运行 Exchange UM 的每台服务器上可用:
- Exchange 命令行管理程序
- 脚本 exchucutil, 它执行以下任务:
    - 为每个 Skype for Business 服务器创建 UM IP 网关。
    - 为每个网关创建一个查寻组。 每个查寻组的引导标识符指定与网关相关联的前端池或标准版服务器使用的 UM SIP URI 拨号计划。
    - 授予 Skype for Business 服务器在 Active Directory 域服务中读取 Exchange UM 对象的权限。



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1 

将 Microsoft Skype for Business 服务器与 Exchange 统一消息 (UM) 集成时, 必须在 Shell 中运行 ExchUcUtil 脚本。 ExchUcUtil 脚本将执行下列操作:

- 为每个 Skype for business 服务器池创建 UM IP 网关。

> [!IMPORTANT]
> ExchUcUtil 脚本将创建一个或多个 UM IP 网关。 您必须在所有 UM IP 网关 (该脚本创建的一个网关除外) 上禁用传出呼叫。 这包括在运行脚本之前创建的 UM IP 网关上禁用传出呼叫。 

- 为每个 UM IP 网关创建一个 UM 查寻组。 每个查寻组的引导标识符指定与 UM IP 网关相关联的 Skype for Business Server 前端池或标准版服务器使用的 UM SIP URI 拨号计划。
- 授予 Skype for Business 服务器读取 Active Directory UM 容器对象 (如 UM 拨号计划、自动助理、UM IP 网关和 UM 查寻组) 的权限。
  > [!IMPORTANT]
  > 必须将每个 UM 林配置为信任在其中部署 Skype for Business 服务器的林, 并且必须将部署 Skype for business Server 2013 的林配置为信任每个 UM 林。 如果 Exchange UM 安装在多个林中, 则必须为每个 UM 林执行 Exchange Server 集成步骤, 否则你将必须指定 Skype for business 服务器域。 例如, ExchUcUtil-林: <lync 域控制器-fqdn>。 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>使用外壳运行 ExchUcUtil 脚本

在组织中与 Skype for business 服务器处于同一拓扑的任何 Exchange 服务器上运行 ExchUcUtil 脚本。 你可以使用 Shell 从邮箱服务器运行脚本, 也可以使用客户端访问服务器上的远程 Windows PowerShell 运行脚本。 如果你在组织中的客户端访问服务器上运行脚本, 客户端访问服务器会将远程 Windows PowerShell 会话代理到组织中的邮箱服务器。
> [!IMPORTANT]
> ExchUcUtil 脚本将创建一个或多个 UM IP 网关。 您必须在所有 UM IP 网关 (该脚本创建的一个网关除外) 上禁用传出呼叫。 这包括在运行脚本之前创建的 UM IP 网关上禁用传出呼叫。 若要禁用 UM IP 网关的传出呼叫, 请参阅禁用 UM IP 网关上的传出呼叫。 
> [!IMPORTANT]
> 您必须具有 Exchange 组织管理角色的权限, 或者是 Exchange 组织管理员安全组的成员才能运行脚本。 

1. 打开 Exchange 命令行管理程序。
2. 在 C:\Windows\System32 提示符下, 键入**cd \<驱动器号>: \Program Files\Microsoft\Exchange Server\V15\Scripts>。ExchUcUtil**, 然后按 Enter。

#### <a name="how-do-you-know-this-worked"></a>如何知道这是正常工作的？

若要验证 ExchUcUtul 脚本是否已成功完成, 请执行下列操作:
- 使用 UMIPGateway cmdlet 或 EAC 查看已创建的新 UM IP 网关或网关。
- 使用 UMHuntGroup cmdlet 或 EAC 查看已创建的新 UM 查寻组或组。

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>在运行 Exchange Server 统一消息的服务器上配置证书
 
如果已部署 Exchange 统一消息 (UM), 请参阅规划文档中的 Skype for Business 服务器中的 Exchange 统一消息集成规划中所述, 并希望向企业语音用户提供 Exchange UM 功能组织中, 你可以使用以下过程在运行 Exchange UM 的服务器上配置证书。

> [!IMPORTANT]
> 对于内部证书, 运行 Skype for Business 服务器的服务器和运行 Microsoft Exchange 的服务器都必须具有相互信任的受信任根颁发机构证书。 证书颁发机构 (CA) 既可以是相同的, 也可以是不同的证书颁发机构, 前提是服务器在其受信任的根颁发机构证书存储中注册了证书颁发机构的根证书。 

必须使用服务器证书配置 Exchange 服务器才能连接到 Skype for Business 服务器:
1. 下载 Exchange 服务器的 CA 证书。
2. 为 Exchange 服务器安装 CA 证书。
3. 验证 CA 是否位于 Exchange 服务器的受信任根 Ca 列表中。
4. 为 Exchange 服务器创建证书请求并安装证书。 
5. 为 Exchange Server 分配证书。


**要下载 CA 证书, 请执行以下操作:**

1. 在运行 Exchange UM 的服务器上, 单击 "**开始**", 单击 "**运行**", 键入**发证\<CA 服务器的 http://名称> "/Certsrv**", 然后单击 **"确定"**。
2. 在 "选择任务" 下, 单击 "**下载 CA 证书、证书链或 CRL**"。
3. 在 "**下载 Ca 证书、证书链或 CRL**" 下, 选择 "**编码方法以基本 64**", 然后单击 "**下载 CA 证书**"。
   > [!NOTE]
   > 您还可以在此步骤中指定可分辨编码规则 (DER) 编码。 如果选择 "DER 编码", 此过程的下一步中和**安装 CA 证书**的步骤10中的文件类型是. p7b 而不是 .cer。 
4. 在 "**文件下载**" 对话框中, 单击 "**保存**", 然后将文件保存到服务器上的硬盘。 (该文件将具有 .cer 或. p7b 文件扩展名, 具体取决于您在上一步中选择的编码。)

**要安装 CA 证书, 请执行以下操作:**

1. 在运行 Exchange UM 的服务器上, 依次单击 "**开始**" 和 "**运行**", 在 "打开" 框中键入**MMC** , 然后单击 **"确定"**, 打开 Microsoft 管理控制台 (MMC)。
2. 在 "**文件**" 菜单上, 单击 "**添加/删除管理单元**", 然后单击 "**添加**"。
3. 在 "**添加独立的管理单元**" 框中, 单击 "**证书**", 然后单击 "**添加**"。
4. 在“**证书管理单元**”对话框中，单击“**计算机帐户**”，然后单击“**下一步**”。
5. 在 "**选择计算机**" 对话框中, 验证 "**本地计算机: (运行此控制台的计算机)** " 复选框是否已选中, 然后单击 "**完成**"。
6. 单击 "**关闭**", 然后单击 **"确定"**。 
7. 在控制台树中, 展开 "**证书 (本地计算机)**", 展开 "**受信任的根证书颁发机构**", 然后单击 "**证书**"。
8. 右键单击 "**证书**", 单击 "**所有任务**", 然后单击 "**导入**"。
9. 单击" **下一步**"。 
10. 单击 "**浏览**" 找到文件, 然后单击 "**下一步**"。 (该文件将具有 .cer 或. p7b 文件扩展名, 具体取决于**下载 CA 证书**的步骤3中所选的编码。
11. 单击 "**将所有证书放**入下列存储"。
12. 单击 "**浏览**", 然后选择 "**受信任的根证书颁发机构**"。 
13. 单击 "**下一步**" 以验证设置, 然后单击 "**完成**"。 


**若要验证 CA 是否位于受信任根 Ca 列表中, 请执行以下操作:**

1. 在运行 Exchange UM 的服务器上, 在 MMC 中展开 "证书 (本地计算机)", 展开 "受信任的根证书颁发机构", 然后单击 "证书"。
2. 在 "详细信息" 窗格中, 验证您的 CA 是否在受信任的 Ca 列表中。


