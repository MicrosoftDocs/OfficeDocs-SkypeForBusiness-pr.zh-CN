---
title: 准备环境
ms.author: v-lanac
author: lanachin
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
description: 了解如何为部署 Microsoft 团队聊天室准备基础结构，以便你可以充分利用所有功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3e520643d40e78065d4b6a0359a8ca567ba2284c
ms.sourcegitcommit: bf6521f0bc91a55dcf849506bb757ebfae54fcb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529175"
---
# <a name="prepare-your-environment"></a>准备环境

本部分概括介绍了准备环境所需的步骤，以便你可以使用 Microsoft 团队聊天室的所有功能。
  
1. 为每个 Microsoft 团队聊天室控制台准备设备帐户。 有关详细信息，请参阅[部署 Microsoft 团队聊天室](rooms-deploy.md)。
    
2. 确保有运行良好的网络/Internet 连接可供设备使用。 
    
   - 它必须能够使用 DHCP 接收 IP 地址。 （不能在第一台设备启动时使用静态 IP 地址配置 Microsoft 团队会议室，但随后可以在设备上或在上游交换机或路由器上配置该设备的静态 IP。）
   - 它必须打开这些端口（除了为媒体打开普通端口）：
   - HTTPS：443
   - HTTP：80
   - 如果你的网络通过代理运行，则还需要提供代理地址或脚本信息。
    
     > [!IMPORTANT]
     > Microsoft 团队聊天室不支持代理身份验证，因为它可能会干扰聊天室的常规操作。 在投入生产之前，确保 Microsoft 团队聊天室已免除代理身份验证。
  
3. 为了改进你的体验，Microsoft 将收集数据。 若要允许 Microsoft 收集数据，请允许以下网站：

   - 遥测客户端终结点：https://vortex.data.microsoft.com/
   - 遥测设置终结点：https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>创建和测试设备帐户

*设备帐户*是 Microsoft 团队聊天室客户端用于访问 Exchange 中的功能（如日历）和启用 Skype for business 的帐户。 有关详细信息，请参阅[部署 Microsoft 团队聊天室](rooms-deploy.md)。
  
### <a name="check-network-availability"></a>检查网络可用性

为了正常运行，Microsoft 团队聊天室设备必须具有满足这些要求的有线网络的访问权限：
  
- 可访问 Active Directory 或 Azure Active Directory (Azure AD) 实例以及 Microsoft Exchange 和 Skype for Business 服务器。
- 可访问能够使用 DHCP 提供 IP 地址的服务器。 在第一台设备启动时，无法使用静态 IP 地址配置 Microsoft 团队会议室。
- 访问 HTTP 端口 80 和 443。
- TCP 和 UDP 端口配置为针对本地 Skype for Business 服务器实施，或 microsoft 团队或 Skype for business online 实施的[microsoft 365 和 Office 365 url 和 IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)的服务器的 "[端口和协议要求](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)" 中所述。

> [!IMPORTANT]
> 务必使用 1 Gbps 的有线网络连接来确保获得所需带宽。

> [!NOTE]
> Microsoft 团队聊天室的软件更新会自动从 Microsoft Store for Business 下载。 请参阅[Microsoft Store For Business 和教育](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)版的先决条件，以验证聊天室控制台是否能够访问应用商店和自我更新。
  
### <a name="certificates"></a>证书

Microsoft 团队聊天室设备使用 Exchange Web 服务、Microsoft 团队或 Skype for business、网络使用和身份验证的证书。 如果相关服务器使用公用证书（联机部署和部分本地部署便属于这种情况），则无需在管理部分执行任何进一步操作来安装证书。 另一方面，如果证书颁发机构为私有 CA（通常用于本地部署），则设备需要信任该 CA，这意味着在设备中安装了 CA + CA 链证书。 将设备添加到域时，可以自动执行此任务。
  
安装证书的方式与任何其他 Windows 客户端一样。 
  
> [!NOTE]
> 为了让 Microsoft 团队聊天室使用 Skype for Business 服务器，可能需要证书。
  
### <a name="proxy"></a>代理

Microsoft 团队聊天室旨在继承 Windows 操作系统中的代理设置。 通过以下方式访问 Windows OS：
  
1. 在 Microsoft 球队会议室 UI 中，单击 "设置" 齿轮图标，系统将在此处提示您输入本地管理员密码（默认密码为 " **sfb**"）。
2. 点击 "**设置**"，然后点击 "**转到 Windows** " 按钮，然后点击 "**转到管理员登录**" 按钮，然后单击 "**管理员**" 按钮（如果计算机已加入域，请选择 **"其他用户"，** 然后使用 .\admin 作为用户名）。
3. 在 regedit 中的 "**搜索窗口**" 框左下角键入（长按屏幕或右键单击，然后选择 "**以管理员身份运行**"）。
4. 单击 HKEY_USERS 文件夹（你将看到计算机用户 SID 列表），确保选择根文件夹 HKEY_USERS。
       
5. 单击 "文件"，然后选择 "**加载配置单元"。**
6. 浏览到**C:\Users\Skype**文件夹，然后在 "文件名" 框中键入 NTUSER，然后按 "打开" 按钮

7. 系统会提示你输入新加载的配置单元的密钥名称;在 Skype 中键入（您现在应该可以看到 Skype 用户的注册表设置）。
 
8. 打开 Skype 密钥并浏览到 HKEY_USERS \Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet 设置，然后确保输入以下设置： 
    
    `[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]`
    
    `"MigrateProxy"=dword:00000001`
    
    `"ProxyEnable"=dword:00000001`
    
    `"ProxyServer"="xx.xx.xx.xx:8080"`
    
    如果 ProxyServer 不存在，你可能必须以字符串形式添加此注册表项，将 xx.xx.xx.xx:8080 更改为你的代理服务器的 IP/主机和端口。
    
