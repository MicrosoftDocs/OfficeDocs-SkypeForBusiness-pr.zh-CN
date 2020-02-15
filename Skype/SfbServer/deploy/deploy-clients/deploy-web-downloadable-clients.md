---
title: 在 Skype for Business Server 中部署 Web 可下载客户端
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 摘要：部署与 Skype for Business 一起使用的 Skype for Business Web 应用和 Skype 会议应用。
ms.openlocfilehash: 7f6bebbc9950a7eb5da202c3b818b1288c811f17
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029043"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>在 Skype for Business Server 中部署 Web 可下载客户端

**摘要：** 部署与 Skype for Business Server 一起使用的 Skype for Business 2015 Web 应用和 Skype 会议应用。

Skype for Business Web App 是安装在运行 Skype for Business Server 的服务器上的 Internet 信息服务（IIS） web 客户端，默认情况下，它将按需部署到尚不具有 Skype for Business 客户端的会议用户。 这些会议用户比不从网络外部连接更频繁。 只要用户单击会议 URL，但未安装 Skype for Business 客户端，用户就会看到使用最新版本的 Skype for Business Web App、Skype 会议应用或 Skype for business for Mac 加入会议的选项。

Skype for Business Web 应用程序中的语音、视频和共享功能需要 Microsoft ActiveX 控件，该控件可用作用户浏览器的插件。 您可以提前安装 ActiveX 控件，也可以允许用户在出现提示时安装它，这是在首次使用 Skype for Business Web App 时，或者在首次访问需要 ActiveX 控件的功能时发生。

> [!NOTE]
> 在 Skype for business Server Edge 服务器部署中，Skype for business Web App 客户端访问需要外围网络中的 HTTPS 反向代理。 您还必须发布简单 Url。 有关详细信息，请参阅[为 Skype For Business Server 中的简单 Url](../../plan-your-deployment/network-requirements/simple-urls.md)[设置反向代理服务器](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx)和 DNS 要求。

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>为 Skype for Business Web 应用启用多重身份验证
<a name="MFA"> </a>

Skype for Business Web App、Skype 会议应用和 Skype for business for Mac 支持多因素身份验证。 除了用户名和密码之外，您还可以需要其他身份验证方法（如智能卡或 Pin），以便在用户登录 Skype for business 会议时对从外部网络进行联接的用户进行身份验证。 你可以通过部署 Active Directory 联合身份验证服务（AD FS）联合服务器并在 Skype for Business Server 中启用被动身份验证来启用多重身份验证。 配置 AD FS 后，会向尝试加入 Skype for Business 会议的外部用户提供一个 AD FS 多重身份验证网页，其中包含用户名和密码质询以及你要使用的任何其他身份验证方法已配置。

> [!IMPORTANT]
> 如果您计划为多因素身份验证配置 AD FS，请注意以下事项：

- 如果会议参与者和组织者在同一组织中或来自 AD FS 联合组织，则多因素 ADFS 身份验证工作正常。 由于 Lync server web 基础结构目前不支持 Lync 联合用户，因此多因素 ADFS 身份验证不起作用。

- 如果使用硬件负载平衡器，请在负载平衡器上启用 cookie 暂留，以便来自 Skype for Business Web 应用或会议应用程序客户端的所有请求均由同一前端服务器处理。

- 当您在 Skype for Business Server 和 AD FS 服务器之间建立信赖方信任时，请分配足够长的令牌有效期，以跨越 Skype for business 会议的最大长度。 通常情况下，令牌寿命为240分钟就足够了。

- 这种配置不适用于 Lync 移动客户端。

### <a name="configure-multi-factor-authentication"></a>配置多重身份验证

