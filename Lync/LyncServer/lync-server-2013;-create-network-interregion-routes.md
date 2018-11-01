---
title: 创建网络区域间路由
TOCTitle: 创建网络区域间路由
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398368(v=OCS.15)
ms:contentKeyID: 49312887
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建网络区域间路由

 

_**上一次修改主题：** 2012-10-20_

“网络区域间路由”定义一对网络区域之间的路由。呼叫允许控制部署中的每对网络区域均需要网络区域间路由。这样部署中的每个网络区域便能够访问任何其他区域。

虽然区域链接会对区域之间的连接设置带宽限制，但是区域间路由可确定连接从一个区域到另一个区域将遍历的链接路径。

有关使用网络区域间路由的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - [New-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

在示例拓扑中，必须为三个区域对中的每一对定义网络区域间路由：北美/EMEA、EMEA/APAC 以及北美/APAC。

## 使用 Lync Server 命令行管理程序创建网络区域间路由

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 **New-CsNetworkInterRegionRoute** cmdlet 来定义所需路由。例如，运行：
    
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"

       &nbsp;
    
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"

       &nbsp;
    
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
    
    > [!NOTE]
    > 北美/APAC 的网络区域间路由需要两个网络区域链接，因为它们之间没有直接网络区域链接。


## 使用 Lync Server 控制面板创建网络区域间路由

1.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“网络配置”。

3.  单击“区域路由”导航按钮。

4.  单击“新建”。

5.  在“新建区域路由”页上，单击“名称”，然后键入网络区域间路由的名称。

6.  单击“网络区域 \#1”，然后在列表中单击要路由到网络区域 \#2 的网络区域。

7.  单击“网络区域 \#2”，然后在列表中单击要路由到网络区域 \#1 的网络区域。

8.  单击“网络区域链接”字段旁边的“添加”，然后添加将用于网络区域间路由的网络区域链接。
    
    > [!NOTE]
    > 如果要为彼此之间没有直接网络区域链接的两个网络区域创建路由，则必须添加所有必要的链接来完成路由。例如，北美/APAC 网络区域间路由需要两个网络区域链接，因为它们之间没有直接网络区域链接。


9.  单击“提交”。

10. 要为拓扑完成网络区域间路由的创建，请为其他网络区域间路由重复步骤 4 至 步骤 9 的设置。

