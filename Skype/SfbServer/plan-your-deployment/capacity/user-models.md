---
title: 用户模型中Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c551371c-d740-4372-bada-f0d713ec0d33
description: 此处介绍的用户模型为容量规划度量和建议提供了在容量规划用户模型用法中介绍Skype for Business Server。
ms.openlocfilehash: 1057d3d4e4d20c4193556aa6801da51ca81effba
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62418415"
---
# <a name="user-models-in-skype-for-business-server"></a>用户模型中Skype for Business Server
 
此处介绍的用户模型为容量规划度量和建议提供了基础，如 Capacity [planning user model usage for Skype for Business Server](user-model.md)。
  
## <a name="skype-for-business-server-user-models"></a>Skype for Business Server用户模型

下表介绍了用户模型，用于注册、联系人、即时消息 (IM) ，以及用户Skype for Business Server。
  
**环境和注册用户模型**

|**类别**|**说明**|
|:-----|:-----|
|部署大小和通讯组  <br/> |我们对含有三个中央站点（每个站点有一个前端池）的大型部署进行了建模。  <br/> |
|Active Directory 用户的百分比  <br/> |假设为组织中 70% 的 Active Directory 用户启用了Skype for Business Server。 这些启用的用户中 80% 每天Skype for Business Server 80% 并发 (登录) 。 本节下文中的数字都以并发用户为基础。  <br/> |
|Active Directory 更改  <br/> |假设每周在 Active Directory 中创建和启用 Skype for Business 的用户总数的 0.5%，并且每周从 Active Directory 和 Skype for Business 禁用 0.5% 的用户。 5% 的用户每周至少更改一个 Active Directory 属性。  <br/> |
|Active Directory 通讯组  <br/> |我们假定，组织的 Active Directory 通讯组数是 Active Directory 所有用户数的三倍。通讯组的大小如下：  <br/> • 64% 的用户数为 2-30  <br/> • 13% 的用户数为 31-50  <br/> • 10% 的用户数为 51-100  <br/> • 13% 的用户数为 101-500  <br/> |
|IP 语音 (VoIP) 用户  <br/> |60% Skype for Business Server用户启用了统一通信 (UC)  (，即其电话号码归用户Skype for Business Server) 。  <br/> |
|注册的客户端分布  <br/> |65% 的客户端运行 Skype for Business 软件，包括 Skype for Business 和 Lync 电话 Edition。  <br/> 30% 的客户端运行以前版本的 Lync 中的客户端软件。  <br/> 5% 的客户端使用 Skype for Business Web应用。  <br/> 如果启用了移动功能，则假设 40% 的用户同时使用移动功能以及之前引用的其他注册客户端选项。 在这种情况下，MPOP (客户端多点) 比率为 1：1.9。 如果禁用移动，MPOP 比率为1:1.5。  <br/> |
|远程用户分布  <br/> |70% 的用户从内部连接。  <br/> 30% 的用户通过边缘服务器连接 (也可以在此处选择拥有控制器，但不需要) 。  <br/> |
|联系人分布  <br/> |一个用户拥有的最大联系人数为 1,000。拥有 1,000 个联系人的用户低于 1%。拥有 100 个或更多联系人的用户低于 25%。  <br/> 使用公共云连接的用户平均拥有 80 个联系人。在这些用户中：  <br/> • 50% 的联系人在组织中。 这些用户中的 10% 为远程用户，从防火墙以外连接。  <br/> • 40% 的联系人是Skype联系人。  <br/> • 10% 的联系人来自联盟伙伴。  <br/> 未使用公共云连接的用户平均拥有 50 个联系人。在这些用户中：  <br/> • 80% 的联系人在组织内部。 这些用户中的 10% 为远程用户，从防火墙以外连接。  <br/> • 20% 的联系人来自联盟伙伴。  <br/> 每个用户在其联系人列表中都有一个通讯组。为了进行性能测试，我们假设通讯组始终是展开的。  <br/> |
|会话时间  <br/> |平均用户登录会话持续 12 个小时。所有用户在会话开始后的 120 分钟内登录。  <br/> |
   
