---
title: 选择允许的成员
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: 正确使用类别可更轻松地创建和管理持久聊天室。 持久聊天管理员可以为每个类别定义 AllowedMembers 和 Creators，还可以定义将应用于类别中创建的所有聊天室的默认聊天室设置和行为。 持久聊天管理员使用控制面板或 cmdlet 创建和管理Windows PowerShell类别。
ms.openlocfilehash: 8c45a16f88bf20ab973927e17807b3241f20e942
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829132"
---
# <a name="select-allowed-members"></a>选择允许的成员

正确使用类别可更轻松地创建和管理持久聊天室。 持久聊天管理员可以为每个类别定义 **AllowedMembers** 和 **Creators，** 还可以定义将应用于类别中创建的所有聊天室的默认聊天室设置和行为。 持久聊天管理员使用控制面板或 cmdlet 创建和管理Windows PowerShell类别。

标识为类别创建者的用户、组织单位 (OU) 和用户组是唯一允许在该类别中创建聊天室的个人和组。 创建类别后，他们可以从类别的 **AllowedMembers** 列表中选择用户、US 和用户组作为聊天室管理员和成员来管理和参与聊天室。

## <a name="tasks-that-you-can-perform"></a>可执行的任务

您可以在“选择允许的成员”页上执行以下任务：

- [配置类别](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [新增的群聊服务器功能](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

有关可以使用 Skype for Business Server 控制面板执行的不同过程的详细信息，请参阅["管理 Skype for Business Server 2015"。](../../manage/manage.md)

## <a name="to-configure-categories-for-chat-rooms"></a>配置聊天室的类别

在 **"** 成员身份"中，在"允许的成员"部分，添加或删除用户和其他 Active Directory 域服务主体 (用户、通讯组、组织单位等) 允许添加为属于该类别的聊天室的成员。 类别允许的主体可以搜索该类别中的聊天室（除非聊天室处于隐藏状态，在这种情况下只有聊天室的成员才能在目录中搜索它）。


有关持久聊天服务器特性和功能的详细信息，请参阅规划文档中的 ["持久聊天服务器](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) 概述"。 有关使用持久聊天服务器配置的详细信息，请参阅部署文档中[](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)的"配置持久聊天服务器"和操作文档中的"管理[Lync Server 2013](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)持久聊天服务器"。

## <a name="see-also"></a>另请参阅

[了解持久聊天成员身份](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
