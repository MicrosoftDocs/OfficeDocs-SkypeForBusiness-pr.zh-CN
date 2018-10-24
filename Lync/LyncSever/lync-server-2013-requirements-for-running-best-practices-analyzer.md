---
title: 运行最佳做法分析器的要求
TOCTitle: 运行最佳做法分析器的要求
ms:assetid: 3c7dc44e-5f8a-40a7-9ebb-9ad707ac0007
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg591345(v=OCS.15)
ms:contentKeyID: 49312567
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 运行最佳做法分析器的要求

 

_**上一次修改主题：** 2016-12-08_

您可以使用 Lync Server 2013 最佳做法分析器扫描 Lync Server 2013 环境。您无法使用它扫描以前的环境，但可以使用该工具以前的版本扫描这些环境。有关下载和使用 Lync Server 2010 和 Office Communications Server 2007 R2 版本的最佳做法分析器的详细信息，请参阅“Lync Server 2010 最佳做法分析器”（网址为 [http://go.microsoft.com/fwlink/?linkid=210536\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=256358%26clcid=0x804)和“Office Communications Server 2007 和 Office Communications Server 2007 R2 的最佳做法分析器”（网址为[http://go.microsoft.com/fwlink/?linkid=256358\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=210651%26clcid=0x804)。

在开始扫描之前，您应该确保 Lync Server 2013 环境中的所有组件都处于运行和联机状态。

> [!NOTE]  
> 最佳做法分析器可能无法访问和扫描您的边缘服务器，具体取决于您的边缘服务器的配置和任何相关外围网络设置（包括防火墙设置和权限）。如果将边缘服务器包含在扫描中且报告指示访问边缘服务器时出现问题，则您可能希望从扫描选项中删除边缘服务器并重新运行扫描，以便报告中不出现问题。


