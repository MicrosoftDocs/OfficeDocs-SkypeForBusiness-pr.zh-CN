---
title: 'Lync Server 2013: 安装中介服务器的文件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60274ced1bf72a17b4c05b4908f60bde32323f12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>在 Lync Server 2013 中安装中介服务器的文件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-08-06_

要成功完成此过程，应至少以本地管理员身份和至少在 RTCUniversalReadOnlyAdmins 组中具有成员身份的域用户身份登录服务器。

使用本主题中的步骤运行 Lync Server 2013 部署向导, 以便在你使用拓扑生成器定义和发布池时, 在你添加到中介服务器池中的计算机上安装中介服务器的文件。 在安装 "中介服务器" 时, 你还可以在中介服务器池中安装和分配每台计算机所需的证书。

在此网站上, 如果你已在前端池或标准版服务器上部署了中介服务器 collocated, 则可以跳过本主题, 而[在 Lync server 2013 中继续配置中继](lync-server-2013-configuring-trunks.md)。

<div>


> [!NOTE]  
> 本主题假定你已经定义并发布了独立的中介服务器池, 如在<A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Lync server 2013 中的拓扑生成器中定义中介服务器</A>和在部署中<A href="lync-server-2013-publish-the-topology.md">发布 Lync server 2013 中的拓扑</A>中所述。文档, 并且已验证中介服务器池中的计算机满足<A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Lync server 2013 中的 "企业语音软件先决条件</A>" 中所述的先决条件, 以及 "<A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">安全和配置先决条件"Lync Server 2013 中的企业语音</A>。



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>为独立的中介服务器池安装文件

1.  在安装媒体中\<, 右键单击 "安装媒体\>**\\设置\\amd64\\**setup.exe", 然后单击 "**以管理员身份运行**"。

2.  在“安装位置”**** 页上，单击“确定”****。

3.  在“最终用户许可协议”**** 页上，单击“我接受”****，然后单击“确定”****。（必须单击该按钮才能继续。）

4.  在 " **Lync server 2010 部署向导**" 页面上, 单击 "**安装或更新 Lync Server 系统**"。

5.  单击“步骤 1: 安装本地配置存储”**** 旁边的“运行”****，然后按照屏幕上的说明进行操作。

6.  在“配置中央管理存储的本地副本”**** 页上，接受默认的“直接从中央管理存储检索”****，然后单击“下一步”****。

7.  在“正在执行命令”**** 页上，当任务状态显示为“已完成”**** 时，单击“完成”****。

8.  在 "**步骤 2: 设置" 或 "删除 Lync 服务器组件**" 旁边, 单击 "**运行**", 然后单击 "**下一步**"。

9.  在“正在执行命令”**** 页上，当任务状态显示为“已完成”**** 时，单击“完成”****。

10. 单击“步骤 3: 请求、安装或分配证书”**** 旁边的“运行”****。按照屏幕上的说明进行操作，接受默认设置。中介服务器需要一个证书，因此要运行“步骤 3”**** 两次：第一次是颁发所需证书，第二次是分配该证书。

11. 正确颁发并分配证书后，在“步骤 4: 启动服务”**** 旁边，单击“运行”****，然后按照屏幕上的说明进行操作。

12. 成功完成“步骤 4”**** 后，重新启动服务器，然后以 DomainAdmins 组的成员身份登录到服务器。

13. 在运行 Lync Server "控制面板" 的计算机上, 验证中介服务器的服务状态是否显示为绿色复选标记的 "Lync Server 控制面板" 的 "**拓扑**" 页面。 如果显示红色 X，请选择相应的中介服务器。 在“操作”**** 菜单上，单击“启动所有服务”****。

如果向中介服务器池添加了多台计算机, 请在中介服务器池中的所有其他计算机上执行此过程中的步骤。 如果不需要为任何其他计算机安装中介服务器的文件, 请按照在[Lync server 2013 中配置中继中](lync-server-2013-configuring-trunks.md)的过程配置此中介服务器池 (或所有中介) 之间的中继连接设置。站点上的服务器) 及其对等。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

