---
title: 先决条件
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d8f0ee6a50d40f938a9f2c6f731b0a4afa647ba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a>先决条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-19_

需要运行 Lync Server 2013 压力和性能工具的各种硬件、软件和系统配置要求。

<div>

## <a name="client-hardware-requirements"></a>客户端硬件要求

若要在 Lync Server 2013 部署中运行 Lync Server 2013 压力和性能工具，请针对要模拟其负载的每个4500用户，至少需要一台满足以下最低硬件要求的专用计算机：

  - 1个千兆网络适配器

  - 8 GB ram

  - 2个双核中央处理单元（Cpu）

</div>

<div>

## <a name="client-software-requirements"></a>客户端软件要求

若要在 Lync Server 2013 部署上运行 Lync Server 2013 压力和性能工具，受支持的操作系统为：

  - Windows Server 2012 操作系统

  - Windows Server 2008 操作系统（64-位版本）

您的客户端计算机必须满足以下软件要求：

  - 您必须已安装[Microsoft .Net Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212)运行时。

  - 在 Windows Server 2008/Windows Server 2012 中，必须启用 "桌面体验" 功能。

  - 您必须已安装[Microsoft Visual c + + 2012 可再发行组件包](https://go.microsoft.com/fwlink/?linkid=143216)（x64）。

  - 完全配置的 Lync Server 2013 部署。

<div>


> [!IMPORTANT]  
> Microsoft 统一通信托管 API （UCMA）4.0 库包含在安装包中，因此 UCMA 不是必需的，也不应安装在客户端计算机上。



</div>

</div>

<div>

## <a name="configuration-requirements"></a>配置要求

将运行 Lync Server 2013 压力和性能工具的计算机必须按照以下要求进行配置：

1.  您必须以域或本地管理员组成员的身份登录。

2.  无法在同时运行 Lync Server 2013 组件的计算机上运行 lync Server 2013 压力和性能工具（LyncPerfTool.exe）。

3.  必须在前端服务器上或用户帐户将驻留的 Standard Edition 服务器上运行 Lync Server 2013 用户创建工具（UserProvisioningTool.exe）。 当该工具运行多次时，为 Microsoft 统一通信启用的每个用户都必须具有唯一的电话号码。

4.  页面文件大小应由系统管理，或者应至少为系统上的 RAM 量的1.5 倍。

</div>

</div>

<span> </span>

</div>

</div>

</div>

