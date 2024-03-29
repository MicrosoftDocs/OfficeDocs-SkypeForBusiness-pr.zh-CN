---
title: 移动客户端创建或编辑推送通知配置
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 推送通知和推送通知交换所 (PNCH) 移动功能的主要组成部分。 推送通知是将消息发送到 PNCH 的过程。 消息将保留在此处，直到它能发往移动客户端或超时段过期为止。
---

# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>移动客户端：创建或编辑推送通知配置
 
推送通知和推送通知交换所 (PNCH) 移动功能的主要组成部分。 推送通知是将消息发送到 PNCH 的过程。 消息将保留在此处，直到它能发往移动客户端或超时段过期为止。 
  
> [!NOTE]
> 时间段在推送通知交换所设置，不能由部署的用户或管理员进行配置。 
  
若要启用推送通知，请执行下列操作：
  
1. **范围：** 记下此策略的范围。 它可以是 **"全局**"（适用于此部署中的所有用户）或 **"站点**"（仅分配给指定站点中的主服务器的用户）。
    
    > [!IMPORTANT]
    > 在一个策略级别应用的策略设置可覆盖在其他策略级别应用的设置。 策略优先级为：用户策略 (站点策略) ，站点策略覆盖全局策略， (影响最小) 。 这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。 
  
2. 通过单击以下复选框选择您要启用的推送通知服务：
    
   - **启用 Microsoft 推送通知** 将推送通知启用到基于云的 PNCH，以便Windows Phone应用Skype for Business推送通知
    
   - **启用 Apple 推送通知** 将为运行 Apple iOS (（例如，iPhone、iPad) 和使用 apple Skype for Business 应用）的 Apple PNCH 启用推送通知
    
3. 完成策略编辑后，单击“提交”可保存更改。如果需要删除所做的更改，请选择“取消”。将不会保存对策略的任何更改。
    

