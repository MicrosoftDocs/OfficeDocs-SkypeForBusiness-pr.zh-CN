---
title: 创建或修改网络子网
TOCTitle: 创建或修改网络子网
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520957(v=OCS.15)
ms:contentKeyID: 49312161
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建或修改网络子网

 

_**上一次修改主题：** 2013-02-21_

网络子网必须与一个网络站点关联，以便确定属于此子网的主机的地理位置。您可以使用 Lync Server 控制面板配置子网。在 Lync Server 控制面板中，可以创建、修改或删除网络子网。有关删除网络子网的详细信息，请参阅[删除网络子网](lync-server-2013-deleting-network-subnets.md)

在大多数实现呼叫允许控制 (CAC) 的 Microsoft Lync Server 2013 部署中，通常都将有大量子网。因此，最好在 Lync Server 命令行管理程序中配置子网。在其中，可以一起调用 **New-CsNetworkSubnet** 和 Windows PowerShell cmdlet **Import-CSV**。通过将这些 cmdlet 配合使用，可以从逗号分隔值 (.csv) 文件读入子网设置，并且同时创建多个子网。有关如何从 .csv 文件创建子网的示例，请参阅 [New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet)。

## 创建网络子网

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“子网”。

4.  在“子网”页上，单击“新建”。

5.  在“新建子网”的“子网 ID”字段中输入值。该值必须是一个 IP 地址（例如 174.11.12.0），并且必须是子网所定义的 IP 地址范围中的第一个地址。

6.  在“掩码”字段中，输入一个 1 到 32 之间的数值。
    
    > [!NOTE]  
    > 该值是要应用于正在创建的子网的位掩码。
    


7.  在“网络站点 ID”中，选择该子网归属的站点。

8.  （可选）在“说明”字段中键入值，用以提供仅通过名称无法表达的更多有关该子网的信息。

9.  单击“提交”。

## 修改网络子网

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“子网”。

4.  在“子网”页上，单击要修改的子网。

5.  在“编辑”菜单上，单击“显示详细信息”。

6.  在“编辑子网”页上，可以修改位掩码、关联的网络站点或说明。如果要修改位掩码，请牢记子网 ID 必须仍为子网所定义的 IP 地址范围中的第一个地址。

7.  单击“提交”。

## 另请参阅

#### 任务

[删除网络子网](lync-server-2013-deleting-network-subnets.md)  

#### 概念

[关于 Lync Server 2013 中的网络区域、站点和子网](lync-server-2013-about-network-regions-sites-and-subnets.md)  

#### 其他资源

[New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet)  
[Set-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkSubnet)  
[Remove-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSubnet)

