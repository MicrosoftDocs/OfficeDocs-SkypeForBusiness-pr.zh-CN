---
title: 创建网络区域链接
TOCTitle: 创建网络区域链接
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413047(v=OCS.15)
ms:contentKeyID: 49314788
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建网络区域链接

 

_**上一次修改主题：** 2012-10-19_

网络内的区域通过物理 WAN 连接进行链接。*网络区域链接* 在为呼叫允许控制 (CAC) 配置的两个区域之间创建链接，并为这两个区域之间的音频和视频流量设置带宽限制。

有关使用网络区域链接的详细信息，请参阅 Lync Server 命令行管理程序文档中以下 cmdlet 的相关内容：

  - [New-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegionLink)

  - [Remove-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegionLink)

示例拓扑具有一条 North America 和 APAC 区域之间的链接，以及一条 EMEA 和 APAC 区域之间的链接。每条区域链接都受 WAN 带宽的限制，如规划文档的[示例：在 Lync Server 2013 中收集呼叫允许控制要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)一节中的“区域链接带宽信息”表所述。

## 使用 Lync Server 命令行管理程序创建网络区域链接

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 New-CsNetworkRegionLink cmdlet 创建区域链接并应用相应的带宽策略配置文件。例如，运行：
    
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link

       &nbsp;
    
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link

## 使用 Lync Server 控制面板创建网络区域链接

1.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“网络配置”。

3.  单击“区域链接”导航按钮。

4.  单击“新建”。

5.  在“新建区域链接”页上，单击“名称”，然后键入网络区域链接的名称。

6.  单击“网络区域 \#1”，然后在列表中单击要链接到“网络区域 \#2”的网络区域。

7.  单击“网络区域 \#2”，然后在列表中单击要链接到“网络区域 \#1”的网络区域。

8.  也可以选择单击“带宽策略”，然后选择要应用于网络区域链接的带宽策略配置文件。
    
    > [!NOTE]  
    > 仅在网络区域链接受带宽限制，并且您希望使用 CAC 控制该链接上的媒体流量时，应用带宽策略。
    


9.  单击“提交”。

10. 要为拓扑完成网络区域链接的创建，请使用其他区域的设置重复步骤 4 至 9。

