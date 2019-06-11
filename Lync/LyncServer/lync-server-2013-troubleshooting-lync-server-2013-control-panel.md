---
title: 'Lync Server 2013: Lync Server 2013 的疑难解答控制面板'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 943f2ab5f0fe808d1bf5e10cf8b451ac1df2575b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a>Lync Server 2013 控制面板疑难解答

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2016-07-28_

本主题提供的信息和过程可帮助你对 Lync Server 2013 控制面板的访问进行故障排除。

<div>

## <a name="internet-browser-requirements"></a>Internet 浏览器要求

Lync Server 控制面板要求安装 Microsoft Silverlight 浏览器插件版本4.0.50524.0 或最新版本。 如果未安装 Silverlight 或者安装了早期版本, 请按照消息中的说明安装所需的版本。

<div>


> [!NOTE]  
> Lync Server 控制面板的其他软件要求与 Lync Server 控制面板和所有其他 Lync Server 2013 管理工具可在其上安装的操作系统相关。 有关详细信息, 请参阅支持文档中的<A href="lync-server-2013-server-and-tools-operating-system-support.md">Lync server 2013 中的 "服务器和工具" 操作系统支持</A>。



</div>

如果由于安全考虑, 您的 Internet 浏览器阻止 Silverlight 安装, 请将打开 Lync Server 控制面板的统一资源定位器 (URL) 添加到受信任的网站列表中。 在 Internet Explorer 安全设置中, 确保 "**运行 ActiveX 控件和插件**" 设置为 "**已启用**"。 有关详细信息, [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060)请参阅。 此外, 请确保浏览器配置为使用 SSL 3.0。

如果 Internet 浏览器配置为使用代理服务器, 请验证是否已将浏览器配置为将自动检测为内部网站的网站跳过代理服务器。 或者, 在代理服务器的 "配置" 设置中将地址添加到浏览器的异常列表中。

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>管理访问 URL 的 DNS 记录和证书要求

如果你配置了一个简单的 URL 来访问 Lync Server 控制面板, 请确保你还配置了使用该管理访问 URL 所需的静态域名系统 (DNS) 主机 (A) 资源记录和证书。 如果你随时更改基本 URL, 请确保更改将反映在相应的 DNS 记录和证书中, 并且你在每个 Director 和前端服务器上运行*Enable-CsComputer*以注册更改。 有关详细信息, 请参阅规划文档中的以下主题:

  - [在 Lync Server 2013 中规划简单 URL](lync-server-2013-planning-for-simple-urls.md)

  - [Lync Server 2013 中简单 URL 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Lync Server 2013 中内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)

有关配置管理访问 URL 的分步过程, 请参阅在部署文档中的[Lync Server 2013 中编辑或配置简单 url](lync-server-2013-edit-or-configure-simple-urls.md) 。

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Internet Information Services (IIS) 要求

Lync Server 控制面板是需要 Internet Information Services (IIS) 的 Lync Server 2013 组件之一。 尤其是, 请确保 HTTP 重定向和 Windows 身份验证功能已启用, 并且万维网发布服务 (W3SVC) 正在运行。

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>World Wide 发布服务 (Windows 服务) 依赖关系

当万维网发布服务停止时, 您不能访问 Lync Server "控制面板"。 你可以使用 Windows 服务 Microsoft 管理控制台 (MMC) 重新启动服务。

**启动万维网发布服务**

1.  登录到作为 Internet 信息服务 (IIS) 的一部分安装万维网发布服务的计算机。

2.  单击 "**开始**", 单击 "**管理工具**", 然后单击 "**服务**"。

3.  右键单击 "**万维网发布服务**", 然后单击 "**开始**"。

</div>

<div>

## <a name="application-pool-mode"></a>应用程序池模式

配置 IIS, 以便 CsManagementAppPool 应用程序池使用网络服务帐户作为其进程模型标识。

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>用户权利和权限

您必须登录 Lync Server 控制面板, 方法是使用 CsAdministrator 组成员的域帐户, 或使用已委派了用户权利和权限的帐户。 您无法使用本地计算机帐户登录到 Lync Server "控制面板"。 有关通过基于角色的访问控制 (RBAC) 委派管理任务的详细信息, 请参阅规划文档中[Lync Server 2013 中的 "规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md)"。

如果你使用简单的 URL 访问 Lync Server 控制面板, 请确保将 web 服务器添加到 RTCUniversalServerAdmins 和 RTCUniversalUserAdmins 组。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 管理工具](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

