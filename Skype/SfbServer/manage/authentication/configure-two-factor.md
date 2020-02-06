---
title: 在 Skype for Business 服务器中配置双因素身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 摘要：在 Skype for Business 服务器中配置双因素身份验证。
ms.openlocfilehash: 40749cbe3e0bf50a6ff6a640038d63d4a4479b7f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818814"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>在 Skype for Business 服务器中配置双因素身份验证

**摘要：** 在 Skype for Business 服务器中配置双因素身份验证。

以下部分介绍了为您的部署配置双重身份验证所需的步骤。 有关双因素身份验证的详细信息，请参阅[为联机管理员网格用户发布启用 Office 365 多重身份验证](https://go.microsoft.com/fwlink/p/?LinkId=313332)。

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>配置企业根证书颁发机构以支持智能卡身份验证

以下步骤介绍如何配置企业根 CA 以支持智能卡身份验证：

有关如何安装企业根 CA 的详细信息，请参阅[安装企业根证书颁发机构](https://go.microsoft.com/fwlink/p/?LinkID=313364)。

1. 使用域管理员帐户登录到企业 CA 计算机。

2. 启动系统管理器，并验证是否已安装“证书颁发机构 Web 注册”角色。

3. 从“管理工具”**** 菜单中，打开“证书颁发机构”**** 管理控制台。

4. 在导航窗格中，展开“证书颁发机构”****。

5. 右键单击“证书模板”****，选择“新建”****，然后选择“要颁发的证书模板”****。

6. 选择“注册代理”****、“智能卡用户”**** 和“智能卡登录”****。

7. 单击“**确定**”。

8. 右键单击“证书模板”****。

9. 选择“管理”****。

10. 打开智能卡用户模板的属性。

11. 单击“安全”**** 选项卡。

12. 更改权限，如下所示：

    - 添加具有读取/注册（允许）权限的各个用户 AD 帐户，或者

    - 添加具有读取/注册（允许）权限且包含智能卡用户的安全组，或者

    - 添加具有读取/注册（允许）权限的域用户组

## <a name="configure-windows-8-for-virtual-smart-cards"></a>为 Windows 8 配置虚拟智能卡

部署双重身份验证和智能卡技术时要考虑的一个因素是实施成本。 Windows 8 提供了许多新的安全功能，最有趣的新增功能之一是支持虚拟智能卡。

对于配备了符合规范版本 1.2 要求的受信任的平台模块 (TPM) 芯片的计算机，组织现在可以享受智能卡登录带来的好处，不必在硬件方面做任何额外投资。 有关详细信息，请参阅[在 Windows 8 中使用虚拟智能卡](https://go.microsoft.com/fwlink/p/?LinkId=313365)。

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>为 Windows 8 配置虚拟智能卡

1. 使用启用了 Skype for Business 的用户的凭据登录到 Windows 8 计算机。

2. 在 Windows 8“开始”屏幕中，将您的光标移动到屏幕右下角。

3. 选择**搜索**选项，然后搜索 ForCommand "提示"。

4. 右键单击“命令提示符”****，然后选择“以管理员身份运行”****。

5. 通过以下命令打开受信任的平台模块 (TPM) 管理控制台：

  ```console
  Tpm.msc
  ```

6. 从 TPM 管理控制台中，验证您的 TPM 规范版本是否至少为 1.2

    > [!NOTE]
    > 如果您收到一个对话框表明找不到兼容的受信任的平台模块 (TPM)，请验证计算机是否具有兼容的 TPM 模块以及是否在系统 BIOS 中启用了它。

7. 关闭 TPM 管理控制台

8. 从命令提示符处，使用以下命令创建新的虚拟智能卡：

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > 要在创建虚拟智能卡时提供自定义 PIN 值，请使用 /pin 提示符。

9. 从命令提示符处，通过运行以下命令来打开计算机管理控制台：

  ```console
  CompMgmt.msc
  ```

10. 在计算机管理控制台中，选择“设备管理”****。

11. 展开“智能卡读取器”****。

12. 验证是否已成功创建新的智能卡读取器。

## <a name="enroll-users-for-smart-card-authentication"></a>为用户注册智能卡身份验证

通常，可通过两种方法为用户注册智能卡身份验证。较为轻松的方法涉及使用 Web 注册直接为用户注册智能卡身份验证，而较为复杂的方法涉及使用注册代理。本主题着重介绍自动注册智能卡证书。

有关作为注册代理代表用户进行注册的详细信息，请参阅[代表其他用户注册证书](https://go.microsoft.com/fwlink/p/?LinkID=313367)。

### <a name="to-enroll-users-for-smart-card-authentication"></a>为用户注册智能卡身份验证

1. 使用支持 Skype for Business 的用户的凭据登录到 Windows 8 工作站。

2. 启动 Internet Explorer。

3. 浏览到**证书颁发机构 Web 注册**页面（例如https://MyCA.contoso.com/certsrv)，

    > [!NOTE]
    > 如果您正在使用 Internet Explorer 10，则可能需要在兼容模式下查看此网站。

4. 在“欢迎”**** 页面上，选择“申请证书”****。

5. 下一步，选择“高级申请”****。

6. 单击“创建并向此 CA 提交一个申请”****。

7. 在“证书模板”**** 部分下方选择“智能卡用户”****，并使用以下值完成高级证书申请：

  - “密钥选项”**** 确认以下设置：

    - 选择“创建新密钥集”**** 单选按钮

    - 对于“CSP”****，选择“Microsoft 基本智能卡加密提供程序”****

    - 对于“密钥用法”****，选择“Exchange”****（这是唯一可用选项）。

    - 对于“密码大小”****，输入 2048

    - 确认已选中“自动密钥容器名称”****

    - 取消选中其他框。

  - 在“其他选项”**** 下方，确认以下值：

    - 对于“申请格式”****，选择“CMC”****。

    - 对于“哈希算法”****，选择“sha1”****。

    - 对于**友好名称**enterSmardcard 证书。

8. 如果您正在使用物理智能卡读取器，请将智能卡插入设备中。

9. 单击“提交”**** 提交证书申请。

10. 出现提示时，输入用于创建虚拟智能卡的 PIN。

    > [!NOTE]
    > 默认的虚拟智能卡 PIN 值为 "12345678"。

11. 颁发证书后，单击“安装此证书”**** 完成注册过程。

    > [!NOTE]
    >  如果您的证书请求失败，出现错误 "此 Web 浏览器不支持生成证书请求"，有三种可能的方法可以解决此问题：

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>配置 Active Directory 联合身份验证服务 (AD FS 2.0)

下面一节介绍如何配置 Active Directory 联合身份验证服务 (AD FS 2.0) 来支持多重身份验证。 有关如何安装 AD FS 2.0 的信息，请参阅[广告 fs 2.0 分步操作和操作方法指南](https://go.microsoft.com/fwlink/p/?LinkId=313374)。

> [!NOTE]
> 安装 AD FS 2.0 时，请勿使用 Windows Server Manager 添加联合身份验证服务角色。 请改为下载并安装[Active Directory 联合身份验证服务 2.0 RTW 程序包](https://go.microsoft.com/fwlink/p/?LinkId=313375)。

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>针对双重身份验证配置 AD FS

1. 使用域管理员帐户登录到 AD FS 2.0 计算机。

2. 启动 Windows PowerShell。

3. 从 Windows PowerShell 命令行，运行以下命令：

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. 运行下面的命令，与将启用被动身份验证的每个服务器建立合作关系，运行时替换特定于部署的服务器名称：

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. 从“管理工具”菜单中，启动 AD FS 2.0 管理控制台。

6. 展开 "**信任关系** > "**信赖方信任**。

7. 验证是否已为 Skype for Business 服务器创建了新信任。

8. 使用 Windows PowerShell 通过运行以下命令为您的依赖方信任创建并分配颁发授权规则：

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. 使用 Windows PowerShell 通过运行以下命令为您的依赖方信任创建并分配颁发转换规则：

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. 从 AD FS 2.0 管理控制台中，右键单击您的依赖方信任并选择“编辑声明规则”****。

11. 选择“颁发授权规则”**** 选项卡，并验证是否已成功创建新的授权规则。

12. 选择“颁发转换规则”**** 选项卡，并验证是否已成功创建新的转换规则。

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>配置 AD FS 2.0 以支持客户端身份验证

有两种可能的身份验证类型可配置为允许 AD FS 2.0 支持使用智能卡进行身份验证：

- 基于表单的身份验证 (FBA)

- 传输层安全性客户端身份验证

使用基于表单的身份验证，您可以开发一个网页以允许用户使用其用户名/密码或使用其智能卡和 PIN 进行身份验证。 本主题着重介绍如何实施传输层安全性客户端身份验证与 AD FS 2.0。 有关 AD FS 2.0 身份验证类型的详细信息，请参阅[广告 fs 2.0：如何更改本地身份验证类型](https://go.microsoft.com/fwlink/p/?LinkId=313384)。

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>配置 AD FS 2.0 以支持客户端身份验证

1. 使用域管理员帐户登录到 AD FS 2.0 计算机。

2. 启动 Windows 资源管理器。

3. 浏览到 C:\inetpub\adfs\ls

4. 创建现有 web.config 文件的备份副本。

5. 使用记事本打开现有 web.config 文件。

6. 从菜单栏中，选择“编辑”****，然后选择“查找”****。

7. 搜索\<localAuthenticationTypes\>。

    请注意，列出了四种身份验证类型，每行一个。

8. 将包含 TLSClient 身份验证类型的行移动到列表顶部。

9. 保存并关闭 web.config 文件。

10. 使用提升的特权启动命令提示符。

11. 通过运行以下命令来重新启动 IIS：

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>配置 Skype for Business Server 被动身份验证

以下部分介绍了如何配置 Skype for Business 服务器以支持被动身份验证。 启用了双因素身份验证的用户将需要使用物理或虚拟智能卡和有效 PIN 才能使用 Skype for Business 客户端登录。

> [!NOTE]
> 强烈建议用户在服务级别为注册机构和 Web 服务启用被动身份验证。如果在全局级别为注册机构和 Web 服务启用被动身份验证，则可能导致未使用受支持的桌面客户端登录的用户遭遇组织范围身份验证失败。

### <a name="web-service-configuration"></a>Web 服务配置

以下步骤介绍了如何为将启用被动身份验证的控制器、企业池和 Standard Edition 服务器创建自定义 Web 服务配置。

### <a name="to-create-a-custom-web-service-configuration"></a>创建自定义 Web 服务配置

1. 使用 Skype for business 管理员帐户登录 Skype for business 服务器前端服务器。

2. 启动 Skype for Business Server 命令行管理程序。

3. 从 Skype for Business Server Management Shell 命令行中，通过运行以下命令为每个 Director、企业版池和标准版服务器创建新的 Web 服务配置：

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > WsFedPassiveMetadataUri FQDN 的值是您的 AD FS 2.0 服务器的联合身份验证服务名称。可通过从导航窗格右键单击“服务”****，然后选择“编辑联合身份验证服务属性”**** 在 AD FS 2.0 管理控制台中找到联合身份验证服务名称值。

4. 通过运行以下命令来验证 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值是否设置正确：

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. 对于客户端，被动身份验证是 Web 票证身份验证最少首选的身份验证方法。 对于将为被动身份验证启用的所有控制器、企业版池和标准版服务器，必须通过运行以下 cmdlet 在 Skype for Business Web 服务中禁用所有其他身份验证类型：

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. 运行以下 cmdlet 验证所有其他身份验证类型是否已成功禁用：

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>代理配置

当为 Skype for Business Web 服务禁用证书身份验证时，Skype for business 客户端将使用较少的首选身份验证类型（如 Kerberos 或 NTLM）对注册机构服务进行身份验证。 仍然需要证书身份验证以允许客户端检索 Web 票证，但是，必须为 Kerberos 和 NTLM 禁用注册机构服务。

以下步骤介绍了如何为将启用被动身份验证的边缘池、企业池和 Standard Edition 服务器创建自定义代理配置。

### <a name="to-create-a-custom-proxy-configuration"></a>创建自定义代理配置

1. 从 Skype for Business 服务器管理外壳程序命令行中，为每个 Skype for business 服务器 Edge 池、企业版池和标准版服务器创建新的代理配置，并通过运行以下命令为被动身份验证启用命令

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. 通过运行以下命令来验证所有其他代理身份验证类型是否已成功禁用：

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>另请参阅

[在 Skype for Business 服务器中管理双因素身份验证](two-factor-authentication.md)

[对 Skype for Business 客户端和 Skype for business 服务器使用双因素身份验证](use-two-factor.md)
