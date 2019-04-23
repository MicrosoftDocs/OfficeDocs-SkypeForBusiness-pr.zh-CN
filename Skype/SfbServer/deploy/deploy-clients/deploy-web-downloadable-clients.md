---
title: 为业务服务器部署中 Skype Web 可下载的客户端
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 摘要： 部署企业 Web 应用程序和 Skype 会议应用程序与 Skype 用于业务 Skype。
ms.openlocfilehash: c974ff9d202c56b0a32c9983706a60b5d73c4de6
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "31959558"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>为业务服务器部署中 Skype Web 可下载的客户端

**摘要：** 部署企业 2015 Web 应用程序的 Skype 和 Skype 会议应用程序与 Skype 用于业务服务器。

企业 Web 应用程序的 Skype 是业务服务器运行 Skype 的服务器安装了 Internet 信息服务 (IIS) web 客户端，默认情况下，它将部署需要向会议用户尚不具有业务客户端的 Skype。 这些会议用户通常从你的网络外连接。 只要用户单击会议 URL，但没有业务客户端安装 Skype，用户将显示使用最新版本的 Skype 企业 Web 应用程序、 Skype 会议应用程序，或 for Business 的 Skype for mac。 加入会议选项

视频和共享的语音功能 Skype 中的企业 Web 应用程序要求用作用户的浏览器插件一个 Microsoft ActiveX 控件。 您可以提前安装 ActiveX 控件或允许用户安装它出现提示时，发生第一次企业 Web 应用程序使用 Skype 或他们访问功能在首次需要的 ActiveX 控件。

