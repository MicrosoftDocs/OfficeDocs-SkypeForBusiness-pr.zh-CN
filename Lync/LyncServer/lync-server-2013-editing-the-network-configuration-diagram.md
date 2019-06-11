---
title: 'Lync Server 2013: 编辑网络配置图表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2772cad1d1a16aa0363b1ab50d0bcaadacb91a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>在 Lync Server 2013 中编辑网络配置图

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-21_

设计器在 Lync Server 2013 中所执行的大部分工作都包含为网络图上的条目定义 IP 地址和完全限定域名 (Fqdn) 的条目。 在此页面上输入的信息将传递到 "规划工具" 中包含的报表和其他信息中。

![规划工具网络图](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "规划工具网络图")

规划工具使用 IP 地址和 Fqdn 的默认文本创建网络图。

编辑网络图和输入值：

1.  选择起始网络段。例如，双击文本 **access1.contoso.com**。在打开的对话框中，键入服务器 access1.contoso.com 的实际 FQDN，并输入实际的 IP 地址以替换 131.107.155.3。

2.  单击“**确定**”以保存条目。

3.  继续编辑 IP 地址和 FQDN，从而为硬件负载平衡器提供虚拟 IP 地址或者为池中服务器的域名系统 (DNS) 负载平衡提供服务器条目。

规划工具的一个有用功能是可以递增地分配一系列 IP 地址和服务器主机名称，而不是要求设计师编辑池中的单台服务器。例如：

1.  双击池化的前端服务器。对话框打开后，选中“**是否要将这些 IP 地址和 FQDN 用作此群集中所有对等服务器的起点？**”。

2.  例如，第一台服务器的起始值是 fe0101.contoso.com，IP 地址是 192.168.21.122。

3.  在“**前端服务器 FQDN**”中键入 **fe0.contoso.com**，在“**前端服务器 IP 地址**”中键入 **192.168.21.131**，然后单击“**确定**”。

4.  自动增量功能会将池中的所有服务器更新为 fe01 到 fe06，将所有 IP 地址更新为 192.168.21.131 到 192.168.21.136。

完成所有编辑后，执行以下步骤以保存拓扑：

若要保存规划工具设计, 请单击 "**文件**", 然后单击 "**保存拓扑**" 或 "**将拓扑另存为**"。 如果出现“**将规划工具另存为**”对话框，请在“**文件名**”中键入文件的名称，然后单击“**保存**”。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中编辑设计](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

