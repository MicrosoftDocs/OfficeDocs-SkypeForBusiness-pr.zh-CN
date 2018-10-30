---
title: Lync Server 2013：使用 Cmdlet 反向执行林准备
TOCTitle: 使用 Cmdlet 反向执行林准备
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413024(v=OCS.15)
ms:contentKeyID: 49314746
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 针对 Lync Server 2013 使用 Cmdlet 反向执行林准备

 

_**上一次修改主题：** 2013-06-19_

使用 **Disable-CsAdForest** cmdlet 可反向执行林准备步骤。

> [!CAUTION]
> 如果在同时部署了早期版本的 Lync Server 的环境中运行 <strong>Disable-CsAdForest</strong> cmdlet，则也会删除早期版本的全局设置。


## 使用 cmdlet 反向执行林准备

1.  以目录林根级域中的 Domain Admins 组成员身份登录到加入域的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  运行：
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    例如：
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Force 参数指定是否强制运行该任务。如果未显示该参数，则即使为 Lync Server 2013 准备了林中的一个域，也不运行此命令。如果指定了 Force 参数，无论林中其他域的状态如何，都将继续执行此操作。
    
    如果不指定 GroupDomain 参数，则默认值为本地域。

## 另请参阅

#### 任务

[为 Lync Server 2013 运行林准备](lync-server-2013-running-forest-preparation.md)  

#### 其他资源

[为 Lync Server 2013 准备林](lync-server-2013-preparing-the-forest.md)

