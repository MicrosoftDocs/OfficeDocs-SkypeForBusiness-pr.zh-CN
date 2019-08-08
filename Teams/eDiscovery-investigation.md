---
title: 在 Microsoft Teams 中对内容进行电子数据展示调查
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: 了解你需要执行电子数据展示时（例如，你需要提交所有电子方式存储的信息用于法律程序时）要完成的事项。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6831ec2cef16e65e2fd8dd722d436c12b7548a5c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236356"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>在 Microsoft Teams 中对内容进行电子数据展示调查
============================

大型企业经常面临高处罚的法律诉讼, 要求提交所有电子存储的信息 (ESI)。

所有团队1:1 或群组聊天将被记录到各自用户的邮箱中, 并且所有信道消息都将记录到代表团队的组邮箱。 SharePoint Online 和 OneDrive for Business 的电子数据展示功能的对象涵盖上载的文件。

1.  若要使用 Microsoft 团队内容执行电子数据展示调查, 请查看[此](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)链接中的步骤1。

2.  Microsoft 团队数据将在 Excel 电子数据展示导出输出中显示为即时消息或对话, 你可以装入。Outlook 中的 PST 以查看导出后的邮件。

    装载团队的 .PST 时，请注意，所有对话均保留在“对话历史记录”下的“团队聊天”文件夹中。 消息的标题与团队和频道一致。 如下图所示，你可以看到 Bob 在 Manufacturing Specs 团队的“Project 7”频道中发送的此消息。

    ![Outlook 中的用户邮箱中的工作组聊天文件夹的屏幕截图](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  要查看某个用户的邮箱中的私人聊天，也在“对话历史记录”下的“团队聊天”文件夹中找到它们。

## <a name="ediscovery-of-guest-to-guest-chats"></a>电子数据展示的来宾到来宾聊天

如果没有邮箱, 来宾至来宾聊天 (没有家乡租户用户的1xN 聊天) 将不会被编制索引, 因此不会包含在电子数据展示中。 为了方便电子数据展示用于来宾到来宾聊天, 创建了一个基于云的邮箱 (或幻影邮箱) 来存储1xN 数据。 团队聊天数据存储在基于云的邮箱中后, 将为电子数据展示和合规性内容搜索编制索引。

下图显示了电子数据展示如何处理没有邮箱的来宾到来宾聊天。

![来宾至来宾-无邮箱聊天](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
