---
title: Lync Server 2013： Lync Server 混合环境概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b39c94b08da65e546fdf3ad01d42ada636ff371d
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Lync Server 2013 混合环境概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-28_

Lync Server 2013 混合环境指的是部署中有一些用户驻留在本地 Lync Server 2013 中，其他用户驻留在 Lync Online 中，但用户共享相同的域，如 user@contoso.com。

<div>

## <a name="about-this-guide"></a>关于本指南

本指南介绍了配置 Lync Server 2013 环境以实现与 Lync Online 的互操作性所需的任务，然后将用户从本地部署迁移到使用 Lync Online。

</div>

<div>

## <a name="prerequisites"></a>先决条件

您需要安装以下应用程序和实用程序，才能完成配置混合部署的任务。 这些文件的安装程序位于针对您的部署提供的安装介质上，以及下表提供的链接中。

  - [Active Directory 联合身份验证服务 (AD FS) 2.0](https://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Microsoft Directory 同步工具9。1](https://go.microsoft.com/fwlink/p/?linkid=257307)

  - [安装 Windows PowerShell 以使用 AD FS 进行单一登录](https://go.microsoft.com/fwlink/p/?linkid=398710)

  - Microsoft Online Services 登录助手（msoidcli-7.0）包含在 Office 365 的桌面安装程序中，可从 Microsoft 365 管理中心的链接到的下载页面获取。

</div>

<div>

## <a name="administrator-credentials"></a>管理员凭据

当系统询问您是否提供管理员凭据时，请使用 Office 365 组织的管理员帐户的用户名和密码。 在将 Active Directory 联合身份验证服务（AD FS）2.0、目录同步、单一登录、联合和移动用户配置为 Lync Online 时，也将使用这些凭据。

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>连接到 Lync Online PowerShell

管理员现在能够使用 Windows PowerShell 管理 Lync Online 及其 Lync Online 用户帐户。 若要执行此操作，必须首先从 Microsoft 下载中心（https://go.microsoft.com/fwlink/?LinkId=294688)）下载并安装 Lync Online 连接器模块。 有关下载、安装和使用 Lync Online 连接器模块的详细信息，以及有关使用 Windows PowerShell 管理 Lync Online 的详细信息，请参阅[Using Windows powershell to Manage Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

