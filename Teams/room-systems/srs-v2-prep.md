---
title: 准备您的环境
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection: M365-voice
description: 本文介绍部署 Microsoft 团队聊天室的基础结构准备。
ms.openlocfilehash: 43c55e094fed4e5e1bca923b863c1cac1f4d894a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33916355"
---
# <a name="prepare-your-environment"></a>准备环境

本节包含概述准备您的环境，以便您可以使用的所有 Microsoft 团队聊天室的功能所需的步骤。
  
1. 为每个 Microsoft 团队聊天室控制台准备设备帐户。 有关详细信息，请参阅[部署 Microsoft 团队 Rooms](room-systems-v2.md) 。
    
2. 确保有运行良好的网络/Internet 连接可供设备使用。 
    
   - 它必须是能够接收使用 DHCP 的 IP 地址。 （Microsoft 团队聊天室不能配置使用静态 IP 地址在第一个单元启动时，但在设备上或上游开关或传送器之后无法配置设备的静态 IP。）
    
   - 它必须具有这些端口 （除了打开媒体的普通端口） 打开：
    
   - HTTPS：443
    
   - HTTP：80
    
   - 如果你的网络通过代理运行，则还需要提供代理地址或脚本信息。
    
     > [!NOTE]
     > Microsoft Teams 会议室不支持 HDCP 输入，已发现它会导致 HDMI 采集功能（视频、音频）出现问题。 请确保连接到 Microsoft Teams 会议室的交换机禁用了 HDCP 选项。 
  
3. 为了改进你的体验，Microsoft 将收集数据。 为了收集数据，我们需要将以下网站列入允许名单：
    
   - 遥测客户端终结点：https://vortex.data.microsoft.com/
    
   - 遥测设置终结点：https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>创建和测试设备帐户

*设备的帐户*是 Microsoft 团队聊天室客户端使用 exchange，访问功能，如日历，以及启用 for Business 的 Skype 的帐户。 有关详细信息，请参阅[部署 Microsoft 团队 Rooms](room-systems-v2.md) 。
  
### <a name="check-network-availability"></a>检查网络可用性

才能正常工作，Microsoft 团队聊天室设备必须有权访问有线网络满足这些要求：
  
- 可访问 Active Directory 或 Azure Active Directory (Azure AD) 实例以及 Microsoft Exchange 和 Skype for Business 服务器。
- 可访问能够使用 DHCP 提供 IP 地址的服务器。 无法使用静态 IP 地址配置 Microsoft 团队聊天室。
- 访问 HTTP 端口 80 和 443。
- TCP 和 UDP 端口配置为中所述[的服务器的端口和协议要求](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)的内部 Skype 对于业务服务器实现，或[Office 365 Url 和 IP 地址范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)的 Microsoft 团队或 for Business 的 Skype 联机实现。

> [!IMPORTANT]
> 务必使用 1 Gbps 的有线网络连接来确保获得所需带宽。
  
### <a name="certificates"></a>证书

您的 Microsoft 团队聊天室设备使用证书的 Exchange Web 服务、 Microsoft 团队或 Skype 业务、 网络使用情况和身份验证。 如果相关服务器使用公用证书（联机部署和部分本地部署便属于这种情况），则无需在管理部分执行任何进一步操作来安装证书。 另一方面，如果证书颁发机构为私有 CA（通常用于本地部署），则设备需要信任该 CA，这意味着在设备中安装了 CA + CA 链证书。 将设备添加到域时，可以自动执行此任务。
  
安装证书的方式与任何其他 Windows 客户端一样。 
  
> [!NOTE]
> 让业务服务器使用 Skype 的 Microsoft 团队聊天室，可能需要证书。
  
### <a name="proxy"></a>代理

Microsoft 团队聊天室旨在继承 Windows 操作系统的代理设置。 通过以下方式访问 Windows OS：
  
1. 在 Microsoft 团队聊天室 UI 中，单击设置齿轮图标，其中将提示您的设备 （默认密码为**sfb**） 上的本地管理员密码。
2. 在**设置**点击**转到 Windows**按钮，然后点击**转到管理登录**按钮，然后单击**管理员**按钮后跟点击 （如果计算机已加入域选择**其他用户，** 然后使用。 \admin 作为用户名)。
3. 在**搜索 Windows**框在注册表编辑器中的底部左侧的类型 （是长按屏幕或右键单击并选择**以管理员身份运行**）。
4. 单击 HKEY_USERS 文件夹（你将看到计算机用户 SID 列表），确保选择根文件夹 HKEY_USERS。
       
5. 单击文件，然后选择**加载配置单元。**
6. 浏览到**C:\Users\Skype**文件夹，然后键入文件名称框 NTUSER.dat 和按打开按钮

7. 系统将提示您为您的新加载配置单元; 键名称键入的 Skype （您会看到 Skype 用户的注册表设置）。
 
8. 打开 Skype 注册表项并浏览到 HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet 设置，然后确保输入这些设置： 
    
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    
    "MigrateProxy"=dword:00000001
    
    "ProxyEnable"=dword:00000001
    
    "ProxyServer"="xx.xx.xx.xx:8080"
    
    如果 ProxyServer 不存在，你可能必须以字符串形式添加此注册表项，将 xx.xx.xx.xx:8080 更改为你的代理服务器的 IP/主机和端口。
    
9. 完成更改突出显示 Skype 用户主要 （根文件夹 Skype），并且选择卸载配置单元，从注册表文件菜单 （将提示您确认-选择**是**） 后。
    
10. 现在可以关闭注册表编辑器并在 Windows 搜索框中键入“注销”。
    
