---
title: "维度和度量值提供为 Microsoft 团队呼叫质量仪表板和 Skype for Business Online"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 11/27/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: e97aeeee-9e43-416f-b433-9cdd63d8874b

description: "Get detailed information about the dimensions and measures exposed by the Call Quality Dashboard for Microsoft Teams and Skype for Business Online."
---

# 维度和度量值提供为 Microsoft 团队呼叫质量仪表板和 Skype for Business Online

> [!重要信息]
> 本文是由机器翻译的，请参阅[免责声明](e97aeeee-9e43-416f-b433-9cdd63d8874b.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/e97aeeee-9e43-416f-b433-9cdd63d8874b) 中查找本文的英文版本以便参考。
  
呼叫质量仪表板 (CQD) Microsoft Teams和Skype for Business Online允许您深入了解使用Microsoft Teams和 Skype for Business 服务所做的呼叫质量。本主题提供有关维度和度量值由 CQD 公开的详细的信息。若要了解有关 CQD 以及如何启用它的详细信息，请参阅[打开并使用 Microsoft 团队和 Skype for Business Online 的呼叫质量仪表板](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md)。
  
## 第一和第二终结点分类

通话质量仪表板 (CQD) 中的很多维度和衡量指标被标记为第一或第二。以下逻辑用于确定将流或通话中涉及的哪些终结点标为第一。
  
- 首先将始终为 Server 终结点 （AV MCU、 中介服务器等） 如果服务器参与流呼叫。
    
- 第二始终是指客户端终结点，除非流的两端均为服务器终结点。
    
- 如果两个端点相同类型，为其次序是第一个与第二个基于用户代理类别的内部排序。这样可以确保排序是一致。
    
例如，每行表示流中涉及的一对用户代理：
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**呼叫方的用户代理类别** <br/> |**被叫方的用户代理类别** <br/> |**First Endpoint** <br/> |**Second Endpoint** <br/> |**First Is Caller** <br/> |
|AV-MCU  <br/> |OC（Skype for Business 客户端）  <br/> |AV-MCU  <br/> |OC（Skype for Business 客户端）  <br/> |是  <br/> |
|OC（Skype for Business 客户端）  <br/> |AV-MCU  <br/> |AV-MCU  <br/> |OC（Skype for Business 客户端）  <br/> |否  <br/> |
|OC（Skype for Business 客户端）  <br/> |OC（Skype for Business 客户端）  <br/> |OC（Skype for Business 客户端）  <br/> |OC（Skype for Business 客户端）  <br/> |否  <br/> |
|AV-MCU  <br/> |中介服务器  <br/> |中介服务器  <br/> |AV-MCU  <br/> ||
|中介服务器  <br/> |AV-MCU  <br/> |中介服务器  <br/> |AV-MCU  <br/> |是  <br/> |
|OC（Skype for Business 客户端）  <br/> |OC 电话（Skype for Business IP 电话）  <br/> |OC（Skype for Business 客户端）  <br/> |OC 电话（Skype for Business IP 电话）  <br/> |是  <br/> |
|OC 电话（Skype for Business IP 电话）  <br/> |OC（Skype for Business 客户端）  <br/> |OC（Skype for Business 客户端）  <br/> |OC 电话（Skype for Business IP 电话）  <br/> |否  <br/> |
   
> [!注释]
> 第一个和第二个分类是分开的终结点的呼叫者或方。呼叫者或方是可用于帮助确定哪些终结点的第一个是呼叫者维度。 
  
## 维度

