---
title: 'Lync Server 2013: Lync Server 混合环境概述'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0420e4aaded9f5ae90d26c4cbdc176e7fb4c6bb5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Lync Server 2013 混合环境概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-05-28_

Lync Server 2013 混合环境指的是一个部署, 其中有一些用户驻留在本地 Lync Server 2013 和其他托管到 Lync Online 的用户, 但用户共享相同的域, 如 user@contoso.com。

<div>

## <a name="about-this-guide"></a>关于本指南

本指南介绍了配置 Lync Server 2013 环境以实现与 Lync Online 的互操作性所必需的任务, 然后将用户从本地部署移动到使用 Lync Online。

</div>

<div>

## <a name="prerequisites"></a>先决条件

您需要安装下列应用程序和实用程序才能完成配置混合部署的任务。 这些文件的安装程序包括在为你的部署提供的安装媒体以及下表中包含的链接中。

  - [Active Directory 联合身份验证服务 (AD FS) 2。0](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Microsoft 目录同步工具9。1](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [安装 Windows PowerShell 以通过 AD FS 进行单一登录](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - Microsoft Online Services 登录助手 (msoidcli-7.0) 包含在 Office 365 的桌面设置中, 可从 Office 365 管理门户中链接到的下载页面获取。

</div>

<div>

## <a name="administrator-credentials"></a>管理员凭据

当系统要求你提供管理员凭据时, 请使用适用于你的 Office 365 租户的管理员帐户的用户名和密码。 将 Active Directory 联合身份验证服务 (AD FS) 2.0、目录同步、单一登录、联盟以及将用户移动到 Lync Online 时, 你也将使用这些凭据。

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>连接到 Lync Online PowerShell

管理员现在能够使用 Windows PowerShell 管理 Lync Online 及其 Lync Online 用户帐户。 若要执行此操作, 必须首先从 Microsoft 下载中心下载并安装 Lync Online Connector 模块 (http://go.microsoft.com/fwlink/?LinkId=294688)。 有关下载、安装和使用 Lync Online 连接器模块的详细信息, 以及有关使用 Windows PowerShell 管理 Lync Online 的详细信息, 请参阅[使用 Windows powershell 管理 Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

