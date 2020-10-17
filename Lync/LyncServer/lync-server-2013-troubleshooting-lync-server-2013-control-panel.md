---
title: Lync Server 2013： Lync Server 2013 控制面板故障排除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7da23bc56d18b1b5e6235551f7b99cc15e658fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535929"
---
# <a name="troubleshooting-lync-server-2013-control-panel"></a>Lync Server 2013 控制面板疑难解答

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-07-28_

本主题提供的信息和过程可帮助您对 Lync Server 2013 控制面板的访问进行故障排除。

<div>

## <a name="internet-browser-requirements"></a>Internet 浏览器要求

Lync Server 控制面板要求安装 Microsoft Silverlight 浏览器插件版本4.0.50524.0 或最新版本。 如果未安装 Silverlight 或者安装了早期版本，请按照邮件中的说明安装所需的版本。

<div>


> [!NOTE]  
> Lync Server 控制面板的其他软件要求适用于可安装 Lync Server 控制面板和所有其他 Lync Server 2013 管理工具的操作系统。 有关详细信息，请参阅可支持性文档中的 <A href="lync-server-2013-server-and-tools-operating-system-support.md">Lync server 2013 中的服务器和工具操作系统支持</A> 。



</div>

如果你的 Internet 浏览器由于安全考虑阻止安装 Silverlight，请将统一资源定位器 (URL) 添加到受信任的网站列表中，将其打开 "Lync Server 控制面板"。 在 Internet Explorer 安全设置中，确保“运行 ActiveX 控件和插件”**** 设置为“已启用”****。 有关详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060) 。 此外，请确保浏览器配置为使用 SSL 3.0。

如果 Internet 浏览器配置为使用代理浏览器，请验证浏览器是否配置为绕过自动检测为内部站点的代理服务器。或者，将地址添加到代理服务器配置设置中的浏览器例外列表中。

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>管理访问 URL 的 DNS 记录和证书要求

如果您配置了一个简单的 URL 来访问 Lync Server 控制面板，请确保还将静态域名系统 (DNS) 主机 () 资源记录和使用该管理访问 URL 所需的证书。 如果你随时更改基 URL，请确保更改将反映在相应的 DNS 记录和证书中，并且在每个控制器和前端服务器上运行 *CsComputer* 以注册更改。 有关详细信息，请参阅规划文档中的以下主题：

  - [在 Lync Server 2013 中规划简单 Url](lync-server-2013-planning-for-simple-urls.md)

  - [Lync Server 2013 中简单 Url 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Lync Server 2013 中的内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)

有关配置管理访问 URL 的分步过程，请参阅部署文档中的在 [Lync Server 2013 中编辑或配置简单 url](lync-server-2013-edit-or-configure-simple-urls.md) 。

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Internet Information Services (IIS) 要求

Lync Server 控制面板是需要 Internet 信息服务 (IIS) 的 Lync Server 2013 组件之一。 特别是要确保启用了 HTTP 重定向和 Windows 身份验证功能，并确保 World Wide Web 发布服务 (W3SVC) 正在运行。

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>World Wide Web 发布服务（Windows 服务）依赖关系

如果停止万维网发布服务，则无法访问 Lync Server 控制面板。 可以使用 Windows 服务 Microsoft 管理控制台 (MMC) 重新启动该服务。

**启动 World Wide Web 发布服务**

1.  登录到将万维网发布服务作为 Internet 信息服务 (IIS) 的一部分安装到的计算机上。

2.  依次单击“开始”****、“管理工具”****，然后单击“服务”****。

3.  右键单击“World Wide Web 发布服务”****，然后单击“启动”****。

</div>

<div>

## <a name="application-pool-mode"></a>应用程序池模式

配置 IIS 以便 CsManagementAppPool 应用程序池将 Network Service 帐户用作其进程模型标识。

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>用户权限

您必须使用作为 CsAdministrator 组成员的域帐户或使用已向其委派用户权限的帐户登录 Lync Server 控制面板。 无法使用本地计算机帐户登录 Lync Server 控制面板。 有关通过基于角色的访问控制 (RBAC) 委派管理任务的详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md) 。

如果使用简单 URL 访问 Lync Server 控制面板，请确保将 web 服务器添加到 RTCUniversalServerAdmins 和 RTCUniversalUserAdmins 组。

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

