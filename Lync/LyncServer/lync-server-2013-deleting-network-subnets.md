---
title: 删除网络子网
TOCTitle: 删除网络子网
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49888591
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除网络子网

 

_**上一次修改主题：** 2013-02-21_

您可以使用以下过程删除子网。从 Lync Server 控制面板中，可以创建、修改或删除网络子网。有关创建或修改网络子网的详细信息，请参阅[创建或修改网络子网](lync-server-2013-create-or-modify-network-subnets.md)。

在大多数实现呼叫允许控制 (CAC) 的 Microsoft Lync Server 2013 部署中，通常都将有大量子网。因此，最好在 Lync Server 命令行管理程序中配置子网。在其中，可以一起调用 **New-CsNetworkSubnet** 和 Windows PowerShell cmdlet **Import-CSV**。通过将这些 cmdlet 配合使用，可以从逗号分隔值 (.csv) 文件读入子网设置，并且同时创建多个子网。有关如何从 .csv 文件创建子网的示例，请参阅 [New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet)。

## 删除网络子网

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“子网”。

4.  在“子网”页上，单击要删除的子网。
    
    > [!NOTE]  
    > 您可以一次删除多个子网。为执行此操作，请按住 CTRL 键，同时选择多个子网。或者，要选择所有子网，请单击“编辑”菜单上的“全选”。
    


5.  在“编辑”菜单中，单击“删除”。

6.  单击“确定”。

## 另请参阅

#### 任务

[创建或修改网络子网](lync-server-2013-create-or-modify-network-subnets.md)

