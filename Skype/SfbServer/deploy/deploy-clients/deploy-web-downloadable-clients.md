---
title: 在 Skype for Business Server 中部署 Web 可下载客户端
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 摘要：部署与 Skype for Business 一同使用的 Skype for Business Web App 和 Skype 会议应用。
ms.openlocfilehash: 20489dddb244b179908f8c8a565bb1f4d539a5a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122126"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>在 Skype for Business Server 中部署 Web 可下载客户端

**摘要：** 部署与 Skype for Business Server 一同使用的 Skype for Business 2015 Web 应用和 Skype 会议应用。

Skype for Business Web App 是一个 Internet Information Services (IIS) Web 客户端，安装在运行 Skype for Business Server 的服务器上，默认情况下，它将按需部署到尚未拥有 Skype for Business 客户端的会议用户。 这些会议用户通常不是从网络外部连接。 每当用户单击会议 URL 但没有安装 Skype for Business 客户端时，都会向用户显示使用最新版本的 Skype for Business Web App、Skype 会议应用或 Skype for Business for Mac 加入会议的选项。

Skype for Business Web App 中的语音、视频和共享功能需要 Microsoft ActiveX 控件，该控件用作用户的浏览器的插件。 你可以提前安装 ActiveX 控件，或允许用户在出现提示时安装它，这发生在他们第一次使用 Skype for Business Web App 或首次访问需要 ActiveX 控件的功能时。

> [!NOTE]
> 在 Skype for Business Server 边缘服务器部署中，外围网络中需要 HTTPS 反向代理才能访问 Skype for Business Web App 客户端。 您还必须发布简单 URL。 有关详细信息，请参阅在[Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md)中设置反向[代理服务器](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers)和简单 URL 的 DNS 要求。

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>为 Skype for Business Web App 启用多重身份验证
<a name="MFA"> </a>

Skype for Business Web App、Skype 会议应用和 Skype for Business for Mac 支持多重身份验证。 除了用户名和密码之外，还可以要求其他身份验证方法（如智能卡或 PIN）来验证在登录到 Skype for Business 会议时从外部网络加入的用户。 可以通过部署 Active Directory 联合身份验证服务 (AD FS) 联合服务器，在 Skype for Business Server 中启用被动身份验证来启用多重身份验证。 配置 AD FS 后，将向尝试加入 Skype for Business 会议的外部用户显示 AD FS 多重身份验证网页，其中包含用户名和密码质询以及已配置的其他身份验证方法。

> [!IMPORTANT]
> 如果您计划为多重身份验证配置 AD FS，则以下为重要注意事项：

- 如果会议参与者和组织者位于同一组织中或都来自 AD FS 联盟组织，则多重 ADFS 身份验证有效。 多重 ADFS 身份验证对 Lync 联盟用户不起作用，因为 Lync Server Web 基础结构当前不支持它。

- 如果使用硬件负载平衡器，请对负载平衡器启用 Cookie 持久性，以便来自 Skype for Business Web App 或会议应用客户端的所有请求都由同一前端服务器处理。

- 在 Skype for Business Server 和 AD FS 服务器之间建立信赖方信任时，分配一个足够长的令牌生命周期，以跨越 Skype for Business 会议的最大长度。 通常，240 分钟的令牌使用时间就足够了。

- 此配置不适用于 Lync 移动客户端。

### <a name="configure-multi-factor-authentication"></a>配置多重身份验证

1. 安装 AD FS 联合服务器角色。 有关详细信息，请参阅 [Active Directory 联合身份验证服务 2.0 部署指南](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))

2. 为 AD FS 创建证书。 有关详细信息，请参阅计划和 [部署](/previous-versions/azure/azure-services/jj205462(v=azure.100)) AD FS 以用于单一登录主题的"联合服务器证书"部分。

3. 从Windows PowerShell命令行接口运行以下命令：

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

