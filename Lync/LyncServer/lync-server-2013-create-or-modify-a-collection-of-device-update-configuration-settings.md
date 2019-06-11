---
title: 创建或修改设备更新配置设置的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d5b53ff6e876a2c5226b6728e0ebde95d55e7ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改设备更新配置设置的集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

只能通过使用 Windows PowerShell 和**CsDeviceUpdateConfiguration** cmdlet 并使用**CsDeviceUpdateConfiguration** cmdlet 进行修改来创建设备更新配置设置 (仅限在网站范围内)。 这些 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。

<div>


> [!NOTE]
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a>创建使用默认值的设备更新配置设置

  - 此命令为 Redmond 网站创建一组新的设备更新配置设置:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    由于前面的命令中未指定强制标识参数之外的任何参数, 因此配置设置的新集合将对其所有属性使用默认值。

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a>在创建设备更新配置设置时更改单个属性值

  - 要创建使用不同属性值的设置，只需包含相应的参数和参数值。 例如, 若要创建设备更新配置设置的集合, 默认情况下, 每隔21天删除旧的日志文件, 请使用下面的一个命令:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a>创建设备更新配置设置时更改多个属性值

  - 可以通过包含多个参数来修改多个属性值。 例如, 此命令将日志清除间隔设置为21天, 日志刷新间隔设置为30分钟:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

有关修改现有设备配置设置的详细信息, 请参阅[CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15)) Cmdlet 的帮助主题。 有关创建配置设置集合的详细信息, 请参阅[CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15)) Cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

