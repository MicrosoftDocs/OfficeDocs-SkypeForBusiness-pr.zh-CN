---
title: Lync Server 2013：将子网与网络站点相关联
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f54ba8be2be6ae042633e519c5d7d27bde834162
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a>在 Lync Server 2013 中将子网与网络站点相关联

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-19_

你的网络中的每个子网都必须与特定的网络站点相关联，因为子网信息用于确定在启动新会话时终结点所在的网络站点。 当会话中每个方的位置已知时，高级企业语音功能可以应用该信息来确定如何处理呼叫设置或路由。

<div>


> [!IMPORTANT]  
> 必须将部署中音频/视频边缘服务器的所有已配置公用 IP 地址添加到网络配置设置中。 这些 IP 地址是作为掩码为 32 的子网进行添加的。 关联的网络站点应与相应的已配置网络站点相对应。 例如，与中央站点芝加哥的 A/V 边缘服务器对应的公共 IP 地址将为 NetworkSiteID 芝加哥。 有关公共 IP 地址的详细信息，请参阅在规划文档中<A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</A>。



</div>

<div>


> [!NOTE]  
> 生成关键运行状况指示器 (KHI) 警报，指定存在于网络中但不与子网关联的 IP 地址列表，或指定包含 IP 地址的子网不与网络站点相关联。该警报在 8 小时内只产生一次。相关的警报信息和示例如下所示：<BR><STRONG>来源：</STRONG>CS 带宽策略服务（核心）<BR><STRONG>事件号码：</STRONG> 36034<BR><STRONG>级别：</STRONG> 2<BR><STRONG>说明：</STRONG>以下 IP 地址的子网： &lt;IP 地址&gt;列表未配置或子网未与网络站点关联。<BR><STRONG>原因：</STRONG>网络配置设置中缺少对应 IP 地址的子网，或者子网未与网络站点关联。<BR><STRONG>解决方案：</STRONG>将对应于 IP 地址列表的子网添加到网络配置设置中，并将每个子网关联到网络站点。<BR>例如，如果警报中的 IP 地址列表指定 10.121.248.226 和 10.121.249.20，则可能是这些 IP 地址没有与子网关联，或者与其关联的子网不属于网络站点。如果 10.121.248.0/24 和 10.121.249.0/24 是与这些地址对应的子网，则可按如下所示解决此问题： 
> <OL>
> <LI>
> <P>确保 IP 地址 10.121.248.226 与子网 10.121.248.0/24 相关联，IP 地址 10.121.249.20 与子网 10.121.249.0/24 相关联。</P>
> <LI>
> <P>确保子网 10.121.248.0/24 和 10.121.249.0/24 分别与一个网络站点相关联。</P></LI></OL>



</div>

有关使用网络子网的详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：

  - [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> 如果你正在使用大量子网，我们建议使用逗号分隔值（CSV）文件将子网与网站相关联。 CSV 文件必须具有以下四列： <STRONG>IPAddress</STRONG>、 <STRONG>mask</STRONG>、 <STRONG>description</STRONG>、 <STRONG>NetworkSiteID</STRONG>。



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a>使用命令行管理程序将子网与网络站点相关联

1.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

2.  运行 **New-CsNetworkSubnet** cmdlet 将子网与网络站点相关联：
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    例如：
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    在此示例中，创建了子网 172.11.12.13 与网络站点“Chicago”之间的关联。

3.  为拓扑中的所有子网重复步骤 2。

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>通过导入 CSV 文件将子网与网络站点关联

1.  创建包含要添加的所有子网的 CSV 文件。例如，创建名为 **subnet.csv** 并包含以下内容的文件：
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  运行以下 cmdlet 以导入**子网 .csv**，然后将其内容存储在 Lync Server 管理存储中：
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 将子网与网络站点相关联

1.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“网络配置”****。

3.  单击“子网”**** 导航按钮。

4.  单击“新建”****。

5.  在“新建子网”**** 页上，单击“子网 ID”****，然后键入由要与网络站点关联的子网定义的 IP 地址范围中的第一个地址。

6.  单击“掩码”****，然后键入要应用于子网的位掩码。

7.  单击“网络站点 ID”****，然后选择要向其中添加此子网的站点的站点 ID。
    
    <div>
    

    > [!NOTE]  
    > 如果尚未创建网络站点，该列表将为空。 有关此过程的详细信息，请参阅<A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync Server 2013 中创建或修改网络网站</A>。 还可以通过运行 <STRONG>Get-CsNetworkSite</STRONG> cmdlet 检索部署的站点 ID。 有关详细信息，请参阅 Lync Server Management Shell 文档。

    
    </div>

8.  （可选）单击“说明”****，然后键入其他信息来说明此子网。

9.  单击“**提交**”。

重复这些步骤以向网络站点中添加其他子网。

</div>

</div>

<span> </span>

</div>

</div>

</div>

