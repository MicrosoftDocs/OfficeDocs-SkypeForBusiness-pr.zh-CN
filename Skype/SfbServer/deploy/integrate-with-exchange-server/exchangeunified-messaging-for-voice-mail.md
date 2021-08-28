---
title: 为Exchange Server语音邮件配置Skype for Business Server统一消息
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 摘要：为Exchange Server语音邮件配置Skype for Business Server统一消息。
ms.openlocfilehash: 94aa013a8330f6469af5a237911b4e627047f7a0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621814"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>为Exchange Server语音邮件配置Skype for Business Server统一消息
 
**摘要：** 为Exchange Server语音邮件配置Skype for Business Server统一消息。
  
Skype for Business Server 2016 或 Exchange Server 2013 中存储语音邮件Exchange Server语音邮件;这些语音邮件随后将在用户的收件箱中显示为电子邮件。 

> [!NOTE]
> Exchange以前已知的统一消息在 Exchange 2019 中不再可用，但您仍可以使用 电话系统 录制语音邮件，然后在用户的 Exchange 邮箱中保留录制。 有关详细信息[，请参阅云语音邮件](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)服务。
  
如果已在 Skype for Business Server 和 Exchange Server 2016 或 Exchange Server 2013 之间配置服务器到服务器身份验证，则已准备好设置统一消息。 为此，必须先在客户端上创建和分配新的统一消息拨号Exchange Server。 例如，这两个命令 (命令行管理程序Exchange内部) 配置新的 3 位拨号计划以用于Exchange：
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

在此示例的第一个命令中，VoIPSecurity 参数和参数值"Secured"指示信号通道使用传输层安全性 (TLS) 。 URIType“SipName”指示将使用 SIP 协议发送和接收消息，CountryOrRegionCode 为 1 指示拨号计划适用于美国。
  
在第二个命令中，传递给 ConfiguredInCountryOrRegionGroups 参数的参数值指定可在此拨号计划中使用的国家/地区组。 参数值"Anywhere， \* ， \* \* " 设置以下内容：
  
- 组名 ("Anywhere")
    
- AllowedNumberString (，一个指示允许任意 \* 数字字符串的通配符) 
    
- DialNumberString (，一个指示允许拨打的任何号码的 \* 通配符) 
    
- TextComment (，一个指示允许任何文本命令的 \* 通配符) 
    
> [!NOTE]
> 创建新拨号计划还会创建默认邮箱策略。 
  
在创建和配置新拨号计划后，必须将新拨号计划添加至统一消息服务器中，然后修改该服务器的启动模式；特别需要指出的是，必须将启动模式设置为“双”。 您可以在命令行管理程序内执行这两Exchange任务：
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

配置统一消息服务器后，接下来应运行 Enable-ExchangeCertificate cmdlet，以确保将 Exchange 证书应用于统一消息服务：
  
```powershell
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

在正确分配证书后，接下来必须在统一消息服务器上停止并重新启动 MsExchangeUM 服务。只要更改启动模式，就必须停止并重新启动此服务。
  
配置完统一消息服务器后，接下来可以配置 UM 调用路由器：
  
```powershell
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

由于启动模式已更改，因此您必须在承载 UM 调用路由器的计算机上停止并重新启动 MsExchangeUMCR 服务。
  
要完成统一消息设置，接下来需要创建 UM 邮箱策略，然后使用该策略为用户启用统一消息。可使用类似如下的命令创建邮箱策略：
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

您可以使用类似如下的命令为用户启用统一消息：
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

在前一个命令中，Extensions 参数表示用户的电话分机号。在该示例中，用户的分机号为 100。
  