> [!NOTE]
> Skype 业务 Server 边缘服务器部署，在外围网络中的 HTTPS 反向代理是需要的 Skype 业务 Web App 客户端访问。 你还必须发布简单的 URL。 有关详细信息，请参阅[设置 Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [Skype 业务服务器中的简单 Url 的 DNS 要求](../../plan-your-deployment/network-requirements/simple-urls.md)。

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>启用 Skype 业务 Web 应用程序的多因素身份的验证
<a name="MFA"> </a>

Skype 企业 Web 应用程序、 Skype 会议应用程序和 Skype for Business for Mac 支持多因素身份验证。 除了用户名和密码，您可以要求其他身份验证方法，例如智能卡或旋转中心点，当用户登录到 Skype 业务会议加入从外部网络的用户进行身份验证。 您可以通过部署 Active Directory 联合身份验证服务 (AD FS) 联合服务器和启用业务服务器中 Skype 被动身份验证启用多重身份验证。 配置 AD FS 后，尝试业务会议加入 Skype 的外部用户显示包含用户名的 AD FS 多因素身份验证网页，以及任何其他身份验证方法的密码质询您已配置。

> [!IMPORTANT]
> 如果您计划配置 AD FS 以进行多重身份验证，则以下是一些重要注意事项：

- 如果会议参加者和组织者位于同一组织中或都来自 AD FS 联盟组织，则 ADFS 多重身份验证生效。ADFS 多重身份验证不适用于 Lync 联盟用户，因为 Lync 服务器 Web 基础结构当前不支持该验证方法。

- 如果您使用硬件负载平衡器，请启用负载平衡器上的 cookie 持久性，以便使来自业务 Web 应用程序或会议应用程序的客户端的 Skype 的所有请求均由同一前端服务器都处理。

- 当您信赖方之间建立信任业务服务器和 AD FS 服务器的 Skype 时，分配足够跨业务会议您 Skype 的最大长度令牌生命。 通常，240 分钟的令牌使用时间就足够了。

- 此配置不适用于 Lync 移动客户端。

### <a name="configure-multi-factor-authentication"></a>配置多重身份验证

1. 安装 AD FS 联盟服务器角色。 有关详细信息，请参阅[Active Directory 联合身份验证服务 2.0 部署指南](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. 为 AD FS 创建证书。 有关详细信息，请参阅["联合身份验证服务器证书"](https://go.microsoft.com/fwlink/p/?LinkId=285376)部分中的规划和部署 AD FS 以用于单一登录主题。

3. 从 Windows PowerShell 命令行界面，运行以下命令：

    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. 通过运行以下命令来建立合作关系：

    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. 设置以下信赖方规则：

    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>禁用 BranchCache 
<a name="MFA"> </a>

Windows 7 和 Windows Server 2008 R2 中的 BranchCache 功能中，可以干扰业务 Web 应用程序 web 组件的 Skype。 若要为企业 Web 应用程序用户的 Skype 阻止问题，请确保为未启用 BranchCache。

有关禁用 BranchCache 的详细信息，请参阅[BranchCache 部署指南](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)。

## <a name="verifying-skype-for-business-web-app-deployment"></a>验证 Skype 业务 Web 应用程序部署
<a name="MFA"> </a>

你可以使用 Test-CsUcwaConference cmdlet 来验证一对测试用户是否可以使用统一通信 Web API (UCWA) 参加会议。 有关此 cmdlet 的详细信息，请参阅中的业务 Server Management Shell 文档 Skype [Test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 。

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Windows Server 2008 R2 上的插件安装疑难解答
<a name="MFA"> </a>

如果运行 Windows Server 2008 R2 的计算机上，安装插件失败，您可能需要修改 Internet Explorer 安全设置或 DisableMSI 注册表项设置。

### <a name="modify-the-security-setting-in-internet-explorer"></a>修改 Internet Explorer 的安全设置

1. 打开 Internet Explorer。

2. 依次单击 **“工具”**、**“Internet 选项”** 和 **“高级”**。

3. 向下滚动至 **“安全”** 部分。

4. 清除 **“不将加密的页存盘”**，然后单击 **“确定”**。

    > [!NOTE]
    > 如果选中，此设置还将导致出错，尝试从 Skype 为企业 Web 应用程序下载附件时。

5. 重新加入会议。插件应该可以无误地下载。

### <a name="modify-the-disablemsi-registry-setting"></a>修改 DisableMSI 注册表设置

1. 单击 **“开始”**，然后单击 **“运行”**。

2. 要访问注册表编辑器，请键入 **regedit**。

3. 导航到 HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer。

4. 编辑或添加类型为 REG_DWORD 的 DisableMSI 注册表项，并将其设置为 0。

5. 重新加入会议。

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>启用 Skype 会议应用程序的业务 Web 应用程序 （可选，仅业务服务器 2015年的 Skype） 替换 Skype
<a name="SMA_Enable"> </a>

此过程是可选的并且适用于 Skype 业务服务器 2015 CU5 及更高版本。 如果不使用它，外部用户将继续使用 Skype 的企业 Web 应用程序加入会议。

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>启用简化会议加入和 Skype 会议应用

1. 启用访问到内容交付网络 (CDN) 时，用户将能够连接到 CDN online 和 for Mac （在 Mac)，获取业务 （Windows) 上的 Skype 会议应用程序和 Skype 和将使用简化了会议加入体验。

   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. 允许客户端日志记录遥测从会议加入网页或 Skype 会议应用程序发送给 Microsoft 服务器 （命令默认为 false）。

   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    在严格符合[业务数据集做法的 Skype](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)信息发送给 Microsoft。

3. 设置超时之前回退到本地承载 Skype 的业务 Web 应用程序体验中，如果 CDN 不可用。 默认值是 6 秒。 如果将该值设置为 0，则没有超时。

   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a>另请参阅
<a name="SMA_Enable"> </a>

[规划会议客户端 （Web 应用程序和会议应用程序）](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[配置会议中的业务服务器 Skype 的与会页面](../../manage/conferencing/meeting-join-page.md)

[Microsoft Online Services 隐私声明](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[许可条款和文档](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
