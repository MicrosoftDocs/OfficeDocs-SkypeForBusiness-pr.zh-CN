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
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: 了解如何准备用于部署 Microsoft Teams 会议室的基础结构，以便可以利用所有功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 181599e6b5181f50548621e4895b400f442646a6
ms.sourcegitcommit: 0fddd05334e37b0086ccc0aebe17a26f8e6e8e6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50884566"
---
# <a name="prepare-your-environment"></a>准备环境

本部分包含准备环境所需的步骤概述，以便可以使用 Microsoft Teams 会议室的所有功能。
  
1. 为每台 Microsoft Teams 会议室控制台准备设备帐户。 有关详细信息 [，请参阅部署 Microsoft Teams](rooms-deploy.md) 会议室。
    
2. 确保有运行良好的网络/Internet 连接可供设备使用。 
    
   它必须能够使用 DHCP 接收 IP 地址。  (首次单元启动时，Microsoft Teams 会议室不能配置静态 IP 地址，但之后，可以在设备或上游交换机或路由器上配置设备的静态 IP 地址。) 

   除了为媒体服务打开 (，还必须让这些端口打开) ：
   - HTTPS：443
   - HTTP：80

   如果你的网络通过代理运行，则还需要提供代理地址或脚本信息。
    
   > [!IMPORTANT]
   > Microsoft Teams 会议室不支持代理身份验证，因为它可能会干扰聊天室的常规操作。 在投入生产之前，请确保 Microsoft Teams 会议室已免除代理身份验证。
  
3. 为了改进你的体验，Microsoft 将收集数据。 若要允许 Microsoft 收集数据，请允许以下网站：

   - 遥测客户端终结点： https://vortex.data.microsoft.com/
   - 遥测设置终结点： https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>创建和测试设备帐户

设备  *帐户*  是 Microsoft Teams 会议室客户端用来从 Exchange 访问功能（如日历）和启用 Skype for Business 的帐户。 有关详细信息 [，请参阅部署 Microsoft Teams](rooms-deploy.md) 会议室。
  
### <a name="check-network-availability"></a>检查网络可用性

若要正常运行，Microsoft Teams 会议室设备必须有权访问满足这些要求的有线网络：
  
- 可访问 Active Directory 或 Azure Active Directory (Azure AD) 实例以及 Microsoft Exchange 和 Skype for Business 服务器。

- 可访问能够使用 DHCP 提供 IP 地址的服务器。 Microsoft Teams 会议室不能在首次单元启动时配置静态 IP 地址。

- 访问 HTTP 端口 80 和 443。

- 根据本地 Skype for Business Server[](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)实现或 Microsoft Teams 或 Skype for Business Online 实现的服务器端口和协议要求或[Microsoft 365 和 Office 365 URL](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)和 IP 地址范围中所述配置 TCP 和 UDP 端口。

> [!IMPORTANT]
> 务必使用 1 Gbps 的有线网络连接来确保获得所需带宽。

> [!NOTE]
> Microsoft Teams 会议室的软件更新会自动从 Microsoft Store for Business 下载。 请参阅 [适用于商业和教育的 Microsoft Store](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 的先决条件，验证会议室主机是否能够访问应用商店和自我更新。
  
### <a name="certificates"></a>证书

Microsoft Teams 会议室设备使用 Exchange Web 服务、Microsoft Teams 或 Skype for Business、网络使用情况和身份验证的证书。 如果相关服务器使用公用证书（联机部署和部分本地部署便属于这种情况），则无需在管理部分执行任何进一步操作来安装证书。 另一方面，如果证书颁发机构为私有 CA（通常用于本地部署），则设备需要信任该 CA，这意味着在设备中安装了 CA + CA 链证书。 将设备添加到域时，可以自动执行此任务。
  
安装证书的方式与任何其他 Windows 客户端一样。 
  
> [!NOTE]
> 可能需要证书才能让 Microsoft Teams 会议室使用 Skype for Business Server。
  
### <a name="proxy"></a>代理

Microsoft Teams 会议室旨在从 Windows OS 继承代理设置。 通过以下方式访问 Windows OS：
  
1. 在 Microsoft Teams 会议室 UI 中，单击"设置"齿轮图标，系统会提示你在设备上输入本地管理员密码 (默认密码是 **sfb**) 。
2. 点击"设置"，然后点击"转到 **Windows"** 按钮，然后点击转到"管理员登录"按钮，然后单击"管理员"按钮 (如果计算机已加入域，请选择"其他用户"，然后使用 .\admin 作为用户名) 。 
3. 在"**搜索 Windows"** 框左下角键入 regedit (长按屏幕或右键单击并选择"以管理员角色运行") 。
4. 单击 HKEY_USERS 文件夹（你将看到计算机用户 SID 列表），确保选择根文件夹 HKEY_USERS。
       
5. 单击"文件"，然后选择" **加载 Hive"。**
6. 浏览到 **C：\Users\Skype** 文件夹，键入"文件名"框 NTUSER.dat，然后按打开按钮

7. 系统会提示输入新加载的 Hive 的密钥名称;键入 Skype (现在应会看到 Skype 用户帐户的注册表) 。
 
8. 打开 Skype 密钥并浏览HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings，然后确保输入这些设置： 
    
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
    
有关 Microsoft Teams [会议室](https://docs.microsoft.com/microsoftteams/rooms/security#network-security) 所需的 FQDN、端口和 IP 地址范围的完整详细信息，请参阅网络安全一文。
  
  
### <a name="create-provisioning-packages"></a>创建设置包

你将使用预配包向 Exchange Server Microsoft 365 或 Office 365 进行身份验证。
  
### <a name="admin-group-management"></a>管理员组管理

加入域后，可以本地管理员身份使用组策略或本地计算机管理来设置安全组，就像对你的域中的 Windows 电脑那样。 该安全组的任何成员均可输入其凭据并解锁设置。
  
> [!NOTE]
> 如果你的 Microsoft Teams 会议室设备失去与域的信任关系（例如，如果在 Microsoft Teams 会议室加入域后将其从域中移除），你将无法通过身份验证进入设备并打开“设置”。 解决方法是使用本地管理员帐户登录。 
  
## <a name="local-accounts"></a>本地帐户

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft Teams 会议室本地用户帐户

该设备帐户通常不使用密码。 可以为其给定密码，但会有一些后果，包括密码过期后用户可能被锁在该控制台应用程序之外。 因此，管理员应确保不允许密码过期。
  
### <a name="admin---local-administrator-account"></a>“Admin”- 本地管理员帐户

Microsoft Teams 会议室的默认密码设置为"sfb"。 可以通过转到"Windows 设置"转到 Windows 或在 AutoUnattend.xml 文件中更改密码 (使用 ADK 中的 Windows 系统映像管理器对 xml 文件进行 \>) 。
  
> [!CAUTION]
> 请务必尽快更改 Microsoft Teams 会议室密码。 
  
还可以通过设置组策略（其中域管理员设为本地管理员）来管理本地管理员密码。
  
本地管理员密码不是安装过程中的一个选项。
  
### <a name="machine-account"></a>计算机帐户

与任何 Windows 设备一样，可以通过右键单击"关于重命名电脑的设置"来 \>  \> **重命名计算机名称**。
  
如果要在将计算机加入域后重命名计算机，请使用 **Rename-Computer（PowerShell** 命令，后跟计算机的新名称）。
  
## <a name="related-topics"></a>相关主题

[规划 Microsoft Teams 会议室](rooms-plan.md)

[Microsoft Teams 会议室要求](requirements.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)

[适用于商业和教育的 Microsoft Store 的先决条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
