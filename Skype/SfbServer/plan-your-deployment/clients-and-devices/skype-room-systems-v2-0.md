---
title: 规划 Skype 会议室系统 v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
description: 本文介绍部署 Skype 会议室系统 v2 下, 一代 Skype 会议室系统相关的规划的注意事项。
ms.openlocfilehash: 7b36e9bc9c85a57b81be542f09d65c357f6020c0
ms.sourcegitcommit: 5cc51e2d3898fccd1969accedb5e185a332e83bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="plan-for-skype-room-systems-v2"></a>规划 Skype 会议室系统 v2
 
本文介绍部署 Skype 会议室系统 v2 下, 一代 Skype 会议室系统相关的规划的注意事项。 
  
 Skype 会议室系统 v2 是 Microsoft 的最新设计用来转换为业务体验丰富的、 协作 Skype 您会议室的会议解决方案。 用户将获得熟悉的 Skype for Business 界面，IT 管理员将体验部署和管理都很轻松的 Windows 10 Skype 会议应用。 Skype 会议室系统 v2 旨在利用现有的设备，如 LCD 面板为了简化安装将 Skype for Business 导入您的会议室。
  
Skype 会议室系统 v2 使用充当 Skype 会议用户界面的专门 UWP 应用程序。 在控制台模式 Surface Pro 4 或 Surface Pro 上运行 （部署 UWP 应用程序之后是将在设备运行的唯一应用程序） 和业务实现需要在您 Skype 自己设备帐户。 它利用液晶显示屏以及相对便宜的外围摄像头和麦克风等现有设备来提供高品质的会议室体验。 软件通过 Windows 应用商店和 Windows 更新来更新。
  
准备您的环境之前，确保您具有必需的硬件和软件。 有关详细信息，请参阅[Skype 会议室系统 v2 要求](requirements.md)。 
  
> [!NOTE]
> Skype 会议室系统 v2 旨在用于与 Skype 业务服务器 2015年或 Skype 业务 online。 早期平台，如 Lync Server 2013 不会使用 Skype 会议室系统 v2。 
  

  
 **为 Skype for Business 而构建**
  
- 一键式加入 Skype 会议
    
- 为配有满屏高清视频和高清宽带音频的会议室优化的 Skype 会议体验
    
- 所有参与者均可使用所选设备从任意位置连接到 Skype 会议
    
- 从目录中（在此可立即看到用户的状态）或通过电话呼叫邀请用户
    
- 支持 Skype for Business PSTN 会议和 PSTN 呼叫，以替代会议室中的单独会议电话
    
 **转换任何会议室**
  
- 专用的 Skype 会议应用针对桌面中心触摸式控制器和会议室前方的大型显示屏进行了优化
    
- 重用会议室显示屏和投影仪的现有投资
    
- 适用于各种类型的会议室，从小型到大型会议室
    
- 经认证的 Skype for Business 音频和视频设备可用于各种规模的会议室
    
- 内置的有线采集可用于将桌面共享投影到会议室和 Skype 会议
    
- 在应用程序用户选择会议的会议室音频和视频 USB 设备和 #x 2776;
    
- （对于旧系统奇偶校验） 的双屏幕支持与 #x 2777;
    
- Themability （内置主题和能够设置自定义主题） 和 #x 2777;
    
 **易于部署、便于管理**
  
- 常开式设备会在检测到会议室中有人时自动唤醒显示屏
    
- UWP（通用 Windows 平台）Skype 会议应用的部署和更新都非常简单
    
- Windows AppLocker 可将设备锁定至 Skype 会议应用
    
- 通过 Intune 和 SCCM (MDM) 作为 Windows 10 企业版设备来监控和管理
    
- 企业级可靠性
    
- 由于最终用户很熟悉 Skype 用户界面，因此只需进行少量培训
    
- 在 Surface Pro 4 平板电脑上运行
    
- 集成会议室控制台状态报告的客户使用 Microsoft 操作管理套件 （请参阅[规划 Skype 会议室系统 v2 管理与 OMS](oms-management.md)） & #x 2776;
    
- 为公共生成 #x 2777; 能够提供反馈
    
- 改进了的遥测周围会议加入可靠性和 #x 2777;
    
- 其他 OMS 报告与 #x 2777;
    
- 面向 IT 管理员来远程配置设备和 #x 2777; 功能
    <!--  - Front-of-Room UX shows room details pre-meeting U2  -->
- Surface Pro 平板电脑和 #x 2778; 上运行
    
- 支持 Windows 10 企业创建者 （英语、 生成 1703年） 的更新和 #x 2778;
    