1. 安装 AD FS 联合服务器角色。 有关详细信息，请参阅[Active Directory 联合身份验证服务2.0 部署指南](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. 为 AD FS 创建证书。 有关详细信息，请参阅规划和部署 AD FS 的["联合服务器证书"](https://go.microsoft.com/fwlink/p/?LinkId=285376)一节，以便与单一登录主题配合使用。

3. 从 Windows PowerShell 命令行界面中，运行以下命令：

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. 通过运行以下命令建立合作关系：

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. 设置以下信赖方规则：

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>禁用 BranchCache
<a name="MFA"> </a>

Windows 7 和 Windows Server 2008 R2 中的 BranchCache 功能可能会干扰 Skype for Business Web App web 组件。 若要防止 Skype for business Web App 用户的问题，请确保未启用 BranchCache。

有关禁用 BranchCache 的详细信息，请参阅[BranchCache 部署指南](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)。

## <a name="verifying-skype-for-business-web-app-deployment"></a>验证 Skype for Business Web 应用部署
<a name="MFA"> </a>

您可以使用 Test-csucwaconference cmdlet 来验证一对测试用户是否可以使用统一通信 Web API （UCWA）参与会议。 有关此 cmdlet 的详细信息，请参阅 Skype for Business Server 命令行管理程序文档中的[test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 。

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>在 Windows Server 2008 R2 上排除插件安装故障
<a name="MFA"> </a>

如果在运行 Windows Server 2008 R2 的计算机上安装插件失败，您可能需要修改 Internet Explorer 安全设置或 DisableMSI 注册表项设置。

### <a name="modify-the-security-setting-in-internet-explorer"></a>在 Internet Explorer 中修改安全设置

1. 打开 Internet Explorer。

2. 依次单击 "**工具**"、" **Internet 选项**" 和 "**高级**"。

3. 向下滚动到 "**安全性**" 部分。

4. 清除 "**不将加密的页面保存到磁盘**"，然后单击 **"确定"**。

    > [!NOTE]
    > 如果选中此选项，则在尝试从 Skype for Business Web 应用下载附件时，此设置也会导致错误。

5. 重新加入会议。 插件应下载，且不会出现错误。

### <a name="modify-the-disablemsi-registry-setting"></a>修改 DisableMSI 注册表设置

1. 单击“开始”****，再单击“运行”****。

2. 若要访问注册表编辑器，请键入**regedit**。

3. 导航到 HKEY_LOCAL_MACHINE \Software\Policies\Microsoft\Windows\Installer。

4. 编辑或添加 REG_DWORD 类型的 DisableMSI 注册表项，并将其设置为0。

5. 重新加入会议。

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>启用 Skype 会议应用程序以替换 Skype for Business Web 应用（可选，Skype for business Server 2015）
<a name="SMA_Enable"> </a>

此过程是可选的，适用于 Skype for Business Server 2015 CU5 及更高版本。 如果不使用它，外部用户将继续使用 Skype for Business Web 应用加入会议。

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>启用简化的会议加入和 Skype 会议应用

1. 当您启用对内容传递网络（CDN）的访问权限时，用户将能够连接到 CDN online 并获取 Skype for business （在 Windows 上）和 Skype for business for Mac （在 Mac 上），并将使用简化的会议加入体验。

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. 允许将来自会议加入网页或 Skype 会议应用的客户端日志记录遥测发送到 Microsoft 服务器（此命令默认为 false）。

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    发送给 Microsoft 的信息严格遵守[Skype For business 数据收集实践](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)。

3. 如果 CDN 不可用，则在回退到本地承载的 Skype for Business Web 应用体验之前设置超时。 默认值为6秒。 如果此值设置为0，则不会有任何超时。

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> 使用 Skype for Business Server 2015 累积更新5中的 MeetingUxUseCdn 时，默认值设置为 False。 这会导致 Skype for Business for Mac 客户端无法将非联合合作伙伴的会议作为来宾加入，即使 Skype for Business 管理员已将 MeetingUxUseCdn 设置为 True 也是如此。 为使此操作正常运行，Skype for Business Server 2015 必须具有累积更新7、6.0.9319.534 或更高版本。 请参阅[启用 Skype 会议应用以替换 skype for Business Server 2015 中的 skype For Business Web 应用](https://support.microsoft.com/kb/4132312)。


## <a name="see-also"></a>另请参阅
<a name="SMA_Enable"> </a>

[规划会议客户端（Web 应用程序和会议应用程序）](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[在 Skype for Business Server 中配置会议加入页面](../../manage/conferencing/meeting-join-page.md)

[Microsoft Online Services 隐私声明](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[许可条款和文档](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
