---
title: 在 Skype for Business Server 2015 中部署 Web 可下载客户端
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 摘要： 为企业 Web 应用程序部署 Skype 和 Skype 会议应用程序一起使用 Skype 业务。
ms.openlocfilehash: e1cee2741e1538da1e4c5ed8e25509415cb16ac3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中部署 Web 可下载客户端
 
**摘要：**为企业 Web 应用程序部署 Skype 和 Skype 会议应用程序一起使用 Skype 业务。
  
Skype 业务 Web 应用程序是安装在服务器上运行 Skype 业务服务器 2015年和默认部署按需会议用户不具有的业务客户端 Skype Internet Information Services (IIS) web 客户端。 这些会议用户通常从你的网络外连接。 每当用户单击会议 URL，但不具有的业务客户端安装 Skype，用户会看到选项以使用最新版本的 Skype 业务 Web 应用程序中加入会议。
  
语音，视频，和共享功能在 Skype 业务 Web 应用程序需要 Microsoft ActiveX 控件用作用户的浏览器插件。 可以预先安装 ActiveX 控件，或者允许用户进行安装时提示您时，发生第一次商业 Web 应用程序使用 Skype 或第一次在使用某一功能需要该 ActiveX 控件。
  
> [!NOTE]
> 在 Skype 业务服务器 2015年边缘服务器部署，在外围网络中的 HTTPS 反向代理服务器是 Skype 业务 Web 应用程序客户端访问的需要。 你还必须发布简单的 URL。 有关详细信息，请参阅[设置了反向代理服务器](http://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx)和[规划简单的 Url](http://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx)。 
  
## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>启用对 Skype 业务 Web 应用程序的多因素身份验证
<a name="MFA"> </a>

Skype 的 Skype 业务 Web 应用程序的业务服务器 2015年版本支持多因素身份验证。 除了用户名称和密码，您可以要求额外的身份验证方法，例如智能卡或针，当他们登录 Skype 业务会议加入来自外部网络的用户进行身份验证。 您可以通过部署活动目录联合身份验证服务 (AD FS) 联合身份验证服务器和启用业务服务器 2015 Skype 在被动身份验证启用多因素身份验证。 AD FS 配置后，外部用户尝试加入 Skype 业务会议显示 AD FS 的多因素身份验证网页，其中包含用户名称和密码挑战以及任何其他身份验证方法，您已配置。
  
> [!IMPORTANT]
> 如果您计划配置 AD FS 以进行多重身份验证，则以下是一些重要注意事项： 
  
- 如果会议参加者和组织者位于同一组织中或都来自 AD FS 联盟组织，则 ADFS 多重身份验证生效。ADFS 多重身份验证不适用于 Lync 联盟用户，因为 Lync 服务器 Web 基础结构当前不支持该验证方法。
    
- 如果使用硬件负载平衡器，启用负载平衡器上的 cookie 持久性，以便由同一个前端服务器处理来自 Skype 业务 Web 应用程序客户端的所有请求。
    
- 您依赖当事方之间建立信任 Skype 业务服务器和 AD FS 服务器，指定令牌的生命周期足够长，以跨您的 Skype 业务会议的最大长度。 通常，240 分钟的令牌使用时间就足够了。
    
- 此配置不适用于 Lync 移动客户端。
    
### <a name="configure-multi-factor-authentication"></a>配置多重身份验证

1. 安装 AD FS 联盟服务器角色。 有关详细信息，请参阅[活动目录联合身份验证服务 2.0 部署指南](https://go.microsoft.com/fwlink/p/?linkid=267511)
    
2. 为 AD FS 创建证书。 有关详细信息，请参见["联合身份验证服务器证书"](https://go.microsoft.com/fwlink/p/?LinkId=285376)一节的计划和部署使用单一登录方式进行登录主题的 AD FS。
    
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
   ```
 
   ```
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   ```

   ```
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>禁用 BranchCache 
<a name="MFA"> </a>

Windows 7 和 Windows Server 2008 R2 中的分支缓存功能可能会干扰 Skype 业务 Web 应用程序的 web 组件。 为了防止问题为 Skype 业务 Web 应用程序用户，确保为未启用 BranchCache。 
  
有关禁用分支缓存，有关详细信息请参阅 BranchCache 部署指南 》，可在 Microsoft 下载中心的 Word 格式[http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?LinkId=268788)和 HTML 格式显示在 Windows Server 2008 R2 技术库在[https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?LinkId=268789)。
  
## <a name="verifying-skype-for-business-web-app-deployment"></a>验证 Skype 业务 Web 应用程序部署
<a name="MFA"> </a>

你可以使用 Test-CsUcwaConference cmdlet 来验证一对测试用户是否可以使用统一通信 Web API (UCWA) 参加会议。 此 cmdlet 的详细信息，请参阅[测试 CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) Skype 业务服务器管理外壳程序的文档中。
  
## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>在 Windows Server 2008 R2 上的插件安装疑难解答
<a name="MFA"> </a>

如果运行 Windows Server 2008 R2 的计算机上无法安装插件，您可能需要修改 Internet Explorer 安全设置或 DisableMSI 注册表项设置。
  
### <a name="modify-the-security-setting-in-internet-explorer"></a>修改 Internet Explorer 的安全设置

1. 打开 Internet Explorer。
    
2. 依次单击**“工具”**、**“Internet 选项”**和**“高级”**。
    
3. 向下滚动至**“安全”**部分。
    
4. 清除**“不将加密的页存盘”**，然后单击**“确定”**。
    
    > [!NOTE]
    > 如果选中，此设置时试图从 Skype 为企业 Web 应用程序下载附件也可导致错误。 
  
5. 重新加入会议。插件应该可以无误地下载。
    
### <a name="modify-the-disablemsi-registry-setting"></a>修改 DisableMSI 注册表设置

1. 单击**“开始”**，然后单击**“运行”**。
    
2. 要访问注册表编辑器，请键入 **regedit**。
    
3. 导航到 HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer。
    
4. 编辑或添加类型为 REG_DWORD 的 DisableMSI 注册表项，并将其设置为 0。
    
5. 重新加入会议。
    
## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional"></a>启用 Skype 会议应用以替换 Skype for Business Web 应用（可选）
<a name="SMA_Enable"> </a>

此过程可选。 如果不使用它，外部用户将继续参加会议对企业 Web 应用程序中使用 Skype。 
  
### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>启用简化会议加入和 Skype 会议应用

1. 访问到内容传递网络 (CDN) 启用时，用户将具有联机连接到 CDN 并下载 Skype 会议的应用程序的能力，将简化会议连接体验。 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. 允许客户端从会议的侧面记录遥测加入网页或 Skype 会议应用程序发送到 Microsoft 服务器 （命令的默认值为 false）。 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    严格遵守[业务数据集合的 Skype](https://support.office.com/en-us/article/Skype-for-Business-data-collection-practices-c17e8ea6-b83b-4345-9401-47a6c8b13aad?ui=en-US&amp;rs=en-US&amp;ad=US)是信息发送给 Microsoft。
    
3. 设置超时之前回退到本地承载的 Skype 业务 Web 应用程序的体验，如果 CDN 不可用。 默认值是 6 秒。 如果将该值设置为 0，则没有超时。
    
   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a>另请参阅
<a name="SMA_Enable"> </a>

#### 

[规划会议客户端 （Web 应用程序和会议的应用程序）](../../plan-your-deployment/clients-and-devices/meetings-clients.md)
  
[规划会议客户端 （Web 应用程序和会议的应用程序）](../../plan-your-deployment/clients-and-devices/meetings-clients.md)
#### 

[配置加入会议页](http://technet.microsoft.com/library/45880423-47f4-49af-b825-cbd8e3fc1046.aspx)
  
[Microsoft Online Services 隐私声明](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)
  
[授权条款和文档](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)

