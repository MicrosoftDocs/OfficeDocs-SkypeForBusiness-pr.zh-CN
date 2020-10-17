---
title: Lync Server 2013：编辑网络配置图
description: Lync Server 2013：编辑网络配置图。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ead2b0b47ec0cb0a98c33d7fff0a644f05f92c71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570588"
---
# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>在 Lync Server 2013 中编辑网络配置图

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

在 Lync Server 2013 中，规划器在 Lync Server 中执行的大部分工作由 "网络图" 上条目的 IP 地址和完全限定域名的条目定义 (Fqdn) 组成。 在此页上输入的信息将包含在规划工具中的报告和其他信息中。

![规划工具网络图](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "规划工具网络图")

规划工具将创建一个网络图，其中包含 IP 地址和 Fqdn 的默认文本。

编辑网络图和输入值：

1.  选择起始网络段。 例如，双击文本 " **access1.contoso.com**"。 在打开的对话框中，键入服务器 access1.contoso.com 的实际 FQDN 和实际 IP 地址，并替换131.107.155.3。

2.  单击 **“确定”** 以保存条目。

3.  继续编辑 IP 地址和 FQDN，从而为硬件负载平衡器提供虚拟 IP 地址或者为池中服务器的域名系统 (DNS) 负载平衡提供服务器条目。

规划工具的一个有用功能是可以递增地分配一系列 IP 地址和服务器主机名称，而不是要求设计师编辑池中的单台服务器。例如：

1.  双击池化的前端服务器。 对话框打开后，选中 **“是否要将 IP 和 FQDN 用作此群集中所有等效服务器的起始点?”**。

2.  例如，第一台服务器的起始值为 fe0101.contoso.com，IP 地址为192.168.21.122。

3.  在**前端服务器 FQDN**中键入**Fe0.contoso.com** ，在**前端服务器 IP 地址**中键入**192.168.21.131** ，然后单击 **"确定"**。

4.  自动递增功能将池中的所有服务器更新为 fe01 到 fe06，并将所有 IP 地址从192.168.21.131 更新为136。

完成所有编辑后，通过完成以下步骤来保存拓扑：

若要保存规划工具设计，请单击 " **文件**"，然后单击 " **保存拓扑** " 或 " **将拓扑另存为**"。 如果出现 **“将规划工具另存为”** 对话框，请在 **“文件名”** 中键入文件的名称，然后单击 **“保存”**。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中编辑设计](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

