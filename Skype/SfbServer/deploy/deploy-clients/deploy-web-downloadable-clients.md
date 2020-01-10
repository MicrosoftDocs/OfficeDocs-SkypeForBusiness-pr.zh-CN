---
title: 在 Skype for Business 服务器中部署 Web 可下载的客户端
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 摘要：部署与 Skype for Business 一起使用的 Skype for business Web 应用和 Skype 会议应用。
ms.openlocfilehash: eb939ddf394ff62b9173939622a8ef3f20faaca9
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003522"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>在 Skype for Business 服务器中部署 Web 可下载的客户端

**摘要：** 部署用于 Skype for Business 服务器的 Skype for business 2015 Web 应用和 Skype 会议应用。

Skype for Business Web 应用是安装在运行 Skype for Business 服务器的服务器上的 Internet 信息服务（IIS） Web 客户端，默认情况下，它将按需部署到尚未使用 Skype for Business 客户端的会议用户。 这些会议用户通常从你的网络外连接。 每当用户单击会议 URL，但未安装 Skype for business 客户端时，将向用户显示使用最新版本的 Skype for Business Web 应用、Skype 会议应用或 Mac 版 Skype for business 加入会议的选项。

Skype for Business Web 应用中的语音、视频和共享功能需要 Microsoft ActiveX 控件，该控件用作用户浏览器的插件。 你可以提前安装 ActiveX 控件，或允许用户在出现提示时安装该控件，这会在首次使用 Skype for business Web 应用时或首次访问需要 ActiveX 控件的功能时进行安装。

> [!NOTE]
> 在 Skype for business Server Edge 服务器部署中，Skype for business Web 应用客户端访问需要在外围网络中使用 HTTPS 反向代理。 你还必须发布简单的 URL。 有关详细信息，请参阅[为 Skype For Business 服务器中的简单 Url](../../plan-your-deployment/network-requirements/simple-urls.md)[设置反向代理服务器](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx)和 DNS 要求。

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>为 Skype for Business Web 应用启用多重身份验证
<a name="MFA"> </a>

Skype for business Web 应用、Skype 会议应用和 Mac 版 Skype for Business 支持多重身份验证。 除了用户名和密码之外，你还可以要求其他身份验证方法（如智能卡或 Pin）对从外部网络登录到 Skype for business 会议的用户进行身份验证。 你可以通过部署 Active Directory 联合身份验证服务（AD FS）联合服务器并在 Skype for Business 服务器中启用被动身份验证来启用多重身份验证。 配置广告 FS 后，尝试加入 Skype for Business 会议的外部用户将显示一个广告 FS 多重身份验证网页，其中包含用户名和密码质询以及任何其他身份验证方法，你已配置。

> [!IMPORTANT]
> 如果您计划配置 AD FS 以进行多重身份验证，则以下是一些重要注意事项：

- 如果会议参加者和组织者位于同一组织中或都来自 AD FS 联盟组织，则 ADFS 多重身份验证生效。ADFS 多重身份验证不适用于 Lync 联盟用户，因为 Lync 服务器 Web 基础结构当前不支持该验证方法。

- 如果使用硬件负载平衡器，请在负载平衡器上启用 cookie 持久性，以便来自 Skype for Business Web 应用或会议应用客户端的所有请求都由同一前端服务器处理。

- 当您在 Skype for Business 服务器和 AD FS 服务器之间建立信赖方信任时，请分配足够长的令牌有效期，以延长 Skype for business 会议的最大长度。 通常，240 分钟的令牌使用时间就足够了。

- 此配置不适用于 Lync 移动客户端。

### <a name="configure-multi-factor-authentication"></a>配置多重身份验证

