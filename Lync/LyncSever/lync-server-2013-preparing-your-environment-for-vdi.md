---
title: Lync Server 2013：针对 VDI 准备环境
TOCTitle: 针对 VDI 准备环境
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205154(v=OCS.15)
ms:contentKeyID: 49313803
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 针对 VDI 准备 Lync Server 2013 环境

 

_**上一次修改主题：** 2013-02-22_

为了准备 Lync VDI 插件的环境，管理员必须执行以下步骤。

1.  在 Lync Server 2013 中，确保针对所有 VDI 用户将 EnableMediaRedirection 设置为 TRUE。有关详细信息，请参阅 [New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy) cmdlet 和 [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy) cmdlet 的帮助主题。

2.  在数据中心计算机上，在所有虚拟机上安装 Lync 2013 客户端。

3.  在本地计算机上，安装 Lync VDI 插件。

