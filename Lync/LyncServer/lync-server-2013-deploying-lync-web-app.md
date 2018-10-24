---
title: 部署 Lync Web App
TOCTitle: 部署 Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205190(v=OCS.15)
ms:contentKeyID: 49314011
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 部署 Lync Web App

 

_**上一次修改主题：** 2016-12-08_

Lync Web App 是随 Lync Server 2013 一起安装的 Internet 信息服务 (IIS) Web 客户端，默认情况下处于启用状态。无需任何其他步骤即可在服务器上启用 Lync Web App 或将 Web 客户端部署给用户。每当用户单击会议 URL，但未安装 Lync 2013 客户端时，即会向该用户呈现使用 Lync Web App 的最新版本加入会议的选项。

Lync Web App 中的语音、视频和共享功能需要 Microsoft ActiveX 控件。您可以提前安装 ActiveX 控件，或允许用户在出现提示时进行安装，用户第一次使用 Lync Web App 或第一次访问需要 ActiveX 控件的功能时，即会出现提示。

> [!NOTE]  
> 在 Lync Server 2013 边缘服务器部署中，在外围网络中，需要 HTTPS 反向代理才能访问 Lync Web App 客户端。您还必须发布简单 URL。有关详细信息，请参阅<a href="lync-server-2013-setting-up-reverse-proxy-servers.md">为 Lync Server 2013 设置反向代理服务器</a>和<a href="lync-server-2013-planning-for-simple-urls.md">在 Lync Server 2013 中规划简单 URL</a>。



## 针对 Lync Web App 启用多重身份验证

Lync Web App 的 Lync Server 2013 版本支持多重身份验证。当从外部网络加入的用户登录到 Lync 会议时，除了用户名和密码以外，您可能需要其他身份验证方法（如智能卡或 PIN）来对他们进行身份验证。您可以通过部署 Active Directory 联合身份验证服务 (AD FS) 联盟服务器并在 Lync Server 2013 中启用被动身份验证，来启用多重身份验证。在配置 AD FS 之后，会向尝试加入 Lync 会议的外部用户呈现 AD FS 多重身份验证网页，该网页包含用户名和密码质询，以及您已配置的任何其他身份验证方法。

> [!IMPORTANT]  
> 如果您计划配置 AD FS 以进行多重身份验证，则以下是一些重要注意事项：
> <ul>
> <li><p>如果会议参与者和组织者位于相同组织中或者来自 AD FS 联盟组织，则多重 ADFS 身份验证才有效。多重 ADFS 身份验证不适用于 Lync 联盟用户，因为 Lync 服务器 Web 基础结构当前不支持它。</p></li>
> <li><p>如果您使用硬件负载平衡器，请启用负载平衡器上的 Cookie 持久性，以便来自 Lync Web App 客户端的所有请求均由同一前端服务器进行处理。</p></li>
> <li><p>在 Lync Server 与 AD FS 服务器之间建立信赖方信任时，请分配足够长的令牌使用时间，以跨越 Lync 会议的最大长度。通常，240 分钟的令牌使用时间就足够了。</p></li>
> <li><p>此配置不适用于 Lync 移动客户端。</p></li>
> </ul>

**配置多重身份验证**

1.  安装 AD FS 联盟服务器角色。有关详细信息，请参阅《Active Directory 联合身份验证服务 2.0 部署指南》，网址为 [http://go.microsoft.com/fwlink/?linkid=267511\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=267511%26clcid=0x804)

2.  为 AD FS 创建证书。有关详细信息，请参阅“规划和部署 AD FS 以用于单一登录”主题（网址是 [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)）中的“联合服务器证书”一节。

3.  从 Windows PowerShell 命令行接口中，运行以下命令：
    
        add-pssnapin Microsoft.Adfs.powershell

4.  通过运行以下命令来建立合作关系：
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  设置以下信赖方规则：
    
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'

       &nbsp;
    
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules

       &nbsp;
    
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml

## BranchCache 配置

Windows 7 和 Windows Server 2008 R2 中的 BranchCache 功能可能会干扰 Lync Web App Web 组件。为了防止 Lync Web App 用户的问题，请确保未启用 BranchCache。

有关禁用 BranchCache 的详细信息，请参阅《BranchCache 部署指南》，该指南在 Microsoft 下载中心内以 Word 格式提供（网址为 [http://go.microsoft.com/fwlink/?linkid=268788\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268788%26clcid=0x804)），而在 Windows Server 2008 R2 技术库中以 HTML 格式提供（网址为 [http://go.microsoft.com/fwlink/?linkid=268789\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268789%26clcid=0x804)）。

## 验证 Lync Web App 部署

您可以使用 Test-CsUcwaConference cmdlet 来验证一对测试用户能否使用统一通信 Web API (UCWA) 参加会议。有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档中的 [Test-CsUcwaConference](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference)。

## 对 Windows Server 2008 R2 上的插件安装进行故障排除

如果在运行 Windows Server 2008 R2 的计算机上安装插件失败，您可能需要修改 Internet Explorer 安全设置或 DisableMSI 注册表项设置。

**在 Internet Explorer 中修改安全设置**

1.  打开 Internet Explorer。

2.  依次单击“工具”、“Internet 选项”和“高级”。

3.  向下滚动至“安全”部分。

4.  清除“不将加密的页存盘”，然后单击“确定”。
    
    > [!NOTE]  
    > 如果已选中，则在尝试从 Lync Web App 下载附件时，此设置还将导致错误。
    


5.  重新加入会议。插件在下载时应无错误。

**修改 DisableMSI 注册表设置**

1.  单击“开始”，然后单击“运行”。

2.  要访问注册表编辑器，请键入“regedit”。

3.  导航到 HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer。

4.  编辑或添加类型为 REG\_DWORD 的 DisableMSI 注册表项，并将其设置为 0。

5.  重新加入会议。

## 另请参阅

#### 概念

[在 Lync Server 2013 中配置与会页面](lync-server-2013-configuring-the-meeting-join-page.md)  
[Lync Server 2013 中 Lync Web App 支持的平台](lync-server-2013-lync-web-app-supported-platforms.md)