**IM 和状态用户模型**

|**类别**|**说明**|
|:-----|:-----|
|对等 IM 会话  <br/> |平均每个用户每天发起六个对等 IM 会话。  <br/> 每个会话 10 条即时消息。  <br/> 每个消息由两条 SIP INFO 消息和两条\<Name\> SIP 200 OK 消息匹配 (状态指示器（如"正在键入")   <br/> |
|组 IM 会话  <br/> |在仅 IM 组会话中发送的平均消息数是每个用户 5 条。  <br/> AV 会议的 IM 部分中发送的平均消息数是每个用户 2 条。  <br/> |
|状态轮询  <br/> |总体上讲，假设状态轮询为平均每个用户每小时 60 次轮询。对于每个用户，假设平均：  <br/> • 在用户的组织选项卡中每天进行一次用户状态轮询 (但不在联系人列表) 。 用户组织选项卡中的非联系人平均数量为 15 个用户。 每天执行两次联系人卡片查看操作。  <br/> • 每次用户单击其他用户启动对话时进行一次状态轮询，估计为每小时一次。  <br/> • 每小时六次用户搜索。 每次执行搜索时，都会针对搜索结果列表中的每个人发送批轮询。 假设搜索结果的平均大小为 20。 如果搜索结果停留在屏幕上，则每 5 分钟就会刷新一次批轮询；假设每小时将进行两次这样的刷新。  <br/> • 当用户在 Outlook 中打开或预览电子邮件时，电子邮件的 To： 和 CC： 字段中的用户状态轮询，估计为每小时五封电子邮件，每封电子邮件四个用户。  <br/> |
|状态订阅  <br/> |当用户将其他用户添加为联系人时，第一个用户将“订阅”第二个用户的五类信息。这些类别的信息的更新会自动发送给第一个用户。 <br/> 针对每个客户端，会发送单个订阅请求以获取平均 40 个联系人状态，以及发送其他 40 个对话以获取联盟联系人状态。  <br/> 扩展通讯组成员的状态可通过持久状态订阅（而非轮询）进行查找，并建模为每个用户每两小时一次扩展。  <br/> 短订阅在用户登录时发生，存在针对所有用户的联系人的批量订阅，然后用户很快注销。 假设每个用户每小时有 6 个短期订阅，其中每个订阅持续 10 分钟。 <br/> |
|状态发布  <br/> |平均每个用户每小时发布状态 4 次，最多每个用户每小时发布 6 次。  <br/> |
|状态文档大小  <br/> |假设完整状态文档的平均大小为 4K，最大为 25K。  <br/> |
   
下表介绍了通讯簿使用用户模型。
  
**通讯簿使用用户模型**

|**通讯簿搜索模式**|**使用情况**|
|:-----|:-----|
|仅通讯簿 Web 查询（通讯簿 Web 查询服务执行的所有查询）  <br/> |每个用户每天四次前缀查询。  <br/> 每个用户每天 60 次精确搜索查询。在这些查询中，40% 为批处理查询，平均每次查询 20 个联系人。剩余的 60% 为单个联系人查询。  <br/> 每个用户每天 25 次照片查询。其中 24 次为单张照片查询，另外一次为批处理查询，平均查询 20 个联系人。  <br/> 每个用户每天一次彻底的组织搜索查询。  <br/> |
|混合模式，结合使用通讯簿文件和 Web 查询。这是默认模式。  <br/> |只有两种查询会连接到网络，即照片查询和彻底的组织搜索查询。  <br/> 每个用户每天 25 次照片查询。其中 24 次为单张照片查询，另外一次为批处理查询，平均查询 20 个联系人。  <br/> 每个用户每天一次彻底的组织搜索查询。  <br/> |
   