在启用其邮箱后，用户 kenmyer@litwareinc.com 应该能够使用 Exchange 统一消息。 您可以通过从命令行管理程序Exchange [Test-CsExUMConnectivity](/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet 来验证用户能否连接到 Skype for Business Server UM：
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

如果已为第二个用户启用了统一消息，则可使用 [Test-CsExUMVoiceMail](/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet 验证第二个用户是否可为第一个用户留下语音邮件。
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>配置统一消息Microsoft Exchange Server 
> [!IMPORTANT]
> 如果要使用 Exchange 统一消息 (UM) 为 企业语音 用户提供呼叫应答、Outlook Voice Access 或自动助理服务，请阅读 Skype for Business 中的[规划 Exchange](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)统一消息集成，然后按照本节中的说明进行操作。 

若要Exchange统一 (UM) UM 企业语音，您需要执行以下任务：

- 在运行统一消息Exchange UM (服务的服务器上) 证书
  > [!NOTE]
  > 将所有客户端访问和邮箱服务器添加到所有 UM SIP URI 拨号计划。 如果没有，出站呼叫路由将不会像预期一样工作。 
- 根据需要创建一个或多个 UM SIP URI 拨号计划以及订阅者访问电话号码，然后创建相应的 L 拨号计划。

- 使用 exchucutil.ps1 脚本可以：
    - 创建 UM IP 网关。
    - 创建 UM 智能寻线。
    - 授予Skype for Business Server UM Active Directory 域服务对象的权限。
- 创建 UM 自动助理对象。
- 创建订阅者访问对象。
- 为每个用户创建 SIP URI，将用户与 UM SIP URI 拨号计划关联。

### <a name="requirements-and-recommendations"></a>要求与建议

在开始之前，本节中的文档假定你已部署以下Exchange角色：客户端访问和邮箱。 在Microsoft Exchange Server中Exchange UM 作为服务在这些服务器上运行。

另外还需注意以下事项：
- 如果Exchange多个林中安装了 UM，则必须Exchange Server UM 林执行统一集成步骤。 此外，必须将每个 UM 林配置为信任部署了 Skype for Business Server 的林，并且必须将部署Skype for Business Server 的林配置为信任每个 UM 林。
- 在运行统一消息服务的 Exchange Server 角色和运行统一消息服务的服务器上执行集成Skype for Business Server。 您应先执行统Exchange Server集成步骤，然后再执行 Lync Server 2013 集成步骤。
  > [!NOTE]
  > 若要了解哪些集成步骤在哪些服务器上执行以及由哪些管理员角色执行，请参阅部署过程[概述，](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)以集成本地统一消息和Skype for Business。 

在通过 UM 运行的每个服务器上，都必须Exchange工具：
- Exchange 命令行管理程序
- 脚本 exchucutil.ps1，它将执行以下任务：
    - 为每个网关创建一个 UM IP Skype for Business Server。
    - 为每个网关创建一个智能寻线。 每个智能寻组的引导标识符指定与网关关联的前端池或Standard Edition使用的 UM SIP URI 拨号计划。
    - 授予Skype for Business Server Active Directory 域服务Exchange UM 对象的权限。



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>使用统一消息配置 Microsoft Exchange 统一ExchUCUtil.ps1 

将 Microsoft Skype for Business Server 与 Exchange 统一 (UM) 集成时，您必须在命令行管理ExchUcUtil.ps1运行 ExchUcUtil.ps1 脚本。 ExchUcUtil.ps1 脚本会执行下列操作：

- 为每个池创建一个 UM IP Skype for Business Server网关。

> [!IMPORTANT]
> ExchUcUtil.ps1 脚本会创建一个或多个 UM IP 网关。 除该脚本创建的一个网关外，必须禁用所有 UM IP 网关上的传出呼叫。 这包括禁用在运行该脚本之前创建的 UM IP 网关上的传出呼叫。 

- 为每个 UM IP 网关创建一个 UM 智能寻线。 每个智能寻线引导标识符指定与 UM IP 网关关联的 Skype for Business Server 前端池或 Standard Edition 服务器使用的 UM SIP URI 拨号计划。
- 授予Skype for Business Server Active Directory UM 容器对象（如 UM 拨号计划、自动助理、UM IP 网关和 UM 智能寻线）的权限。
  > [!IMPORTANT]
  > 必须将每个 UM 林配置为信任部署了 Skype for Business Server 的林，并且必须将部署 Skype for Business Server 2013 的林配置为信任每个 UM 林。 如果Exchange多个林中安装了 UM，则必须为每个 UM 林执行 Exchange Server 集成步骤，否则您必须指定 Skype for Business Server 域。 例如，ExchUcUtil.ps1 –Forest：<lync-domain-controller-fqdn>。 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>使用命令行管理程序运行 ExchUcUtil.ps1 脚本

在ExchUcUtil.ps1拓扑与 Skype for Business Server 相同的组织中任何 Exchange 服务器上运行 Skype for Business Server。 您可以使用命令行管理程序从邮箱服务器运行此脚本，也可以使用客户端访问服务器上的远程 Windows PowerShell 运行此脚本。 如果在组织中的客户端访问服务器上运行此脚本，则客户端访问服务器会将远程 Windows PowerShell 会话代理到组织中的邮箱服务器。
> [!IMPORTANT]
> ExchUcUtil.ps1 脚本会创建一个或多个 UM IP 网关。除该脚本创建的一个网关外，必须禁用所有 UM IP 网关上的传出呼叫。这包括禁用在运行该脚本之前创建的 UM IP 网关上的传出呼叫。若要禁用 UM IP 网关上的传出呼叫，请参阅禁用 UM IP 网关的传出呼叫。[!IMPORTANT]
> 您必须具有 Exchange Organization Management 角色的权限，或是 Exchange Organization Administrators 安全组成员，才能运行此脚本。 

1. 打开 Exchange 命令行管理程序。
2. 在 C：\Windows\System32 提示符下，键入 **cd \<drive letter> ：\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1**，然后按 Enter。

#### <a name="how-do-you-know-this-worked"></a>您如何知道这有效？

若要验证是否已成功完成 ExchUcUtul.ps1 脚本，请执行以下操作：
- 使用 Get-UMIPGateway cmdlet 或 EAC 查看新 UM IP 网关或已创建的网关。
- 使用 Get-UMHuntGroup cmdlet 或 EAC 查看新 UM 智能寻线或已创建的智能寻线。

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>在运行统一消息的Exchange Server配置证书
 
如果已部署 Exchange 统一消息 (UM) （如规划文档中的规划 Skype for Business Server 中的 Exchange 统一消息集成中所述）并且希望向贵组织的 企业语音 用户提供 Exchange UM 功能，可以使用以下过程在运行 Exchange UM 的服务器上配置证书。

> [!IMPORTANT]
> 对于内部证书，运行 Skype for Business Server 和运行 Microsoft Exchange 必须具有相互信任的受信任的根证书颁发机构证书。 证书 (CA) 可以相同，也可以不同，只要服务器在受信任的根证书颁发机构证书存储中注册了证书颁发机构的根证书。 

必须使用Exchange Server证书配置服务器证书，才能连接到Skype for Business Server：
1. 为 Exchange Server 下载 CA 证书。
2. 为 Exchange Server 安装 CA 证书。
3. 确保该 CA 在 Exchange Server 的受信任的根 CA 列表中。
4. 为 Exchange Server 创建证书请求并安装该证书。 
5. 为 Exchange Server 分配证书。


**下载 CA 证书：**

1. 在运行 UM 的Exchange，单击"开始"，单击"运行"，http:// **\<name of your Issuing CA Server> /certsrv"，** 然后单击"确定 **"。**
2. 在"选择任务"下，单击 **"下载 CA 证书、证书链或 CRL"。**
3. 在 **"下载 CA 证书、证书链或 CRL"** 下，选择"编码方法 **到 Base 64"，** 然后单击"**下载 CA 证书"。**
   > [!NOTE]
   > 还可以在此步骤可辨别编码规则 (DER) 编码。 如果选择 DER 编码，则本过程的下一步中和 **“安装 CA 证书”** 的步骤 10 中的文件类型为 .p7b，而非 .cer。 
4. 在 **“文件下载”** 对话框中单击 **“保存”**，然后将文件保存到服务器上的硬盘中。（文件的扩展名将为 .cer 或 .p7b，具体取决于在上一步中选择的编码。）

**安装 CA 证书：**

1. 在运行 UM 的Exchange，打开 Microsoft 管理控制台 (MMC) ，方法是单击"开始"，再单击"运行"，在"打开"框中键入 **mmc，** 然后单击"确定 **"。**
2. 在 **“文件”** 菜单上，单击 **“添加/删除管理单元”**，然后单击 **“添加”**。
3. 在 **“添加独立管理单元”** 框中，单击 **“证书”**，然后单击 **“添加”**。
4. 在 **“证书管理单元”** 对话框中，单击 **“计算机帐户”**，然后单击 **“下一步”**。
5. 在 **"选择计算机**"对话框中，确认"本地计算机 **： (** 运行此控制台的计算机) 复选框，然后单击"完成 **"。**
6. 单击 **“关闭”**，然后单击 **“确定”**。 
7. 在控制台树中，展开 **“证书(本地计算机)”**，展开 **“受信任的根证书颁发机构”**，然后单击 **“证书”**。
8. 右键单击 **“证书”**，单击 **“全部任务”**，然后单击 **“导入”**。
9. 单击 **“下一步”**。 
10. 单击 **“浏览”** 找到文件，然后单击 **“下一步”**。（文件的扩展名将为 .cer 或 .p7b，具体取决于在 **“下载 CA 证书”** 的步骤 3 中选择的编码。）
11. 单击 **"将所有证书** 放在以下存储中"。
12. 单击 **“浏览”**，然后选择 **“受信任的根证书颁发机构”**。 
13. 单击 **“下一步”** 以验证设置，然后单击 **“完成”**。 


**验证 CA 是否位于受信任的根 CA 列表中：**

1. 在运行 UM 的Exchange，在 MMC 中展开"证书 (本地计算机) ，展开"受信任的根证书颁发机构"，然后单击"证书"。
2. 在详细信息窗格中，验证您的 CA 是否位于受信任的 CA 列表中。