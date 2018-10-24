---
title: Lync Server 2013：创建或修改网络区域
TOCTitle: 创建或修改网络区域
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412933(v=OCS.15)
ms:contentKeyID: 49314110
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建或修改网络区域

 

_**上一次修改主题：** 2012-10-19_

*网络区域* 是在呼叫允许控制、E9-1-1 和媒体旁路的配置中使用的网络中心或网络中枢。使用以下过程创建或修改网络区域。例如，如果已为一个语音功能创建网络区域，则不需要创建新的网络区域；其他高级企业语音功能也将使用这些网络区域。但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，然后部署呼叫允许控制，则需要修改网络区域定义，以指定中央站点。有关详细信息，请参阅 [为 CAC 配置网络区域](lync-server-2013-configure-network-regions-for-cac.md)。

> [!NOTE]  
> 有关网络区域定义的任何特定于功能的要求均编档在相应功能的部署主题中。



有关使用网络区域的详细信息，请参阅 Lync Server 命令行管理程序文档中以下 cmdlet 的相关内容：

  - [New-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegion)

## 创建网络区域

创建可由呼叫允许控制、E9-1-1 或媒体旁路使用的网络区域。

## 使用 Lync Server 命令行管理程序创建网络区域

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 New-CsNetworkRegion cmdlet 创建网络区域：
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    例如：
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    在此示例中，您创建了一个称为“NorthAmerica”的网络区域，此区域与站点 ID 为 CHICAGO 的中央站点相关联。

3.  要为拓扑完成网络区域的创建，请使用每个网络区域的设置重复步骤 2。

## 使用 Lync Server 控制面板 创建网络区域

1.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“网络配置”。

3.  单击“区域”。

4.  单击“新建”。

5.  在“新建区域”页上，单击“名称”，然后键入网络区域的名称。

6.  单击“中央站点”，然后单击列表中的某个中央站点。

7.  或者，单击“说明”，然后键入其他信息以描述此网络站点。

8.  单击“提交”。

9.  要为拓扑完成网络区域的创建，请使用其他区域的设置重复步骤 4 至 8。

## 修改网络区域

修改现有网络区域的设置，以实现对基本区域信息的更改或者新功能所需的更改。

## 使用 Lync Server 命令行管理程序修改网络区域

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 Set-CsNetworkRegion cmdlet 修改现有网络区域：
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    例如：
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    在此示例中，您通过更改说明修改了称为“NorthAmerica”的现有网络区域（在本主题前面的过程中创建）。如果“NorthAmerica”区域已存在说明，此命令将使用该值覆盖它；如果尚未设置说明，此命令会进行设置。

3.  要修改其他网络区域，请使用其他区域的设置重复步骤 2。

## 使用 Lync Server 控制面板 修改网络区域

1.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“网络配置”。

3.  单击“区域”导航按钮。

4.  在表中，单击要修改的网络区域。

5.  单击“编辑”，然后单击“显示详细信息...”。

6.  在“编辑区域”页上，根据需要更改此网络区域的设置的值。

7.  单击“提交”。

8.  要完成网络区域的修改，请使用其他区域的设置重复步骤 4 至 7。

