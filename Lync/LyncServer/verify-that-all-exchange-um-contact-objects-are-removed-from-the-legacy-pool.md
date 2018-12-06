---
title: 验证所有 Exchange UM 联系人对象是否已从旧池中删除
TOCTitle: 验证所有 Exchange UM 联系人对象是否已从旧池中删除
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49888432
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 验证所有 Exchange UM 联系人对象是否已从旧池中删除

 

_**上一次修改主题：** 2012-09-26_

使用 **OCSUmUtil** 工具或 **Get-CsExumContact** cmdlet 可以验证 Exchange UM 联系对象是否已从旧 Office Communications Server 2007 R2 池中删除。 **OCSUmUtil** 位于以下文件夹中：

%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe

**OCSUmUtil** 必须从具有以下权限的用户帐户运行：

  - RTCUniversalServerAdmins 和 RTCUniversalUserAdmins 组中的成员身份（包括读取 Exchange Server 统一消息设置的权限）

  - 在指定的组织单位 (OU) 容器中创建联系对象的域权限

有关使用 **Get-CsExumContact** cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档中的 [Get-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExUmContact)。

