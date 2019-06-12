---
title: 先决条件
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74603ed20fe144ca89d3ac13bc00fef0e7d6ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a>先决条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-19_

需要运行 Lync Server 2013 应力和性能工具的各种硬件、软件和系统配置要求。

<div>

## <a name="client-hardware-requirements"></a>客户端硬件要求

若要在 Lync Server 2013 部署上运行 Lync Server 2013 应力和性能工具, 对于要模拟其负载的每个4500用户, 您至少需要一台专用计算机, 满足以下最低硬件要求:

  - 1 GB 的网络适配器

  - 8 GB ram

  - 2个双核中央处理单元 (Cpu)

</div>

<div>

## <a name="client-software-requirements"></a>客户端软件要求

若要在 Lync Server 2013 部署上运行 Lync Server 2013 应力和性能工具, 受支持的操作系统包括:

  - Windows Server 2012 操作系统

  - Windows Server 2008 操作系统 (64 位版)

客户端计算机必须满足以下软件要求:

  - 必须安装[Microsoft .Net Framework 4.5](http://go.microsoft.com/fwlink/?linkid=143212)运行时。

  - 在 Windows Server 2008/Windows Server 2012 上, 必须启用 "桌面体验" 功能。

  - 必须已安装[Microsoft Visual c + + 2012 可再发行程序包](http://go.microsoft.com/fwlink/?linkid=143216)(x64)。

  - 已完全配置的 Lync Server 2013 部署。

<div>


> [!IMPORTANT]  
> Microsoft 统一通信托管 API (UCMA) 4.0 库包含在安装包中, 因此 UCMA 不是必需的, 也不应在客户端计算机上安装。



</div>

</div>

<div>

## <a name="configuration-requirements"></a>配置要求

将运行 Lync Server 2013 应力和性能工具的计算机必须按照以下要求进行配置:

1.  您必须以 "域" 或 "本地管理员" 组的成员身份登录。

2.  Lync Server 2013 应力和性能工具 (LyncPerfTool) 无法在同时运行 Lync Server 2013 组件的计算机上运行。

3.  必须在前端服务器或用户帐户所驻留的标准版服务器上运行 Lync Server 2013 用户创建工具 (UserProvisioningTool)。 当该工具运行多次时, 已启用 Microsoft 统一通信的每个用户都必须具有唯一的电话号码。

4.  页面文件大小应由系统管理, 或者在系统上的 RAM 数量至少应为1.5 倍。

</div>

</div>

<span> </span>

</div>

</div>

</div>

