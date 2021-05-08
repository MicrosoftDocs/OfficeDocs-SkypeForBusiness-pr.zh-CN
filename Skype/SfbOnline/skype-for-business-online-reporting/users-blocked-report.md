---
title: 阻止的用户报告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 0ac844b2-1b08-4e5a-addf-03cde7af7a40
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: '此报告以及其他Skype for Business一起提供有关活动的详细信息，包括整个组织的 PSTN 使用情况。 '
ms.openlocfilehash: 174a186b2f629dced46910fd206d33ce82b701c8
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238128"
---
# <a name="users-blocked-report"></a>阻止的用户报告

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

新的Skype for Business **报表** 仪表板显示组织中Skype for Business产品的活动概述。 它使你能够深入到各个产品级报告，从而更细致地了解每个产品内的活动。 例如，可以使用阻止Skype for Business报告查看组织中已阻止进行 PSTN 呼叫的用户。 此报告以及其他Skype for Business一起提供有关活动的详细信息，包括整个组织的 PSTN 使用情况。
  
 有关更多 [可用报表，](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 请查看报表概述。
  
> [!NOTE]
> 以管理员Skype for Business登录到管理中心时，可以看到所有Microsoft 365报表。 
  
## <a name="how-to-get-to-the-skype-for-business-users-blocked-report"></a>如何访问用户Skype for Business报告

![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**

- 转到管理中心>**管理Skype for Business**  >  **报告**  >    >  **用户被阻止**。
    
## <a name="interpret-the-skype-for-business-users-blocked-report"></a>解释Skype for Business阻止的报告

通过查看显示的每个列，可以查看被阻止的用户。
  
以下是此报告的外观。 
  
![被阻止的用户报告](../images/df50a413-7a51-4340-a59b-3f83de941762.png)

下表显示了被阻止进行呼叫的所有用户的细分。 这将显示分配有电话系统音频会议的所有用户。 你可以添加/删除表格的列。
***
![第一](../images/sfbcallout1.png)
*   **用户 ID** 是用户的登录。
*   **电话** 数字是分配给用户的数量。 
*   **阻止操作时间** 是 (UTC) 阻止用户进行呼叫的时间。
*   **阻止** 操作是阻止用户时采取的操作类型。
*   **阻止操作** 原因是阻止用户进行调用的原因。
***
![第二](../images/sfbcallout2.png)<br/>
如果你希望创建将一列或多列中的所有数据进行分组的视图，请单击某个列并将其拖动到" **若要按特定列进行分组，请将列标题拖至此处**"。
***
![第三](../images/sfbcallout3.png)<br/>
你还可以单击或点击" **导出到 Excel**"按钮，将报告数据导出到 Excel .csv 文件中。

此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 如果用户数少于 2000，可以在报表本身的表中进行排序和筛选。 如果拥有的用户超过 2000 人，你需要导出数据进行筛选和排序。
***

## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype for Business活动报告](activity-report.md)你可以看到你的用户使用对等会议会话、组织会议会话和参与会议会话的用户数。
    
- [Skype for Business设备使用情况报告](device-usage-report.md)你可以查看设备，包括Windows操作系统和移动设备，这些设备已安装Skype for Business应用，并使用它进行即时消息和会议。
    
- [Skype for Business组织者活动报告](conference-organizer-activity-report.md)可以看到有多少用户正在组织使用即时消息、音频/视频、应用程序共享、Web、拨入/拨出 - 第三方和拨入/拨出 -Microsoft 的会议。
    
- [Skype for Business会议参与者活动报告](conference-participant-activity-report.md)你可以看到正在参与多少个即时消息、音频/视频、应用程序共享、Web 和电话拨入/拨出式会议。
    
- [Skype for Business对等活动报告](peer-to-peer-activity-report.md)可以看到有多少用户使用即时消息、音频/视频、应用程序共享和传输文件。
    
- [Skype for Business PSTN 使用情况报告](pstn-usage-report.md)可以看到入站/出站呼叫花费的时间以及这些调用的成本。

- [Skype for Business PSTN 分钟](pstn-minute-pools-report.md)数池报告，可以看到组织内部当月使用的分钟数。

- [Skype for Business会话详细信息报告](session-details-report.md)可以看到有关单个用户的呼叫体验的详细信息。
   
## <a name="related-topics"></a>相关主题
[管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