下表介绍了会议模型。
  
**会议模型**

|**类别**|**说明**|
|:-----|:-----|
|计划的会议与“立即开会”会议  <br/> |60% 计划内会议，40% 计划外会议。  <br/> 在安排的会议中，我们假设有 80% 分配有会议，即定期会议;10% 为一次开放会议;8% 为一次匿名会议，2% 为一次关闭会议。  <br/> |
|会议客户端分布  <br/> |对于计划内会议：  <br/> • 65% 的会议用户使用 Skype for Business 2016。  <br/> • 5% 的会议用户使用 Skype for Business Web应用。  <br/> • 30% 的会议用户使用早期客户端，包括 Lync 2013 和 Microsoft Lync 2010。  <br/> 对于计划外会议：  <br/> • 70% 的会议用户使用 Skype for Business。  <br/> • 30% 的会议用户使用早期客户端，包括 Lync 2013 和 Microsoft Lync 2010。  <br/> |
|会议并发  <br/> |5% 的用户将在工作时间参加会议。因此，在一个有 80,000 个用户的池中，在任何时候都可能有多达 4,000 个用户参加会议。  <br/> |
|会议音频分布  <br/> |40% VoIP 音频和电话拨入式混合会议，VoIP 用户和电话拨入用户的比率为 3:1。  <br/> 35% 仅 VoIP 音频。  <br/> 15% 仅电话拨入式会议音频。  <br/> 10% 无音频（仅 IM 会议，平均每个用户发出 5 条消息）。  <br/> |
|会议媒体混合  <br/> |75% 的会议为 Web 会议，其中包括音频以及一些其他协作形式。  <br/> 这些会议的其他协作方式如下：  <br/> **注意：** 这些数字最多超过 100%，因为一个会议可以有多个协作方法。 <br/> • 50% 添加应用程序共享。 假设一个用户以每秒 1.1 MB 的峰值发送数据。  <br/> • 50% 添加即时消息 (每个用户平均添加 2 条消息) 。  <br/> • 20% 添加数据协作，包括 PowerPoint 或白板。在这些文件中，每个会议平均显示 2 PowerPoint 个文件，平均 PowerPoint 文件大小为 10 MB (（不含嵌入式视频) ）或 30 MB (（带嵌入式视频) ）。 每个白板平均有 20 个批注。  <br/> • 20% 添加视频。 在这些用户当中，70% 的用户参加启用了多视图视频的会议，其中每个用户会收到 2-3 个视频流。  <br/> • 15% 添加共享笔记。  <br/> |
|会议参与者分布  <br/> |50% 为经过身份验证的内部用户。  <br/> 25% 为经过身份验证的远程访问用户。  <br/> 15% 为匿名用户。  <br/> 10% 为联盟用户。  <br/> |
|与会分布  <br/> |用户被模拟为在前 5 分钟内加入会议。  <br/> |
   
在常规前端池中，Skype for Business Server支持的最大会议大小为 250 个用户。 每个池一次可承载一个 250 个用户的会议。 召开这样的大型会议的同时，池还可以承载其他较小的会议。 另外，通过设置专用池承载这些会议，可以支持多达 1000 位用户的会议。 有关详细信息，请参阅在 Skype for Business Server 中[规划大型Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md)。
  
模拟会议的方式如下：
  
- 85% 的会议有 4 个参与者。
    
- 10% 的会议有 6 个参与者。
    
- 5% 的会议有 11 个参与者。
    
- 用户数为 250 的一次大型会议。
    
下表详细说明了涉及电话拨入用户的会议的用户模型。
  
**电话拨入式会议用户模型**

