---
title: 配置 SIP 网关
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/8/2022
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 了解如何配置 SIP 网关。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c93aec7cb65cdd40c05a540b51a3da8ba268c7e9
ms.sourcegitcommit: feb9b7d10e38f5a629ee9202b5aaec5beef4de9b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2022
ms.locfileid: "69343279"
---
# <a name="configure-sip-gateway"></a>配置 SIP 网关

本文介绍如何配置 SIP 网关，以便组织可以通过 Microsoft Teams 使用兼容的 SIP 设备。 若要了解 SIP 网关可为组织执行哪些操作，以及组织需要哪些硬件、软件和许可证，请阅读 [规划 SIP 网关](sip-gateway-plan.md)。

在配置 SIP 网关之前，请执行以下操作：

- **将 SIP 设备重置为出厂默认设置。** 你或你的组织的用户必须将与 SIP 网关一起使用的每个 SIP 设备重置为其出厂默认设置。 若要了解如何执行此操作，请参阅制造商的说明。

- **打开防火墙以Microsoft 365 和 Teams。** 打开网络的防火墙以Microsoft 365 和 Teams 流量，如[Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)中所述。 仅出站流量需要防火墙规则。

- **确保 SIP 设备不在代理后面。** 确保 http/s 流量绕过任何公司 http/s 代理。

- **打开 UDP 端口。** 为 IP 范围 52.112.0.0/14 和 52.122.0.0/15 打开 49152 到 53247 范围内的 UDP 端口。

- **打开 TCP 端口。** 打开 IP 范围 52.112.0.0/14 和 52.122.0.0/15 的 TCP 端口 5061。

