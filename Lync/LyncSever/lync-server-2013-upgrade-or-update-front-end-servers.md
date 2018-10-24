---
title: 在 Lync Server 2013 中升级或更新前端服务器
TOCTitle: 在 Lync Server 2013 中升级或更新前端服务器
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204736(v=OCS.15)
ms:contentKeyID: 49312227
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中升级或更新前端服务器

 

_**上一次修改主题：** 2013-06-28_

Enterprise Edition 池中的前端服务器组织到 *升级域* 中。升级域是池中前端服务器的子集，由 拓扑生成器 自动创建。

当您升级服务器时，必须每次在一个升级域中执行操作。将一个升级域中的每个服务器关闭，升级并重新启动它，然后在继续移动到其他升级域。确保跟踪目前为止已升级了哪些升级域和服务器。升级每个服务器时，请使用以下流程图。

![升级服务器流程图](images/JJ204736.42ed59a4-1c26-49f7-ade4-a5a788457ab9(OCS.15).jpg "升级服务器流程图")

## 对池中的前端服务器应用升级

1.  在池中的前端服务器上，运行以下 cmdlet：
    
    **Get-CsPoolUpgradeReadinessState**
    
    如果 *PoolUpgradeState* 的值为 **Busy**，请等待 10 分钟，然后重试 **Get-CsPoolUpgradeReadinessState**。如果您在每次尝试之间等待 10 分钟后至少连续三次看到 **Busy**，或者看到 **PoolUpgradeState** 的 **InsufficientActiveFrontEnds** 的任何结果，表明池存在问题。如果该池与灾难恢复拓扑中的另一个前端池配对，则应将池故障转移到备份池，然后更新该池中的服务器。有关详细信息，请参阅[在 Lync Server 2013 中对池进行故障转移](lync-server-2013-failing-over-a-pool.md)。
    
    如果 *PoolUpgradeState* 的值为 **Ready**，请转至步骤 2。

2.  **Get-CsPoolUpgradeReadinessState** cmdlet 还返回有关池中每个升级域的信息，以及有关每个升级域中包含哪些前端服务器的信息。对于包含要升级服务器的升级域，如果 **ReadyforUpgrade** 值为 **True**，则您可以立即安全地升级这些服务器。为此，请执行以下操作：
    
    1.  使用 `Stop-CsWindowsService -Graceful -Verbose` cmdlet 停止与您将要升级的前端服务器的新连接。
        
        > [!NOTE]  
		> 如果您在计划的服务器停机时间内执行这些服务器升级，则可以不带 -<strong>Graceful</strong> 参数运行此 cmdlet，如下所示：<strong>Stop-CsWindowsService</strong>。这将立即关闭服务，而不等待填充所有现有服务请求。
    
    2.  升级与此升级域相关联的服务器。
    
    3.  重新启动这些服务器，并确保它们接受新连接。

3.  为池中的每个其他升级域重复步骤 1 和 2，直至升级完所有 前端服务器。