|**类别**|**说明**|
|:-----|:-----|
|Authenticated/anonymous  <br/> |70% 的呼叫者通过匿名加入，并提示输入记录的名称。30% 经过身份验证加入。  <br/> |
|呼叫持续时间和保持音乐  <br/> |不包括保持音乐的平均呼叫持续时间：50 秒。  <br/> 50% 的电话拨入用户会听到保持音乐，平均持续 5 分钟。  <br/> |
|双音多频 (DTMF)  <br/> |15% 的仅电话拨入式会议有电话领导。10% 包含电话拨入用户的混合会议也有电话领导。  <br/> 20% 的电话领导在每次会议中使用 2 个 DTMF 命令。  <br/> |
|通知语言  <br/> |模拟使用英语作为通知语言。  <br/> |
   
下表详细说明了会议厅的用户模型。
  
**会议厅用户模型**

|**类别**|**说明**|
|:-----|:-----|
|会议厅中的用户数量  <br/> |5% 的电话拨入用户通过会议厅，25% 其他用户通过会议厅  <br/> |
|从会议厅加入  <br/> |在模拟中，所有用户在客户端超时之前由演示者许可加入。  <br/> |
   
下表说明了其他对等会话的用户模型。
  
**对等会话用户模型**

|**类别**|**说明**|
|:-----|:-----|
|应用程序共享  <br/> |每个用户每个月参加 5 个对等应用程序共享会话，平均每天参加 0.25 个会话。  <br/> |
|文件传输  <br/> |每个用户每个月参加 1 个对等文件传输会话（IM 会话的一部分），平均每天参加 0.05 个会话。传输的会话文件平均大小为 1 MB。  <br/> |
   
下表介绍了用于策略的用户模型。
  
**策略用户模型**

|**类别**|**说明**|
|:-----|:-----|
|会议、状态和存档策略  <br/> |假设有一个全局策略、10 个标记会议策略、4 个存档策略和 10 个标记状态策略。  <br/> |
|语音策略  <br/> |假设每个站点有一个全局策略和 2 个标记策略。 100% 的站点都有站点策略，并为 30% 的用户分配每用户策略。 假设每个站点有一个拨号计划和两个路由。  <br/> |
   
## <a name="busy-hour"></a>忙时

对于对等会话，使用忙时呼叫尝试 (BHCA) 计算峰值负载。此语音行业术语假设将在 20% 的时间内完成一天中 50% 的呼叫。可使用以下公式进行计算：
  
 `BHCA=(total calls * 0.5) / 1.6`
  
通过运行 VoIP 模拟忙时的性能测试和每天至少 1.6 小时的忙时负载的其他对等会话。
  
会议峰值负载假设在 4 小时的高峰时间内发生 8 小时工作日 75% 的会议。这些高峰时间的负载是平均会议负载的 1.5 倍。
  
## <a name="enterprise-voice-to-pstn-calls"></a>企业语音 PSTN 呼叫

以下假设适用于企业语音调用：
  
- 60% 的用户已启用 pstN 企业语音，60% 的用户启用了 PSTN 呼叫。
    
- 启用了 PSTN 呼叫的其中每一位用户在忙碌时段都发出 4 个 PSTN 呼叫。每个呼叫的持续时间为 3 分钟。
    
- 其中 65% 的 PSTN 语音呼叫使用媒体旁路。
    
## <a name="mobility"></a>移动性

假设为 40% 的注册用户启用了移动。对于启用了移动的每一位用户，假设移动客户端的活动是在该用户其他 MPOP 实例活动的基础上进行增加，但会议交互除外，对其而言，移动客户端只是可用来参与会议的另一种客户端类型。
  
## <a name="persistent-chat"></a>持久聊天

假设 25% 的注册用户将参与到持久聊天会话中，并具有以下特征：
  
- 每个用户平均 1.5 个聊天室
    
- 每个聊天室每小时将产生 12 个轮询请求，每个轮询请求平均针对 10 个用户
    
## <a name="response-group-and-call-park"></a>响应组和呼叫驻留

假设 0.15% 的注册用户属于响应组。假设 0.02% 的注册用户在任何给定的时间点都有驻留呼叫。
  