9. 完成更改后，请突出显示 Skype 用户密钥（Skype 的根文件夹），然后从 "注册表文件" 菜单中选择 "卸载配置单元" （系统将提示您确认-选择 **"是"** ）。
    
10. 现在可以关闭注册表编辑器并在 Windows 搜索框中键入“注销”。
    
11. 返回登录屏幕，选择 **Skype** 用户。 如果上述所有步骤均已成功，Microsoft 团队聊天室设备将成功登录。
    
要使用此应用程序，你必须能够连接至下面所述的终结点。要查看 IP 地址，请展开描述通信流的表下面的 IP 地址部分。
  
**防火墙代理主机名/端口示例**

|用途|源或凭据|源端口|目标|CDN|ExpressRoute for Office 365|目标 IP|目标端口|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|身份验证与标识  <br/> |请参阅[Microsoft 365 和 Office 365 身份验证和标识](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|门户与共享  <br/> |请参阅[Microsoft 365 管理中心和共享](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|SIP 信号  <br/> |客户端计算机或已登录用户  <br/> |临时端口  <br/> |\*。 contoso.com  <br/> |否  <br/> |是  <br/> |[Skype for Business IP 范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|持久型共享对象模型 (PSOM) 连接 Web 会议  <br/> |客户端计算机或已登录用户  <br/> |临时端口  <br/> |\*。 contoso.com  <br/> |否  <br/> |是  <br/> |[Skype for Business IP 范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|HTTPS 下载  <br/> |客户端计算机或已登录用户  <br/> |临时端口  <br/> |\*。 contoso.com  <br/> |否  <br/> |是  <br/> |[Skype for Business IP 范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|音频  <br/> |客户端计算机或已登录用户  <br/> |TCP/UDP 50,000-50019  <br/> |\*。 contoso.com  <br/> |否  <br/> |是  <br/> |[Skype for Business IP 范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、UDP 3478、TCP/UDP 50,000-59,999  <br/> |
|视频  <br/> |客户端计算机或已登录用户  <br/> |TCP/UDP 50,020-50039  <br/> |\*。 contoso.com  <br/> |否  <br/> |是  <br/> |[Skype for Business IP 范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、UDP 3478、TCP/UDP 50,000-59,999  <br/> |
|桌面共享  <br/> |客户端计算机或已登录用户  <br/> |TCP/UDP 50,040-50059  <br/> |\*。 contoso.com  <br/> |否  <br/> |是  <br/> |[Skype for Business IP 范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443，50,000-59,999  <br/> |
|用于 iOS 设备中的 Lync Mobile 2010 的 Lync Mobile 推送通知 Android、Nokia Symbian 或 Windows Phone 移动设备不需要此功能。  <br/> |客户端计算机或已登录用户  <br/> |临时端口  <br/> |\*。 contoso.com  <br/> |否  <br/> |是  <br/> |[Skype for Business IP 范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Skype Telemetry  <br/> |客户端计算机或已登录用户  <br/> |临时端口  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |否  <br/> |否  <br/> |不适用  <br/> |TCP 443  <br/> |
|Skype 客户端快速提示  <br/> |客户端计算机或已登录用户  <br/> |临时端口  <br/> |quicktips.skypeforbusiness.com  <br/> |否  <br/> |否  <br/> |不适用  <br/> |TCP 443  <br/> |

> [!NOTE]
> Contoso.com 和 broadcast.skype.com 的通配符代表专门用于 Microsoft 365 或 Office 365 的节点的长列表。 
  
### <a name="create-provisioning-packages"></a>创建设置包

你将使用预配包对 Exchange Server、Microsoft 365 或 Office 365 进行身份验证。
  
### <a name="admin-group-management"></a>管理员组管理

加入域后，可以本地管理员身份使用组策略或本地计算机管理来设置安全组，就像对你的域中的 Windows 电脑那样。 该安全组的任何成员均可输入其凭据并解锁设置。
  
> [!NOTE]
> 如果你的 Microsoft Teams 会议室设备失去与域的信任关系（例如，如果在 Microsoft Teams 会议室加入域后将其从域中移除），你将无法通过身份验证进入设备并打开“设置”。 解决方法是使用本地管理员帐户登录。 
  
## <a name="local-accounts"></a>本地帐户

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft 团队聊天室本地用户帐户

该设备帐户通常不使用密码。 可以为其给定密码，但会有一些后果，包括密码过期后用户可能被锁在该控制台应用程序之外。 因此，管理员应确保不允许密码过期。
  
### <a name="admin---local-administrator-account"></a>“Admin”- 本地管理员帐户

Microsoft 团队会议室默认密码设置为 "sfb"。 通过转到 Windows 设置，可在本地更改密码 \> 。转到 windows 或 AutoUnattend.xml 文件（使用 ADK 的 Windows 系统映像管理器对 xml 文件进行更改）。
  
> [!CAUTION]
> 请务必尽快更改 Microsoft 团队聊天室密码。 
  
还可以通过设置组策略（其中域管理员设为本地管理员）来管理本地管理员密码。
  
本地管理员密码不是安装过程中的一个选项。
  
### <a name="machine-account"></a>计算机帐户

与任何 Windows 设备很相似，可通过右键单击 " \> 重命名 PC" 的设置来重命名计算机名称 \> 。
  
 如果您想要在将计算机加入到域之后重命名该计算机，请使用 "重命名计算机 PowerShell" 命令，后跟计算机的新名称。
  
## <a name="related-topics"></a>相关主题

[规划 Microsoft 团队聊天室](rooms-plan.md)

[Microsoft Teams 会议室要求](requirements.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)

[Microsoft Store for Business 和教育版的先决条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
