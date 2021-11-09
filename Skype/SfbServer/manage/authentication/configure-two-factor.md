---
title: 在客户端中配置双重Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 摘要：在客户端部署中配置双重Skype for Business Server。
ms.openlocfilehash: 1e28c88f28d765737415b01d82e2e8a7621c3744
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844245"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>在客户端中配置双重Skype for Business Server

**摘要：** 在客户端中配置双重Skype for Business Server。

以下各节介绍为部署配置双重身份验证所需的步骤。 有关双重身份验证详细信息，请参阅为联机管理员启用Office 365多重身份验证[- 网格用户帖子](https://go.microsoft.com/fwlink/p/?LinkId=313332)。

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>配置Enterprise根证书颁发机构以支持智能卡身份验证

以下步骤介绍如何配置 Enterprise 根 CA 以支持智能卡身份验证：

若要了解如何安装根 CA Enterprise，请参阅安装Enterprise[根证书颁发机构](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10))。

1. 使用域管理员Enterprise CA 计算机登录。

2. 启动系统管理器，并验证是否安装了证书颁发机构 Web 注册角色。

3. 从" **管理工具"菜单中** ，打开 **证书颁发机构** 管理控制台。

4. 在导航窗格中，展开"**证书颁发机构"。**

5. 右键单击 **"证书模板"，** 选择 **"新建"，** 然后选择"**要颁发的证书模板"。**

6. 选择 **注册代理**、 **智能卡用户** 和 **智能卡登录**。

7. 单击“**确定**”。

8. 右键单击 **"证书模板"。**

9. 选择"**管理"。**

10. 打开"智能卡用户"模板的属性。

11. 单击"安全 **"选项卡** 。

12. 更改权限，如下所示：

    - 使用读取/注册权限添加单个用户 AD (允许) 权限，或

    - 添加包含具有读取/注册权限的智能卡 (允许) 组，或

    - 添加具有读取/注册权限的域 (允许) 组

## <a name="configure-windows-8-for-virtual-smart-cards"></a>配置Windows 8智能卡的组

部署双重身份验证和智能卡技术时要考虑的一个因素是实施成本。 Windows 8提供了许多新的安全功能，其中一项最有趣的新功能是支持虚拟智能卡。

对于配备了受信任的平台模块 (TPM) 芯片（符合规范版本 1.2）的计算机，组织现在可以从智能卡登录中获益，而无需在硬件方面进行任何其他投资。 有关详细信息，请参阅将[虚拟智能卡与 Windows 8。](https://go.microsoft.com/fwlink/p/?LinkId=313365)

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>配置Windows 8智能卡的组

1. 使用启用Windows 8的用户的凭据登录到Skype for Business计算机。

2. 在Windows 8屏幕中，将光标移到屏幕右下角。

3. 选择" **搜索"** 选项，然后搜索"命令提示"。

4. 右键单击命令 **提示符**，然后选择以 **管理员角色运行**。

5. 通过运行以下命令 (TPM) 管理控制台中打开受信任的平台模块：

   ```console
   Tpm.msc
   ```

6. 从 TPM 管理控制台中，验证 TPM 规范版本是否至少为 1.2

    > [!NOTE]
    > 如果您收到一个对话框，指出找不到兼容的信任平台模块 (TPM) ，请验证计算机是否具有兼容的 TPM 模块，以及它在系统 BIOS 中是否已启用。

7. 关闭 TPM 管理控制台

8. 在命令提示符下，使用下列命令创建新的虚拟智能卡：

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

   > [!NOTE]
   > 若要在创建虚拟智能卡时提供自定义 PIN 值，请改为使用 /pin 提示符。

9. 在命令提示符下，通过运行以下命令打开计算机管理控制台：

  ```console
  CompMgmt.msc
  ```

10. 在"计算机管理"控制台中，选择"**设备管理"。**

11. 展开 **智能卡读卡器**。

12. 验证是否成功创建了新的虚拟智能卡读卡器。

## <a name="enroll-users-for-smart-card-authentication"></a>为用户注册智能卡身份验证

通常有两种方法为用户注册智能卡身份验证。 更简单的方法涉及让用户使用 Web 注册直接注册智能卡身份验证，而更复杂的方法涉及使用注册代理。 本主题重点介绍智能卡证书的自注册。

有关代表用户注册为注册代理的信息，请参阅代表其他用户注册 [证书](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11))。

