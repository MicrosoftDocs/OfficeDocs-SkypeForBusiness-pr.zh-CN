---
title: 移动客户端创建或编辑推送通知配置
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: 推送通知和推送通知交换所 (PNCH) 是移动功能的主要组成部分。推送通知是将消息发送到 PNCH 的过程。消息将保留在此处，直到它能发往移动客户端或超时段过期为止。
ms.openlocfilehash: 96c20e19444f275076b18830a89d74dba93df39b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880205"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>移动客户端：创建或编辑推送通知配置
 
推送通知和推送通知交换所 (PNCH) 是移动功能的主要组成部分。推送通知是将消息发送到 PNCH 的过程。消息将保留在此处，直到它能发往移动客户端或超时段过期为止。 
  
> [!NOTE]
> 时间段在推送通知交换所设置，不能由部署的用户或管理员进行配置。 
  
若要启用推送通知，请执行下列操作：
  
1. **范围：** 注意此策略的范围。范围可以是“**全局**”，此范围适用于该部署中的所有用户，也可以是“**站点**”，此范围是仅分配给指定站点中主服务器的用户。
    
    > [!IMPORTANT]
    > 在一个策略级别应用的策略设置可能会覆盖在另一个策略级别应用的设置。策略优先顺序为：用户策略（影响力最大）覆盖站点策略，站点策略覆盖全局策略（影响力最小）。这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。 
  
2. 通过单击以下复选框选择您要启用的推送通知服务：
    
   - **启用 Microsoft 推送通知**将启用通知推送到基于云的 PNCH for Windows Phone 与 Skype 的业务应用程序
    
   - **启用 Apple 推送通知**将启用通知推送到运行 Apple iOS （如 iPhone、 iPad） 和业务应用程序使用 Skype 的设备的 Apple PNCH
    
3. 完成策略编辑后，单击“**提交**”可保存更改。如果需要删除所做的更改，请选择“**取消**”。将不会保存对策略的任何更改。
    

