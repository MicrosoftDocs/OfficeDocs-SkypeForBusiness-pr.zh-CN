---
title: Lync Server 2013：拓扑测试问题
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 254fb591acca4f58bf27b300d5ead3e615e026ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>Lync Server 2013 中的拓扑测试问题

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

与**enable-cstopology** cmdlet 类似，最佳实践分析工具提供了一种验证 Lync Server 2013 在全局级别正常运行的方法。 默认情况下，最佳实践分析工具（如 cmdlet）将检查整个 Lync Server 2013 基础结构，验证所需的服务是否正在运行，以及是否为这些服务以及通用用户权限设置了相应的用户权限和权限安装 Lync Server 2013 时创建的安全组。

除了验证 Lync Server 的整体有效性之外， **enable-cstopology**还会检查特定服务的有效性。 有关使用 cmdlet 测试特定服务的详细信息，请参阅 Lync Server 命令行管理程序文档中的[enable-cstopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) 。 使用以下信息可帮助解决您的拓扑问题。

<div>


> [!NOTE]  
> 最佳做法分析器可能无法访问和扫描您的边缘服务器，具体取决于您的边缘服务器的配置和任何相关外围网络设置（包括防火墙设置和权限）。如果将边缘服务器包含在扫描中并且报告指示访问边缘服务器时出现问题，请清除“边缘服务器”<STRONG></STRONG>复选框并重新运行扫描以防止报告中出现问题。



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>解决拓扑问题

如果拓扑测试发现您的拓扑有问题，那么这些问题可能由您在发布或启用拓扑时发生的问题导致。

对拓扑进行更改时，仅当发布和启用了这些更改，它们才会生效。 您必须使用拓扑生成器进行拓扑更改。 在进行更改后，您可以使用拓扑生成器发布和启用这些更改。

发布更改时，新的信息（例如，新网站或新的服务器角色）将被写入到中央管理存储。 但是，这些新（或最新修改的）对象不会立即加入您的拓扑。 仅当启用了已更新的拓扑，对象才会加入您的拓扑。 如果在拓扑生成器中选择 "发布" 选项，则会发生这两个步骤：发布更改（即，它们被写入到中央管理存储），然后启用新的拓扑。

默认情况下，RTCUniversalServerAdmins 组的成员有权运行 **Publish-CsTopology** cmdlet 和 **Enable-CsTopology** cmdlet。 但是，如果尚未委派安装权限，您必须以域管理员身份登录才能运行 **Publish-CsTopology**。 若要向 RTCUniversalServerAdmins 提供实际使用**enable-cstopology** cmdlet 的权限，您必须在每个包含运行 Lync Server 服务的计算机的 Active Directory 容器上运行**CsSetupPermission** cmdlet。 若要使 RTCUniversalServerAdmins 能够使用**enable-cstopology** cmdlet，您必须针对每个包含运行 Lync Server 服务的计算机的 Active Directory 域服务容器运行**CsSetupPermission** cmdlet。 请注意，这适用于使用拓扑生成器启用和发布拓扑。 如果您没有使用**CsSetupPermission**委派权限，则只有域管理员可以通过拓扑生成器启用和发布拓扑。

</div>

</div>

<span> </span>

</div>

</div>

</div>