### <a name="to-enroll-users-for-smart-card-authentication"></a>为用户注册智能卡身份验证

1. 使用启用了 Windows 8 的用户的凭据登录到 Skype for Business 工作站。

2. 启动Internet Explorer。

3. 浏览到证书 **颁发机构 Web 注册** (例如 https://MyCA.contoso.com/certsrv) 。

    > [!NOTE]
    > 如果你使用的是Internet Explorer 10，可能需要在兼容模式下查看此网站。

4. 在"**欢迎"** 页上，选择"**请求证书"。**

5. 接下来，选择"**高级请求"。**

6. 选择 **"创建并提交对此 CA 的请求"。**

7. 选择 **"证书模板****"部分下的**"智能卡用户"，然后使用下列值完成高级证书请求：

  - **密钥选项** 确认他以下设置：

    - 选择" **创建新密钥集"单** 选按钮

    - 对于 **云** 解决方案提供商，选择 **"Microsoft 基本智能卡加密提供程序"**

    - 对于 **"密钥** 用法 **"，Exchange (** 这是唯一可用于密钥) 。

    - 对于 **"密钥大小**"，输入 2048

    - 确认 **已选择"自动密钥** 容器名称"

    - 将其他框保持未选中状态。

  - 在 **"其他选项"** 下，确认以下值：

    - 对于 **"请求格式"，** 选择 **"CMC"。**

    - 对于 **哈希算法，** 选择 **sha1**。

    - 对于 **"友好名称** "，输入"证书"。

8. 如果使用物理智能卡读卡器，请将智能卡插入设备。

9. 单击 **"提交** "以提交证书请求。

10. 系统提示时，输入用于创建虚拟智能卡的 PIN。

    > [!NOTE]
    > 默认虚拟智能卡 PIN 值为"12345678"。

11. 颁发证书后，单击 **"安装此证书** "以完成注册过程。

    > [!NOTE]
    >  如果证书请求失败并出现错误"此 Web 浏览器不支持生成证书请求"，则有三种可能的方法可以解决此问题：
    >- 启用"兼容性视图"Internet Explorer。
    >- 启用"打开 Intranet 设置"选项Internet Explorer。
    >- 选择"选项"菜单中"安全"选项卡下的"将所有区域重置为Internet Explorer设置。

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>配置 Active Directory 联合身份验证服务 (AD FS 2.0) 

下一节介绍如何配置 Active Directory 联合身份验证服务 (AD FS 2.0) 以支持多重身份验证。 若要了解如何安装 AD FS 2.0，请参阅 [AD FS 2.0 分步指南和操作指南](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))。

> [!NOTE]
> 安装 AD FS 2.0 时，Windows服务器管理器添加 Active Directory 联合身份验证服务角色。 相反，请下载并安装 [Active Directory 联合身份验证服务](/troubleshoot/windows-server/identity/availability-description-afds)。

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>为双因素身份验证配置 AD FS

1. 使用域管理员帐户登录到 AD FS 2.0 计算机。

2. 启动 Windows PowerShell。

3. 从Windows PowerShell命令行运行以下命令：

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. 通过运行以下命令与将启用被动身份验证的每台服务器建立合作关系，替换特定于您的部署的服务器名称：

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. 从"管理工具"菜单中，启动 AD FS 2.0 管理控制台。

6. 展开 **"信任**  >  **关系信赖方信任"。**

7. 验证是否为用户创建了新的信任Skype for Business Server。

8. 通过运行以下命令，使用 Windows PowerShell为信赖方信任创建和分配颁发授权规则：

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. 通过运行以下命令，使用 Windows PowerShell为信赖方信任创建和分配颁发转换规则：

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. 从 AD FS 2.0 管理控制台中，右键单击信赖方信任并选择"**编辑声明规则"。**

11. 选择颁发 **授权规则** 选项卡并验证是否成功创建了新的授权规则。

12. 选择颁发 **转换规则** 选项卡并验证是否成功创建了新的转换规则。

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>配置 AD FS 2.0 以支持客户端身份验证

可以配置两种可能的身份验证类型，以允许 AD FS 2.0 支持使用智能卡进行身份验证：

- 基于表单的身份验证 (FBA) 

- 传输层安全性客户端身份验证

