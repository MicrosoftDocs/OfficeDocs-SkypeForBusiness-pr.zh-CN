---
title: 未分配的电话号码新建或编辑现有
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。
ms.openlocfilehash: 87d83f6285e36abf6b063ba7d6c4d1a93cadc633
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41792160"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>未分配的电话号码：创建新的编辑现有的

> [!NOTE]
> 将 Skype for business 2019 与 Exchange 2013 或 Exchange 2016 集成时，exchange UM 将在 Skype for business Server 2019 中保持可用。 由于 Exchange 2019 中的支持的更改，Exchange UM 集成已被取消重点，取而代之的是云语音邮件和云自动助理功能。

未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。

> [!IMPORTANT]
> 创建新的未分配号码范围或编辑现有的号码范围后，单击 **"确定"** 以返回到列出所有号码范围的 "**未分配号码**" 页面。 在新的 "**未分配的数字范围**" 页面或 "**编辑未分配的号码 Rage** " 页面上所做的更改将不会提交到数据库，直到单击 "**未分配号码**" 页面上的 "**全部提交**"。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。

- **名称**键入标识未分配的号码范围的描述性名称。 保存区域后，此名称不能更改。

- **数字范围**在第一个字段中，键入未分配的号码范围的起始编号。 在第二个字段中，键入区域的结束编号。

  - 该范围的起始号码必须小于或等于该范围的结束号码。

  - 如果号码范围的起始号码或结束号码包含分机号，那么号码范围的起始号码和结束号码都必须包含分机号，并且起始号码和结束号码的分机号必须相同。

  - 该号码必须与正则表达式（电话：）匹配？（\+)?[1-9] \d{0,17}（; ext = [1-9] \d{0,9}）？。 这意味着该号码可能会以字符串电话开始：（如果未指定该字符串将自动添加），则加号（+）和数字1到9。 电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。

- **公告服务**选择 "**通知**"，让通知应用程序处理传入呼叫或**exchange Um** ，让 exchange um 自动助理处理传入呼叫。

- 如果已选择 "**发布**" 发布**服务**：

  - **目标服务器的 FQDN**选择运行通知应用程序的应用程序服务的服务 ID，该应用程序将处理传入呼叫到此范围的未分配号码。

  - **公告**选择要为此未分配号码范围播放的公告。

- 如果您已选择 " **EXCHANGE UM** for**宣告服务**"：

  - **自动助理电话号码**选择 Exchange UM 自动助理的电话号码。

有关公告功能和功能的详细信息，请参阅规划文档中的[Skype For business 中的公告应用程序计划](../../../plan-your-deployment/enterprise-voice-solution/announcement.md)。 有关使用未分配号码范围的详细信息，请参阅操作文档中的[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)。


