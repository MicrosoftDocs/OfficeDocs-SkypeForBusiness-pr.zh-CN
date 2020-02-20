---
title: Lync Server 2013：创建带宽策略配置文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 579bd9a2131a177fbece81bdbceec343e73edc89
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a>在 Lync Server 2013 中创建带宽策略配置文件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

**“带宽策略”定义对实时音频和视频内容的带宽使用量的限制。带宽策略应用于**“带宽策略配置文件”，后者可以应用于多个网络站点以进行呼叫允许控制。

有关应在 CAC 部署中设置的带宽限制的准则，请参阅规划文档中的在[Lync Server 2013 中定义呼叫允许控制的要求](lync-server-2013-defining-your-requirements-for-call-admission-control.md)。

有关使用带宽策略和策略配置文件的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - [新 CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

以下过程中创建的示例策略会为音频总流量、各个音频会话、视频总流量和各个视频会话设置限制。 例如，5Mb\_链路带宽策略配置文件将设置以下限制：

  - 音频限制：2,000 kbps

  - 音频会话限制：200 kbps

  - 视频限制：1,400 kbps

  - 视频会话限制：700 kbps

<div class=" ">


> [!NOTE]  
> 最小音频会话限制值为 40 kbps。最小视频会话限制值为 100 kbps。



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a>使用命令行管理程序创建带宽策略配置文件

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  对于要创建的每个带宽策略配置文件，请运行 New-CsNetworkBandwidthPolicyProfile cmdlet。例如，运行：
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板创建带宽策略配置文件

1.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

2.  在左侧导航栏中，单击“网络配置”****。

3.  单击“策略配置文件”**** 导航按钮。

4.  单击“新建”****。

5.  在“新建策略配置文件”**** 页上，单击“名称”****，然后键入带宽策略配置文件的名称。

6.  单击“音频限制”****，然后键入允许的所有音频会话组合的最大 kbps 数。

7.  单击“音频会话限制”****，然后键入允许的每个单独音频会话的最大 kbps 数。

8.  单击“视频限制”****，然后键入允许的所有视频会话组合的最大 kbps 数。

9.  单击“视频会话限制”****，然后键入允许的每个单独视频会话的最大 kbps 数。

10. （可选）单击“说明”****，然后键入其他信息来说明该带宽策略配置文件。

11. 单击“提交”****。

12. 要完成为拓扑创建带宽策略配置文件，请为其他带宽策略配置文件的设置重复步骤 4 至步骤 11。

</div>

</div>

<span> </span>

</div>

</div>

</div>

