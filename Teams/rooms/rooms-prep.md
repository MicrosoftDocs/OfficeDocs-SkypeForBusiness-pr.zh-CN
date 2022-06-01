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
description: 了解如何为部署Microsoft Teams 会议室准备基础结构，以便可以利用所有功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0bedb70ade23f92424a14e4bea3f1462fc2cbccf
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823051"
---
# <a name="prepare-your-environment"></a>准备环境

本部分概述了准备环境所需的步骤，以便可以使用Microsoft Teams 会议室的所有功能。
  
1. 为每个Microsoft Teams 会议室控制台准备一个资源帐户。 有关详细信息，请参阅[“部署Microsoft Teams 会议室](rooms-deploy.md)”。
    
2. 确保有运行良好的网络/Internet 连接可供设备使用。
  
3. 为了改进你的体验，Microsoft 将收集数据。 若要允许 Microsoft 收集数据，请允许以下网站：

   - 遥测客户端终结点： `https://vortex.data.microsoft.com/`
   - 遥测设置终结点：` https://settings.data.microsoft.com/`
    
### <a name="create-and-test-a-resource-account"></a>创建和测试资源帐户

*资源帐户* 是Microsoft Teams 会议室客户端用来从Exchange访问功能（如日历）和连接到Microsoft Teams的帐户。 有关详细信息，请参阅[“部署Microsoft Teams 会议室](rooms-deploy.md)”。
  
### <a name="check-network-availability"></a>检查网络可用性

若要正常运行，Microsoft Teams 会议室必须有权访问满足以下要求的有线网络：
  
- 访问 Active Directory 或 Azure Active Directory (Azure AD) 实例，以及 Microsoft Exchange 和Microsoft Teams。

- 可访问能够使用 DHCP 提供 IP 地址的服务器。 Microsoft Teams 会议室无法在第一个单元启动时使用静态 IP 地址进行配置。

- 访问 HTTP 端口 80 和 443。

- 根据本地Skype for Business Server实现的[服务器的端口和协议要求](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)中所述配置的 TCP 和 UDP 端口，或者[为Microsoft Teams Microsoft 365和Office 365 URL 和 IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)。

如果你的网络通过代理运行，则还需要提供代理地址或脚本信息。
    
> [!IMPORTANT]
> Microsoft Teams 会议室不支持代理身份验证，因为它可能会干扰会议室的常规操作。 在投入生产之前，请确保Microsoft Teams 会议室已免除代理身份验证。

> [!IMPORTANT]
> 务必使用 1 Gbps 的有线网络连接来确保获得所需带宽。

> [!NOTE]
> Microsoft Teams 会议室的软件更新会自动从适用于企业的 Microsoft Store下载。 请参阅[适用于企业的 Microsoft Store和教育的先决条件](/microsoft-store/prerequisites-microsoft-store-for-business)，验证会议室控制台是否能够访问商店和自我更新。
  
### <a name="certificates"></a>证书

Microsoft Teams 会议室设备使用证书Exchange Web 服务、Microsoft Teams或Skype for Business、网络使用情况和身份验证。 如果相关服务器使用公共证书（这是联机和某些本地部署的情况），则管理员不应采取进一步操作来安装证书。 另一方面，如果证书颁发机构是专用 CA，则设备需要信任该 CA。 这意味着在设备上安装 CA + CA 链证书。 将设备添加到域时，可以自动执行此任务。
  
安装证书的方式与任何其他 Windows 客户端一样。

> [!IMPORTANT]
> 如果代理服务器使用内部签名的证书，则必须在Microsoft Teams 会议室设备上安装内部证书链（包括根 CA）。
  
> [!NOTE]
> 可能需要证书才能Microsoft Teams 会议室使用Skype for Business Server。
  
### <a name="proxy"></a>代理

Microsoft Teams 会议室旨在从Windows OS 继承代理设置。 通过以下方式访问 Windows OS：
  