Windows 7 和 Windows Server 2008 R2 中的 BranchCache 功能可能会干扰 Skype for Business Web App Web 组件。 若要防止 Skype for Business Web App 用户的问题，请确保未启用 BranchCache。

有关禁用 BranchCache 的详细信息，请参阅 [BranchCache 部署指南](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)。

## <a name="verifying-skype-for-business-web-app-deployment"></a>验证 Skype for Business Web App 部署
<a name="MFA"> </a>

可以使用 Test-CsUcwaConference cmdlet 验证一对测试用户能否使用 UCWA (统一通信 Web API 参与) 。 有关此 cmdlet 的详细信息，请参阅 Skype for Business Server 命令行管理程序文档中的[Test-CsUcwaConference。](/powershell/module/skype/test-csucwaconference?view=skype-ps)

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Windows Server 2008 R2 上的插件安装疑难解答
<a name="MFA"> </a>

如果在运行 Windows Server 2008 R2 的计算机上安装插件失败，您可能需要修改 Internet Explorer 安全性设置或 DisableMSI 注册表项设置。

### <a name="modify-the-security-setting-in-internet-explorer"></a>修改 Internet Explorer

1. 打开 Internet Explorer。

2. 单击 **"工具**"，单击 **"Internet 选项**"，然后单击"**高级"。**

3. 向下滚动到"安全性 **"** 部分。

4. 清除 **"不将加密页面保存到磁盘"，** 然后单击"确定 **"。**

    > [!NOTE]
    > 如果选中此设置，则尝试从 Skype for Business Web App 下载附件时也会导致错误。

5. 重新加入会议。 插件应下载且不会出现错误。

### <a name="modify-the-disablemsi-registry-setting"></a>修改 DisableMSI 注册表设置

1. 单击“开始”，然后单击“运行”。

2. 若要访问注册表编辑器，请键入 **regedit**。

3. 导航到HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer。

4. 编辑或添加类型为 REG_DWORD的 DisableMSI 注册表项，将其设置为 0。

5. 重新加入会议。

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Enable Skype Meetings App to replace Skype for Business Web App (Optional， Skype for Business Server 2015 only) 
<a name="SMA_Enable"> </a>

此过程是可选的，适用于 Skype for Business Server 2015 CU5 及更高版本。 如果不使用它，外部用户将继续使用 Skype for Business Web App 加入会议。

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>启用简化的会议加入和 Skype 会议应用

1. 当你启用对内容交付网络 (CDN) 的访问权限时，用户将能够在 Windows) 和 Mac) 上的 Skype for Business (上联机连接到 CDN 和获取 Skype 会议应用 (，并且将使用简化的会议加入体验。

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. 允许将来自与会网页或 Skype 会议应用的客户端日志记录遥测发送到 Microsoft 服务器， (命令默认为 false) 。

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    发送给 Microsoft 的信息严格遵循 [Skype for Business 数据收集实践](/skypeforbusiness/legal-and-regulatory/data-collection-practices)。

3. 设置回退到本地托管的 Skype for Business Web App 体验（如果 CDN 不可用）前的超时。 默认值为 6 秒。 如果此值设置为 0，则没有超时。

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> 对于 Skype for Business Server 2015 累积更新 5 中的 MeetingUxUseCdn，默认值设置为 False。 这会导致 Skype for Business for Mac 客户端无法以来宾身份加入非联盟伙伴的会议的问题，即使 Skype for Business 管理员将 MeetingUxUseCdn 设置为 True 也是如此。 为此，Skype for Business Server 2015 必须具有累积更新 7、6.0.9319.534 或更高版本。 请参阅 [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312)。


## <a name="see-also"></a>另请参阅
<a name="SMA_Enable"> </a>

[Plan for Meetings clients (Web App and Meetings App) ](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[在 Skype for Business Server 中配置与会页面](../../manage/conferencing/meeting-join-page.md)

[Microsoft Online Services 隐私声明](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[许可条款和文档](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)