1. 安装 AD FS 联盟服务器角色。 有关详细信息，请参阅[Active Directory 联合身份验证服务2.0 部署指南](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. 为 AD FS 创建证书。 有关详细信息，请参阅和部署 AD FS 的计划["联合服务器证书"](https://go.microsoft.com/fwlink/p/?LinkId=285376)部分，以便与单一登录主题配合使用。

3. 从 Windows PowerShell 命令行界面中，运行以下命令：

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. 通过运行以下命令来建立合作关系：

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

Windows 7 和 Windows Server 2008 R2 中的 BranchCache 功能可能会干扰 Skype for Business Web App web 组件。 若要防止 Skype for business Web 应用用户出现问题，请确保未启用 "BranchCache"。

有关禁用 BranchCache 的详细信息，请参阅[BranchCache 部署指南](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)。

## <a name="verifying-skype-for-business-web-app-deployment"></a>验证 Skype for business Web 应用部署
<a name="MFA"> </a>

你可以使用 Test-CsUcwaConference cmdlet 来验证一对测试用户是否可以使用统一通信 Web API (UCWA) 参加会议。 有关此 cmdlet 的详细信息，请参阅 Skype for Business 服务器管理外壳文档中的[Test CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 。

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Windows Server 2008 R2 上的插件安装疑难解答
<a name="MFA"> </a>

如果在运行 Windows Server 2008 R2 的计算机上安装插件失败，可能需要修改 Internet Explorer 安全设置或 DisableMSI 注册表项设置。

### <a name="modify-the-security-setting-in-internet-explorer"></a>修改 Internet Explorer 的安全设置

1. 打开 Internet Explorer。

2. 依次单击 **“工具”**、**“Internet 选项”** 和 **“高级”**。

3. 向下滚动至 **“安全”** 部分。

4. 清除 **“不将加密的页存盘”**，然后单击 **“确定”**。

    > [!NOTE]
    > 如果选中此设置，则当尝试从 Skype for Business Web 应用下载附件时，此设置也会导致错误。

5. 重新加入会议。插件应该可以无误地下载。

### <a name="modify-the-disablemsi-registry-setting"></a>修改 DisableMSI 注册表设置

1. 单击 **“开始”**，然后单击 **“运行”**。

2. 要访问注册表编辑器，请键入 **regedit**。

3. 导航到 HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer。

4. 编辑或添加类型为 REG_DWORD 的 DisableMSI 注册表项，并将其设置为 0。

5. 重新加入会议。

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>启用 Skype 会议应用以替换 Skype for Business Web 应用（可选，Skype for business Server 2015 仅限）
<a name="SMA_Enable"> </a>

此过程是可选的，适用于 Skype for Business Server 2015 CU5 和更高版本。 如果不使用它，外部用户将继续使用 Skype for Business Web 应用加入会议。

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>启用简化会议加入和 Skype 会议应用

1. 当你启用对内容交付网络（CDN）的访问时，用户可以连接到 CDN online 并获取 Skype for Mac 应用（在 Windows 上）和 Skype for business for Mac （Mac），并且将使用简化的会议加入体验。

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. 允许客户端从会议加入网页或 Skype 会议应用发送到 Microsoft 服务器的客户端日志记录遥测（该命令默认为 false）。

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    发送给 Microsoft 的信息严格遵守[Skype For business 数据收集实践](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)。

3. 如果 CDN 不可用，则在回退到本地托管的 Skype for business Web 应用体验之前设置超时。 默认值是 6 秒。 如果将该值设置为 0，则没有超时。

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> 借助 Skype for Business Server 2015 中的 MeetingUxUseCdn 累积更新5，默认值设置为 False。 这会导致 Mac 版 Skype for Business 客户无法以来宾身份加入非联盟合作伙伴的会议，即使 Skype for business 管理员已将 MeetingUxUseCdn 设置为 True 也是如此。 若要使用此功能，Skype for business Server 2015 必须具有累积更新7、6.0.9319.534 或更高版本。 请参阅[在 skype for Business Server 2015 中启用 Skype 会议应用以替换 skype For Business Web 应用](https://support.microsoft.com/kb/4132312)。


## <a name="see-also"></a>另请参阅
<a name="SMA_Enable"> </a>

[规划会议客户端（Web 应用和会议应用）](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[在 Skype for Business 服务器中配置会议加入页面](../../manage/conferencing/meeting-join-page.md)

[Microsoft Online Services 隐私声明](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[许可条款和文档](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
