---
title: Activity report
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 8cbe2eb2-1194-4fd7-b1ee-9f9287c82424
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_ReportsS4BActivity
ms.custom:
- Reporting
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: fd167f9effb06bca43362fa4e9db3652ae8d15a4
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="activity-report"></a>Activity report

全新的 Office 365" **报告**"仪表板会为你显示组织中不同 Office 365 产品上所发生活动的概况。 It enables you to drill in to individual product-level reports to give you more granular insight about the activities within each product. For example, you can use the **Skype for Business activity** report to see how much your users are using peer-to-peer or organized conferencing sessions, or how much they're participating in conferencing sessions. 

Check out the [Reports overview](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) to learn more.
  
This report, along with the other Skype for Business reports, gives you details on activity across your organization. 当你为组织进行调查、规划及执行其他业务决策时，这些详细信息非常有用。
  
> [!NOTE]
> You can see all of the Skype for Business reports when you log on as an administrator in the Office 365 admin center. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>如何访问 Skype for Business 活动报告

1. Go to the **Office 365 admin center** > **Reports** > **Usage**.
    
2. On the **Usage** page, click **Skype for Business activity** on the **Select a report list** on the left, or click the **Skype for Business activity** widget.
    
     ![Skype for Business DashBoard Widget.](../images/3925bc24-18fd-471e-8e93-edf5ccd3cdb7.png)
  
    > [!IMPORTANT]
    > Depending on the Office 365 subscription you have, you might not see all the products and reports shown here. 
  
## <a name="interpret-the-skype-for-business-activity-report"></a>解释 Skype for Business 活动报告

可通过查看" **活动**"和" **用户**"图表，了解用户的 Skype for Business 活动。
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/>
可以查看" **Skype for Business 活动**"报告以了解过去 7 天、30 天、90 天或 180 天的趋势。

    > [!Note]
    > If you click into the details of a specific day, the table will only show data for the 30 days up to the date when the report was generated.
***
![Number 2](../images/sfbcallout2.png)<br/>
每个报表包含此报表的生成日期。 The reports usually reflect a 24- to 48-hour latency from time of activity. 
***
![Number 3](../images/sfbcallout3.png)<br/>使用" **活动**"图表上的交互式图表数据可了解使用趋势并查看组织中正在进行的会话活动数。它将显示在整个组织中" **对等会话**"、" **组织**"和" **参与**"会议会话的总数和类型。 
***
![Number 4](../images/sfbcallout4.png)<br/>
使用" **用户**"图表上的交互式图表数据可了解使用趋势并查看参与组织中正在举行的会议活动的唯一用户数。 It will show you the total number of users along with the types of **Peer-to-peer sessions**, **Organized**, and **Participated** in conference sessions.
***
![Number 5](../images/sfbcallout5.png)<br/>
你可以通过单击图例上的项目筛选你在图表上看到的系列。 For example, on the **Activity** chart, click or tap **Peer-to-peer sessions**, **Organized**, or **Participated** to see only the info related to each one. 更改此选择不会更改网格表中的信息。 
***
![Number 6](../images/sfbcallout6.png)<br/>
每个图表都具有"X"（水平）轴和"Y"（垂直）轴。
*    On the **Activity** chart, the Y axis is the total number of peer-to-peer, organized, and participated in conference sessions that are held.
*    On the **Users** activity chart, the Y axis is the number of unique users attending in each type of peer-to-peer, organized, and participated in conference.

这两个图表的 X 轴都表示此特定报表的所选日期范围。 
***
![Number 7](../images/sfbcallout7.png)<br/>
The table shows you a breakdown of all the conferencing activities per user. This shows all users who have Skype for Business assigned to them and their conferencing activities. 你可以向该表格中添加其他列。
*    **Username** is the name of the user.
*    " **已删除**"表示用户的许可证已删除。 <br/> <br/> **Note:** Activity for a deleted user will still display in a report as long as he or she was licensed at some time during the selected time period. The **Deleted** column helps you to note that the user may no longer be active, but contributed to the data in the report.<br/><br/>
*    **Deleted date** is the date on which the user's license was removed.
*    " **上次活动日期(UTC)**"是该用户最近参与对等会话、组织或参与会议的时间。
*    **Peer-to-peer** shows the total number of peer-to-peer conference sessions that the user used.
*    " **组织会议**"显示该用户组织的会议的总数。
*    " **参与会议**"显示该用户参与的会议总数。
*    " **分配的产品**"表示分配给此用户的 Office 365 产品。<br/>

If your organization's policies prevent you from viewing reports where user information is identifiable, you can change the privacy setting for all these reports. Check out the **Hide user details in the reports** section in the [Activity Reports in the Office 365 admin center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).
***
![Number 8](../images/sfbcallout8.png)<br/>
Click or tap the **Columns** icon in any of the columns to add or remove columns from the report.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Number 9](../images/sfbcallout9.png)<br/>
你还可以单击或点击" **导出**"按钮，将报告数据导出到 Excel .csv 文件中。           <br/> ![Skype for Business Reporting Export Button.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 If you have fewer than 2000 users, you can sort and filter within the table in the report itself. 如果拥有的用户超过 2000 人，你需要导出数据进行筛选和排序。 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype for Business device usage report](device-usage-report.md) You can to see the devices, including Windows-based operating systems and mobile devices, that have the Skype for Business app installed and are using it for IM and meetings.
    
- [Skype for Business conference organizer activity report](conference-organizer-activity-report.md) You can see how much your users are organizing conferences that use IM, audio/video, application sharing, Web, dial-in/out - 3rd party, and dial-in/out - Microsoft.
    
- [Skype for Business peer-to-peer activity report](peer-to-peer-activity-report.md) You can see how much your users are using IM, audio/video, application sharing, and transferring files.
    
- [Skype for Business users blocked report](users-blocked-report.md) You can see the users in your organization that have been blocked from making PSTN calls.
    
- [Skype for Business PSTN usage report](pstn-usage-report.md) You can see the number of minutes spent in inbound/outbound calls and cost for these calls.

- [Skype for Business PSTN minute pools report](pstn-minute-pools-report.md) you can see the number of minutes consumed during the current month within your organization.

- [Skype for Business session details report](session-details-report.md) You can see details about individual user's call experiences.

    
## <a name="related-topics"></a>相关主题
[Office 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 