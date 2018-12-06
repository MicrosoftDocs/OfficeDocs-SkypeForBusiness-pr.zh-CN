---
title: 删除授权主机条目
TOCTitle: 删除授权主机条目
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204902(v=OCS.15)
ms:contentKeyID: 49312896
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除授权主机条目

 

_**上一次修改主题：** 2012-09-26_

本主题介绍如何删除旧授权主机项（在 Lync Server 2013 中称为 *受信任的应用程序项* ）。将远程呼叫控制迁移到 Office Communications Server 2007 R2 部署时，必须从 Lync Server 2013 部署中删除所有 SIP/CSTA 网关的现有授权主机项。必须使用 Office Communications Server 2007 R2 附带的管理工具删除现有授权主机项。

## 删除 Office Communications Server 2007 R2 部署中授权的主机条目

1.  打开 Office Communications Server 2007 R2 管理控制台。

2.  展开树，并右键单击创建授权主机的池。

3.  单击“属性”，然后单击“前端属性”。

4.  单击“主机授权”选项卡。

5.  选择一台服务器，然后单击“删除”。

6.  在“属性”中，单击“确定”。

