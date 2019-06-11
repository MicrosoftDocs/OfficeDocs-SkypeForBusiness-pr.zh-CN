---
title: 'Lync Server 2013: 配置 Active Directory 联合身份验证服务 (AD FS 2.0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924f9c1b6e7fe64186eeee6a34364417d497866b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>为 Lync Server 2013 配置 Active Directory 联合身份验证服务 (AD FS 2.0)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-07-03_

下面一节介绍如何配置 Active Directory 联合身份验证服务 (AD FS 2.0) 来支持多重身份验证。 有关如何安装 AD FS 2.0 的信息, 请参阅广告 FS 2.0 分步介绍和操作指南[http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374)。

<div class="">


> [!NOTE]  
> 安装 AD FS 2.0 时，请勿使用 Windows Server Manager 添加联合身份验证服务角色。 请改为在<A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>RTW 下载并安装 Active Directory 联合身份验证服务2.0 程序包。



</div>

<div>


**针对双重身份验证配置 AD FS**

1.  使用域管理员帐户登录到 AD FS 2.0 计算机。

2.  启动 Windows PowerShell。

3.  从 Windows PowerShell 命令行，运行以下命令：
    
        add-pssnapin Microsoft.Adfs.PowerShell

4.  使用 Lync Server 2013 的累积更新建立与每个 Lync Server 2013 的合作关系: 7 月 2013 Director、Enterprise Pool 和标准版服务器, 通过运行以下命令来启用被动身份验证, 并替换特定于你的部署的服务器名称:
    
        Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  从“管理工具”菜单中，启动 AD FS 2.0 管理控制台。

6.  展开 "**信任关系** \> "**信赖方信任**。

7.  验证是否已为 Lync Server 2013 创建了新信任, 其中包含 Lync Server 2013 的累积更新: 7 月2013企业版池或标准版服务器。

8.  使用 Windows PowerShell 通过运行以下命令为您的依赖方信任创建并分配颁发授权规则：
    
       ```
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  使用 Windows PowerShell 通过运行以下命令为您的依赖方信任创建并分配颁发转换规则：
    
       ```
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. 从 AD FS 2.0 管理控制台中，右键单击您的依赖方信任并选择“编辑声明规则”****。

11. 选择“颁发授权规则”**** 选项卡，并验证是否已成功创建新的授权规则。

12. 选择“颁发转换规则”**** 选项卡，并验证是否已成功创建新的转换规则。

</div>

</div>

<span> </span>

</div>

</div>

</div>