1. 在Microsoft Teams 会议室 UI 中，单击设置齿轮图标，系统会提示你在设备上输入本地管理员密码， (默认密码为 **sfb**) 。
2. 点击 **设置**，然后点击 **“转到Windows**”按钮，然后点击 **“转到管理员登录**”按钮，然后单击 **“管理员**”按钮 (如果计算机已加入域，请选择 **“其他用户”，** 然后使用 .\admin 作为用户名) 。
3. 在 **“搜索Windows** 框的左下方键入 regedit (长按屏幕或右键单击并选择 **”以管理员身份运行**) 。
4. 单击 HKEY_USERS 文件夹（你将看到计算机用户 SID 列表），确保选择根文件夹 HKEY_USERS。
       
5. 单击“文件”，然后选择 **“加载 Hive”。**
6. 浏览到 **C：\Users\Skype** 文件夹，并在“文件名”框 NTUSER.dat 中键入并按打开按钮

7. 系统会提示你为新加载的 Hive 输入密钥名称;键入Skype (现在应会看到Skype用户) 的注册表设置。
 
8. 打开Skype键并浏览到HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings然后确保输入以下设置： 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    如果 ProxyServer 不存在，你可能必须以字符串形式添加此注册表项，将 xx.xx.xx.xx:8080 更改为你的代理服务器的 IP/主机和端口。
 
    如果客户使用的是 PAC 文件，则配置类似于以下示例：

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. 完成更改后，请突出显示 Skype 用户注册表项（Skype 的根文件夹），并从“注册表文件”菜单中选择“卸载配置单元”（系统将提示你确认 - 请选择 **是**）。
    
10. 现在可以关闭注册表编辑器并在 Windows 搜索框中键入“注销”。
    
11. 返回登录屏幕，选择 **Skype** 用户。 如果上述所有步骤都成功，则Microsoft Teams 会议室设备将成功登录。
    
有关Microsoft Teams 会议室所需的 FQDN、端口和 IP 地址范围的完整详细信息，请参阅[“网络安全](./security.md#network-security)”一文。
  
### <a name="admin-group-management"></a>管理员组管理

如果选择加入域 (Azure Active Directory或 Active Directory) ，则可以使用Microsoft Endpoint Manager、组策略或本地计算机管理将安全组设置为本地管理员，就像在域中Windows电脑一样。 该安全组的任何成员均可输入其凭据并解锁设置。
  
> [!NOTE]
> 如果你的 Microsoft Teams 会议室设备失去与域的信任关系（例如，如果在 Microsoft Teams 会议室加入域后将其从域中移除），你将无法通过身份验证进入设备并打开“设置”。 解决方法是使用本地管理员帐户登录。 
  
## <a name="local-accounts"></a>本地帐户

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft Teams 会议室本地用户帐户

Teams 会议室包含名为“Skype”的无密码本地帐户。 此帐户用于登录Windows以启动Teams 会议室应用。 不支持将密码应用到此帐户。 有关详细信息，请参阅[Microsoft Teams 会议室安全](security.md)性。
  
### <a name="admin---local-administrator-account"></a>“Admin”- 本地管理员帐户

Microsoft Teams 会议室默认密码设置为“sfb”。 密码可以通过管理员模式或AutoUnattend.xml文件在本地更改， (使用 ADK 中的Windows系统映像管理器对 xml 文件) 进行更改。
  
> [!CAUTION]
> 请务必尽快更改Microsoft Teams 会议室密码。 
  
本地管理员密码不是安装过程中的一个选项。

可以在Microsoft Teams 会议室安全性文章中阅读有关[管理员](security.md)帐户的详细信息。
  
### <a name="machine-account"></a>计算机帐户

与任何Windows设备一样，可以通过右键单击 **设置** \> **“关于** \> **重命名电脑”来** 重命名计算机名称。
  
如果要在将计算机加入域后重命名计算机，请使用 [Rename-Computer](/powershell/module/microsoft.powershell.management/rename-computer)（PowerShell 命令），后跟计算机的新名称。
  
## <a name="related-topics"></a>相关主题

[规划Microsoft Teams 会议室](rooms-plan.md)

[Microsoft Teams 会议室要求](requirements.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)

[适用于企业的 Microsoft Store和教育的先决条件](/microsoft-store/prerequisites-microsoft-store-for-business)
