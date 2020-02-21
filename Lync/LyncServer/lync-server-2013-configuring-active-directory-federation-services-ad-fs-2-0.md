---
title: Lync Server 2013：配置 Active Directory 联合身份验证服务（AD FS 2.0）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9daaec9cbe32f031c7ee99731b1d7c7c9ec10ac1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>为 Lync Server 2013 配置 Active Directory 联合身份验证服务（AD FS 2.0）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-07-03_

下一节介绍如何配置 Active Directory 联合身份验证服务（AD FS 2.0）以支持多重身份验证。 有关如何安装 AD FS 2.0 的信息，请参阅 AD FS 2.0 分步和操作方法指南[https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374)。

<div class="">


> [!NOTE]  
> 安装 AD FS 2.0 时，请勿使用 Windows Server 管理器添加 Active Directory 联合身份验证服务角色。 请改为在上<A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>下载并安装 Active Directory 联合身份验证服务 2.0 RTW 包。



</div>

<div>


**将 AD FS 配置为进行双重身份验证**

1.  使用域管理员帐户登录到 AD FS 2.0 计算机。

2.  启动 Windows PowerShell。

3.  从 Windows PowerShell 命令行中，运行以下命令：
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  使用 Lync Server 2013 的累积更新建立与每个 Lync Server 2013 的合作关系：7月 2013 Director、Enterprise Pool 和 Standard Edition Server，通过运行以下命令将启用被动身份验证，并替换特定于您的部署的服务器名称：
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  从 "管理工具" 菜单中，启动 AD FS 2.0 管理控制台。

6.  展开 "**信任关系** \> "**信赖方信任**。

7.  验证是否已为你的 Lync Server 2013 创建了新的信任，并具有 Lync Server 2013 的累积更新：7月 2013 Enterprise Pool 或 Standard Edition Server。

8.  通过运行以下命令为您使用 Windows PowerShell 的信赖方信任创建并分配发布授权规则：
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  通过运行以下命令为您使用 Windows PowerShell 的信赖方信任创建并分配一个颁发转换规则：
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. 从 AD FS 2.0 管理控制台中，右键单击您的信赖方信任，然后选择 "**编辑声明规则**"。

11. 选择 "**颁发授权规则**" 选项卡，并验证是否已成功创建新的授权规则。

12. 选择 "**颁发转换规则**" 选项卡，并验证是否已成功创建新的转换规则。

</div>

</div>

<span> </span>

</div>

</div>

</div>