使用基于表单的身份验证，您可以开发允许用户通过使用其用户名/密码或通过使用其智能卡和 PIN 进行身份验证的网页。 本主题重点介绍如何使用 AD FS 2.0 实现传输层安全客户端身份验证。 有关 AD FS 2.0 身份验证类型的信息，请参阅 [AD FS 2.0：如何更改本地身份验证类型](https://go.microsoft.com/fwlink/p/?LinkId=313384)。

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>配置 AD FS 2.0 以支持客户端身份验证

1. 使用域管理员帐户登录到 AD FS 2.0 计算机。

2. 启动 Windows 资源管理器。

3. 浏览到 C：\inetpub\adfs\ls

4. 创建现有数据库文件的web.config副本。

5. 使用"web.config打开现有 记事本。

6. 从"菜单"栏中，选择 **"编辑"，** 然后选择"查找 **"。**

7. 搜索 \<localAuthenticationTypes\> 。

    请注意，列出了四种身份验证类型，每行一种。

8. 将包含 TLSClient 身份验证类型的行移到 部分的列表顶部。

9. 保存并关闭web.config文件。

10. 使用提升的权限启动命令提示符。

11. 通过运行以下命令来重新启动 IIS：

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>配置Skype for Business Server身份验证

以下部分介绍如何配置Skype for Business Server以支持被动身份验证。 启用后，启用了双重身份验证的用户需要使用物理或虚拟智能卡和有效 PIN 才能使用 Skype for Business 客户端登录。

> [!NOTE]
> 强烈建议客户在服务级别为注册器和 Web 服务启用被动身份验证。 如果在全局级别为注册器和 Web 服务启用被动身份验证，则可能导致未使用受支持的桌面客户端登录的用户在组织范围内进行身份验证失败。

### <a name="web-service-configuration"></a>Web 服务配置

以下步骤介绍如何为将启用被动身份验证的控制器、Enterprise池Standard Edition服务器创建自定义 Web 服务配置。

### <a name="to-create-a-custom-web-service-configuration"></a>创建自定义 Web 服务配置

1. 使用 Skype for Business Server 帐户登录到 Skype for Business 前端服务器。

2. 启动 Skype for Business Server 命令行管理程序。

3. 在 Skype for Business Server 命令行管理程序命令行中，通过运行以下命令，为每个将启用被动身份验证的控制器、Enterprise 池和 Standard Edition 服务器创建新的 Web 服务配置：

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

   > [!CAUTION]
   > WsFedPassiveMetadataUri FQDN 的值为 AD FS 2.0 服务器的联合身份验证服务名称。 可以在 AD FS 2.0 管理控制台中找到联合身份验证服务名称值，方法是从导航窗格中右键单击"服务"，然后选择"编辑联合身份验证服务 **属性"。**

4. 通过运行以下命令验证 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值是否正确设置：

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. 对于客户端，被动身份验证是 Webticket 身份验证最不首选的身份验证方法。 对于将启用被动Enterprise的所有控制器、Enterprise 池和 Standard Edition 服务器，必须通过运行以下 cmdlet 在 Skype for Business Web 服务中禁用所有其他身份验证类型：

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. 通过运行以下 cmdlet 验证所有其他身份验证类型是否成功禁用：

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>代理配置

当为 Skype for Business Web 服务禁用证书身份验证时，Skype for Business 客户端将使用不太首选的身份验证类型（如 Kerberos 或 NTLM）向注册器服务进行身份验证。 仍然需要证书身份验证以允许客户端检索 Web 令牌，但是，必须为注册器服务禁用 Kerberos 和 NTLM。

以下步骤介绍如何为将启用被动身份验证的边缘池、Enterprise池Standard Edition服务器创建自定义代理配置。

### <a name="to-create-a-custom-proxy-configuration"></a>创建自定义代理配置

1. 从 Skype for Business Server 命令行，为每个 Skype for Business Server 边缘池、Enterprise 池和 Standard Edition 服务器创建新的代理配置，这些服务器通过运行以下命令启用被动身份验证命令：

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. 通过运行以下命令验证是否成功禁用所有其他代理身份验证类型：

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>另请参阅

[在客户端中管理双重Skype for Business Server](two-factor-authentication.md)

[在客户端和客户端Skype for Business双重Skype for Business Server](use-two-factor.md)