- **) 打开以下 https 终结点 (IP 地址和 URL：**

  - 13.75.175.145
  - 52.189.219.201
  - 51.124.34.164
  - 13.74.250.91
  - 13.83.55.36
  - 23.96.103.40
  - https://blobsdgapac.blob.core.windows.net
  - https://blobsdgemea.blob.core.windows.net
  - https://blobsdgnoam.blob.core.windows.net
  - https://httpblobsdgapac.blob.core.windows.net
  - https://httpblobsdgemea.blob.core.windows.net
  - https://httpblobsdgnoam.blob.core.windows.net


以下部分介绍了作为管理员配置 SIP 网关必须执行的操作。

- [验证 SIP 网关是否可用于组织](#verify-that-sip-gateway-is-available-for-your-organization)。

- [为组织中的用户启用 SIP 网关](#enable-sip-gateway-for-the-users-in-your-organization)。

- [设置 SIP 网关预配服务器 URL](#set-the-sip-gateway-provisioning-server-url)。

本文还介绍如何：

- [为了方便起见，单独或分批注册 SIP 设备](#provision-and-enroll-sip-devices-as-common-area-phones)。  

- [查看和监视 SIP 设备。](#view-and-monitor-sip-devices)

- [启用对多语言用户界面的支持。](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>验证 SIP 网关是否可用于组织

1. 登录到 [Teams 管理中心](https://admin.teams.microsoft.com/)。

2. 在左侧选择“ **Teams 设备** ”，查看 **“SIP 设备** ”选项卡是否可见。 如果是，则为组织启用 SIP 网关服务。

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>为组织中的用户启用 SIP 网关

可以通过以下两种方式之一为组织启用 SIP 网关：使用 Teams 管理中心或使用 PowerShell cmdlet。

### <a name="by-using-teams-admin-center"></a>使用 Teams 管理中心

若要在 Teams 管理中心启用 SIP 网关，请执行以下步骤：

1. 转到 [Teams 管理中心](https://admin.teams.microsoft.com/)

2. 在左侧的 **“语音**”下，选择“ **呼叫策略**”。

3. 在 **“管理策略”** 下的右侧，选择分配给用户的相应呼叫策略，或者根据需要创建新的呼叫策略并将其分配给所需的用户。

4. 选择 **“管理策略**”，选择一个策略，然后选择“ **编辑**”。

5. 打开 **“SIP 设备可用于呼叫**”的设置，然后选择“ **保存**”。


### <a name="by-using-powershell"></a>使用 PowerShell

还可以使用 PowerShell [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) cmdlet 启用 SIP 网关。 若要为 SIP 设备启用用户，请选择一个策略，并将 属性 `-AllowSIPDevicesCalling` 设置为 `True`。 默认值 `False`为 ，因此除非启用，否则用户将无法使用其 SIP 设备。

> [!NOTE]
> - 策略传播最多可能需要 24 小时。

## <a name="set-the-sip-gateway-provisioning-server-url"></a>设置 SIP 网关预配服务器 URL

可以在动态主机配置协议 (DHCP) 服务器中设置 SIP 网关预配服务器的 URL。 远程工作的用户必须手动配置它。

### <a name="using-dhcp"></a>使用 DHCP

对于每个 SIP 设备，请设置以下 SIP 网关预配服务器 URL 之一： 

- Emea： `http://emea.ipp.sdg.teams.microsoft.com`
- 美洲： `http://noam.ipp.sdg.teams.microsoft.com`
- 亚太： `http://apac.ipp.sdg.teams.microsoft.com`

通过在 DHCP 服务器中配置上述 SIP 网关预配服务器 URL，将 SIP 设备添加到 Teams 组织。 若要详细了解 DHCP 服务器，请参阅 [部署和管理 DHCP](/training/modules/deploy-manage-dynamic-host-configuration-protocol)。 此外，可以使用 DHCP 选项 42 (NTP) 服务器指定网络时间协议，使用 DHCP 选项 2 指定协调世界时 (UTC) 的偏移量（以秒为单位）。 组织中的设备将路由到 SIP 网关预配服务器。 成功预配的 SIP 电话将显示 Teams 徽标和用于登录的软按钮。

确保 SIP 设备处于支持的最低载入固件版本。 在载入期间，SIP 网关会将默认配置和身份验证用户界面推送到设备。 若要了解 SIP 设备所需的固件版本，请参阅 [规划 SIP 网关](sip-gateway-plan.md)。

### <a name="manually"></a>手动

远程工作的用户必须使用以下步骤将预配服务器 URL 手动配置到其 SIP 设备：

1. 在设备上打开 **“设置”** 并获取设备的 IP 地址。

2. 打开浏览器窗口，输入设备的 IP 地址，根据需要登录 () 并在设备的 Web 实用工具中配置预配服务器的 URL。

3. 在 **“设置”** 或“Web 实用工具 **的高级设置”** 下，输入上面显示的预配服务器 URL。

> [!NOTE]
> - 只能将兼容的 SIP 设备载入到 SIP 网关。 
> - 必须先将 Cisco IP 电话刷写到多平台固件，然后才能载入。 若要了解如何操作，请参阅 [Cisco 固件转换指南](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)。
> - 对于 Yealink 电话，请使用选项 66。
> - 对于 Cisco、Poly 和 AudioCode 电话，请使用选项 160。 
> - 对于 Cisco 设备，请将 **/$PSN.xml** 追加到预配服务器 URL。


## <a name="configure-conditional-access"></a>配置条件访问

条件访问是 Azure Active Directory (Azure AD) 功能，可帮助确保访问 Microsoft 365 资源的设备得到适当的管理和保护。 SIP 网关使用 Azure AD 对 SIP 设备进行身份验证，因此，如果组织对企业网络中的设备使用条件访问，则应排除以下 IP 地址：

- 北美：
    - 美国东部：52.170.38.140
    - 美国西部：40.112.144.212
-   EMEA 区域：
    - 欧盟北部：40.112.71.149
    - 欧盟西部：40.113.112.67
-   APAC 区域：
    - 澳大利亚东部：20.92.120.71
    - 澳大利亚东南部：13.73.115.90

有关详细信息，请参阅 [IP 地址范围](/azure/active-directory/conditional-access/location-condition#ip-address-ranges)。

## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>将 SIP 设备预配和注册为公用区域电话

> [!NOTE]
> SIP 设备必须先载入 SIP 网关，然后才能注册。

若要简化任务，可以在 Teams 管理中心中一次注册一个 SIP 设备，也可以分批注册 SIP 设备。 操作步骤如下：

1. 登录到 [**Teams 管理中心**](https://admin.teams.microsoft.com)。

2. 选择 **“Teams 设备** > **SIP 设备**”。

3. 在右上角，选择 **“操作** > **预配设备** ”，然后执行以下步骤之一：

  - **若要预配一台设备，请执行以下操作：**

     a. 在 **“等待激活**”下，选择“ **添加**”。

     b. 在 **“添加 MAC 地址** ”窗格中，输入设备的 **MAC 地址** 和 **位置** ，然后选择“ **应用**”。
     
     c. 在 **“等待激活**”下，选择刚刚添加的设备，然后选择“ **生成验证码**”。
     
     d. 在“ **预配设备** ”窗格的 **“验证码**”下，记下 SIP 设备的验证码。

   - **若要预配多个设备，请执行以下操作：**

     a. 在右侧的 **“等待激活**”下，选择“**导出**” (Microsoft Excel 图标) 。
     
     b. 在“ **预配设备** ”窗格的“ **上传多个 MAC 地址**”下，选择 **“下载模板**”。
     
     c. **将Template_Provisioning.csv** 保存到计算机，并填写 **“MAC ID**”和“**位置”** 字段。
    
     d. 在 **“预配设备** ”窗格中，选择“ **上传多个 MAC 地址**”。 

     e. 在“ **上传 MAC 地址** ”窗格的右侧，选择“ **选择文件**”，然后选择包含数据的 **Template_Provisioning.csv** 文件。

     F。 在 **“预配设备** ”窗格的“ **等待激活**”下，选择一台设备，然后选择“ **生成验证码** ”，为每个预配的设备生成一次性验证码。 记下每个 SIP 设备的验证码。

4. 在 SIP 设备上，拨打注册功能代码，后跟验证码。 在 SIP 设备上，拨打 SIP 网关用于注册一次性验证码验证) 的注册功能代码 \*55* (，然后拨入此特定设备的 Teams 管理员中心生成的验证码。 例如，如果验证码123456，请拨打 \*55\*123456 注册设备。

5.  在 **“预配设备** ”窗格的 **“等待登录**”下，选择“ **注销**”。

6. 在 **“登录用户** ”对话框中，复制或记下 SIP 设备的配对代码。

7. 转到 [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)，然后在 **“输入代码”** 下输入 SIP 设备的配对代码，然后选择“ **下一步**”。

8. 在“Microsoft **登录**”页上的 **“Email或电话**”字段中，输入 SIP 设备的电子邮件地址，然后选择“**下一步**”。

9. 在“ **密码** ”页上，输入 SIP 设备的电子邮件地址的密码，然后选择“ **登录**”。

10. 在“ **是否尝试登录到 Teams SIP 设备网关** ”页上，选择“ **继续**”。

## <a name="how-to-sign-in-and-sign-out"></a>如何登录和注销

用户的个人设备仅支持本地登录。 若要从管理员中心注销设备，请执行以下步骤：

1. 登录到 [**Teams 管理中心**](https://admin.teams.microsoft.com)。

2. 选择 **“Teams 设备** > **SIP 设备**”。

3. 在右侧，选择 SIP 设备，然后选择“ **注销**”。


### <a name="user-pairing-and-sign-in"></a>用户配对和登录

若要在用户使用公司凭据进行身份验证后配对 SIP 设备，用户必须：

1. 在 SIP 电话上按 **“登录”** 以显示身份验证 URL 和配对代码。 配对代码对时间敏感。 如果过期，用户必须在手机上按 **“后退** ”，然后再次开始登录过程。

2. 在用户的桌面或移动浏览器中导航到身份验证 URL，并使用公司凭据登录。

3. 将 SIP 电话上显示的配对代码输入到 Web 身份验证应用中，以将 SIP 电话与用户帐户配对。 成功登录（可能需要一段时间），如果设备支持，SIP 电话将显示电话号码和用户名。

> [!NOTE]
> Azure Active Directory Web 身份验证应用中显示的设备位置是设备连接到的 SIP 网关数据中心。 范围内的 SIP 电话不支持 OAuth，因此 SIP 网关通过 Web 身份验证应用对用户进行身份验证，然后将设备与用户的凭据配对。 在此处了解详细信息：[Microsoft 标识平台和 OAuth 2.0 设备授权流](/azure/active-directory/develop/v2-oauth2-device-code)。

### <a name="sign-out"></a>注销

若要注销，设备用户可以：

- 在 SIP 设备上按 **“注销** ”，然后按照设备上所述的步骤进行操作。 

若要在 Teams 管理中心注销设备，请执行以下操作：

1. 登录到 [**Teams 管理中心**](https://admin.teams.microsoft.com)。

2. 选择 **“Teams 设备** > **SIP 设备**”。

3. 在右侧的“ **SIP 设备** ”窗格中，选择设备。

4. 在设备的 **“详细信息”窗格中**，选择“ **详细信息** ”选项卡，然后在右上方的 **“操作”** 菜单上，选择“ **注销**”。 

## <a name="view-and-monitor-sip-devices"></a>查看和监视 SIP 设备

设备的用户至少登录一次后，可以在 Teams 管理中心查看和监视 SIP 设备清单。 操作步骤如下：

1. 登录到 [Teams 管理中心](https://admin.teams.microsoft.com/)。

2. 选择 **“Teams 设备** > **SIP 设备**”。 右侧列出了所有已登录 SIP 设备。

## <a name="restart-a-sip-device"></a>重启 SIP 设备

1. 登录到 [Teams 管理中心](https://admin.teams.microsoft.com)。

2. 选择 **“Teams 设备** > **SIP 设备**”。 

3. 在右侧，选择要重启的 SIP 设备，然后选择“ **重启**”。


> [!NOTE]
> - 从租户中删除 SIP 设备目前在 Teams 管理中心不可用。 
> - 命令执行取决于设备可用性，它可能与 Teams 管理中心中显示的执行状态不匹配。 如果尝试在不支持 SIP 网关的设备上启用 SIP 网关，则不会执行该命令。

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>将策略更改同步到 SIP 设备以强制实施策略

用户登录时，会将用户详细信息和策略提取到 SIP 设备。 此后，针对已登录用户所做的任何策略更改将在一小时内同步到设备。 设备必须定期使用 SIP 网关刷新其注册。 SIP 电话依赖于呼叫重定向，因此管理员必须将 中的 `Set-CsTeamsCallingPolicy` 属性设置为 。`AllowCallRedirect` `Enabled`


## <a name="set-a-sip-devices-ui-language"></a>设置 SIP 设备的 UI 语言

SIP 设备通常可以多种语言显示信息。 设置其 UI 语言会影响其界面，包括软键和登录/注销系统消息。 设置 UI 语言是在预配服务器中使用 DHCP 服务器完成的，或者通过在 URL 中追加代码字符串手动完成，如以下示例所示。

如何为 Polycom、AudioCodes 和 Yealink 电话设置德语：
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

如何为 Cisco 手机设置日语：
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>支持的语言

|语言名称|语言代码]
|-------------|-------------|
|英语 (默认) |en       |
|西班牙语      |es           |
|日语     |ja           |
|德语       |德           |
|法语       |fr           |
|葡萄牙语   |铂           |

> [!Note]
> - Yealink 不支持日语，Polycom VVX 部分支持日语。
> - 如果 SIP 终结点不支持所选语言，则系统默认为英语。
> - 如果未通过预配 URL 设置 **lang_xx** 参数，则使用英语作为默认语言。
> - 如果 **登录以发出紧急呼叫** 文本未翻译为其他语言，由于屏幕大小限制，在以下 IP 电话型号上 **按“登录** ”上将显示英文缩写版本：
>   - Poly VVX 150、VVX 201
>   - Cisco CP-6821、CP-7811、CP-7821、CP-7841、CP-7861
>   - 由于字符串长度限制，语音邮件软键标签在 Poly VVX 的所有语言中使用 **VM** 文本进行硬编码。

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams 和 IPv6

SIP 网关仅支持 IPv4。 Microsoft Teams 服务和客户端支持 IPv4 和 IPv6。 如果要控制与 Microsoft Teams 的通信，请使用 [Microsoft 365 URL 和 IP 地址范围中的 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)。

## <a name="emergency-calling"></a>紧急呼叫

SIP 网关支持动态紧急呼叫 (动态 E911) ，用于通过网络共享网络属性的兼容 SIP 设备。 这些属性在 Teams 管理中心进行预配，可以是本地 IP 和子网长度的组合，也可以是机箱 ID 和网络端口号的组合。 对于不共享位置属性的设备，或者如果出于任何原因未动态解析位置，SIP 网关将继续支持基于已注册地址的紧急呼叫。 目前，直接路由方案不支持已注册的地址。 有关紧急呼叫的详细信息，请参阅 [计划和管理紧急呼叫](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)。

## <a name="report-problems-to-microsoft"></a>向Microsoft报告问题

若要报告问题，请联系 [Microsoft 支持部门](https://support.microsoft.com)。
