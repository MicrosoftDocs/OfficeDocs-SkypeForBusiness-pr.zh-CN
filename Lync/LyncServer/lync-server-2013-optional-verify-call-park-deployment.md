---
title: Lync Server 2013：（可选）验证呼叫寄存部署
TOCTitle: （可选）验证呼叫寄存部署
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413076(v=OCS.15)
ms:contentKeyID: 49314839
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# （可选）在 Lync Server 2013 中验证呼叫寄存部署

 

_**上一次修改主题：** 2012-09-11_

安装并配置 呼叫寄存后，需要验证该配置以确保寄存呼叫和取回呼叫按预期工作。至少必须验证以下内容：

  - 呼叫启用 呼叫寄存的用户，并使该用户寄存此呼叫。
    
    > [!NOTE]  
	> 如果执行该测试之前刚刚在语音策略中启用 呼叫寄存，则寄存此呼叫的用户需要从 Lync Server 中注销然后重新登录，才能查看转接呼叫列表中的 呼叫寄存选项。
    


  - 拨打通道号码以取回此呼叫。

  - 寄存其他呼叫，使之前寄存的呼叫超时，并且不接听回拨。验证超时的呼叫是否正确路由到为 **OnTimeoutURI** 指定的回退目标。

