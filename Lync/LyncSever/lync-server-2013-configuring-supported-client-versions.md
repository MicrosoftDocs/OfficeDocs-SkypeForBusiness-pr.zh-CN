---
title: 配置支持的客户端版本
TOCTitle: 配置支持的客户端版本
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412832(v=OCS.15)
ms:contentKeyID: 49313919
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置支持的客户端版本

 

_**上一次修改主题：** 2012-12-14_

在 Lync Server 2013 中，可以设置客户端版本策略以指定您的环境中所支持的客户端版本。此外，可以使用全局客户端版本配置，为尚未定义版本策略并因此尚未明确得到支持或限制的客户端指定默认操作。

您也可以使用客户端版本策略来管理客户端更新。如果设置客户端版本策略并使用“允许并升级”和“阻止并升级”选项，客户端将从 Windows Server 更新服务（如果正在使用此服务）或 Microsoft Update 接收更新的软件。

## 客户端版本策略设置

默认的客户端版本策略要求所有客户端运行 Lync 或 Microsoft Office Communicator 2007 R2。如果您环境中的客户端运行 Communicator 的早期版本，则可能需要重新配置客户端版本规则，以防止客户端和设备在连接到 Lync Server 2013 时意外受阻或更新。您可以修改默认规则，也可以在“客户端版本策略”列表的更高位置添加一个规则来覆盖默认规则。此外，由于发布累计更新 (CU)，应将客户端版本策略配置为要求最新更新。

