---
title: 准备环境
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: 了解如何准备基础结构以部署Microsoft Teams 会议室以便可以利用所有功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b92325fe9c7c43497fd9647306cfb6b218f5fde0
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015032"
---
# <a name="prepare-your-environment"></a>准备环境

本部分包含准备环境所需的步骤概述，以便可以使用 Microsoft Teams 会议室。
  
1. 为每台主机准备Microsoft Teams 会议室帐户。 有关详细信息[，Microsoft Teams 会议室](rooms-deploy.md)部署应用程序。
    
2. 确保有运行良好的网络/Internet 连接可供设备使用。
  
3. 为了改进你的体验，Microsoft 将收集数据。 若要允许 Microsoft 收集数据，请允许以下网站：

   - 遥测客户端终结点： https://vortex.data.microsoft.com/
   - 遥测设置终结点： https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-resource-account"></a>创建和测试资源帐户

*资源帐户* 是一个帐户，Microsoft Teams 会议室客户端用来从日历Exchange访问功能，以及连接到Microsoft Teams。 有关详细信息[，Microsoft Teams 会议室](rooms-deploy.md)部署应用程序。
  
### <a name="check-network-availability"></a>检查网络可用性

若要正常运行，Microsoft Teams 会议室必须有权访问满足这些要求的有线网络：
  
- 访问 Active Directory 或 Azure Active Directory (Azure AD) 实例，以及 Microsoft Exchange Microsoft Teams。

- 可访问能够使用 DHCP 提供 IP 地址的服务器。 Microsoft Teams 会议室单元启动时无法使用静态 IP 地址配置该地址。

- 访问 HTTP 端口 80 和 443。

- 根据本地 Skype for Business Server 实现或 Microsoft 365[](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)和 Office 365 URL 和[IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)地址范围的服务器端口和协议要求中所述配置的 TCP 和 UDP 端口Microsoft Teams。

如果你的网络通过代理运行，则还需要提供代理地址或脚本信息。
    
> [!IMPORTANT]
> Microsoft Teams 会议室不支持代理身份验证，因为它可能会干扰聊天室的常规操作。 在投入Microsoft Teams 会议室之前，请确保已免除代理身份验证。

> [!IMPORTANT]
> 务必使用 1 Gbps 的有线网络连接来确保获得所需带宽。

> [!NOTE]
> 系统会自动Microsoft Teams 会议室下载适用于 适用于企业的 Microsoft Store 的软件更新。 请参阅[适用于企业的 Microsoft Store](/microsoft-store/prerequisites-microsoft-store-for-business)和教育的先决条件，验证会议室主机是否能够访问应用商店和自我更新。
  
### <a name="certificates"></a>证书

你的 Microsoft Teams 会议室 设备使用证书Exchange Web 服务、Microsoft Teams或Skype for Business、网络使用情况和身份验证。 如果相关服务器使用公共证书（联机部署和某些本地部署的情况）则管理员无需执行进一步操作来安装证书。 另一方面，如果证书颁发机构是专用 CA，则设备需要信任该 CA。 这意味着在设备上安装了 CA + CA 链证书。 将设备添加到域时，可以自动执行此任务。
  
安装证书的方式与任何其他 Windows 客户端一样。 
  
> [!NOTE]
> 可能需要证书才能Microsoft Teams 会议室Skype for Business Server。
  
### <a name="proxy"></a>代理

Microsoft Teams 会议室从操作系统继承代理Windows设置。 通过以下方式访问 Windows OS：
  
1. 在 Microsoft Teams 会议室 UI 中，单击 设置 齿轮图标，系统会提示输入设备的本地管理员密码 (默认密码是 **sfb**) 。
2. 点击 **设置，** 然后点击"转到 **Windows"** 按钮，然后点击转到"管理员登录"按钮，然后单击"管理员"按钮 (如果计算机已加入域，请选择"其他用户"，然后使用 .\admin作为用户名) 。 
3. 在"**搜索Windows"** 框中，键入 regedit (长按屏幕或右键单击并选择"以管理员角色运行") 。 
4. 单击 HKEY_USERS 文件夹（你将看到计算机用户 SID 列表），确保选择根文件夹 HKEY_USERS。
       
5. 单击"文件"，然后选择" **加载 Hive"。**
6. 浏览到 **C：\Users\Skype** 文件夹，键入"文件名"框 NTUSER.dat，然后按打开按钮

7. 系统会提示输入新加载的 Hive 的密钥名称;键入Skype (现在应会看到"用户"Skype的注册表) 。
 
8. 打开Skype密钥并浏览HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings，然后确保输入这些设置： 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    如果 ProxyServer 不存在，你可能必须以字符串形式添加此注册表项，将 xx.xx.xx.xx:8080 更改为你的代理服务器的 IP/主机和端口。
 
    如果客户使用 PAC 文件，配置将如以下示例所示：

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. 完成更改后，请突出显示 Skype 用户注册表项（Skype 的根文件夹），并从“注册表文件”菜单中选择“卸载配置单元”（系统将提示你确认 - 请选择 **是**）。
    
10. 现在可以关闭注册表编辑器并在 Windows 搜索框中键入“注销”。
    
11. 返回登录屏幕，选择 **Skype** 用户。 如果上述所有步骤都成功，Microsoft Teams 会议室设备将成功登录。
    
请参阅[网络安全一文](./security.md#network-security)，了解有关 FQDN、端口和 IP 地址范围进行配置所需的Microsoft Teams 会议室。
  
### <a name="admin-group-management"></a>管理员组管理

如果选择加入域 (Azure Active Directory 或 Active Directory) ，可以使用 Microsoft Endpoint Manager、组策略或本地计算机管理将安全组设置为本地管理员，就像在域中为 Windows 电脑设置安全组一样。 该安全组的任何成员均可输入其凭据并解锁设置。
  
> [!NOTE]
> 如果你的 Microsoft Teams 会议室设备失去与域的信任关系（例如，如果在 Microsoft Teams 会议室加入域后将其从域中移除），你将无法通过身份验证进入设备并打开“设置”。 解决方法是使用本地管理员帐户登录。 
  
## <a name="local-accounts"></a>本地帐户

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft Teams 会议室本地用户帐户

Teams 会议室包括名为"Skype"的无密码本地帐户。 此帐户用于登录到 Windows以启动 Teams 会议室 应用。 不支持将密码应用到此帐户。 有关详细信息[Microsoft Teams 会议室安全](security.md)。
  
### <a name="admin---local-administrator-account"></a>“Admin”- 本地管理员帐户

Microsoft Teams 会议室默认密码设置为"sfb"。 可以通过管理员模式或 AutoUnattend.xml 文件在本地更改密码 (使用 ADK 中的 Windows 系统映像管理器更改 xml 文件) 。
  
> [!CAUTION]
> 请务必尽快更改Microsoft Teams 会议室密码。 
  
本地管理员密码不是安装过程中的一个选项。

可以在安全中心一文Microsoft Teams 会议室[管理员帐户](security.md)。
  
### <a name="machine-account"></a>计算机帐户

与任何Windows一样，可以通过右键单击"关于重命名电脑"设置 \> **重命名** \> **计算机名称**。
  
如果要在将计算机加入域后重命名计算机，请使用 [Rename-Computer（PowerShell](/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-7.2)命令，后跟计算机的新名称）。
  
## <a name="related-topics"></a>相关主题

[计划Microsoft Teams 会议室](rooms-plan.md)

[Microsoft Teams 会议室要求](requirements.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)

[教育适用于企业的 Microsoft Store的先决条件](/microsoft-store/prerequisites-microsoft-store-for-business)
