---
title: Lync Server 2013：创建或修改网络站点
TOCTitle: 创建或修改网络站点
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398218(v=OCS.15)
ms:contentKeyID: 49312089
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建或修改网络站点

 

_**上一次修改主题：** 2013-02-24_

呼叫允许控制 (CAC)、E9-1-1 和媒体旁路部署均依赖于在网络区域中定义且始终与网络区域关联的 *网络站点* 的配置。一个网络站点代表一个分支机构位置、一组建筑或一所高校。多个网络站点代表具有类似带宽的子网的集合。

使用以下过程创建或修改网络站点。例如，如果已为一个语音功能创建网络站点，则不需要创建新的网络站点；其他语音功能也将使用这些站点。但是，可能需要修改现有的网络站点定义来应用特定于功能的设置。例如，如果已为 E9-1-1 创建网络站点，则需要在部署呼叫允许控制的过程中修改该网络站点，以便应用带宽策略配置文件。

> [!NOTE]  
> 如果存在，您可以找到网站站点的特定示例和要求，因为它们与每个功能的部署文档中的高级语音功能相关：
<ul>
<li><p><a href="lync-server-2013-configure-network-sites-for-cac.md">在 Lync Server 2013 中为 CAC 配置网络站点</a></p></li>
</ul>



有关使用网络站点的详细信息，请参阅 Lync Server 命令行管理程序文档中以下 cmdlet 的相关内容：

  - [New-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSite)

  - [Get-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSite)

  - [Set-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkSite)

  - [Remove-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkSite)

## 创建网络站点

创建可由呼叫允许控制、E9-1-1 或媒体旁路使用的网络区域。

## 使用命令行管理程序创建网络站点

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 New-CsNetworkSite cmdlet 创建网络站点：
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    例如：
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    在此示例中，您创建了一个称为“Chicago”的网络站点，该站点位于“NorthAmerica”网络区域。
    
    > [!NOTE]  
    > 为了成功运行此命令，NorthAmerica 网络区域必须已经存在。
    


3.  要为拓扑完成网络站点的创建，请使用其他站点的设置重复步骤 2。

## 使用 Lync Server 控制面板创建网络站点

1.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“网络配置”。

3.  单击“站点”导航按钮。

4.  单击“新建”。

5.  在“新建站点”页上，单击“名称”，然后键入网络站点的名称。

6.  单击“区域”，然后单击列表中的某个区域。

7.  或者，单击“带宽策略”，然后单击列表中的某个带宽策略。
    
    > [!NOTE]  
    > 只有在站点上部署呼叫允许控制时才需要带宽策略。
    


8.  或者，单击“位置策略”，然后单击列表中的某个位置策略。
    
    > [!NOTE]  
    > 只有在站点上部署 E9-1-1 时才需要位置策略。
    


9.  或者，单击“说明”，然后键入其他信息以描述此网络站点。

10. 单击“提交”。

11. 要为拓扑完成网络站点的创建，请使用其他站点的设置重复步骤 4 至 10。

## 修改网络站点

修改可由呼叫允许控制、E9-1-1 或媒体旁路使用的网络区域。

## 修改网络站点

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 Set-CsNetworkSite cmdlet 修改网络站点：
    
        Set-CsNetworkSite -Identity <string>
    
    例如：
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    在此示例中，称为“Albuquerque”的站点将移动到“NorthAmerica”网络区域。要修改网络站点配置以部署呼叫允许控制、E9-1-1 或媒体旁路，请分别运行带有 BWPolicyProfileID 参数或 LocationPolicy 参数的 Set-CsNetworkSite cmdlet 来修改网络站点设置。
    
    > [!NOTE]  
    > 尽管存在用于媒体旁路的 BypassID 参数，但强烈建议您不要覆盖自动生成的旁路 ID。您无需指定其他参数来为媒体旁路配置网络站点。
    


3.  要为拓扑完成网络站点的修改，请使用其他站点的设置重复步骤 2。

## 使用 Lync Server 控制面板修改网络站点

1.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“网络配置”。

3.  单击“站点”导航按钮。

4.  在表中，单击要修改的网络站点。

5.  单击“编辑”，然后单击“显示详细信息...”。

6.  在“编辑站点”页上，根据需要更改此网络站点的设置的值。

7.  单击“提交”。

8.  要完成网络站点的修改，请使用其他站点的设置重复步骤 4 至 7。

