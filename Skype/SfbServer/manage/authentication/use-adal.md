---
title: 如何将新式验证 (ADAL) 与 Skype for Business 配合使用
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: 本文介绍如何使用现代身份验证 （这基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0） 可以位于年 3 月 2016 for Business 的业务服务器 2015年的 Skype Skype 的累积更新。
ms.openlocfilehash: d6e78d60371b56c3a2cc959ded0ec7d7394d82cb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32191521"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>如何将新式验证 (ADAL) 与 Skype for Business 配合使用
 
本文介绍如何使用现代身份验证 （这基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0） 可以位于年 3 月 2016 for Business 的 Skype 业务服务器 2015，或从初始 Skype 的累积更新业务服务器 2019 Skype 的的发行版。
  
## <a name="whats-in-this-article"></a>本文中的内容

[在池中配置 ADAL 并将 AD FS 设置为安全令牌服务器](use-adal.md#BKMK_Config)
  
[用于启用 ADAL 登录的其他选项（如 Office 客户端应用）](use-adal.md#BKMK_Options)
  
[新式验证/ADAL 不受支持的客户端](use-adal.md#BKMK_Support)
  
### <a name="configure-adal-in-your-pool-and-set-ad-fs-as-security-token-server"></a>在池中配置 ADAL 并将 AD FS 设置为安全令牌服务器
<a name="BKMK_Config"> </a>

在此过程中，将连接到业务服务器池的配置为使用 ADAL Skype 所安装的 AD FS。
  
1. 安装年 3 月 2016年累积更新 （或更高版本） 的 Skype 业务服务器 2015 到您 Skype 业务服务器池或 Standard Edition server。 （计划维护时段，根据需要运行自动安装的 Windows Update）。
    
2. 在您的内部部署 AD FS 服务器、[下载](https://aka.ms/sfbadalscripts)安装 AdfsOAuthTrustForSfB 脚本。 （这需要完成每个 AD FS 服务器场或独立 AD FS 服务器。 它不会不需要 AD FS 代理服务器或 Web 应用程序代理上完成。）
    
3. 记下的内部和外部 Web 服务的完全限定域名 (Fqdn) 为您 Skype 业务服务器池或 Standard Edition server。 需要对所有 Skype for Business 池执行此操作。
    
4. 从 PowerShell 在 AD FS 服务器上，运行`Setup-AdfsOAuthTrustForSfB.ps1`（对于 Windows Server 2012 R2) 或`Setup-Adfs2016OAuthTrustForSfB.ps1`（对于 Windows Server 2016 或更高版本。）您需要输入正确的 Url 的内部和外部 Web 服务完全限定域名 (Fqdn)。 下面是一个示例：
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    对于任何其他池，您将需要池 Web 服务 Url 手动添加到 Skype 的业务服务器信赖方信任在 AD FS。
    
    > [!IMPORTANT]
    > 不能对池同时使用被动身份验证和 ADAL。 必须禁用被动身份验证才能使用 ADAL。 有关如何为池设置身份验证的 PowerShell cmdlet，请参阅[这](https://technet.microsoft.com/en-us/library/gg398396.aspx)篇文章。
  
    > [!TIP]
    > 如果您有其他池，需要将其作为[标识符](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx)添加到信赖方信任在 AD FS.> 转到您的 AD FS 服务器并打开 AD FS 管理。 展开信任关系\>信赖方信任。 右键单击信赖方信任列出和属性的右键单击\>标识符\>键入其他池 URL(s)\>单击添加。 
  
5. 返回到您 Skype 业务 Server 前端服务器或 Standard Edition server 的服务器。 从此处，您必须运行 cmdlet 创建的 OAuth 服务器和修改的 OAuth 配置才能与 Skype 的业务。 您只需执行的业务服务器部署的 Skype 每次此步骤。 下面是一个示例：
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > 您在此命令中看到的标识 URL 实际上是 AD FS 联合身份验证服务名称时，您可以看到 AD FS 管理中右键单击服务\>属性。 类型始终是 ADFS，并且始终是 MetadataURL\<您的 AD FS 服务名称\>+"/ FederationMetadata/2007-06/FederationMetadata.xml"。 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. 仍在您 Skype 业务 Server 前端服务器或 Standard Edition server，通过输入用户名和池 FQDN 的 SIP 地址来测试新的配置。 您只需执行的业务服务器部署的 Skype 每次此步骤。 下面是一个示例：
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. 出现提示时，请务必输入测试用户的凭据。 验证测试是否成功完成。
    
    > [!NOTE]
    > 当您 STS 的 URL 将解析为 AD FS*内部*时，您将看到的提示将**Windows 安全**提示。 如果 URL 在外部解析，你将看到一个名为“**登录**”的提示。 通常，我们在这里需要“**Windows 安全**”提示。 请注意，此行为各不相同，特别是当你实施了基于表单的身份验证 (FBA) 时。
  
另外请注意，当 STS URL 解析为内部 AD FS 服务器时，在浏览器中启用 Windows 集成身份验证，其中许多不同的用户登录到客户端应用程序的计算机可能失败进行身份验证，除非明确是在浏览器配置为提示用户输入凭据在给定浏览器中安全区域。 以 kiosk 为例。 登录到操作系统的帐户可能不同于登录到 Skype for Business 客户端的用户帐户。 如果的确如此，你可能会看到此处所述的故障。
    
可以查看和更改此浏览器设置在 Internet Explorer 中的单击\>工具 （或齿轮） \> Internet 选项\>安全选项卡\>（如本地 Intranet) 的安全区域。 从此对话框，单击“自定义级别”按钮并滚动到“设置”对话框中的列表末尾。 在用户身份验证下\>登录\>您将看到用户名和密码提示选项。 如果在你的 kiosk 中，启动 Skype for Business 客户端的用户不同于（具有不同的帐户）登录计算机的用户，你可能需要在组策略中测试将这些计算机的这个选项设置为“打开”。
    
最后，重要的是，你可能会遇到多个提示，因为安全系统会收集对你的帐户进行身份验证或授权所需的信息。
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>用于启用 ADAL 登录的其他选项（如 Office 客户端应用）
<a name="BKMK_Options"> </a>

既然 ADAL 配置为您的业务 Skype 和 （自动） 对于 Office 2016 跨平台客户端应用程序，您可能想要利用它，Exchange Online 中 （其中不是 On 默认情况下），或在 Office 2013 客户端。
  
> [!IMPORTANT]
> 需要了解期望现代身份验证登录从您的客户端应用程序是什么？ 了解一下[如何现代身份验证适用于 Office 2013 和 Office 2016 客户端应用程序](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US)。 
  
要打开 Exchange Online 的现代身份验证，您将需要运行某些 PowerShell cmdlet。 对于 Office 2013 客户端应用程序，您将需要更改某些客户端计算机上的注册表项。
  
- 连接到 Exchange Online 并运行以下 cmdlet:
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- 为要启用新式验证的每个设备或计算机设置这些注册表项。 在大型组织中需要一个 GPO。 有关如何使 GPO 的信息，请参阅创建组策略对象修改域联接计算机上的注册表的[这](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)篇文章。
    
|注册表项  <br/> |类型  <br/> |值  <br/> |
|:-----|:-----|:-----|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
这些注册表项设置后, 设置为[使用 Multifactor 身份验证 (MFA) 与 Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US)的 Office 应用程序。
  
> [!TIP]
> 要在 Office 2013 的设备上禁用现代的身份验证，将设置为零值的 HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL 注册表项。 请注意，类似的注册表项 (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) 也用于 Office 2016 的设备上禁用现代身份验证。
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>新式验证/ADAL 不受支持的客户端
<a name="BKMK_Support"> </a>

某些客户端版本不支持 OAuth。你可以在用于添加和删除程序的控制面板中检查你的 Office 客户端版本，以便将你的版本号与此处所列的版本（或版本范围）进行比较：
  
- Office 客户端 15.0。[0000-4766]。\*
    
- Office 客户端 16.0。[0000-4293]。\*
    
- Office 客户端 16.0.6001.[0000-1032]
    
- Office 客户端 16.0。[6000-6224]。\*
    
> [!NOTE]
> 混合现代身份验证中也有与 Skype 的业务内部部署，如果您想要了解，请访问[如何配置 for Business 的 Skype 本地用于混合现代身份验证](https://docs.microsoft.com/en-us/office365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication)
