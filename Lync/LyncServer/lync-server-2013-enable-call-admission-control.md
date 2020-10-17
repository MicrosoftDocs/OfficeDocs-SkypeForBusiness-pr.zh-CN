---
title: Lync Server 2013：启用呼叫允许控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e129e109a62006d72b8b1db44c28effa8911e6c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528759"
---
# <a name="enable-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中启用呼叫允许控制

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

配置完呼叫允许控制部署的网络设置后，必须启用 CAC 来使带宽策略生效。

有关详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - [CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a>使用命令行管理程序启用呼叫允许控制

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行 Set-CsNetworkConfiguration cmdlet 以在网络中启用 CAC。例如，运行：
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    如果要在网络中禁用 CAC，请运行以下命令：
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板启用呼叫允许控制

1.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

2.  在左侧导航栏中，单击“网络配置”****。

3.  单击“全局”**** 导航按钮。

4.  单击列表中的“全局”****，然后在“编辑”**** 菜单中选择“显示详细信息”****。

5.  在“编辑全局设置”**** 页上，选中“启用呼叫允许控制”**** 复选框。
    
    <div>
    

    > [!NOTE]  
    > 如果要在整个部署中禁用呼叫允许控制，请清除此复选框。

    
    </div>

6.  单击“提交”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

