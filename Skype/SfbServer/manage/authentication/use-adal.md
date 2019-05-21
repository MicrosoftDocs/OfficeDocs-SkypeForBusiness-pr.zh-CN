---
title: 如何将新式验证 (ADAL) 与 Skype for Business 配合使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: 本文介绍如何使用新式身份验证 (基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0), 该身份验证可在 skype for business Server 2015 的 skype for business 的 3 2016 月累积更新中找到。
ms.openlocfilehash: 9fe4470e1f8f6e2cd345cd176250fb1ffb16448f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286121"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>如何将新式验证 (ADAL) 与 Skype for Business 配合使用
 
本文介绍了如何使用新式身份验证 (基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0), 该身份验证可在年 3 2016 月累积更新中找到 skype for business Server 2015 的 skype for business 累积更新或初始发布 Skype for business Server 2019。
  
## <a name="whats-in-this-article"></a>本文中的内容

[在你的池中配置 ADAL 并将 AD FS 设置为安全令牌服务器](use-adal.md#BKMK_Config)
  
[用于启用 ADAL 登录的其他选项（如 Office 客户端应用）](use-adal.md#BKMK_Options)
  
[新式验证/ADAL 不受支持的客户端](use-adal.md#BKMK_Support)
  
### <a name="configure-adal-in-your-pool-and-set-ad-fs-as-security-token-server"></a>在你的池中配置 ADAL 并将 AD FS 设置为安全令牌服务器
<a name="BKMK_Config"> </a>

在此过程中, 将你的 AD FS 安装连接到为 ADAL 配置的 Skype for business 服务器池。
  
1. 将 Skype for business Server 2015 的2016年3月累积更新 (或更新) 安装到 Skype for business 服务器池或标准版服务器。 (如有需要, 请安排维护窗口, 以便为自动安装运行 Windows 更新。)
    
2. 在本地 AD FS 服务器上,[下载](https://aka.ms/sfbadalscripts)安装 AdfsOAuthTrustForSfB 脚本。 (需要针对每个 AD FS 场或独立的 AD FS 服务器执行此操作。 无需在 AD FS 代理或 Web 应用程序代理上执行此操作。)
    
3. 记下您的 Skype for business 服务器池或标准版服务器的内部和外部 Web 服务的完全限定域名 (Fqdn)。 需要对所有 Skype for Business 池执行此操作。
    
4. 在 AD FS 服务器上的 PowerShell 中, 运行`Setup-AdfsOAuthTrustForSfB.ps1` (适用于 windows Server 2012 R2) 或`Setup-Adfs2016OAuthTrustForSfB.ps1` (适用于 windows server 2016 或更高版本)。)您需要为内部和外部 Web 服务完全限定的域名 (Fqdn) 输入正确的 Url。 下面是一个示例：
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    对于任何其他池, 你需要将池 Web 服务 Url 手动添加到 AD FS 中的 Skype for business 服务器信赖方信任。
    
    > [!IMPORTANT]
    > 不能对池同时使用被动身份验证和 ADAL。 必须禁用被动身份验证才能使用 ADAL。 有关如何为池设置身份验证的 PowerShell cmdlet, 请[](https://technet.microsoft.com/en-us/library/gg398396.aspx)参阅本文。
  
    > [!TIP]
    > 如果你有其他池, 你需要将其作为[标识符](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx)添加到 ad fs 中的信赖方信任。 > 转到你的 ad fs 服务器并打开 Ad fs 管理。 展开 "信任\>关系" 信赖方信任。 右键单击列出的信赖方信任, 然后右键单击以查看属性\>标识符\>键入其他池 URL \>单击 "添加"。 
  
5. 返回到 Skype for business 服务器前端或标准版服务器服务器。 在此处, 你必须运行创建 OAuth 服务器的 cmdlet, 并修改该 OAuth 配置以使用 Skype for Business。 您只需为每个 Skype for business 服务器部署执行此步骤。 下面是一个示例：
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > 在此命令中看到的 "Identity" URL 实际上是在你右键单击 "服务\>属性" 时你可以在 Ad fs 管理中看到的 Ad Fs 联合身份验证服务名称。 "Type" 始终为 "ADFS", 而 "MetadataURL" 始终\<是你的 AD FS 服务名称\> + "/FederationMetadata/2007-06/FederationMetadata.xml"。 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. 仍在 Skype for business Server 前端或标准版服务器上, 通过输入用户和池 FQDN 的 SIP 地址来测试新配置。 您只需为每个 Skype for business 服务器部署执行此步骤。 下面是一个示例：
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. 出现提示时，请务必输入测试用户的凭据。 验证测试是否成功完成。
    
    > [!NOTE]
    > 当你的 STS URL*内部*解析为 AD FS 时, 你将看到的提示将是**Windows 安全**提示。 如果 URL 在外部解析，你将看到一个名为“**登录**”的提示。 通常，我们在这里需要“**Windows 安全**”提示。 请注意，此行为各不相同，特别是当你实施了基于表单的身份验证 (FBA) 时。
  
另请注意, 当 STS URL 解析为内部 AD FS 服务器, 并且在浏览器中启用了 Windows 集成身份验证时, 有多个不同用户登录到客户端应用程序的计算机可能会出现身份验证失败, 除非该浏览器显式配置为在给定的浏览器安全区域提示用户输入其凭据。 以 kiosk 为例。 登录到操作系统的帐户可能不同于登录到 Skype for Business 客户端的用户帐户。 如果的确如此，你可能会看到此处所述的故障。
    
通过单击\> "工具" (或齿轮) \> internet 选项\> "安全" 选项卡\>和安全区域 (如 "本地 Intranet"), 可在 Internet Explorer 中查看和更改此浏览器设置。 从此对话框，单击“自定义级别”按钮并滚动到“设置”对话框中的列表末尾。 在 "用户\>身份\>验证登录" 下, 你将看到 "提示输入用户名和密码" 选项。 如果在你的 kiosk 中，启动 Skype for Business 客户端的用户不同于（具有不同的帐户）登录计算机的用户，你可能需要在组策略中测试将这些计算机的这个选项设置为“打开”。
    
最后，重要的是，你可能会遇到多个提示，因为安全系统会收集对你的帐户进行身份验证或授权所需的信息。
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>用于启用 ADAL 登录的其他选项（如 Office 客户端应用）
<a name="BKMK_Options"> </a>

现在, 针对你的 Skype for business 和 (自动) 为跨平台的 Office 2016 客户端应用配置了 ADAL, 你可能希望将其用于 Exchange Online (默认情况下不是 "打开"), 或在 Office 2013 客户端中使用。
  
> [!IMPORTANT]
> 需要了解来自客户端应用的新式身份验证登录所期望的内容？ 查看[新式身份验证对于 office 2013 和 office 2016 客户端应用的作用](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US)。 
  
若要为 Exchange Online 打开新式身份验证, 你需要运行一些 PowerShell cmdlet。 对于 Office 2013 客户端应用, 你需要在客户端计算机上更改某些注册表项。
  
- 连接到 Exchange Online 并运行以下 cmdlet:
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- 为要启用新式验证的每个设备或计算机设置这些注册表项。 在大型组织中需要一个 GPO。 有关如何创建 GPO 的信息, 请参阅本文的 "创建组策略对象以修改加入域的计算机上的注册表"。 [ ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)
    
|注册表项  <br/> |类型  <br/> |值  <br/> |
|:-----|:-----|:-----|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
设置这些密钥后, 将 Office 应用设置为[使用多重身份验证 (MFA) 和 Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
> [!TIP]
> 若要在适用于 Office 2013 的设备上禁用新式验证, 请将 HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL 注册表项设置为零值。 请注意, 类似的注册表项 (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) 也可用于在 Office 2016 的设备上禁用新式身份验证。
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>新式验证/ADAL 不受支持的客户端
<a name="BKMK_Support"> </a>

某些客户端版本不支持 OAuth。你可以在用于添加和删除程序的控制面板中检查你的 Office 客户端版本，以便将你的版本号与此处所列的版本（或版本范围）进行比较：
  
- Office 客户端15.0。[0000-4766]。\*
    
- Office 客户端16.0。[0000-4293]。\*
    
- Office 客户端 16.0.6001.[0000-1032]
    
- Office 客户端16.0。[6000-6224]。\*
    
> [!NOTE]
> 本地 Skype For Business 还提供混合新式身份验证, 如果你想了解更多信息, 请访问[如何配置本地 skype for business 以使用混合新式身份验证](https://docs.microsoft.com/en-us/office365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication)
