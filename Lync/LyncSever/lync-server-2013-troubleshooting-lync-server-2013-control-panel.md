---
title: Lync Server 2013 控制面板疑难解答
TOCTitle: Lync Server 2013 控制面板疑难解答
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg195689(v=OCS.15)
ms:contentKeyID: 49312876
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 控制面板疑难解答

 

_**上一次修改主题：** 2016-12-08_

本主题提供的信息和过程可帮助您解决访问 Lync Server 2013 控制面板的问题。

## Internet 浏览器要求

Lync Server 控制面板需要安装 Microsoft Silverlight 浏览器插件 4.0.50524.0 版或更新版本。如果未安装 Silverlight 或者安装了早期版本，请按照消息中的说明进行操作来安装所需的版本。

> [!NOTE]  
> 与可在其上安装 Lync Server 控制面板和所有其他 Lync Server 控制面板管理工具的操作系统有关的 Lync Server 2013的其他软件要求。有关详细信息，请参阅可支持性文档中的<a href="lync-server-2013-server-and-tools-operating-system-support.md">Lync Server 2013 中的服务器和工具操作系统支持</a>。


如果 Internet 浏览器因安全注意事项而阻止安装 Silverlight，请将打开 Lync Server 控制面板的统一资源定位器 (URL) 添加到受信任网站的列表。在 Internet Explorer 安全设置中，确保“运行 ActiveX 控件和插件”设置为“已启用”。有关详细信息，请参阅 [http://go.microsoft.com/fwlink/?linkid=214060\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=214060%26clcid=0x804)。此外，请确保浏览器配置为使用 SSL 3.0。

如果 Internet 浏览器配置为使用代理浏览器，请验证浏览器是否配置为绕过自动检测为内部站点的代理服务器。或者，将地址添加到代理服务器配置设置中的浏览器例外列表中。

## 管理访问 URL 的 DNS 记录和证书要求

如果配置了简单 URL 来访问 Lync Server 控制面板，请确保还配置了使用该管理访问 URL 所必需的静态域名系统 (DNS) 主机 (A) 资源记录和证书。如果在任何时候更改基 URL，请确保该更改反映到相应的 DNS 记录和证书中，并确保对每个控制器和前端服务器运行 *Enable-CsComputer* 来注册该更改。有关详细信息，请参阅规划文档中的以下主题：

  - [在 Lync Server 2013 中规划简单 URL](lync-server-2013-planning-for-simple-urls.md)

  - [Lync Server 2013 中简单 URL 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Lync Server 2013 中内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)

有关配置管理访问 URL 的分步过程，请参阅部署文档中的[在 Lync Server 2013 中编辑或配置简单 URL](lync-server-2013-edit-or-configure-simple-urls.md)。

> [!NOTE]  
> 如果 Web 服务器上有多个网络适配器，则必须为每个额外的网络适配器手动配置 DNS 以便 DNS 解析正常运行。


## Internet Information Services (IIS) 要求

Lync Server 控制面板是需要 Internet Information Services (IIS) 的 Lync Server 2013 的组件之一。特别是要确保启用了 HTTP 重定向和 Windows 身份验证功能，并确保 World Wide Web 发布服务 (W3SVC) 正在运行。

## World Wide Web 发布服务（Windows 服务）依赖关系

World Wide Web 发布服务停止时，无法访问 Lync Server 控制面板。可以使用 Windows 服务 Microsoft 管理控制台 (MMC) 重新启动该服务。

**启动 World Wide Web 发布服务**

1.  登录到其中 World Wide Web 发布服务是作为 Internet Information Services (IIS) 的一部分安装的计算机。

2.  依次单击“开始”、“管理工具”，然后单击“服务”。

3.  右键单击“World Wide Web 发布服务”，然后单击“启动”。

## 应用程序池模式

配置 IIS 以便 CsManagementAppPool 应用程序池将 Network Service 帐户用作其进程模型标识。

## 用户权限

必须使用具有 CsAdministrator 组成员身份的域帐户或使用已为其委派用户权限的帐户登录到 Lync Server 控制面板。不能使用本地计算机帐户登录到 Lync Server 控制面板。有关通过基于角色的访问控制 (RBAC) 委派管理任务的详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md)。

如果使用简单 URL 访问 Lync Server 控制面板，请确保将 Web 服务器添加到 RTCUniversalServerAdmins 和 RTCUniversalUserAdmins 组。

## 另请参阅

#### 概念

[Lync Server 2013 管理工具](lync-server-2013-lync-server-administrative-tools.md)

