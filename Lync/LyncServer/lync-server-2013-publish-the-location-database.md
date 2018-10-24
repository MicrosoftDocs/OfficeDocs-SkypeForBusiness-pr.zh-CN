---
title: 发布位置数据库
TOCTitle: 发布位置数据库
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398974(v=OCS.15)
ms:contentKeyID: 49314457
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 发布位置数据库

 

_**上一次修改主题：** 2012-10-30_

只有在添加到位置数据库的新位置发布后，客户端才能使用这些位置。

有关详细信息，请参阅 Lync Server 命令行管理程序文档中有关以下 cmdlet 的内容：

  - **Publish-CsLisConfiguration**

如果使用紧急位置标识号 (ELIN) 网关，还需要将 ELIN 上载到公用电话交换网 (PSTN) 运营商的自动位置标识 (ALI) 数据库。PSTN 运营商可能需要特定格式的 ELIN 记录。请联系 PSTN 运营商了解详细信息。可以从位置信息服务数据库中导出记录并根据需要对其进行格式化。

## 发布位置数据库

  - 启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

  - 运行以下 cmdlet 发布位置数据库。
    
        Publish-CsLisConfiguration