11. 返回登录屏幕，选择 **Skype** 用户。 如果上述所有步骤都是成功，Microsoft 团队聊天室设备将登录成功。
    
要使用此应用程序，你必须能够连接至下面所述的终结点。要查看 IP 地址，请展开描述通信流的表下面的 IP 地址部分。
  
**防火墙代理主机名/端口示例**

|用途|源或凭据|源端口|目标|CDN|ExpressRoute for Office 365|目标 IP|目标端口|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|身份验证与标识  <br/> |请参阅[Office 365 身份验证和标识](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|门户与共享  <br/> |请参阅[Office 365 门户和共享](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|SIP 信号  <br/> |客户端计算机或已登录用户  <br/> |临时端口  <br/> |\*。 contoso.com  <br/> |否  <br/> |是  <br/> |[业务 IP 范围的的 Skype](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|持久型共享对象模型 (PSOM) 连接 Web 会议  <br/> |客户端计算机或已登录用户  <br/> |临时端口  <br/> |\*。 contoso.com  <br/> |否  <br/> |是  <br/> |[业务 IP 范围的的 Skype](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|HTTPS 下载  <br/> |客户端计算机或已登录用户  <br/> |临时端口  <br/> |\*。 contoso.com  <br/> |否  <br/> |是  <br/> |[业务 IP 范围的的 Skype](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|音频  <br/> |客户端计算机或已登录用户  <br/> |TCP/UDP 50,000-50019  <br/> |\*。 contoso.com  <br/> |否  <br/> |是  <br/> |[业务 IP 范围的的 Skype](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、UDP 3478、TCP/UDP 50,000-59,999  <br/> |
|视频  <br/> |客户端计算机或已登录用户  <br/> |TCP/UDP 50,020-50039  <br/> |\*。 contoso.com  <br/> |否  <br/> |是  <br/> |[业务 IP 范围的的 Skype](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、UDP 3478、TCP/UDP 50,000-59,999  <br/> |
|桌面共享  <br/> |客户端计算机或已登录用户  <br/> |TCP/UDP 50,040-50059  <br/> |\*。 contoso.com  <br/> |否  <br/> |是  <br/> |[业务 IP 范围的的 Skype](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443，50,000-59,999  <br/> |
|用于 iOS 设备中的 Lync Mobile 2010 的 Lync Mobile 推送通知 Android、Nokia Symbian 或 Windows Phone 移动设备不需要此功能。  <br/> |客户端计算机或已登录用户  <br/> |临时端口  <br/> |\*。 contoso.com  <br/> |否  <br/> |是  <br/> |[业务 IP 范围的的 Skype](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Skype Telemetry  <br/> |客户端计算机或已登录用户  <br/> |临时端口  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |否  <br/> |否  <br/> |不适用  <br/> |TCP 443  <br/> |
|Skype 客户端快速提示  <br/> |客户端计算机或已登录用户  <br/> |临时端口  <br/> |quicktips.skypeforbusiness.com  <br/> |否  <br/> |否  <br/> |不适用  <br/> |TCP 443  <br/> |
   
> [!NOTE]
> 用于 contoso.com 和 broadcast.skype.com 的通配符表示供 Office 365 独占使用的长节点列表。 
  
### <a name="create-provisioning-packages"></a>创建设置包

您将使用设置包对 Exchange Server 或 Office 365 进行身份验证。
  
### <a name="admin-group-management"></a>管理员组管理

加入域后，可以本地管理员身份使用组策略或本地计算机管理来设置安全组，就像对你的域中的 Windows 电脑那样。 该安全组的任何成员均可输入其凭据并解锁设置。
  
> [!NOTE]
> 如果你的 Microsoft Teams 会议室设备失去与域的信任关系（例如，如果在 Microsoft Teams 会议室加入域后将其从域中移除），你将无法通过身份验证进入设备并打开“设置”。 解决方法是使用本地管理员帐户登录。 
  
## <a name="local-accounts"></a>本地帐户

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft 团队聊天室本地用户帐户

该设备帐户通常不使用密码。 可以为其给定密码，但会有一些后果，包括密码过期后用户可能被锁在该控制台应用程序之外。 因此，管理员应确保不允许密码过期。
  
### <a name="admin---local-administrator-account"></a>“Admin”- 本地管理员帐户

Microsoft 团队聊天室的默认密码设置为"sfb"。 可以转到 Windows 设置本地更改密码\>转到 Windows 或 AutoUnattend.xml 文件 （使用从 ADK 到 xml 文件中进行更改的 Windows 系统映像管理器） 中。
  
> [!CAUTION]
> 请务必尽快更改的 Microsoft 团队聊天室密码。 
  
还可以通过设置组策略（其中域管理员设为本地管理员）来管理本地管理员密码。
  
本地管理员密码不是安装过程中的一个选项。
  
### <a name="machine-account"></a>计算机帐户

得多任何 Windows 设备，如计算机名称可以重命名通过设置中右键单击\>有关\>重命名 PC。
  
 如果您希望将计算机加入到域后重命名，使用计算机的新名称后跟重命名计算机 PowerShell 命令。
  
## <a name="see-also"></a>另请参阅

[规划 Microsoft 团队聊天室](skype-room-systems-v2-0.md)

[Microsoft 团队聊天室要求](requirements.md)
  
[部署 Microsoft 团队聊天室](room-systems-v2.md)
  
[配置 Microsoft 团队聊天室控制台](console.md)
  
[管理 Microsoft Teams 会议室](skype-room-systems-v2.md)
