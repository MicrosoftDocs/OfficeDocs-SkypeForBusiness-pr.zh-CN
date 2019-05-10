---
title: 未分配的电话号码创建新的或编辑现有的
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。
ms.openlocfilehash: 89990e7ec0de5f2f4423b4c2862518a8c46dae63
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835309"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>未分配的电话号码：创建新的编辑现有的

> [!NOTE]
> Exchange UM 仍可在 Skype 的业务服务器 2019年与 Exchange 2013 或 Exchange 2016 集成 for Business 2019 Skype 时。 由于 Exchange 2019 中支持的变化，Exchange UM 集成正在弱化支持云语音邮件和云自动助理功能。

未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。

> [!IMPORTANT]
> 创建一个新的未分配号码范围或编辑现有完成后，单击**确定**返回到**未分配号码**页，其中列出了所有的号码范围。 单击**全部提交****未分配号码**页上，在**新建未分配号码范围**页上或**编辑未分配号码 Rage**页所做的更改才提交到数据库。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。

- **名称**键入标识未分配号码范围的描述性名称。 保存范围后，无法更改此名称。

- **号码范围**在第一个字段中，键入未分配号码范围的开始号码。 在第二个字段中，键入该范围的结束号码。

  - 该范围的起始号码必须小于或等于该范围的结束号码。

  - 如果号码范围的起始号码或结束号码包含分机号，那么号码范围的起始号码和结束号码都必须包含分机号，并且起始号码和结束号码的分机号必须相同。

  - 数必须匹配的正则表达式 (tel:) ? (\+) ? [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) ?。 这意味着数可能以字符串 tel 开头: （如果不指定该字符串它将自动添加为您），一个加号 （+） 和一个数字 1 至 9。 电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。

- **公告服务**选择**通知**能够处理传入呼叫通知应用程序或**Exchange UM**以具有 Exchange UM 自动助理处理传入呼叫。

- 如果选择**通知****通知**服务：

  - **目标服务器的 FQDN**选择运行将处理到此未分配号码范围的传入呼叫通知应用程序的应用程序服务的服务 ID。

  - **通知**选择要为此未分配号码范围播放的通知。

- 如果选择**Exchange UM** **通知**服务：

  - **自动助理电话号码**选择 Exchange UM 自动助理的电话号码。

有关通知特性和功能的详细信息，请参阅规划文档中的[规划 Skype for Business 中的通知应用程序](../../../plan-your-deployment/enterprise-voice-solution/announcement.md)。 有关使用未分配号码范围的详细信息，请参阅操作文档中的[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)。


