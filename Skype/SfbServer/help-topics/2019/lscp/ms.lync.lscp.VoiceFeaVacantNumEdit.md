---
title: 未分配电话号码 创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。
ms.openlocfilehash: fb9542cb48fbcbda2bba42a2d691e26030edc9dd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606521"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>未分配电话号码：创建新的或编辑现有的

> [!NOTE]
> Exchange当您将 Skype for Business 2019 与 Exchange 2013 或 Exchange 2016 集成时，UM 在 Skype for Business Server 2019 中仍然可用。 由于 2019 年 Exchange 支持的变化，EXCHANGE UM 集成的重要性正在减少，以支持 云语音邮件 和云自动助理功能。

未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。

> [!IMPORTANT]
> 在创建完新的未分配号码范围或编辑完现有未分配号码范围后，单击“确定”可返回到列出所有号码范围的“未分配号码”页。在单击“未分配号码”页上的“全部提交”后，您在“新建未分配号码范围”页或“编辑未分配号码范围”页上所做的更改才会被提交到数据库。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。

- **名称** 键入标识未分配号码范围的描述性名称。 保存区域后，此名称将无法更改。

- **号码范围** 第一个字段中，键入未分配号码范围的开始号码。 第二个字段中，键入范围的结束号码。

  - 该范围的起始号码必须小于或等于该范围的结束号码。

  - 如果号码范围的起始号码或结束号码包含分机号，那么号码范围的起始号码和结束号码都必须包含分机号，并且起始号码和结束号码的分机号必须相同。

  - 该数字必须与正则表达式 `tel:` () ？ () ？[ \+ 1-9]\d {0,17} (;ext=[1-9]\d {0,9}) ？。 这意味着该号码可能以字符串"tel："开头。 如果不指定该字符串，将自动添加该字符串，例如加号 (+) ，以及 1 到 9 的数字。 电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。

- **通知服务** 选择 **"** 通知"让通知应用程序处理传入呼叫或Exchange **UM，** 让 UM Exchange UM 自动助理处理传入呼叫。

- 如果选择“通知”作为“通知服务”：

  - **目标服务器的 FQDN** 选择运行通知应用程序的应用程序服务的服务 ID，该服务将处理对此未分配号码范围的传入呼叫。

  - **公告** 选择要为此未分配号码范围播放的公告。

- 如果选择“Exchange UM”作为“通知服务”：

  - **自动助理电话号码** 选择 UM 呼叫Exchange电话号码自动助理。

有关通知特性和功能的详细信息，请参阅规划文档中Skype for Business[中的规划](../../../plan-your-deployment/enterprise-voice-solution/announcement.md)通知应用程序。 有关使用未分配号码范围的详细信息，请参阅操作文档中的[Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers)。