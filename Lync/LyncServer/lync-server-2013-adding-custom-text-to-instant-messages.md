---
title: Lync Server 2013：向即时消息添加自定义文本
TOCTitle: 向即时消息添加自定义文本
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398847(v=OCS.15)
ms:contentKeyID: 52061121
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中向即时消息添加自定义文本

 

_**上一次修改主题：** 2013-02-20_

将免责声明或警告添加到每个 Lync 2013 即时消息 (IM) 对话的开头，方法是使用带有 IMWarning 参数的 **New-CSClientPolicy** 或 **Set-CSClientPolicy**Lync Server 命令行管理程序 cmdlet。

以下示例中的命令会在新的 IM 对话开始时，在"对话"窗口的顶部添加安全提醒：

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

使用 **Grant-CSClientPolicy** 将此新策略分配给用户。有关详细信息，请参阅 Lync Server 命令行管理程序文档中的 **New-CSClientPolicy** 和 **Grant-CSClientPolicy**。

