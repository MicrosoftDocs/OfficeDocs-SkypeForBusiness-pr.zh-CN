---
title: 如何将新式验证 (ADAL) 与 Skype for Business 配合使用
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: 本文介绍了如何使用现代的身份验证 （这依赖于活动目录身份验证库 (ADAL) 以及 OAuth 2.0） 3 月 2016年中可以找到有关业务的业务服务器 2015年的 Skype 的 Skype 的累积更新。
ms.openlocfilehash: efd0e35ce92143e9fb5fda03301eb51d2926c979
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>如何将新式验证 (ADAL) 与 Skype for Business 配合使用
 
本文介绍了如何使用现代的身份验证 （这依赖于活动目录身份验证库 (ADAL) 以及 OAuth 2.0） 3 月 2016年中可以找到有关业务的业务服务器 2015年的 Skype 的 Skype 的累积更新。
  
## <a name="whats-in-this-article"></a>本文中的内容

[什么是 ADAL？](use-adal.md#BKMK_ADAL)
  
[在你的池中配置 ADAL 并将 ADFS 设置为安全令牌服务器](use-adal.md#BKMK_Config)
  
[用于启用 ADAL 登录的其他选项（如 Office 客户端应用）](use-adal.md#BKMK_Options)
  
[新式验证/ADAL 不受支持的客户端](use-adal.md#BKMK_Support)
  
## <a name="what-is-adal"></a>什么是 ADAL？
<a name="BKMK_ADAL"> </a>

ADAL 是“Active Directory Authentication Library”的缩写，它和 OAuth 2.0 是新式验证的基础。 此代码库旨在使目录中的受保护的资源 （如 Skype 业务) 通过安全令牌的客户端应用程序。 ADAL 与 OAuth 2.0 配合工作来支持更多身份验证和授权方案，例如多重身份验证 (MFA) 和更多的 SAML 身份验证形式。
  
充当客户端的各种应用可以利用新式验证来帮助访问受安全保护的资源。 在业务服务器 2015年的 Skype，这项技术为使用户对资源的授权的适当级别使用内部部署客户端和内部服务器之间。
  
新式验证对话（基于 ADAL 和 OAuth 2.0）具有一些常见元素。
  
- 客户端发出请求的资源，在这种情况下，客户端是 Skype 的业务。
    
- 没有的资源的客户端需要特定级别的访问，该资源由目录服务安全，在这种情况下的资源是业务服务器 2015年的 Skype。
    
- OAuth 连接，换句话说，是专门用来*授权*用户访问资源。 （OAuth 闻名的更具描述性的名称，服务器授权和通常缩写为 S2S）
    
在 Skype 的服务器 2015年现代商业身份验证 (ADAL) 对话，Skype 的业务服务器 2015年通过 ADFS (Windows Server 2012 R2 在 ADFS 3.0) 进行通信。 可能会使用其他一些身份提供程序 (IdP) 执行身份验证，但是需要将 Skype for Business 服务器配置为直接与 ADFS 进行通信。 如果您还没有配置 ADFS 使用 Skype 的业务服务器 2015年请填写[ADFS 安装](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)。
  
ADAL 包括在 3 月 2016年累积更新的业务服务器 2015，Skype 和 3 月 2016年安装累积更新为 Skype 的业务**必须**成功配置的需要。
  
> [!NOTE]
> 在初始版本中，只有当不涉及混合 Skype 拓扑时才支持本地环境中的新式验证。 例如，如果环境是纯粹的业务服务器 2015 Skype。 此陈述可能会发生更改。 
  
必须下载包含 ps1 文件与 ADAL 使用的命令的 PowerShell 程序包才能成功配置。
  
### <a name="configure-adal-in-your-pool-and-set-adfs-as-security-token-server"></a>在你的池中配置 ADAL 并将 ADFS 设置为安全令牌服务器
<a name="BKMK_Config"> </a>

在此过程中，则连接到配置为 ADAL 的业务服务器 2015年池 Skype ADFS 的安装。
  
1. 安装 3 月 2016年到您的业务服务器 2015年池 Skype 业务服务器 2015年或标准版服务器的 Skype 的累积更新。 （安排维护窗口，根据需要运行 Windows 更新的自动安装）。
    
2. 在您的内部部署 ADFS 的服务器，请[下载](https://aka.ms/sfbadalscripts)安装 AdfsOAuthTrustForSfB 脚本。 （这需要每个 ADF 场或独立 ADFS 服务器完成。 它不需要在 ADFS 代理服务器或代理服务器上完成）。
    
3. 记下的内部和外部 Web 服务您 Skype 业务服务器 2015年池或标准版服务器的完全合格的域名 (Fqdn)。 需要对所有 Skype for Business 池执行此操作。
    
4. 从 ADFS 服务器上的 PowerShell，运行 Setup-AdfsOAuthTrustForSfB。你需要输入内部和外部 Web 服务 FQDN 的正确 URL。下面是一个示例：
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    对于任何其他池，需要池的 Web 服务 Url 手动添加到 Skype 业务服务器 2015年信赖方信任在 ADF 中。
    
    > [!IMPORTANT]
    > 不能对池同时使用被动身份验证和 ADAL。 必须禁用被动身份验证才能使用 ADAL。 如何设置身份验证池 PowerShell cmdlet 请参见[这](https://technet.microsoft.com/en-us/library/gg398396.aspx)篇文章。
  
    > [!TIP]
    > 如果您有其他池需要将它们用作[标识符](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx)添加到配置成信赖方信任在 ADFS。 > 转到 ADF 服务器并打开 ADFS 管理。 信任关系展开\>信赖方信任。 右击配置成信赖方信任列出并右击属性\>标识符\>键入其他池 URL(s)\>单击添加。 
  
5. 返回到您 Skype 业务服务器 2015年前端或标准版服务器的服务器。 从这里，您必须运行 cmdlet 的 OAuth 服务器创建和修改该 OAuth 配置使用 Skype 的业务。 您只需执行 Skype 业务服务器 2015年部署的每一次此步骤。 下面是一个示例：
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > 在此命令中看到的身份 URL 实际上是 ADFS 联合身份验证服务名称右键单击服务时，可以看到在 ADFS 管理\>属性。 Type 始终是 ADF，并且始终是 'MetadataURL'\<您 ADFS 服务名称\>+"/ FederationMetadata/2007-06/FederationMetadata.xml"。 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. 仍在您 Skype 业务服务器 2015年前端或标准版服务器中，通过输入用户名和池的 FQDN 的 SIP 地址中测试新的配置。 您只需执行 Skype 业务服务器 2015年部署的每一次此步骤。 下面是一个示例：
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. 出现提示时，请务必输入测试用户的凭据。验证测试是否成功完成。
    
    > [!NOTE]
    > STS URL 解析为 ADFS*内部*，您会看到的提示将**Windows 安全**提示。 如果 URL 在外部解析，你将看到一个名为“**登录**”的提示。 通常，我们在这里需要“**Windows 安全**”提示。 请注意，此行为各不相同，特别是当你实施了基于表单的身份验证 (FBA) 时。
  
此外，请注意，当 STS URL 解析为内部 ADFS 服务器并且在浏览器中启用了 Windows 集成身份验证时，许多不同用户在其上登录到客户端应用程序的计算机可能无法进行身份验证，除非浏览器显式配置为在给定的浏览器安全区域中提示用户提供其凭据。以 kiosk 为例。登录到操作系统的帐户可能不同于登录到 Skype for Business 客户端的用户帐户。如果的确如此，你可能会看到此处所述的故障。
    
您可以查看和更改此浏览器设置在 Internet Explorer 中的单击\>工具 （或齿轮） \> Internet 选项\>安全选项卡\>和安全区域 （例如本地 Intranet)。 从此对话框，单击“自定义级别”按钮并滚动到“设置”对话框中的列表末尾。 在用户身份验证下\>登录\>您将看到提示用户名和密码选项。 如果在你的 kiosk 中，启动 Skype for Business 客户端的用户不同于（具有不同的帐户）登录计算机的用户，你可能需要在组策略中测试将这些计算机的这个选项设置为“打开”。
    
最后，重要的是，你可能会遇到多个提示，因为安全系统会收集对你的帐户进行身份验证或授权所需的信息。
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>用于启用 ADAL 登录的其他选项（如 Office 客户端应用）
<a name="BKMK_Options"> </a>

现在，ADAL 配置为您的业务 Skype 和 （自动） 办公室 2016年跨平台的客户端应用程序，您可能需要 Exchange Online （其中不 On，默认情况下），或者在 Office 2013 客户端中利用它。
  
> [!IMPORTANT]
> 需要了解现代身份验证登录从客户端应用程序期望是什么？ 看一看[如何现代验证用于办公室 2013年和 Office 2016 的客户端应用程序的工作原理](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US)。 
  
若要启用 Exchange Online 的现代身份验证，您需要运行一些 PowerShell cmdlet。 对于 Office 2013 客户端应用程序，需要更改客户端计算机上的某些注册表项。
  
- 连接到 Exchange 联机并运行以下 cmdlet:
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- 为要启用新式验证的每个设备或计算机设置这些注册表项。 在大型组织中需要一个 GPO。 如何使一个 GPO 的信息，请参阅创建组策略对象来修改域联接计算机上的注册表[这](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)篇文章。
    
||||
|:-----|:-----|:-----|
|注册表项  <br/> |类型  <br/> |值  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
一旦设置了这些参数，设置为[使用 Multifactor 身份验证 (MFA) 与 Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US)Office 2013 应用程序。
  
> [!TIP]
> 要禁用 Office 2013 的设备上的现代身份验证，请为零值设置 HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL 注册表项。 请注意，类似的注册表项 (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) 也可用来禁用 Office 2016 年的设备上的现代身份验证。
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>新式验证/ADAL 不受支持的客户端
<a name="BKMK_Support"> </a>

某些客户端版本不支持 OAuth。你可以在用于添加和删除程序的控制面板中检查你的 Office 客户端版本，以便将你的版本号与此处所列的版本（或版本范围）进行比较：
  
- Office 客户端于 15.0。[0000-4766]。\*
    
- Office 客户端 16.0。[0000-4293]。\*
    
- Office 客户端 16.0.6001.[0000-1032]
    
- Office 客户端 16.0。[6000-6224]。\*
    

