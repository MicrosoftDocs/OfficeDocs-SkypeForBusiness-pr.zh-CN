---
title: Lync Server 2013：部署 Lync Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b7415be2210e6c791434ced8af8f309b49603e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a>在 Lync Server 2013 中部署 Lync Web App

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-07-18_

Lync Web App 是使用 Lync Server 2013 安装的 Internet Information Services （IIS） Web 客户端，默认情况下处于启用状态。 无需额外步骤即可在服务器上启用 Lync Web App 或将 Web 客户端部署到用户。 当用户单击会议 URL 但未安装 Lync 2013 客户端时，将向用户显示通过使用最新版本的 Lync Web App 加入会议的选项。

Lync Web App 中的语音、视频和共享功能需要 Microsoft ActiveX 控件。 你可以提前安装 ActiveX 控件，或允许用户在出现提示时安装该控件，这会在首次使用 Lync Web App 时或首次访问需要 ActiveX 控件的功能时进行安装。

<div class=" ">


> [!NOTE]  
> 在 Lync Server 2013 Edge 服务器部署中，Lync Web App 客户端访问需要在外围网络中使用 HTTPS 反向代理。 你还必须发布简单的 URL。 有关详细信息，请参阅为<A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync server 2013 设置反向代理服务器</A>和<A href="lync-server-2013-planning-for-simple-urls.md">在 Lync Server 2013 中规划简单 url</A>。



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>为 Lync Web App 启用多重身份验证

Lync Server 2013 版本的 Lync Web App 支持多重身份验证。 除了用户名和密码之外，你还可以要求其他身份验证方法（如智能卡或 Pin）对从外部网络登录到 Lync 会议的用户进行身份验证。 你可以通过在 Lync Server 2013 中部署 Active Directory 联合身份验证服务（AD FS）联合服务器并启用被动身份验证来启用多因素身份验证。 配置广告 FS 后，尝试加入 Lync 会议的外部用户将显示一个广告 FS 多重身份验证网页，其中包含用户名和密码质询以及已配置的任何其他身份验证方法。.

<div class=" ">


> [!IMPORTANT]  
> 如果您计划配置 AD FS 以进行多重身份验证，则以下是一些重要注意事项： 
> <UL>
> <LI>
> <P>如果会议参加者和组织者位于同一组织中或都来自 AD FS 联盟组织，则 ADFS 多重身份验证生效。ADFS 多重身份验证不适用于 Lync 联盟用户，因为 Lync 服务器 Web 基础结构当前不支持该验证方法。</P>
> <LI>
> <P>如果使用硬件负载平衡器，请在负载平衡器上启用 cookie 持久性，以便来自 Lync Web App 客户端的所有请求都由同一前端服务器处理。</P>
> <LI>
> <P>当您在 Lync Server 和 AD FS 服务器之间建立信赖方信任时，请分配足够长的令牌有效期以使您的 Lync 会议的最大长度更长。 通常，240 分钟的令牌使用时间就足够了。</P>
> <LI>
> <P>此配置不适用于 Lync 移动客户端。</P></LI></UL>



</div>

**配置多因素身份验证**

1.  安装 AD FS 联盟服务器角色。 有关详细信息，请参阅 Active Directory 联合身份验证服务2.0 部署指南，网址为<http://go.microsoft.com/fwlink/p/?linkid=267511>

2.  为 AD FS 创建证书。 有关详细信息，请参阅用于的计划和部署 AD FS 的 "联合身份验证服务器证书" 部分以与的单一登录主题配合[http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)使用。

3.  从 Windows PowerShell 命令行界面中，运行以下命令：
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  通过运行以下命令来建立合作关系：
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  设置以下信赖方规则：
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a>BranchCache 配置

Windows 7 和 Windows Server 2008 R2 中的 BranchCache 功能可能会干扰 Lync Web App web 组件。 若要防止 Lync Web App 用户出现问题，请确保未启用 "BranchCache"。

有关禁用 BranchCache 的详细信息，请参阅 "BranchCache 部署指南"，该指南在 Windows Server 2008 R2 技术库[http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788)中的 Microsoft 下载中心和 HTML 格式的 Word 格式中均提供[http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789)。

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>验证 Lync Web App 部署

你可以使用 Test-CsUcwaConference cmdlet 来验证一对测试用户是否可以使用统一通信 Web API (UCWA) 参加会议。 有关此 cmdlet 的详细信息，请参阅 Lync Server Management Shell 文档中的[Test CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) 。

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Windows Server 2008 R2 上的插件安装疑难解答

如果在运行 Windows Server 2008 R2 的计算机上安装插件失败，可能需要修改 Internet Explorer 安全设置或 DisableMSI 注册表项设置。

**修改 Internet Explorer 中的安全设置**

1.  打开 Internet Explorer。

2.  依次单击 **“工具”**、**“Internet 选项”** 和 **“高级”**。

3.  向下滚动至 **“安全”** 部分。

4.  清除 **“不将加密的页存盘”**，然后单击 **“确定”**。
    
    <div class=" ">
    

    > [!NOTE]  
    > 如果选中此设置，则当尝试从 Lync Web App 下载附件时，此设置也会导致错误。

    
    </div>

5.  重新加入会议。 插件应该可以无误地下载。

**修改 DisableMSI 注册表设置**

1.  单击 **“开始”**，然后单击 **“运行”**。

2.  要访问注册表编辑器，请键入 **regedit**。

3.  导航到 HKEY\_本地\_计算机\\软件\\策略\\Microsoft\\Windows\\Installer。

4.  编辑或添加 "REG\_DWORD" 类型的 DisableMSI 注册表项，并将其设置为 "0"。

5.  重新加入会议。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置与会页面](lync-server-2013-configuring-the-meeting-join-page.md)  
[Lync Web App 支持的 Lync Server 2013 平台](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