下表列出了 CQD 中目前使用的维度：
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**维度名称** <br/> |**数据类型/单位** <br/> |**说明** <br/> |**空值表示的意思** <br/> |**实例值** <br/> |
|First Network  <br/> |字符串  <br/> |当上载到门户的子网与租户建筑物映射数据中存在子网时，第一终结点用于媒体流的子网。  <br/> |空值指示子网映射数据中未定义未报告的终结点或网络的网络数据。  <br/> |10.0.1.12.0  <br/> |
|First Network Name  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第一终结点用于媒体流的子网的名称。  <br/> |空值表示终结点未报告网络数据，或网络的子网映射数据中没有定义网络名称。  <br/> |USA/ WA/ REDMOND  <br/> |
|First Network Range  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第一终结点用于媒体流的子网的网络前缀/范围。  <br/> |空值表示终结点未报告网络数据，或网络的子网映射数据中没有定义网络范围。  <br/> |24  <br/> |
|First Building Name  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第一终结点所在建筑物的名称。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义建筑物名称。  <br/> |主楼  <br/> |
|First Ownership Type  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第一终结点所在建筑物的所有权类型。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义所有权。  <br/> |Contoso-IT  <br/> |
|First Building Type  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第一终结点所在建筑物的类型。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义建筑物类型。  <br/> |开放式办公室  <br/> |
|First Building Office Type  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第一终结点所在建筑物的办公类型。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义建筑物办公类型。  <br/> |办公室  <br/> |
|First City  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第一终结点所在的城市。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义城市。  <br/> |Redmond  <br/> |
|First Zip Code  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第一终结点所在地的邮政编码。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义邮政编码。  <br/> |98052  <br/> |
|First Country  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第一终结点所在的国家/地区。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义国家/地区。  <br/> |USA  <br/> |
|First State  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第一终结点所在的省/自治区/直辖市。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义省/自治区/直辖市。  <br/> |WA  <br/> |
|First Region  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第一终结点所在的地区。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义地区。  <br/> |北美  <br/> |
|First Express Route  <br/> |布尔值  <br/> |如果根据上载到门户的子网与租户建筑物映射数据，第一终结点用于媒体流的子网启用了快速路由，则为 True。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有设置快速路由标志。  <br/> |true  <br/> |
|Second Network  <br/> |字符串  <br/> |当上载到门户的子网与租户建筑物映射数据中存在子网时，第二终结点用于媒体流的子网。  <br/> |空值指示子网映射数据中未定义未报告的终结点或网络的网络数据。  <br/> |10.0.1.12.0  <br/> |
|Second Network Name  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第二终结点用于媒体流的子网的名称。  <br/> |空值表示终结点未报告网络数据，或网络的子网映射数据中没有定义网络名称。  <br/> |USA/ WA/ REDMOND  <br/> |
|Second Network Range  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第二终结点用于媒体流的子网的网络前缀/范围。  <br/> |空值表示终结点未报告网络数据，或网络的子网映射数据中没有定义网络范围。  <br/> |24  <br/> |
|Second Building Name  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第二终结点所在建筑物的名称。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义建筑物名称。  <br/> |主楼  <br/> |
|Second Ownership Type  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第二终结点所在建筑物的所有权类型。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义所有权。  <br/> |Contoso - IT  <br/> |
|Second Building Type  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第二终结点所在建筑物的类型。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义建筑物类型。  <br/> |开放式办公室  <br/> |
|Second Building Office Type  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第二终结点所在建筑物的办公类型。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义建筑物办公类型。  <br/> |办公室  <br/> |
|Second City  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第二终结点所在的城市。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义城市。  <br/> |Redmond  <br/> |
|Second Zip Code  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第二终结点所在地的邮政编码。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义邮政编码。  <br/> |98052  <br/> |
|Second Country  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第二终结点所在的国家/地区。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义国家/地区。  <br/> |USA  <br/> |
|Second State  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第二终结点所在的省/自治区/直辖市。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义省/自治区/直辖市。  <br/> |WA  <br/> |
|Second Region  <br/> |字符串  <br/> |根据上载到门户的子网与租户建筑物映射数据，第二终结点所在的地区。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有定义地区。  <br/> |北美  <br/> |
|Second Express Route  <br/> |布尔值  <br/> |如果根据上载到门户的子网与租户建筑物映射数据，第二终结点用于媒体流的子网启用了快速路由，则为 True。  <br/> |空值表示终结点未报告网络数据、网络不在企业网络内或网络的子网映射数据中没有设置快速路由标志。  <br/> |true  <br/> |
|First Inside Corp  <br/> |枚举  <br/> | 根据上载到门户的子网与租户建筑物映射数据，指出第一终结点是否位于企业网络内部的子网上。默认情况下，认为终结点位于外部。 <br/>  可能的值： <br/>  内部 <br/>  外部 <br/> |-  <br/> |内部  <br/> |
|Second Inside Corp  <br/> |枚举  <br/> | 根据上载到门户的子网与租户建筑物映射数据，指出第二终结点是否位于企业网络内部的子网上。默认情况下，认为终结点位于外部。 <br/>  可能的值： <br/>  内部 <br/>  外部 <br/> |-  <br/> |内部  <br/> |
|First Tenant Id  <br/> |字符串  <br/> |第一终结点的 Office 365 租户 ID。  <br/> |空值表示无法确定第一终结点的租户 ID。这可能意味着该终结点登录到了本地 Skype for Business Server 部署。  <br/> |00000000 - 0000 -0000 - 0000 - 000000000000  <br/> |
|Second Tenant Id  <br/> |字符串  <br/> |第二终结点的 Office 365 租户 ID。  <br/> |空值表示无法确定第二终结点的租户 ID。这可能意味着该终结点登录到了本地 Skype for Business Server 部署。  <br/> |00000000 - 0000 - 0000 - 0000 - 000000000000  <br/> |
|First Pool  <br/> |字符串  <br/> |分配给第一终结点的 Skype for Business Online 池 FQDN  <br/> |空值表示无法确定第一终结点的 Skype for Business Online 池。这可能意味着该终结点登录到了本地 Skype for Business Server 部署。  <br/> |pool1.lync.com  <br/> |
|Second Pool  <br/> |字符串  <br/> |分配给第二终结点的 Skype for Business Online 池 FQDN  <br/> |空值表示无法确定第二终结点的 Skype for Business Online 池。这可能意味着该终结点登录到了本地 Skype for Business Server 部署。  <br/> |pool1.lync.com  <br/> |
|Is Federated  <br/> |布尔值  <br/> |如果流的两端是联盟租户，则为 True，否则为 False。  <br/> |空值表示无法确定是否为联盟流，或者没有收集某些信号数据。  <br/> |False  <br/> |
|QoE Record Available  <br/> |布尔值  <br/> |如果为通话/会话提供至少一个用户体验质量报告，则为 True。很多维度和衡量指标仅在 QoE 记录可用时才可用。如果通话没有成功建立，QoE 记录将不可用。  <br/> |-  <br/> |True  <br/> |
|CDR Record Available  <br/> |布尔值  <br/> |如果为通话/会话提供至少一个呼叫详细记录，则为 True。  <br/> |-  <br/> |True  <br/> |
|Media Line Label  <br/> |整型  <br/> |SDP 中用于媒体行的标签。使用"媒体类型"来确定是否为视频、音频、应用共享或基于视频的屏幕共享使用标签。  <br/> |空值表示终结点未报告此数据。  <br/> |0  <br/> |
|Media Type  <br/> |字符串  <br/> |媒体的类型（视频、音频、应用共享或基于视频的屏幕共享）。  <br/> |-  <br/> |音频  <br/> |
|First Is Server  <br/> |布尔值  <br/> |如果第一个终结点是会议服务器（AVMCU、ASMCU）、其他媒体服务器（中介服务器）等类型的服务器终结点，则为 True，否则为客户端终结点。可能的值：客户端、服务器。  <br/> |-  <br/> |客户端  <br/> |
|Second Is Server  <br/> |布尔值  <br/> |如果第二个终结点是会议服务器（AVMCU、ASMCU）、其他媒体服务器（中介服务器）等类型的服务器终结点，则为 True，否则为客户端终结点。可能的值：客户端、服务器。  <br/> |-  <br/> |客户端  <br/> |
|First Is Caller  <br/> |布尔值  <br/> |如果第一个终结点为呼叫方（启动会话的建立），则为 True。  <br/> |-  <br/> |True  <br/> |
|First Network Connection Detail  <br/> |字符串  <br/> | 第一终结点使用的网络类型。可能的值： <br/>  有线 <br/>  Wifi <br/>  MobileBB <br/>  隧道 <br/>  其他 <br/> |空值表示终结点未报告此数据。  <br/> |有线  <br/> |
|Second Network Connection Detail  <br/> |字符串  <br/> | 第二终结点使用的网络类型。可能的值： <br/>  有线 <br/>  Wifi <br/>  MobileBB <br/>  隧道 <br/>  其他 <br/> |空值表示终结点未报告此数据。  <br/> |有线  <br/> |
|Stream Direction  <br/> |字符串  <br/> | 指示流在终结点之间的方向。可能的值： <br/>  第一到第二 <br/>  第二到第一 <br/> |空值表示没有报告可以指示流方向的数据。  <br/> |第一到第二  <br/> |
|Payload Description  <br/> |字符串  <br/> |流中最后使用的编解码器的名称。  <br/> |空值表示没有数据可用。  <br/> |SILKWide  <br/> |
|Audio and Video Call  <br/> |布尔值  <br/> |如果通话同时包括音频流和视频流，则为 True，否则为 False。  <br/> |空值表示没有报告可以指示流媒体类型的数据。  <br/> |True  <br/> |
|Duration 5 seconds or less  <br/> |布尔值  <br/> |如果流的持续时间小于或等于 5 秒，则为 True，否则为 False。  <br/> |-  <br/> |true  <br/> |
|Duration 60 seconds or more  <br/> |布尔值  <br/> |如果流的持续时间大于或等于 60 秒，则为 True，否则为 False。  <br/> |-  <br/> |true  <br/> |
|Duration (Seconds)  <br/> |范围（秒）  <br/> |流的持续时间，以秒为单位。值按范围分组表示。  <br/> |-  <br/> |062: [1 -2)  <br/> |
|Duration (Minutes)  <br/> |范围（分钟）  <br/> |流的持续时间，以分钟为单位。值按范围分组表示。  <br/> |-  <br/> |065: [3 - 4)  <br/> |
|EndTime  <br/> |日期时间  <br/> |流结束的时间。请注意，此维度可能包含过多的行，导致无法用作报告中的一个维度。它可能会转为用作筛选器。  <br/> |-  <br/> |2017-02-01 T00:00:01  <br/> |
|年  <br/> |整型  <br/> |流开始的年份。  <br/> |-  <br/> |2017  <br/> |
|月  <br/> |整型  <br/> |流开始的月份。  <br/> |-  <br/> |2  <br/> |
|日  <br/> |整型  <br/> |流开始的日期。  <br/> |-  <br/> |1  <br/> |
|小时  <br/> |整型  <br/> |流开始的小时时间。  <br/> |-  <br/> |1  <br/> |
|分钟  <br/> |整型  <br/> |流开始的分钟时间。  <br/> |-  <br/> |30  <br/> |
|秒  <br/> |整型  <br/> |流开始的秒钟时间。  <br/> |-  <br/> |12  <br/> |
|Day Of Year  <br/> |整型  <br/> |流的开始日期是一年中的第几天。  <br/> |-  <br/> |32  <br/> |
|Day Of Week  <br/> |字符串  <br/> |流的开始时间是星期几。  <br/> |-  <br/> |星期三  <br/> |
|Day Number Of Week  <br/> |整型  <br/> |流的开始时间是一周的第几天。  <br/> |-  <br/> |3  <br/> |
|Month Year  <br/> |字符串  <br/> |流开始的月份和年份。  <br/> |-  <br/> |2017-02  <br/> |
|Full Month  <br/> |日期时间  <br/> |流开始的完整月份。  <br/> |-  <br/> |2017-02-01 T00:0:00  <br/> |
|First Domain  <br/> |字符串  <br/> |使用第一终结点的用户的域。如果第一终结点是会议服务器，则为会议组织者的域。也可能是场景中使用的服务帐户的域。  <br/> |-  <br/> |contoso.com  <br/> |
|Second Domain  <br/> |字符串  <br/> |使用第二终结点的用户的域。如果第二终结点是会议服务器，则为会议组织者的域。也可能是场景中使用的服务帐户的域。  <br/> |-  <br/> |contoso.com  <br/> |
|First User Agent Category  <br/> |字符串  <br/> |第一终结点的用户代理的类别。  <br/> |空值表示当前没有映射的用户代理，如第三方用户代理。  <br/> |OC  <br/> |
|Second User Agent Category  <br/> |字符串  <br/> |第二终结点的用户代理的类别。  <br/> |空值表示当前没有映射的用户代理，如第三方用户代理。  <br/> |OC  <br/> |
|First User Agent  <br/> |字符串  <br/> |第一终结点的用户代理字符串。  <br/> |空值表示第一终结点未报告用户代理。  <br/> |UCCAPI/16.0.7766.5281 OC/16.0.7766.2047 (Skype for Business)  <br/> |
|Second User Agent  <br/> |字符串  <br/> |第二终结点的用户代理字符串。  <br/> |空值表示第二终结点未报告用户代理。  <br/> |UCCAPI/16.0.7766.5281 OC/16.0.7766.2047 (Skype for Business)  <br/> |
|Conference Type  <br/> |字符串  <br/> | 会议 URI 的类型。可能的值： <br/>  conf:applicationsharing <br/>  conf:audio-video <br/>  conf:focus <br/> |空值表示非会议场景。  <br/> |conf:audio-video  <br/> |
|Conference Id  <br/> |字符串  <br/> |与流关联的会议 ID。请注意，此维度可能包含过多的行，导致无法用作报告中的一个维度。它可能会转为用作筛选器。  <br/> |空值表示非会议场景。  <br/> |0001P6GK  <br/> |
|First Client App Version  <br/> |字符串  <br/> |第一终结点使用的应用程序的版本。数据从用户代理字符串解析。  <br/> |空值表示无法解析版本字符串或未报告该值。  <br/> |16.0.7766.2047  <br/> |
|Second Client App Version  <br/> |字符串  <br/> |第二终结点使用的应用程序的版本。数据从用户代理字符串解析。  <br/> |空值表示无法解析版本字符串或未报告该值。  <br/> |16.0.7766.2047  <br/> |
|Transport  <br/> |字符串  <br/> | 流使用的网络传输类型。可能的值： <br/>  UDP <br/>  TCP <br/>  无法识别 <br/>  "无法识别"表示系统无法确定传输类型是 TCP 还是 UDP。 <br/> |空值表示未报告传输类型或未建立媒体路径。  <br/> |UDP  <br/> |
|First Connectivity Ice  <br/> |字符串  <br/> | 第一终结点使用的 ICE 连接类型。可能的值： <br/>  直接 - 直接网络路径 <br/>  中继 - 通过中继 <br/>  HTTP - 通过 HTTP 代理 <br/>  失败 - 连接失败。 <br/> |空值表示未报告连接类型或未建立媒体路径。  <br/> |直接  <br/> |
|Second Connectivity Ice  <br/> |字符串  <br/> | 第二终结点使用的 ICE 连接类型。可能的值： <br/>  直接 - 直接网络路径 <br/>  中继 - 通过中继 <br/>  HTTP - 通过 HTTP 代理 <br/>  失败 - 连接失败。 <br/> |空值表示未报告连接类型或未建立媒体路径。  <br/> |直接  <br/> |
|First IP Address  <br/> |字符串  <br/> |第一终结点的 IP 地址。请注意，此维度可能包含过多的行，导致无法用作报告中的一个维度。它可能会转为用作筛选器。  <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |10.0.0.10  <br/> |
|Second IP Address  <br/> |字符串  <br/> |第二终结点的 IP 地址。  <br/> > [!注释]> 此维度可能包含过多的行，导致无法用作报告中的一个维度。它可能会转为用作筛选器。           |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |10.0.0.10  <br/> |
|First Link Speed  <br/> |位/秒  <br/> |第一终结点使用的网络适配器报告的链路速度，以"位/秒"为单位。  <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |10000000  <br/> |
|Second Link Speed  <br/> |位/秒  <br/> |第二终结点使用的网络适配器报告的链路速度，以"位/秒"为单位。  <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |10000000  <br/> |
|First Port  <br/> |端口号  <br/> |第一终结点用于媒体的网络端口号。  <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |50018  <br/> |
|Second Port  <br/> |端口号  <br/> |第二终结点用于媒体的网络端口号。  <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |50018  <br/> |
|First Reflexive Local IP  <br/> |字符串  <br/> |媒体中继服务器观察到的第一终结点的 IP 地址。通常是与流的第一终结点关联的公共内部 IP 地址。  <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |104.43.195.251  <br/> |
|Second Reflexive Local IP  <br/> |字符串  <br/> |媒体中继服务器观察到的第二终结点的 IP 地址。通常是与流的第二终结点关联的公共内部 IP 地址。  <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |104.43.195.251  <br/> |
|First Relay IP  <br/> |字符串  <br/> |第一终结点分配的媒体中继服务器的 IP 地址。  <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |104.43.195.251  <br/> |
|Second Relay IP  <br/> |字符串  <br/> |第二终结点分配的媒体中继服务器的 IP 地址。  <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |104.43.195.251  <br/> |
|First Relay Port  <br/> |整型  <br/> |第一终结点在媒体中继服务器上分配的媒体端口。  <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |3478  <br/> |
|Second Relay Port  <br/> |整型  <br/> |第二终结点在媒体中继服务器上分配的媒体端口。  <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |3478  <br/> |
|First Subnet  <br/> |字符串  <br/> |第一终结点用于媒体流的子网，每个八进制数用短划线隔开。  <br/> |空值指示未建立媒体路径，或使用 IPv6 不报告终结点，此数据。  <br/> |104.43.195.0  <br/> |
|Second Subnet  <br/> |字符串  <br/> |第二终结点用于媒体流的子网，每个八进制数用短划线隔开。  <br/> |空值指示未建立媒体路径，或使用 IPv6 不报告终结点，此数据。  <br/> |104.43.195.0  <br/> |
|First VPN  <br/> |布尔值  <br/> |如果第一终结点使用的网络适配器指出它是 VPN 连接则为 True，否则为 False。有些 VPN 不会正确报告此数据。  <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |True  <br/> |
|Second VPN  <br/> |布尔值  <br/> |如果第二终结点使用的网络适配器指出它是 VPN 连接则为 True，否则为 False。有些 VPN 不会正确报告此数据。  <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |True  <br/> |
|Applied Bandwidth Source  <br/> |字符串  <br/> | 指示应用于流的带宽来源。可能的值： <br/>  Static Max <br/>  API Modality <br/>  API Modality_All <br/>  Api SendSide BWLimit <br/>  首选值 <br/>  TURN <br/>  ReceiveSide TURN <br/>  API SDP Modality、Remote RecvSide BWLimit <br/>  API ServiceQuality <br/>  API SDP <br/>  Receive SidePDP <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |StaticMax  <br/> |
|Bandwidth Est  <br/> |范围（位/秒）  <br/> |第一和第二终结点之间可用的平均带宽估计值，以"位/秒"为单位。  <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |026: [260000 - 270000)  <br/> |
|Mediation Server Bypass Flag  <br/> |布尔值  <br/> |如果媒体流绕过中介服务器，在客户端与 PSTN 网关/PBX 之间直接传输，则为 True。否则为 False。  <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |True  <br/> |
|First Cdr Connectivity Type  <br/> |字符串  <br/> | 指示第一终结点选择用于此流的 ICE 连接路径。可能的值； <br/>  OS <br/>  PeerDerived <br/>  Stun <br/>  Turn <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |OS  <br/> |
|Second Cdr Connectivity Type  <br/> |字符串  <br/> | 指示第二终结点选择用于此流的 ICE 连接路径。可能的值； <br/>  OS <br/>  PeerDerived <br/>  Stun <br/>  Turn <br/> |空值表示终结点未报告此数据或未建立媒体路径。  <br/> |OS  <br/> |
|First Capture Dev  <br/> |字符串  <br/> | 第一终结点使用的捕获设备的名称。对于： <br/>  音频流 - 用于麦克风的设备 <br/>  视频流 - 用于照相机的设备 <br/>  基于视频的屏幕共享流 - 屏幕截取器 <br/>  应用共享流 - 空 <br/> |空值表示终结点未报告此数据、未建立媒体路径或流为基于视频的屏幕共享或应用程序共享。  <br/> |头戴式麦克风 (Microsoft LifeChat LX-6000)  <br/> |
|Second Capture Dev  <br/> |字符串  <br/> | 第二终结点使用的捕获设备的名称。对于： <br/>  音频流 - 用于麦克风的设备 <br/>  视频流 - 用于照相机的设备 <br/>  基于视频的屏幕共享流 - 屏幕截取器 <br/>  应用共享流 - 空 <br/> |空值表示终结点未报告此数据、未建立媒体路径或流为基于视频的屏幕共享或应用程序共享。  <br/> |头戴式麦克风 (Microsoft LifeChat LX-6000)  <br/> |
|First Capture Dev Driver  <br/> |字符串  <br/> | 第一终结点使用的捕获设备驱动器的名称，格式为"制造商: 版本"。对于： <br/>  音频流 - 用于麦克风的驱动器 <br/>  视频流 - 用于照相机的驱动器 <br/>  基于视频的屏幕共享和应用共享流 - 空 <br/> |空值表示终结点未报告此数据、未建立媒体路径或流为基于视频的屏幕共享或应用程序共享。  <br/> |Microsoft: 10.0.14393.0  <br/> |
|Second Capture Dev Driver  <br/> |字符串  <br/> | 第二终结点使用的捕获设备驱动器的名称，格式为"制造商: 版本"。对于： <br/>  音频流 - 用于麦克风的驱动器 <br/>  视频流 - 用于照相机的驱动器 <br/>  基于视频的屏幕共享和应用共享流 - 空 <br/> |空值表示终结点未报告此数据、未建立媒体路径或流为基于视频的屏幕共享或应用程序共享。  <br/> |Microsoft: 10.0.14393.0  <br/> |
|First Render Dev  <br/> |字符串  <br/> | 第一终结点使用的呈现设备的名称。对于： <br/>  音频流 - 用于麦克风的驱动器 <br/>  视频流 - 用于照相机的驱动器 <br/>  基于视频的屏幕共享和应用共享流 - 空 <br/> |空值表示终结点未报告此数据、未建立媒体路径或流为基于视频的屏幕共享或应用程序共享。  <br/> |头戴式麦克风 (Microsoft LifeChat LX-6000)  <br/> |
|Second Render Dev  <br/> |字符串  <br/> | 第二终结点使用的呈现设备的名称。对于： <br/>  音频流 - 用于麦克风的驱动器 <br/>  视频流 - 用于照相机的驱动器 <br/>  基于视频的屏幕共享和应用共享流 - 空 <br/> |空值表示终结点未报告此数据、未建立媒体路径或流为基于视频的屏幕共享或应用程序共享。  <br/> |头戴式麦克风 (Microsoft LifeChat LX-6000)  <br/> |
|First Render Dev Driver  <br/> |字符串  <br/> | 第一终结点使用的呈现设备驱动器的名称。对于： <br/>  音频流 - 用于麦克风的驱动器 <br/>  视频流 - 用于照相机的驱动器 <br/>  基于视频的屏幕共享和应用共享流 - 空 <br/> |空值表示终结点未报告此数据、未建立媒体路径或流为基于视频的屏幕共享或应用程序共享。  <br/> |Microsoft: 10.0.14393.0  <br/> |
|Second Render Dev Driver  <br/> |字符串  <br/> | 第二终结点使用的呈现设备驱动器的名称。对于： <br/>  音频流 - 用于麦克风的驱动器 <br/>  视频流 - 用于照相机的驱动器 <br/>  基于视频的屏幕共享和应用共享流 - 空 <br/> |空值表示终结点未报告此数据、未建立媒体路径或流为基于视频的屏幕共享或应用程序共享。  <br/> |Microsoft: 10.0.14393.0  <br/> |
|First CPU Name  <br/> |字符串  <br/> |第一终结点使用的 CPU 的名称。  <br/> |空值表示终结点未报告此数据。  <br/> |Contoso CPU X11 @ 1.80GHz  <br/> |
|Second CPU Name  <br/> |字符串  <br/> |第二终结点使用的 CPU 的名称。  <br/> |空值表示终结点未报告此数据。  <br/> |Contoso CPU X11 @ 1.80GHz  <br/> |
|First CPU Number Of Cores  <br/> |内核数量  <br/> |第一终结点上可用的 CPU 内核数。  <br/> |空值表示终结点未报告此数据。  <br/> |8  <br/> |
|Second CPU Number Of Cores  <br/> |内核数量  <br/> |第二终结点上可用的 CPU 内核数。  <br/> |空值表示终结点未报告此数据。  <br/> |8  <br/> |
|First CPU Processor Speed  <br/> |CPU 速度，单位为 MHz  <br/> |第一终结点使用的 CPU 的速度，单位为 MHz。  <br/> |空值表示终结点未报告此数据。  <br/> |1800  <br/> |
|Second CPU Processor Speed  <br/> |CPU 速度，单位为 MHz  <br/> |第二终结点使用的 CPU 的速度，单位为 MHz。  <br/> |空值表示终结点未报告此数据。  <br/> |1800  <br/> |
|First Endpoint  <br/> |字符串  <br/> |如果第一终结点为服务器或云服务客户端，此终结点报告的计算机名称。  <br/> |空值表示终结点未报告此数据。  <br/> |计算机名称  <br/> |
|Second Endpoint  <br/> |字符串  <br/> |如果第二终结点为服务器或云服务客户端，此终结点报告的计算机名称。  <br/> |空值表示终结点未报告此数据。  <br/> |计算机名称  <br/> |
|First OS  <br/> |字符串  <br/> |第一终结点报告的完整操作系统和体系结构字符串。  <br/> |空值表示终结点未报告此数据。  <br/> |Windows 10.0.14996 SP: 0.0 Type: 1(Workstation) Suite: 256 Arch: x64 WOW64: True  <br/> |
|Second OS  <br/> |字符串  <br/> |第二终结点报告的完整操作系统和体系结构字符串。  <br/> |空值表示终结点未报告此数据。  <br/> |Windows 10.0.14996 SP: 0.0 Type: 1(Workstation) Suite: 256 Arch: x64 WOW64: True  <br/> |
|First OS Filtered  <br/> |字符串  <br/> |第一终结点报告的操作系统名称和主要版本及次要版本。有时候此字符串可能包含多个操作系统名称和版本。  <br/> |空值表示此终结点没有报告该信息或没有收到此终结点的报告。  <br/> |Windows 10  <br/> |
|Second OS Filtered  <br/> |字符串  <br/> |第二终结点报告的操作系统名称和主要版本及次要版本。有时候此字符串可能包含多个操作系统名称和版本。  <br/> |空值表示此终结点没有报告该信息或没有收到此终结点的报告。  <br/> |Windows 10  <br/> |
|First OS Architecture  <br/> |字符串  <br/> |第一终结点报告的硬件体系结构。  <br/> |空值表示此终结点没有报告该信息、没有收到此终结点的报告或无法识别体系结构的格式。  <br/> |x64  <br/> |
|Second OS Architecture  <br/> |字符串  <br/> |第二终结点报告的硬件体系结构。  <br/> |空值表示此终结点没有报告该信息、没有收到此终结点的报告或无法识别体系结构的格式。  <br/> |x64  <br/> |
|First Virtualization Flag  <br/> |字符串  <br/> | 指示第一终结点报告的虚拟化环境类型的标志。可能的值： <br/>  "0x00"- 无 <br/>  "0x01"- HyperV <br/>  "0x02"- VMWare <br/>  "0x04" - 虚拟 PC <br/>  "0x08"- Xen PC <br/> |空值表示终结点未报告此数据。  <br/> |0x00  <br/> |
|Second Virtualization Flag  <br/> |字符串  <br/> | 指示第二终结点报告的虚拟化环境类型的标志。可能的值： <br/>  "0x00"- 无 <br/>  "0x01"- HyperV <br/>  "0x02"- VMWare <br/>  "0x04" - 虚拟 PC <br/>  "0x08"- Xen PC <br/> |空值表示终结点未报告此数据。  <br/> |0x00  <br/> |
|First Wifi Microsoft Driver  <br/> |字符串  <br/> |第一终结点报告的所使用的 Microsoft WiFi 驱动器的名称。值可能会根据终结点使用的语言进行本地化。  <br/> |空值表示终结点没有使用 WiFi 或未报告驱动器信息。  <br/> |Microsoft 托管网络虚拟适配器  <br/> |
|Second Wifi Microsoft Driver  <br/> |字符串  <br/> |第二终结点报告的所使用的 Microsoft WiFi 驱动器的名称。值可能会根据终结点使用的语言进行本地化。  <br/> |空值表示终结点没有使用 WiFi 或未报告驱动器信息。  <br/> |Microsoft 托管网络虚拟适配器  <br/> |
|First Wifi Vendor Driver  <br/> |字符串  <br/> |第一终结点报告的 Wifi 驱动器的供应商和名称。  <br/> |空值表示终结点没有使用 WiFi 或未报告驱动器信息。  <br/> |Contoso 双频 Wireless-AC 驱动器  <br/> |
|Second Wifi Vendor Driver  <br/> |字符串  <br/> |第二终结点报告的 Wifi 驱动器的供应商和名称。  <br/> |空值表示终结点没有使用 WiFi 或未报告驱动器信息。  <br/> |Contoso 双频 Wireless-AC 驱动器  <br/> |
|First Wifi Microsoft Driver Version  <br/> |字符串  <br/> |第一终结点报告的 Microsoft Wifi 驱动器的版本。  <br/> |空值表示终结点没有使用 WiFi 或未报告驱动器信息。  <br/> |Microsoft:10.0.14393.0  <br/> |
|Second Wifi Microsoft Driver Version  <br/> |字符串  <br/> |第二终结点报告的 Microsoft Wifi 驱动器的版本。  <br/> |空值表示终结点没有使用 WiFi 或未报告驱动器信息。  <br/> |Microsoft:10.0.14393.0  <br/> |
|First Wifi Vendor Driver Version  <br/> |字符串  <br/> |第一终结点报告的 Wifi 驱动器的供应商和版本。  <br/> |空值表示终结点没有使用 WiFi 或未报告驱动器信息。  <br/> |Contoso:15.1.1.0  <br/> |
|Second Wifi Vendor Driver Version  <br/> |字符串  <br/> |第二终结点报告的 Wifi 驱动器的供应商和版本。  <br/> |空值表示终结点没有使用 WiFi 或未报告驱动器信息。  <br/> |Contoso:15.1.1.0  <br/> |
|First Wifi Channel  <br/> |字符串  <br/> |第一终结点使用的 Wifi 频道。  <br/> |空值表示未使用 WiFi 或未报告频道。  <br/> |10  <br/> |
|Second Wifi Channel  <br/> |字符串  <br/> |第二终结点使用的 Wifi 频道。  <br/> |空值表示未使用 WiFi 或未报告频道。  <br/> |10  <br/> |
|First Wifi Radio Type  <br/> |字符串  <br/> |第一终结点使用的 WiFi 无线电的类型。HRDSSS 等于 802.11b。  <br/> |空值表示未使用 WiFi 或未报告 WiFi 类型。  <br/> |802.11ac  <br/> |
|Second Wifi Radio Type  <br/> |字符串  <br/> |第二终结点使用的 WiFi 无线电的类型。HRDSSS 等于 802.11b。  <br/> |空值表示未使用 WiFi 或未报告 WiFi 类型。  <br/> |802.11ac  <br/> |
|First DNS Suffix  <br/> |字符串  <br/> |第一终结点报告的与网络适配器关联的 DNS 后缀。请注意，可能会为任何类型的网络适配器报告此值。  <br/> |空值表示终结点未报告此值。  <br/> |corp.contoso.com  <br/> |
|Second DNS Suffix  <br/> |字符串  <br/> |第二终结点报告的与网络适配器关联的 DNS 后缀。请注意，可能会为任何类型的网络适配器报告此值。  <br/> |空值表示终结点未报告此值。  <br/> |corp.contoso.com  <br/> |
|First Wifi Band  <br/> |字符串  <br/> |第一终结点报告的所使用的 Wifi 波段。  <br/> |空值表示终结点未计算或未报告此值。  <br/> |5.0 Ghz  <br/> |
|Second Wifi Band  <br/> |字符串  <br/> |第二终结点报告的所使用的 Wifi 波段。  <br/> |空值表示终结点未计算或未报告此值。  <br/> |5.0 Ghz  <br/> |
|First Wifi Signal Strength  <br/> |字符串  <br/> |第一终结点报告的 WiFi 信号强度百分比 [0-99]。  <br/> |空值表示终结点未计算或未报告此值。  <br/> |081: [90 - 100)  <br/> |
|Second Wifi Signal Strength  <br/> |字符串  <br/> |第二终结点报告的 WiFi 信号强度百分比 [0-99]。  <br/> |空值表示终结点未计算或未报告此值。  <br/> |081: [90 - 100)  <br/> |
|First Wifi Battery Charge  <br/> |范围（百分比）  <br/> |第一终结点报告的电池剩余电量的百分比估计值 [0-99]。值按范围分组表示。0 表示设备已插电。  <br/> |空值表示未使用 WiFi 或未报告电量值。  <br/> |081: [90 - 100)  <br/> |
|Second Wifi Battery Charge  <br/> |范围（百分比）  <br/> |第二终结点报告的电池剩余电量的百分比估计值 [0-99]。值按范围分组表示。0 表示设备已插电。  <br/> |空值表示未使用 WiFi 或未报告电量值。  <br/> |081: [90 - 100)  <br/> |
|Audio Degradation Avg  <br/> |范围（平均意见得分 0-5）  <br/> |关于流降级的网络平均意见得分的平均值。表示网络损耗和抖动对所收到的音频质量的影响程度。值按范围分组表示。  <br/> |空值表示接收流的终结点没有报告网络 MOS 降级，或者此流不是音频流。  <br/> |015: [0.01 - 0.02)  <br/> |
|Jitter  <br/> |范围（毫秒）  <br/> |流的平均抖动值，以毫秒为单位。值按范围分组表示。  <br/> |空值表示接收流的终结点没有报告抖动数据。  <br/> |065: [2 - 3)  <br/> |
|Jitter Max  <br/> |范围（毫秒）  <br/> |流的最大抖动值，以毫秒为单位。值按范围分组表示。  <br/> |空值表示接收流的终结点没有报告抖动数据。  <br/> |065: [2 - 3)  <br/> |
|Packet Loss Rate  <br/> |范围（百分比）  <br/> |流的平均丢包率。值按范围分组表示。  <br/> |空值表示接收流的终结点没有报告丢包数据。  <br/> |050: [1.8 - 1.9)  <br/> |
|Packet Loss Rate Max  <br/> |范围（百分比）  <br/> |流的最大丢包率。值按范围分组表示。  <br/> |空值表示接收流的终结点没有报告丢包数据。  <br/> |041: [0.95 - 1)  <br/> |
|Overall Avg Network MOS  <br/> |范围 (MOS)  <br/> |流的网络 MOS 平均值。值按范围分组表示。  <br/> |空值表示接收流的终结点没有报告网络 MOS 降级，或者此流不是音频流。  <br/> |076: [4.4 - 4.5)  <br/> |
|Ratio Concealed Samples Avg  <br/> |范围（比率）  <br/> |含有丢包隐藏生成样本的音频帧数与总音频帧数的比率。值按范围分组表示。0.1 表示 10% 的帧包含隐藏样本。  <br/> |空值表示流的接收方没有报告此值，或者流不是音频流。  <br/> |015: [0.01 - 0.02)  <br/> |
|Ratio Stretched Samples Avg  <br/> |范围（比率）  <br/> |通过拉伸样本补偿抖动或丢失的音频帧数与总音频帧数的比率。值按范围分组表示。0.1 表示 10% 的音频帧包含拉伸样本。  <br/> |空值表示流的接收方没有报告此值，或者流不是音频流。  <br/> |017: [0.03 - 0.04)  <br/> |
|Round Trip  <br/> |范围（毫秒）  <br/> |计算的平均网络传播往返时间，根据 RFC3550 以毫秒为单位指定。值按范围分组表示。  <br/> |空值表示终结点未计算或未报告此值。  <br/> |070: [15 - 20)  <br/> |
|Round Trip Max  <br/> |范围（毫秒）  <br/> |计算的最大网络传播往返时间，根据 RFC3550 以毫秒为单位指定。值按范围分组表示。  <br/> |空值表示终结点未计算或未报告此值。  <br/> |098: [350 - 375)  <br/> |
|Network Jitter Avg  <br/> |范围（毫秒）  <br/> |会话期间以 20 秒时间窗口计算的平均网络抖动，以毫秒为单位。值按范围分组表示。  <br/> |空值表示流不是音频流，或接收流的终结点未报告此数据。  <br/> |066: [3 - 4)  <br/> |
|Video Post FECPLR  <br/> |范围（比率）  <br/> |应用 FEC 后，跨所有视频流和编解码器汇总的丢包率。值按范围分组表示。  <br/> |空值表示流不是视频流或基于视频的屏幕共享流，或接收流的终结点未报告此数据。  <br/> |014: [0 - 0.01)  <br/> |
|Video Local Frame Loss Percentage Avg  <br/> |范围（百分比）  <br/> |向用户显示的视频帧丢失平均百分比。值按范围分组表示。其中包括从网络丢失恢复的帧。  <br/> |空值表示流不是视频流或基于视频的屏幕共享流，或接收流的终结点未报告此数据。  <br/> |160: [80 - 85)  <br/> |
|Recv Frame Rate Average  <br/> |范围（每秒帧数）  <br/> |在会话持续期间计算到的所有视频流每秒接收的平均帧数。值按范围分组表示。  <br/> |空值表示流不是视频流或基于视频的屏幕共享流，或接收流的终结点未报告此数据。  <br/> |101: [14.5 - 15)  <br/> |
|Low Frame Rate Call Percent  <br/> |范围（百分比）  <br/> |帧速率低于 7.5 帧/秒的通话时间的百分比。值按范围分组表示。  <br/> |空值表示流不是视频流或基于视频的屏幕共享流，或接收流的终结点未报告此数据。  <br/> |099: [13.5 - 14)  <br/> |
|Low Resolution Call Percent  <br/> |范围（百分比）  <br/> |分辨率较低的通话时间的百分比。值按范围分组表示。较小维度的阈值为 120 像素。  <br/> |空值表示流不是视频流或基于视频的屏幕共享流，或接收流的终结点未报告此数据。  <br/> ||
|Video Packet Loss Rate  <br/> |范围（比率）  <br/> |在会话持续期间计算到的平均丢包比率（小数），根据 RFC3550 指定。值按范围分组表示。  <br/> |空值表示流不是视频流或基于视频的屏幕共享流，或接收流的终结点未报告此数据。  <br/> |037: [0.75 - 0.8)  <br/> |
|Video Frame Rate Avg  <br/> |范围（每秒帧数）  <br/> |在会话持续期间计算到的视频流每秒接收的平均帧数。值按范围分组表示。  <br/> |空值表示流不是视频流或基于视频的屏幕共享流，或接收流的终结点未报告此数据。  <br/> |135: [31.5 - 32)  <br/> |
|Dynamic Capability Percent  <br/> |范围（百分比）  <br/> |客户端以低于此类型 CPU 预期视频处理容量的 70% 运行的时间的百分比，按范围分组。  <br/> |空值表示流不是视频流或基于视频的屏幕共享流，或接收流的终结点未报告此数据。  <br/> |122: [25 - 25.5)  <br/> |
|Spoiled Tile Percent Total  <br/> |范围（百分比）  <br/> |没有被发送到远程对等点（例如，从 MCU 到查看器）而是被丢弃的图块的百分比。值按范围分组表示。丢弃图块可能是由于客户端与服务器之间的带宽限制所致。  <br/> |空值表示流不是应用程序共享流，或发送流的终结点未报告此数据。  <br/> |140: [34 - 34.5)  <br/> |
|AppSharing Relative OneWay Average  <br/> |范围（毫秒）  <br/> |终结点之间的应用程序共享流的相对单向平均延迟，以毫秒为单位。值按范围分组表示。  <br/> |空值表示流不是应用程序共享流，或发送流的终结点未报告此数据。  <br/> |126: [27 - 27.5)  <br/> |
|AppSharing RDP Tile Processing Latency Average  <br/> |范围（毫秒）  <br/> |在会议服务器上处理 RDP 堆栈图块的平均延迟，以毫秒为单位。值按范围分组表示。  <br/> |空值表示流不是会议中的应用程序共享流，或发送流的终结点未报告此数据。  <br/> |103: [15.5 - 16)  <br/> |
|Audio FEC Used  <br/> |布尔值  <br/> |True 表示通话期间在某些点上使用了音频前向纠错 (FEC)。False 表示未使用。  <br/> |空值表示流不是音频流，或发送流的终结点未报告此数据。  <br/> |True  <br/> |
|ClassifiedPoorCall  <br/> |布尔值  <br/> |如果根据以下文章中列出的指标将流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |空值表示没有报告可以将流分类为好或差的足够指标。  <br/> |True  <br/> |
|Video Poor Due To VideoPostFecplr  <br/> |布尔值  <br/> |如果根据以下文章中列出的"FEC PLR 后的视频"指标阈值将流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于非视频流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是视频流。  <br/> |true  <br/> |
|Video Poor Due To Video Local Frame Loss Percentage Avg  <br/> |布尔值  <br/> |如果根据以下文章中列出的"视频本地帧丢失平均百分比"指标阈值将视频流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于非视频流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是视频流。  <br/> |true  <br/> |
|Video Poor Due To Recv Frame Rate Average  <br/> |布尔值  <br/> |如果根据以下文章中列出的"帧平均接收速率"指标阈值将视频流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于非视频流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是视频流。  <br/> |true  <br/> |
|Video Poor Due To Low Frame Rate Call Percent  <br/> |布尔值  <br/> |如果根据以下文章中列出的"低帧速率通话百分比"指标阈值将视频流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于非视频流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是视频流。  <br/> |true  <br/> |
|Video Poor Due To Low Resolution Call Percent  <br/> |布尔值  <br/> |如果根据以下文章中列出的"低分辨率通话百分比"指标阈值将视频流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于非视频流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是视频流。  <br/> |true  <br/> |
|Video Poor Due To Video Packet Loss Rate  <br/> |布尔值  <br/> |如果根据以下文章中列出的"视频丢包率"指标阈值将视频流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds.)。对于非视频流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是视频流。  <br/> |true  <br/> |
|Video Poor Due To Video Frame Rate Avg  <br/> |布尔值  <br/> |如果根据以下文章中列出的"视频帧平均速率"指标阈值将视频流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于非视频流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是视频流。  <br/> |true  <br/> |
|Video Poor Due To Dynamic Capability Percent  <br/> |布尔值  <br/> |如果根据以下文章中列出的"动态容量百分比"指标阈值将视频流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于非视频流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是视频流。  <br/> |true  <br/> |
|VBSS Poor Due To Video Post Fec plr  <br/> |布尔值  <br/> |如果根据以下文章中列出的"FEC PLR 后的视频"指标阈值将基于视频的屏幕共享流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于基于视频的屏幕共享流以外的流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是基于视频的屏幕共享流。  <br/> |true  <br/> |
|VBSS Poor Due To Video Local Frame Loss Percentage Avg  <br/> |布尔值  <br/> |如果根据以下文章中列出的"视频本地帧丢失平均百分比"指标阈值将基于视频的屏幕共享流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于基于视频的屏幕共享流以外的流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是基于视频的屏幕共享流。  <br/> |true  <br/> |
|VBSS Poor Due To Recv Frame Rate Average  <br/> |布尔值  <br/> |如果根据以下文章中列出的"帧平均接收速率"指标阈值将基于视频的屏幕共享流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于基于视频的屏幕共享流以外的流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是基于视频的屏幕共享流。  <br/> |true  <br/> |
|VBSS Poor Due To Low Frame Rate Call Percent  <br/> |布尔值  <br/> |如果根据以下文章中列出的"低帧速率通话百分比"指标阈值将基于视频的屏幕共享流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于基于视频的屏幕共享流以外的流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是基于视频的屏幕共享流。  <br/> |true  <br/> |
|VBSS Poor Due To LowResolutionCallPercent  <br/> |布尔值  <br/> |如果根据以下文章中列出的"低分辨率通话百分比"指标阈值将 VBSS 分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于基于视频的屏幕共享流以外的流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是基于视频的屏幕共享流。  <br/> |true  <br/> |
|AppSharing Poor Due To Spoiled Tile Percent Total  <br/> |布尔值  <br/> |如果根据以下文章中列出的"总损坏图块百分比"指标阈值将应用程序共享流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于非应用程序共享流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是应用程序共享流。  <br/> |true  <br/> |
|AppSharing Poor Due To Relative OneWay Average  <br/> |布尔值  <br/> |如果根据以下文章中列出的"相对单向平均延迟"指标阈值将应用程序共享流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于非应用程序共享流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是应用程序共享流。  <br/> |true  <br/> |
|AppSharing Poor Due To RDP Tile Processing Latency Average  <br/> |布尔值  <br/> |如果根据以下文章中列出的"RDP 图块处理平均延迟"指标阈值将应用程序共享流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于非应用程序共享流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是应用程序共享流。  <br/> |true  <br/> |
|Audio Poor Due To Jitter  <br/> |布尔值  <br/> |如果根据以下文章中列出的"抖动"指标阈值将音频流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于非音频流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是音频共享流。  <br/> |true  <br/> |
|Audio Poor Due To RoundTrip  <br/> |布尔值  <br/> |如果根据以下文章中列出的"往返时间"指标阈值将音频流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于非音频流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是音频共享流。  <br/> |true  <br/> |
|Audio Poor Due To Packet Loss  <br/> |布尔值  <br/> |如果根据以下文章中列出的"丢包"指标阈值将音频流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于非音频流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是音频共享流。  <br/> |true  <br/> |
|Audio Poor Due To Degradation  <br/> |布尔值  <br/> |如果根据以下文章中列出的"降级"指标阈值将音频流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于非音频流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是音频共享流。  <br/> |true  <br/> |
|Audio Poor Due To Concealed Ratio  <br/> |布尔值  <br/> |如果根据以下文章中列出的"隐藏比率"指标阈值将音频流分类为差，则为 True：[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。对于非音频流，始终为 False。  <br/> |空值表示终结点未报告此数据，或流不是音频共享流。  <br/> |true  <br/> |
|Unclassified  <br/> |布尔值  <br/> |如果具有可以将流分类为好或差的足够数据，则为 0。否则为 1。  <br/> |-  <br/> |1  <br/> |
|OnePercent PacketLoss  <br/> |布尔值  <br/> |如果丢包率超过 1%，则为 1。否则为 0。  <br/> |-  <br/> |1  <br/> |
|Poor Reason  <br/> |标志  <br/> | 用于确定为何将流分类为差的一系列标志。由于将流分类为差的原因有很多，因此可能会有设置多个标记。有关详细信息，请参阅[在 Lync 2013 QoE 中将通话分类为差的基础的是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/>  可能的值： <br/>  隐藏比率 <br/>  降级 <br/>  Jitter <br/>  丢包 <br/>  Round Trip <br/>  Dynamic Capability Percent <br/>  Low Frame Rate Call Percent <br/>  Recv Frame Rate Average <br/>  Video Frame Rate Avg <br/>  Video Local Frame Loss Percentage Avg <br/>  Video Packet Loss Rate <br/>  Fec plr 后的视频 <br/>  RDP 图块处理平均延迟 <br/>  相对单向平均延迟 总损坏图块百分比 <br/> |空值表示流未被分类为差。  <br/> |隐藏比率 | 降级  <br/> |
|Poor  <br/> |布尔值  <br/> |如果具有可以将流分类为好或差的足够数据且流被分类为差，则为 1。否则为 0。  <br/> |-  <br/> |1  <br/> |
|Good  <br/> |布尔值  <br/> |如果具有可以将流分类为好或差的足够数据且流被分类为好，则为 1。否则为 0。  <br/> |-  <br/> |1  <br/> |
|First Feedback Rating  <br/> |用户评级 (1-5)  <br/> |第一终结点对与流关联的通话进行的评级，等级为 1-5（5 = 很好）。0 表示向用户显示了通话评级调查，但用户没有对其体验进行评级。  <br/> |空值表示没有向第一终结点显示调查。  <br/> |5  <br/> |
|Second Feedback Rating  <br/> |用户评级 (1-5)  <br/> |第二终结点对与流关联的通话进行的评级，等级为 1-5（5 = 很好）。0 表示向用户显示了通话评级调查，但用户没有对其体验进行评级。  <br/> |空值表示没有向第二终结点显示调查。  <br/> |5  <br/> |
|First Feedback Tokens  <br/> |字符串  <br/> |包含反馈标记列表的字符串，每个反馈标记都具有布尔标志，用于指出该标记是否通过第一终结点的用户提供反馈进行了设置。  <br/> |空值表示第一终结点的用户没有提供反馈。  <br/> |{DistortedSpeech:1; ElectronicFeedback:1; BackgroundNoise:1; MuffledSpeech:1; Echo:1;}  <br/> |
|Second Feedback Tokens  <br/> |字符串  <br/> |包含反馈标记列表的字符串，每个反馈标记都具有布尔型标志，用于指出该标记是否通过第二终结点的用户提供反馈进行了设置。  <br/> |空值表示第二终结点的用户没有提供反馈。  <br/> |{DistortedSpeech:1; ElectronicFeedback:1; BackgroundNoise:1; MuffledSpeech:1; Echo:1;}  <br/> |
|First Feedback Has Audio Issue  <br/> |布尔值  <br/> |如果第一终结点的反馈标记指出流包含音频问题，则为 True，否则为 False。  <br/> |-  <br/> |false  <br/> |
|Second Feedback Has Audio Issue  <br/> |布尔值  <br/> |如果第二终结点的反馈标记指出流包含音频问题，则为 True，否则为 False。  <br/> |-  <br/> |false  <br/> |
|First Feedback Has Video Issue  <br/> |布尔值  <br/> |如果第一终结点的反馈标记指出流包含视频问题，则为 True，否则为 False。  <br/> |-  <br/> |false  <br/> |
|Second Feedback Has Video Issue  <br/> |布尔值  <br/> |如果第二终结点的反馈标记指出流包含视频问题，则为 True，否则为 False。  <br/> |-  <br/> |false  <br/> |
|First Echo Event Causes  <br/> |标志  <br/> | 指示第一终结点上发生设备回声事件的原因的标志。一个流可能拥有多个标志。标志包括： <br/>  BAD_TIMESTAMP - 从所使用的具有较差质量的捕获设备或呈现设备上获得的音频时间戳 <br/>  POSTAEC_ECHO - 消除回声后仍具有较高水平的回声 <br/>  MIC_CLIPPING - 拥有最大信号强度显著实例的捕获设备上的信号强度 <br/>  EVENT_ANLP - 包含高噪音的捕获设备上的音频采样。 <br/> |空值表示非音频流，或者第一终结点未报告事件原因。  <br/> |BAD_TIMESTAMP | POSTAEC_ECHO  <br/> |
|Second Echo Event Causes  <br/> |标志  <br/> | 指示第二终结点上发生设备回声事件的原因的标志。一个流可能拥有多个标志。标志包括： <br/>  BAD_TIMESTAMP - 从所使用的具有较差质量的捕获设备或呈现设备上获得的音频时间戳 <br/>  POSTAEC_ECHO - 消除回声后仍具有较高水平的回声 <br/>  MIC_CLIPPING - 拥有最大信号强度显著实例的捕获设备上的信号强度 <br/>  EVENT_ANLP - 包含高噪音的捕获设备上的音频采样。 <br/> |空值表示非音频流，或者第一终结点未报告事件原因。  <br/> |BAD_TIMESTAMP | POSTAEC_ECHO  <br/> |
|First Echo Percent Mic In  <br/> |范围（百分比）  <br/> |在消除回声之前，第一终结点从捕获设备或麦克风设备检测到音频中存在回声的时间百分比。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |068: [5 - 10)  <br/> |
|Second Echo Percent Mic In  <br/> |范围（百分比）  <br/> |在消除回声之前，第二终结点从捕获设备或麦克风设备检测到音频中存在回声的时间百分比。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |068: [5 - 10)  <br/> |
|First Echo Percent Send  <br/> |范围（百分比）  <br/> |在消除回声之后，第一终结点从捕获设备或麦克风设备检测到音频中存在回声的时间百分比。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |068: [5 - 10)  <br/> |
|Second Echo Percent Send  <br/> |范围（百分比）  <br/> |在消除回声之后，第二终结点从捕获设备或麦克风设备检测到音频中存在回声的时间百分比。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |068: [5 - 10)  <br/> |
|First Send Signal Level  <br/> |范围（dB、分贝）  <br/> |对于被分类为单声道语音或左声道立体声语音的音频，第一终结点发送的音频的平均能量水平。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |055: [-15 - -10)  <br/> |
|Second Send Signal Level  <br/> |范围（dB、分贝）  <br/> |对于被分类为单声道语音或左声道立体声语音的音频，第二终结点发送的音频的平均能量水平。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |055: [-15 - -10)  <br/> |
|First Recv Signal Level  <br/> |范围（dB、分贝）  <br/> |对于被分类为单声道语音或左声道立体声语音的音频，第一终结点接收的音频的平均能量水平。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |056: [-10 - -5)  <br/> |
|Second Recv Signal Level  <br/> |范围（dB、分贝）  <br/> |对于被分类为单声道语音或左声道立体声语音的音频，第二终结点接收的音频的平均能量水平。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |056: [-10 - -5)  <br/> |
|First Send Noise Level  <br/> |范围（dB、分贝）  <br/> |对于被分类为单声道噪音或左声道立体声噪音的音频，第一终结点发送的音频的平均能量水平。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |048: [-50 - -45)  <br/> |
|Second Send Noise Level  <br/> |范围（dB、分贝）  <br/> |对于被分类为单声道噪音或左声道立体声噪音的音频，第二终结点发送的音频的平均能量水平。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |048: [-50 - -45)  <br/> |
|First Recv Noise Level  <br/> |范围（dB、分贝）  <br/> |对于被分类为单声道噪音或左声道立体声噪音的音频，第一终结点接收的音频的平均能量水平。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |048: [-50 - -45)  <br/> |
|Second Recv Noise Level  <br/> |范围（dB、分贝）  <br/> |对于被分类为单声道噪音或左声道立体声噪音的音频，第二终结点接收的音频的平均能量水平。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |048: [-50 - -45)  <br/> |
|First Network Send Quality Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到网络导致已发送音频的质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |015: [0.01 - 0.02)  <br/> |
|Second Network Send Quality Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到网络导致已发送音频的质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |015: [0.01 - 0.02)  <br/> |
|First Network Receive Quality Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到网络导致已接收音频的质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |015: [0.01 - 0.02)  <br/> |
|Second Network Receive Quality Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到网络导致已接收音频的质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |015: [0.01 - 0.02)  <br/> |
|First Network Delay Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到网络延迟足以影响实时双向通信能力。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second Network Delay Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到网络延迟足以影响实时双向通信能力。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|First Network Bandwidth Low Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到可用带宽或带宽策略低到足以导致已发送音频的质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second Network Bandwidth Low Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到可用带宽或带宽策略低到足以导致已发送音频的质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|First CPU Insufficient Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到可用 CPU 资源不足并导致已发送和已接收音频的质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second CPU Insufficient Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到可用 CPU 资源不足并导致已发送和已接收音频的质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|First Device Half Duplex AEC Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到问题并在半双工模式下运行回声消除器，从而影响了实时双向通信能力。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second Device Half Duplex AEC Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到问题并在半双工模式下运行回声消除器，从而影响了实时双向通信能力。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|First Device Render Not Functioning Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到呈现设备未正常工作。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second Device Render Not Functioning Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到呈现设备未正常工作。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|First Device Capture Not Functioning Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到捕获设备未正常工作。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second Device Capture Not Functioning Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到捕获设备未正常工作。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|First Device Glitches Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到播放或捕获的音频中存在干扰或缺陷，导致发送或接收的音频质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second Device Glitches Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到播放或捕获的音频中存在干扰或缺陷，导致发送或接收的音频质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|First Device Low SNR Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到语音降低到噪音级别，导致发送的音频质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second Device Low SNR Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到语音降低到噪音级别，导致发送的音频质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|First Device Low Speech Level Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到语音级别降低，导致发送的音频质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second Device Low Speech Level Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到语音级别降低，导致发送的音频质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|First Device Clipping Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到捕获的音频中存在削波现象，导致发送的音频质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second Device Clipping Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到捕获的音频中存在削波现象，导致发送的音频质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|First Device Echo Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到回声，导致发送的音频质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second Device Echo Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到回声，导致发送的音频质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|First Device Near End To Echo Ratio Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到近端信号级别与回声级别的比率，该比率导致发送的音频质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second Device Near End To Echo Ratio Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到近端信号级别与回声级别的比率，该比率导致发送的音频质量差。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|First Device Render Zero Volume Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到设备呈现音量设置为 0。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second Device Render Zero Volume Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到设备呈现音量设置为 0。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|First Device Render Mute Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第一终结点检测到设备呈现被静音。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second Device Render Mute Event Ratio  <br/> |范围（比率）  <br/> |满足以下条件的通话的比率（小数）：第二终结点检测到设备呈现被静音。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|First Device Multiple Endpoints Event Count  <br/> |范围（比率）  <br/> |通话期间，第一终结点检测到同一房间或声音环境中存到多个终结点的次数。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second Device Multiple Endpoints Event Count  <br/> |范围（比率）  <br/> |通话期间，第二终结点检测到同一房间或声音环境中存到多个终结点的次数。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|First Device Howling Event Count  <br/> |范围（比率）  <br/> |通话期间，第一终结点检测到同一房间或声音环境中存到两个或更多个终结点并因此导致存在啸声或尖叫声的差质量音频的次数。值按范围分组表示。  <br/> |空值表示非音频流，或者第一终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Second Device Howling Event Count  <br/> |范围（比率）  <br/> |通话期间，第二终结点检测到同一房间或声音环境中存到两个或更多个终结点并因此导致存在啸声或尖叫声的差质量音频的次数。值按范围分组表示。  <br/> |空值表示非音频流，或者第二终结点未报告数据。  <br/> |016: [0.02 - 0.03)  <br/> |
|Error Report Sender  <br/> |字符串  <br/> |指示发送流的通话错误报告的终结点。此报告包含额外的遥测并可能指出通话中的通话设置或断线问题。  <br/> |空值表示没有发送通话错误报告。  <br/> |第一  <br/> |
|Is Media Error  <br/> |字符串  <br/> |指示为流报告的通话错误是否为媒体级错误。此报告包含额外的遥测并可能指出通话中的通话设置或断线问题。  <br/> |空值表示没有发送通话错误报告。  <br/> |True  <br/> |
|Media Failure Type  <br/> |字符串  <br/> | 与流关联的媒体故障的类型。可能的值： <br/>  Midcall <br/>  CallSetup <br/>  NotMediaFailure <br/> |空值表示没有发送通话错误报告。  <br/> |Midcall  <br/> |
|Rtp Rtcp Mux  <br/> |布尔值  <br/> |True 表示在同一端口多路复用 RTP 和 RTCP。否则为 False。  <br/> |空值表示终结点未报告此数据。  <br/> |True  <br/> |
|Stun Version  <br/> |整型  <br/> |建立通话所使用的 STUN 协议的版本。  <br/> |空值表示终结点未报告此数据。  <br/> |2  <br/> |
|Media Relay  <br/> |字符串  <br/> |用于会话的一个或多个媒体中继的 IP 地址。对于流，可能会报告一对中继，中间用"+"隔开。  <br/> |空值表示终结点未报告此数据。  <br/> |"13.107.8.2 + 13.107.8.2"  <br/> |
|Call Setup Failure Reason  <br/> |枚举  <br/> | 通话未能建立媒体连接的原因分类。可能的值： <br/>  缺少 FW 深度包检测免除规则 - 表示由于深度包检测规则，路径上的网络设备可能阻止建立媒体路径。这可能是因为未正确配置代理或防火墙规则。 <br/>  缺少 FW IP 阻止免除规则 - 表示路径上的网络设备可能阻止与 Office 365 网络建立媒体路径。这可能是因为未正确将代理或防火墙规则配置为允许访问用于 Skype for Business 流量的 IP 地址和端口。 <br/>  其他 - 表示通话无法建立媒体路径，但是未能对根本原因进行分类。 <br/>  不媒体故障-表示与媒体路径设施检测到任何问题。 <br/> |空值表示通话没有因为已知的媒体问题而未能建立。  <br/> |缺少 FW IP 阻止免除规则  <br/> |
|Is Anonymous Join Session  <br/> |布尔值  <br/> |如果用户匿名加入会议，则为 True，否则为 False。  <br/> |空值表示没有数据可以确定用户是否为匿名加入。  <br/> |True  <br/> |
|Has Media Diag Blob  <br/> |布尔值  <br/> |如何会话具有媒体诊断数据，则为 True，否则为 False。  <br/> |空值表示没有为此流收集某些信号数据。  <br/> |True  <br/> |
|Used Dns Resolve Cache  <br/> |布尔值  <br/> |如果终结点使用了 DNS 缓存来解析媒体中继地址，则为 True，否则为 False。  <br/> |空值表示终结点未报告此数据。  <br/> |False  <br/> |
|Network Connection Detail Pair  <br/> |枚举对  <br/> | 表示第一和第二终结点的网络连接详情的成对值。可能的值： <br/>  wifi : wifi <br/>  wifi : 有线 <br/>  有线 : wifi <br/>  有线 : 有线 <br/>  MobileBB : MobileBB <br/>  MobileBB : 其他 <br/>  MobileBB : 隧道 <br/>  MobileBB : wifi <br/>  MobileBB : 有线 <br/>  其他 : 其他 <br/>  其他 : wifi <br/>  其他 : 有线 <br/>  隧道 : 隧道 <br/>  隧道 : wifi <br/>  隧道 : 有线 <br/>  : MobileBB <br/>  : 其他 <br/>  : 隧道 <br/>  : wifi <br/>  : 有线 <br/>  : <br/> |枚举中的空值表示终结点网络连接类型未知。当无法建立通话时可能会出现这种情况。  <br/> |有线 : 有线  <br/> |
|User Agent Category Pair  <br/> |枚举对  <br/> |表示第一和第二终结点的用户代理类别的成对值。  <br/> |枚举中的空值表示终结点用户代理不是已知类型。  <br/> |AV-MCU : OC  <br/> |
|Is Server Pair  <br/> |枚举对  <br/> |表示第一和第二终结点是客户端还是服务器的成对值。可能的值：客户端 : 客户端、客户端 : 服务器、服务器 : 服务器。  <br/> |没有空值  <br/> |客户端 : 服务器  <br/> |
|Connectivity Ice Pair  <br/> |枚举对  <br/> | 表示每个终结点使用的 ICE 连接类型的成对值。可能的值： <br/>  直接 : 直接 <br/>  直接 : 失败 <br/>  直接 : HTTP <br/>  失败 : 失败 <br/>  失败 : 中继 <br/>  HTTP : 中继 <br/>  : <br/>  : 直接 <br/>  : 失败 <br/>  : HTTP <br/>  : 中继 <br/> |枚举中的空值表示终结点使用的 ICE 连接未知或未被报告。  <br/> |直接 : 中继  <br/> |
|OS Pair  <br/> |枚举对  <br/> |表示第一和第二终结点的操作系统名称和版本的成对值。  <br/> |枚举中的空值表示无法解析或终结点未报告操作系统名称。  <br/> |Windows 10 : Windows 10  <br/> |
|Tenant Id Pair  <br/> |枚举对  <br/> |表示第一和第二终结点的租户 ID 的成对值。  <br/> |枚举中的空值表示无法确定租户标识符。当终结点登录到了本地 Skype for Business Server 部署时可能会出现此情况。  <br/> |00000000 - 0000 - 0000 - 0000 - 000000000000 : 00000000 - 0000 - 0000 - 0000 - 000000000000  <br/> |
|Building Name Pair  <br/> |枚举对  <br/> |表示第一和第二终结点的建筑物名称的成对值。  <br/> |枚举中的空值表示无法确定终结点的建筑物名称。这可能是因为终结点位于企业网络外部，或正在从没有子网映射的站点访问网络。  <br/> |主建筑 : 分支站点建筑  <br/> |
|Inside Corp Pair  <br/> |枚举对  <br/> | 根据子网映射，显示终结点位于企业网络内部还是外部的成对值。可能的值： <br/>  内部 : 内部 <br/>  内部 : 外部 <br/>  外部 : 外部 <br/> |-  <br/> |内部 : 内部  <br/> |
|Scenario Pair  <br/> |枚举对  <br/> |显示终结点位于企业网络内部还是外部（根据子网映射确定）以及网络连接详情的成对值。  <br/> > [!注释]> 对值用"--"隔开。           |枚举中的空值表示一个或两个终结点的网络连接类型未知。  <br/> |客户端-内部--客户端-内部-wifi  <br/> |
|IsTeams  <br/> |布尔值  <br/> |True 表示第一个和第二个用户代理流是 Microsoft 团队终结点。  <br/> False 指示用户代理的 Skype for Business 终结点。  <br/> ||True  <br/> |
   
### 关于维度数据类型/单位的说明：

#### 范围

按范围或分组表示的维度值使用以下格式显示：
  
 _<sort order string> [<lower bound inclusive> - <upper bound exclusive)_
  
例如，持续时间（分钟）维度表示以分钟为单位的通话持续时间，报告的值以取值范围的形式表示。
  
|||
|:-----|:-----|
|**Duration (Minutes)** <br/> |**解释方法** <br/> |
|062: [0 - 0)  <br/> |流持续时间 = 0 分钟  <br/> |
|064: [1 - 2)  <br/> |1 分钟 < = 流持续时间 < 2 分钟  <br/> |
|065: [2 - 3)  <br/> |2 分钟 < = 流持续时间 < 3 分钟  <br/> |
|066: [3 - 4)  <br/> |3 分钟 < = 流持续时间 < 4 分钟  <br/> |
|…  <br/> |…  <br/> |
   
<排序字符串> 用于控制数据显示的顺序，可以用于筛选功能。例如，利用持续时间（分钟）<"065"的筛选器可以显示持续时间小于 2 分钟的流（筛选器应包含前导"0"才能正常使用）。
  
> [!注释]
> 排序字符串的实际值并不重要。 
  
#### 枚举对

按枚举对表示的维度使用以下格式显示：
  
 _<enumeration value from one end point> : < enumeration value from the other endpoint>_
  
枚举值的顺序一致，但此顺序不反映第一或第二终结点的顺序。
  
例如，网络连接详情对显示两个终结点的网络连接详情值：
  
|||
|:-----|:-----|
|**Network Connection Detail Pair** <br/> |**解释方法** <br/> |
|有线 : 有线  <br/> |第一和第二终结点均使用有线以太网连接。  <br/> |
|有线 : wifi  <br/> |第一个终结点使用有线以太网连接且第二个终结点使用 Wi-Fi 连接，或第二个终结点使用有线以太网连接且第一个终结点使用 Wi-Fi 连接。  <br/> |
|: wifi  <br/> |第一个终结点使用 WiFi 连接且第二个终结点使用的网络连接未知，或第二个终结点使用 WiFi 连接且第一个终结点使用的网络连接未知。  <br/> |
|…  <br/> |…  <br/> |
   
#### 空值

上表列出了维度可能出现空值的原因。如果"QoE 记录可用性"维度为 False，则很多维度和衡量指标都将为空。这通常出现在通话未能成功建立的情况下。
  
## 衡量指标

下表列出了通话质量仪表板 (CQD) 中目前可用的衡量指标：
  
||||
|:-----|:-----|:-----|
|**衡量指标名称** <br/> |**单位** <br/> |**说明** <br/> |
|Total Stream Count  <br/> |流的数量  <br/> |媒体流的数量，不区分媒体的类型。  <br/> |
|Audio Stream Count  <br/> |流的数量  <br/> |音频流的数量。  <br/> |
|AppSharing Stream Count  <br/> |流的数量  <br/> |基于 RDP 的应用程序共享流的数量。  <br/> |
|Video Stream Count  <br/> |流的数量  <br/> |视频流的数量。  <br/> |
|VBSS Stream Count  <br/> |流的数量  <br/> |基于视频的屏幕共享流的数量。  <br/> |
|Audio Poor Stream Count  <br/> |流的数量  <br/> |根据以下文章中列出的网络指标被分类为差的音频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Audio Good Stream Count  <br/> |流的数量  <br/> |根据以下文章中列出的网络指标被分类为好的音频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Audio Unclassified Stream Count  <br/> |流的数量  <br/> |数据不足，无法根据以下文章中列出的网络指标被分类为好或坏的音频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Audio Poor Percentage  <br/> |百分比  <br/> |根据以下文章中列出的网络指标被分类为差的所有音频流的百分比：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Audio OnePercent PacketLoss Count  <br/> |流的数量  <br/> |丢包率大于 1% 的音频流的数量。  <br/> |
|Audio OnePercent PacketLoss Percentage  <br/> |百分比  <br/> |丢包率大于 1% 的所有音频流的百分比。  <br/> |
|Audio Poor Due To Jitter Count  <br/> |流的数量  <br/> |抖动指标超过以下文章中所列阈值的音频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Audio Poor Due To PacketLoss Count  <br/> |流的数量  <br/> |丢包指标超过以下文章中所列阈值的音频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Audio Poor Due To Degradation Count  <br/> |流的数量  <br/> |降级指标超过以下链接中所列阈值的音频流的数量：[https://aka.ms/cqd_quality_thresholds](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Audio Poor Due To RoundTrip Count  <br/> |流的数量  <br/> |往返时间超过以下文章中所列阈值的音频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Audio Poor Due To ConcealedRatio Count  <br/> |流的数量  <br/> |隐藏比率超过以下文章中所列阈值的音频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|AppSharing Poor Due To SpoiledTilePercentTotal Count  <br/> |流的数量  <br/> |总损坏图块百分比指标超过以下文章中所列阈值的应用程序共享流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|AppSharing Poor Due To RelativeOneWayAverage Count  <br/> |流的数量  <br/> |总损坏图块百分比指标超过以下链接中所列阈值的应用程序共享流的数量：[https://aka.ms/cqd_quality_thresholds](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|AppSharing Poor Due To RDPTileProcessingLatencyAverage Count  <br/> |流的数量  <br/> |RDP 图块处理平均延迟超过以下文章中所列阈值的应用程序共享流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Video Poor Due To VideoPostFecplr Count  <br/> |流的数量  <br/> |Fec plr 后的视频超过以下文章中所列阈值的视频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Video Poor Due To VideoLocalFrameLossPercentageAvg Count  <br/> |流的数量  <br/> |视频本地帧丢失平均百分比超过以下文章中所列阈值的视频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Video Poor Due To RecvFrameRateAverage Count  <br/> |流的数量  <br/> |帧平均接收速率超过以下文章中所列阈值的视频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Video Poor Due To LowFrameRateCallPercent Count  <br/> |流的数量  <br/> |低帧速率通话百分比超过以下文章中所列阈值的视频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Video Poor Due To LowResolutionCallPercent Count  <br/> |流的数量  <br/> |低分辨率通话百分比超过以下文章中所列阈值的视频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Video Poor Due To VideoPacketLossRate Count  <br/> |流的数量  <br/> |视频丢包率超过以下链接中所列阈值的视频流的数量：[https://aka.ms/cqd_quality_thresholds](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Video Poor Due To VideoFrameRateAvg Count  <br/> |流的数量  <br/> |视频帧平均速率超过以下文章中所列阈值的视频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Video Poor Due To DynamicCapabilityPercent Count  <br/> |流的数量  <br/> |动态容量百分比超过以下文章中所列阈值的视频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|VBSS Poor Due To VideoPostFecplr Count  <br/> |流的数量  <br/> |Fec plr 后的视频超过以下文章中所列阈值的基于视频的屏幕共享流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|VBSS Poor Due To VideoLocalFrameLossPercentageAvg Count  <br/> |流的数量  <br/> |视频本地帧丢失平均百分比超过以下链接中所列阈值的基于视频的屏幕共享流的数量：[https://aka.ms/cqd_quality_thresholds](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|VBSS Poor Due To RecvFrameRateAverage Count  <br/> |流的数量  <br/> |帧平均接收速率超过以下文章中所列阈值的基于视频的屏幕共享流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|VBSS Poor Due To LowFrameRateCallPercent Count  <br/> |流的数量  <br/> |低帧速率通话百分比超过以下文章中所列阈值的基于视频的屏幕共享流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|VBSS Poor Due To LowResolutionCallPercent Count  <br/> |流的数量  <br/> |低分辨率通话百分比超过以下文章中所列阈值的基于视频的屏幕共享流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Video Poor Stream Count  <br/> |流的数量  <br/> |根据以下文章中列出的网络指标被分类为差的视频流的数量：[https://aka.ms/cqd_quality_thresholds](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Video Good Stream Count  <br/> |流的数量  <br/> |根据以下文章中列出的网络指标被分类为好的视频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Video Unclassified Stream Count  <br/> |流的数量  <br/> |数据不足，无法根据以下文章中列出的网络指标被分类为好或坏的视频流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Video Poor Percentage  <br/> |百分比  <br/> |根据以下文章中列出的网络指标被分类为差的所有视频流的百分比：[https://aka.ms/cqd_quality_thresholds](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|AppSharing Poor Stream Count  <br/> |流的数量  <br/> |根据以下文章中列出的网络指标被分类为差的应用程序共享流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|AppSharing Good Stream Count  <br/> |流的数量  <br/> |根据以下文章中列出的网络指标被分类为好的应用程序共享流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|AppSharing Unclassified Stream Count  <br/> |流的数量  <br/> |数据不足，无法根据以下文章中列出的网络指标被分类为好或坏的应用程序共享流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|AppSharing Poor Percentage  <br/> |百分比  <br/> |根据以下文章中列出的网络指标被分类为差的所有应用程序共享流的百分比：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|VBSS Poor Stream Count  <br/> |流的数量  <br/> |根据以下文章中列出的网络指标被分类为差的基于视频的屏幕共享流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|VBSS Good Stream Count  <br/> |流的数量  <br/> |根据以下文章中列出的网络指标被分类为好的基于视频的屏幕共享流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|VBSS Unclassified Stream Count  <br/> |流的数量  <br/> |数据不足，无法根据以下文章中列出的网络指标被分类为好或坏的基于视频的屏幕共享流的数量：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|VBSS Poor Percentage  <br/> |百分比  <br/> |根据以下文章中列出的网络指标被分类为差的所有基于视频的屏幕共享流的百分比：[在 Lync 2013 QoE 中将通话分类为差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Avg Call Duration  <br/> |秒  <br/> |流的平均持续时间，以秒为单位。  <br/> |
|First Feedback Rating Avg  <br/> |用户评级 (1-5)  <br/> |使用第一终结点的用户报告的流平均评级。通话评级分为 1-5 级，评级适用于通话的所有流。  <br/> |
|Second Feedback Rating Avg  <br/> |用户评级 (1-5)  <br/> |使用第二终结点的用户报告的流平均评级。通话评级分为 1-5 级，评级适用于通话的所有流。  <br/> |
|First Feedback Rating Count  <br/> |被评级的流的数量  <br/> |使用第一终结点的用户进行了评级的流的数量。通话评级分为 1-5 级，评级适用于通话的所有流。  <br/> |
|Second Feedback Rating Count  <br/> |被评级的流的数量  <br/> |使用第二终结点的用户进行了评级的流的数量。通话评级分为 1-5 级，评级适用于通话的所有流。  <br/> |
|First Feedback Rating Poor Count  <br/> |被评级的流的数量  <br/> |被使用第一终结点的用户评级为 1 或 2 的流的数量。通话评级分为 1-5 级，评级适用于通话的所有流。  <br/> |
|Second Feedback Rating Poor Count  <br/> |被评级的流的数量  <br/> |被使用第二终结点的用户评级为 1 或 2 的流的数量。通话评级分为 1-5 级，评级适用于通话的所有流。  <br/> |
|First Feedback Rating Poor Percentage  <br/> |被评级的流的数量  <br/> |被使用第一终结点的用户评级为 1 或 2 的所有流的百分比。通话评级分为 1-5 级，评级适用于通话的所有流。  <br/> |
|Second Feedback Rating Poor Percentage  <br/> |被评级的流的数量  <br/> |被使用第二终结点的用户评级为 1 或 2 的所有流的百分比。通话评级分为 1-5 级，评级适用于通话的所有流。  <br/> |
|First Feedback Token Audio Issue Count  <br/> |被评级流的数量  <br/> |被使用第一终结点的用户指出存在音频问题的流的数量。  <br/> |
|Second Feedback Token Audio Issue Count  <br/> |被评级流的数量  <br/> |被使用第二终结点的用户指出存在音频问题的流的数量。  <br/> |
|First Feedback Token Video Issue Count  <br/> |被评级的流的数量  <br/> |用户使用的第一个端点位置指示视频的问题的流数。  <br/> |
|Second Feedback Token Video Issue Count  <br/> |被评级的流的数量  <br/> |使用第二个终结点的用户位置指示视频的问题的流数。  <br/> |
|Audio SLA Good Call Count  <br/> |通话的数量  <br/> |划分为会议网络性能目标音频呼叫的 Skype for Business 语音质量 SLA ([批量许可的 Microsoft 产品和联机服务](http://aka.ms/voicequalitysla)) 的范围内的数字。  <br/> |
|Audio SLA Poor Call Count  <br/> |通话的数量  <br/> |音频呼叫的 Skype for Business 语音质量 SLA ([批量许可的 Microsoft 产品和联机服务](http://aka.ms/voicequalitysla)) 划分为不能满足网络性能目标的范围内的数字。  <br/> |
|Audio SLA Call Count  <br/> |通话的数量  <br/> |音频呼叫的 Skype for Business 语音质量 SLA ([批量许可的 Microsoft 产品和联机服务](http://aka.ms/voicequalitysla)) 的范围内的数字。  <br/> |
|Audio SLA Good Call Percentage  <br/> |百分比  <br/> |Skype for Business 语音质量 SLA（[Microsoft 产品和在线服务的批量许可](http://aka.ms/voicequalitysla)）范围内被分类为满足网络性能目标的音频通话的百分比。  <br/> |
|Audio Good Call Stream Count  <br/> |流的数量  <br/> |在此处列出的音频流在其中进行呼叫 （呼叫腿） 这两种音频流不属于差基于网络指标数：[将呼叫划分为在 Lync 2013 QoE 质量较差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Audio Poor Call Stream Count  <br/> |流的数量  <br/> |在此处列出的呼叫 （呼叫腿） 中的至少一个音频流属于差基于网络指标的音频流数：[将呼叫划分为在 Lync 2013 QoE 质量较差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Audio Unclassified Call Stream Count  <br/> |流的数量  <br/> |在其中进行呼叫 （呼叫腿） 这两种音频流可能不属于由于缺少网络指标的音频流数。  <br/> |
|Audio Poor Call Percentage  <br/> |百分比  <br/> |下面列出的所有音频流调用 （呼叫腿） 中的至少一个音频流属于差基于网络指标的百分比：[将呼叫划分为在 Lync 2013 QoE 质量较差的基础是什么？](https://aka.ms/cqd_quality_thresholds)。  <br/> |
|Avg First Echo Percent Mic In  <br/> |百分比  <br/> |在流持续期间，第一终结点在消除回声之前通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。  <br/> |
|Avg Second Echo Percent Mic In  <br/> |百分比  <br/> |在流持续期间，第二终结点在消除回声之前通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。  <br/> |
|Avg First Echo Percent Send  <br/> |百分比  <br/> |在流持续期间，第一终结点在消除回声之后通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。  <br/> |
|Avg Second Echo Percent Send  <br/> |百分比  <br/> |在流持续期间，第二终结点在消除回声之后通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。  <br/> |
|Avg First Audio Send Signal Level  <br/> |分贝  <br/> |对于被分类为单声道语音或左声道立体声语音的音频，第一终结点发送的音频的平均能量水平。  <br/> |
|Avg Second Audio Send Signal Level  <br/> |分贝  <br/> |对于被分类为单声道语音或左声道立体声语音的音频，第二终结点发送的音频的平均能量水平。  <br/> |
|Avg First Audio Recv Signal Level  <br/> |分贝  <br/> |对于被分类为单声道语音或左声道立体声语音的音频，第一终结点接收的音频的平均能量水平。  <br/> |
|Avg Second Audio Recv Signal Level  <br/> |分贝  <br/> |对于被分类为单声道语音或左声道立体声语音的音频，第二终结点接收的音频的平均能量水平。  <br/> |
|Avg First Audio Send Noise Level  <br/> |分贝  <br/> |对于被分类为单声道噪音或左声道立体声噪音的音频，第一终结点发送的音频的平均能量水平。  <br/> |
|Avg Second Audio Send Noise Level  <br/> |分贝  <br/> |对于被分类为单声道噪音或左声道立体声噪音的音频，第二终结点发送的音频的平均能量水平。  <br/> |
|Avg First Audio Recv Noise Level  <br/> |分贝  <br/> |对于被分类为单声道噪音或左声道立体声噪音的音频，第一终结点接收的音频的平均能量水平。  <br/> |
|Avg Second Audio Recv Noise Level  <br/> |分贝  <br/> |对于被分类为单声道噪音或左声道立体声噪音的音频，第二终结点接收的音频的平均能量水平。  <br/> |
|First Audio Echo BAD_TIMESTAMP Count  <br/> |流的数量  <br/> |具有以下特征的流的数量：第一终结点的差质量设备时间戳导致了回声，限制了已发送音频中的回声消除。  <br/> |
|First Audio Echo POSTAEC_ECHO Count  <br/> |流的数量  <br/> |具有以下特征的流的数量：第一终结点在已发送音频进行回声消除后检测到了高回声。  <br/> |
|First Audio Echo EVENT_ANLP Count  <br/> |流的数量  <br/> |具有以下特征的流的数量：第一终结点在捕获的音频中检测到噪音，限制了已发送音频中的回声消除。  <br/> |
|First Audio Echo EVENT_DNLP Count  <br/> |流的数量  <br/> |具有以下特征的流的数量：第一终结点在捕获的音频中检测到噪音，限制了已发送音频中的回声消除。  <br/> |
|First Audio Echo MIC_CLIPPING Count  <br/> |流的数量  <br/> |具有以下特征的流的数量：第一终结点在捕获的音频中检测到削波，限制了已发送音频中的回声消除。  <br/> |
|First Audio Echo BAD_STATE Count  <br/> |流的数量  <br/> |具有以下特征的流的数量：第一终结点检测到内部状态问题，限制了已发送音频中的回声消除。  <br/> |
|Second Audio Echo BAD_TIMESTAMP Count  <br/> |流的数量  <br/> |具有以下特征的流的数量：第二终结点的差质量设备时间戳导致了回声，限制了已发送音频中的回声消除。  <br/> |
|Second Audio Echo POSTAEC_ECHO Count  <br/> |流的数量  <br/> |具有以下特征的流的数量：第二终结点在已发送音频进行回声消除后检测到了高回声。  <br/> |
|Second Audio Echo EVENT_ANLP Count  <br/> |流的数量  <br/> |具有以下特征的流的数量：第二终结点在捕获的音频中检测到噪音，限制了已发送音频中的回声消除。  <br/> |
|Second Audio Echo EVENT_DNLP Count  <br/> |流的数量  <br/> |具有以下特征的流的数量：第二终结点在捕获的音频中检测到噪音，限制了已发送音频中的回声消除。  <br/> |
|Second Audio Echo MIC_CLIPPING Count  <br/> |流的数量  <br/> |具有以下特征的流的数量：第二终结点在捕获的音频中检测到削波，限制了已发送音频中的回声消除。  <br/> |
|Second Audio Echo BAD_STATE Count  <br/> |流的数量  <br/> |具有以下特征的流的数量：第二终结点检测到内部状态问题，限制了已发送音频中的回声消除。  <br/> |
|Total Call Setup Failed Stream Count  <br/> |流的数量  <br/> |呼叫之初无法在终结点之间建立媒体路径的流的数量。  <br/> |
|Total Call Dropped Stream Count  <br/> |流的数量  <br/> |媒体路径未正常终止的流的数量。  <br/> |
|Total Media Failed Stream Count  <br/> |流的数量  <br/> |媒体路径未能建立或未正常终止的流的数量。  <br/> |
|Total Media Succeeded Stream Count  <br/> |流的数量  <br/> |媒体路径成功建立并正常终止的流的数量。  <br/> |
|Total Call Setup Succeeded Stream Count  <br/> |流的数量  <br/> |呼叫之初在终结点之间成功建立媒体路径的流的数量。  <br/> |
|Total Call Setup Failure Percentage  <br/> |百分比  <br/> |呼叫之初无法在终结点之间建立媒体路径的所有流的百分比。  <br/> |
|Total Call Dropped Failure Percentage  <br/> |百分比  <br/> |已成功建立流位置媒体路径未正常终止的百分比。  <br/> |
|Total Answer Seizure Ratio  <br/> |比率  <br/> |持续时间低于 5 秒钟的通话占通话总数的比率。  <br/> |
|Total Short Call Percentage  <br/> |百分比  <br/> |长度低于 1 分钟的所有通话的百分比。  <br/> |
|Total Media Failure Percentage  <br/> |百分比  <br/> |媒体路径未能建立或未正常终止的所有流的百分比。  <br/> |
|Avg Audio Degradation  <br/> |平均意见得分 (0-5)  <br/> |关于流降级的网络平均意见得分的平均值。表示网络损耗和抖动对所收到的音频质量的影响程度。  <br/> |
|Avg Jitter  <br/> |毫秒  <br/> |流的平均网络抖动，以毫秒为单位。  <br/> |
|Avg Jitter Max  <br/> |毫秒  <br/> |流的最大网络抖动值，以毫秒为单位。  <br/> |
|Avg Packet Loss Rate  <br/> |百分比  <br/> |以 5 秒钟时间间隔计算到的流的平均丢包百分比的平均值。  <br/> |
|Avg Packet Loss Rate Max  <br/> |百分比  <br/> |以 5 秒钟时间间隔计算到的流的最大丢包百分比的平均值。  <br/> |
|Avg Overall Avg Network MOS  <br/> |平均意见得分 (0-5)  <br/> |流的网络平均意见得分的平均值。表示通过考虑网络损耗、抖动和编解码器对所收到的音频质量的平均估计。  <br/> |
|Avg Ratio Concealed Samples  <br/> |比率  <br/> |含有丢包隐藏生成样本的音频帧数与流的总音频帧数的平均比率的平均值。0.1 表示 10% 的帧包含隐藏样本。  <br/> |
|Avg Ratio Stretched Samples  <br/> |比率  <br/> |通过拉伸样本补偿抖动或丢失的音频帧数与流的总音频帧数的平均比率的平均值。0.1 表示 10% 的音频帧包含拉伸样本。  <br/> |
|Avg Round Trip  <br/> |毫秒  <br/> |计算的平均网络传播往返时间的平均值，根据 RFC3550 以毫秒为单位指定。  <br/> |
|Avg Round Trip Max  <br/> |毫秒  <br/> |计算的最大网络传播往返时间的平均值，根据 RFC3550 以毫秒为单位指定。  <br/> |
|Avg Network Jitter  <br/> |毫秒  <br/> |会话期间以 20 秒时间窗口计算的流的平均网络抖动的平均值，以毫秒为单位。  <br/> |
|Avg Video Post FECPLR  <br/> |比率  <br/> |应用 FEC 后，跨所有视频流和编解码器汇总的丢包率的平均值。  <br/> |
|Avg Video Local Frame Loss Percentage  <br/> |百分比  <br/> |向用户显示的流视频帧丢失平均百分比。其中包括从网络丢失恢复的帧。  <br/> |
|Avg Video Recv Frame Rate Average  <br/> |帧/秒  <br/> |在会话持续期间计算到的流的所有视频流每秒接收的平均帧数的平均值。  <br/> |
|Avg Video Low Frame Rate Call Percent  <br/> |百分比  <br/> |帧速率低于 7.5 帧/秒的流通话时间的平均百分比。  <br/> |
|Avg Video Low Resolution Call Percent  <br/> |百分比  <br/> |分辨率较低的流通话时间的平均百分比。较小维度的阈值为 120 像素。  <br/> |
|Avg Video Packet Loss Rate  <br/> |比率  <br/> |在会话持续期间计算到的流的平均丢包比率（小数）的平均值，根据 RFC3550 指定。  <br/> |
|Avg Video Frame Rate  <br/> |帧/秒  <br/> |在会话持续期间计算到的视频流每秒接收的平均帧数。值按范围分组表示。  <br/> |
|Avg Video Dynamic Capability Percent  <br/> |毫秒  <br/> |客户端以低于此类型 CPU 预期视频处理容量的 70% 运行的流时间的平均百分比。  <br/> |
|Avg AppSharing Spoiled Tile Percent Total  <br/> |毫秒  <br/> |没有被发送到远程对等点（例如，从 MCU 到查看器）而是被丢弃的图块的平均百分比。丢弃图块可能是由于客户端与服务器之间的带宽限制所致。  <br/> |
|Avg AppSharing Relative OneWay  <br/> |毫秒  <br/> |终结点之间的应用程序共享流的相对单向平均延迟的平均值，以毫秒为单位。  <br/> |
|Avg AppSharing RDP Tile Processing Latency  <br/> |毫秒  <br/> |在会议服务器上处理 RDP 堆栈图块的流平均延迟的平均值，以毫秒为单位。  <br/> |
|Media Failed Due To Firewall IP Blocked Stream Count  <br/> |流的数量  <br/> |由于网络设备阻止访问 Skype for Business 服务器而未能建立的流的数量。这些故障通常意味着未正确将代理、防火墙或其他网络安全设备配置为允许访问 Office 365 中的 Skype for Business 使用的 IP 地址和端口。  <br/> |
|Firewall IP Blocked Media Failure Percentage  <br/> |百分比  <br/> |由于网络设备阻止访问 Skype for Business 服务器而未能建立的流的百分比。这些故障通常意味着未正确将代理、防火墙或其他网络安全设备配置为允许访问 Office 365 中的 Skype for Business 使用的 IP 地址和端口。  <br/> |
|Media Failed Due To Firewall DPI Stream Count  <br/> |流的数量  <br/> |由于深度包检测不允许 Skype for Business 流量导致网络设备阻止访问进而未能建立的流的数量。这些故障通常意味着未正确将代理、防火墙或其他网络安全设备配置为允许访问 Office 365 中的 Skype for Business 使用的 IP 地址和端口。  <br/> |
|Firewall DPI Media Failure Percentage  <br/> |百分比  <br/> |由于深度包检测不允许 Skype for Business 流量导致网络设备阻止访问进而未能建立的流的百分比。这些故障通常意味着未正确将代理、防火墙或其他网络安全设备配置为允许访问 Office 365 中的 Skype for Business 使用的 IP 地址和端口。  <br/> |
   
## 
<a name="MT_Footer"> </a>

> [!注释]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