- 支持[Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system)停靠硬件和 #x 2778;
    
- 对环境控件 (Crestron) 和 #x 2778; OEM 支持
    
- [Polycom MSR](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)系列支持停靠硬件和 #x 2779;
    
- 对[Logitech Brio](https://www.logitech.com/en-us/product/brio)和 #x 2779; 支持

- 支持[联想集线器 500](https://www3.lenovo.com/us/en/hub500)停靠硬件和 #x277A;  
    
& #x 2776;-在更新 1 （软件 ver.中引入的功能 2.0.2.0)。
  
& #x 2777;-在更新 2 （软件 ver.中引入的功能 3.0.6.0)。 
  
& #x 2778;-更新 3 （软件 ver.中引入的功能 3.0.12.0)。 
  
& #x 2779;-更新 4 （软件 ver.中引入的功能 3.0.15.0)。 

& #x277A;-更新 5 （软件 ver.中引入的功能 3.1.98.0)。 
  
## <a name="preparing-your-skype-for-business-environment"></a>准备 Skype for Business 环境

本节包含概述准备您的环境，以便您可以使用的所有的 Skype 会议室系统 v2 功能所需的步骤。
  
1. 为每个 Skype 会议室系统 v2 控制台准备设备帐户。 有关详细信息，请参阅[部署 Skype 会议室系统 v2](../../deploy/deploy-clients/room-systems-v2.md) 。
    
2. 确保有运行良好的网络/Internet 连接可供设备使用。 
    
  - 它必须能够接收 IP 地址使用 DHCP (注意： Skype 会议室系统 v2 不能配置静态 IP 地址在第一个单元启动时使用)
    
  - 除了打开用于 Skype for Business 媒体的常规端口之外，还必须打开以下端口：
    
  - HTTPS：443
    
  - HTTP：80
    
  - 如果你的网络通过代理运行，则还需要提供代理地址或脚本信息。
    
    > [!NOTE]
    > V2 不支持 HDCP 输入，观察到与 HDMI 会导致问题的 Skype 会议室系统接收功能 （视频、 音频）。 注意确保交换机连接到 Skype 会议室系统 v2 已关闭的 HDCP 选项。 
  
3. 为了改进你的体验，Microsoft 将收集数据。为了收集数据，我们需要将以下网站列入允许名单：
    
  - 遥测客户端终结点：https://vortex.data.microsoft.com/
    
  - 遥测设置终结点：https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>创建和测试设备帐户

*设备的帐户*是 Skype 会议室系统 v2 客户端使用 exchange，访问功能，如日历，以及启用 for Business 的 Skype 的帐户。 有关详细信息，请参阅[部署 Skype 会议室系统 v2](../../deploy/deploy-clients/room-systems-v2.md) 。
  
### <a name="check-network-availability"></a>检查网络可用性

才能正常工作，Skype 会议室系统 v2 设备必须有权访问有线网络满足这些要求：
  
- 可访问 Active Directory 或 Azure Active Directory (Azure AD) 实例以及 Microsoft Exchange 和 Skype for Business 服务器。
    
- 可访问能够使用 DHCP 提供 IP 地址的服务器。 Skype 会议室系统 v2 不能配置使用静态 IP 地址。
    
- 访问 HTTP 端口 80 和 443。
    
- TCP 和 UDP 端口配置为内部 Skype 业务实施或[Office 365 Url 和 IP 地址范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)的 Skype 的业务联机实施的[Lync Server 2013 的端口要求](https://technet.microsoft.com/en-us/library/gg398798%28v=ocs.15%29.aspx)中所述。
    
> [!IMPORTANT]
> 务必使用 1 Gbps 的有线网络连接来确保获得所需带宽。 
  
### <a name="certificates"></a>证书

Skype 会议室系统 v2 设备使用证书的 Exchange Web 服务、 Skype 业务、 网络使用情况和身份验证。 如果相关服务器使用公用证书（联机部署和部分本地部署便属于这种情况），则无需在管理部分执行任何进一步操作来安装证书。 另一方面，如果证书颁发机构为私有 CA（通常用于本地部署），则设备需要信任该 CA，这意味着在设备中安装了 CA + CA 链证书。 将设备添加到域时，可以自动执行此任务。
  
安装证书的方式与任何其他 Windows 客户端一样。 
  
> [!NOTE]
> 让业务服务器使用 Skype 的 Skype 会议室系统 v2 可能需要证书。 
  
### <a name="proxy"></a>代理

Skype 会议室系统 v2 旨在继承 Windows 操作系统的代理设置。 通过以下方式访问 Windows OS：
  
1. 在 Skype 会议室系统 v2 UI 中，单击设置齿轮图标，其中将提示您 （默认密码为"sfb"） 的设备上的本地管理员密码。
    
2. 点击"设置"上的"转到 Windows"按钮，然后点击上打开后跟上"获得管理员登录到中"按钮，然后单击"管理员"按钮 (如果计算机加入域选择"其他用户"，然后使用。 \admin 作为用户名)。
    
3. 在"搜索 Windows"框在注册表编辑器 （长按屏幕或右单击，然后选择"以管理员身份运行"） 中的底部左侧的类型。
    
4. 单击 HKEY_USERS 文件夹（你将看到计算机用户 SID 列表），确保选择根文件夹 HKEY_USERS。
    
    系统将提示您为您的新加载配置单元; 键名称键入的 Skype （您会看到 Skype 用户的注册表设置）。
    
5. 单击“文件”，然后选择“加载配置单元”。
    
6. 浏览到文件夹“C:\Users\Skype”，在“文件名”框中键入 NTUSER.dat 并按“打开”按钮
    
7. 打开 Skype 注册表项并浏览到 HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet 设置，然后确保输入这些设置： 
    
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    
    "MigrateProxy"= dword:00000001
    
    "ProxyEnable"= dword:00000001
    
    "ProxyServer"="xx.xx.xx.xx:8080"
    
    如果 ProxyServer 不存在，你可能必须以字符串形式添加此注册表项，将 xx.xx.xx.xx:8080 更改为你的代理服务器的 IP/主机和端口。
    
8. 完成更改突出显示 Skype 用户主要 （根文件夹 Skype），并且选择卸载配置单元，从注册表文件菜单 （将提示您确认-选择**是**） 后。
    
9. 现在可以关闭注册表编辑器并在 Windows 搜索框中键入“注销”。
    
10. 返回登录屏幕，选择 **Skype** 用户。 如果上述所有步骤都是成功，Skype 会议室系统 v2 设备将登录成功。
    
要使用此应用程序，你必须能够连接至下面所述的终结点。要查看 IP 地址，请展开描述通信流的表下面的 IP 地址部分。
  
**防火墙代理主机名称/端口示例**

|**用途**|**源或凭据**|**源端口**|**目标**|**CDN**|**Office 365 的 ExpressRoute**|**目标 IP**|**目标端口**|
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

使用该设置包可在使用 Exchange Server 或 Skype for Business Server 时进行身份验证。
  
### <a name="admin-group-management"></a>管理员组管理

加入域后，可以本地管理员身份使用组策略或本地计算机管理来设置安全组，就像对你的域中的 Windows 电脑那样。 该安全组的任何成员均可输入其凭据并解锁设置。
  
> [!NOTE]
> 如果 Skype 会议室系统 v2 设备丢失与 （例如，如果您 Skype 会议室系统 v2 从域中删除后加入域） 域的信任，您将无法进行身份验证到设备，然后打开设置。 解决方法是使用本地管理员帐户登录。 
  
## <a name="local-accounts"></a>本地帐户

### <a name="skype-room-systems-local-user-account"></a>Skype 会议室系统本地用户帐户

该设备帐户通常不使用密码。 可以为其给定密码，但会有一些后果，包括密码过期后用户可能被锁在该控制台应用程序之外。 因此，管理员应确保不允许密码过期。
  
### <a name="admin---local-administrator-account"></a>“Admin”- 本地管理员帐户

Skype 会议室系统 v2 的默认密码设置为"sfb"。 可以转到 Windows 设置本地更改密码\>转到 Windows 或 AutoUnattend.xml 文件 （使用从 ADK 到 xml 文件中进行更改的 Windows 系统映像管理器） 中。
  
> [!CAUTION]
> 请务必尽快更改的 Skype 会议室系统 v2 密码。 
  
还可以通过设置组策略（其中域管理员设为本地管理员）来管理本地管理员密码。
  
本地管理员密码安装过程中不包括作为选项。
  
### <a name="machine-account"></a>计算机帐户

得多任何 Windows 设备，如计算机名称可以重命名通过设置中右键单击\>有关\>重命名 PC。
  
 如果您希望将计算机加入到域后重命名，使用计算机的新名称后跟重命名计算机 PowerShell 命令。
  
## <a name="see-also"></a>另请参阅

#### 

[Skype 会议室系统 v2 要求](requirements.md)
  
[部署 Skype 会议室系统 v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[配置 Skype 会议室系统 v2 控制台](../../deploy/deploy-clients/console.md)
  
[管理 Skype 会议室系统 v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

