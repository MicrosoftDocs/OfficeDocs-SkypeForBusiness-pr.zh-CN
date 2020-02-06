---
title: Skype for Business 服务器中的 UCWA 事件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 摘要：了解 Skype for Business 服务器中的统一通信 Web API （UCWA）。
ms.openlocfilehash: db6aee15564fe9fca05c33ec5a6dd37988195956
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817621"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Skype for Business 服务器中的 UCWA 事件
 
**摘要：** 了解 Skype for Business 服务器中的统一通信 Web API （UCWA）。
  
Skype for business 服务器使用统一通信 Web API （UCWA）来实现许多用途，从访问 Microsoft Exchange 到联系人搜索以更新移动客户端的状态。
  
UCWA 将运行行为的记录编写成“信息”、“警告”和“错误”事件类型。下表介绍了可由 UCWA 组件编写的事件。
  
|**事件 ID**|**事件类型**|**摘要**|**原因和解决方法**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |信息  <br/> |UCWA 已初始化  <br/> |不适用  <br/> 不适用  <br/> |
|20002  <br/> |错误  <br/> |UCWA 在初始化期间遇到意外异常  <br/> |初始化期间出现意外错误  <br/> 检查相关事件日志条目中的异常详细信息以确定可能的原因  <br/> |
|20003  <br/> |错误  <br/> |UCWA 遇到未经处理的异常  <br/> |出现未经处理的异常  <br/> 重新启动服务器。如果问题仍然存在，请联系产品支持人员  <br/> |
|20004  <br/> |错误  <br/> |无法访问 Exchange 获取高清照片  <br/> |与 Exchange 的连接不可用  <br/> 确保与 Exchange 的连接可用  <br/> |
|20005  <br/> |信息  <br/> |从无法访问 Exchange 获取高清照片的故障中恢复  <br/> |不适用  <br/> |
|20006  <br/> |错误  <br/> |无法访问 Exchange 进行联系人搜索  <br/> |与 Exchange 的连接不可用  <br/> 确保与 Exchange 的连接可用  <br/> |
|20007  <br/> |信息  <br/> |从无法在 Exchange 中搜索联系人的故障中恢复  <br/> |不适用  <br/> |
|20008  <br/> |警告  <br/> |尝试订阅超过每应用程序允许的状态订阅数量  <br/> |尝试订阅超过每应用程序允许的状态订阅数量  <br/> 检查客户端中不必要的订阅  <br/> |
|20009  <br/> |警告  <br/> |尝试订阅超过每批允许的状态订阅数量  <br/> |尝试订阅超过每批允许的状态订阅数量  <br/> 检查客户端中不必要的订阅  <br/> |
|20010  <br/> |错误  <br/> |无法检索带内数据  <br/> |无法检索带内数据  <br/> 如果问题仍然存在，请联系产品支持人员  <br/> |
|20011  <br/> |错误  <br/> |无法订阅状态  <br/> |无法订阅状态  <br/> 如果问题仍然存在，请联系产品支持人员  <br/> |
|20012  <br/> |错误  <br/> |未能注册终结点  <br/> |未能注册终结点  <br/> 如果问题仍然存在，请联系产品支持人员  <br/> |
|20013  <br/> |错误  <br/> |IM MCU 不可用  <br/> |IM MCU 不可用  <br/> 查看 IM MCU 是否在运行  <br/> |
|20014  <br/> |信息  <br/> |从无法连接 IM MCU 的故障中恢复  <br/> |不适用  <br/> |
|20015  <br/> |错误  <br/> |AV MCU 不可用  <br/> |AV MCU 不可用  <br/> 查看 AV MCU 是否在运行  <br/> |
|20016  <br/> |信息  <br/> |从无法连接 AV MCU 的故障中恢复  <br/> |不适用  <br/> |
|20017  <br/> |错误  <br/> |AS MCU 不可用  <br/> |AS MCU 不可用  <br/> 查看 AS MCU 是否在运行  <br/> |
|20018  <br/> |信息  <br/> |从无法连接 AS MCU 的故障中恢复  <br/> |不适用  <br/> |
|20019  <br/> |错误  <br/> |Data MCU 不可用  <br/> |Data MCU 不可用  <br/> 查看 Data MCU 是否在运行  <br/> |
|20020  <br/> |信息  <br/> |从无法连接 Data MCU 的故障中恢复  <br/> |不适用  <br/> |
|20021  <br/> |错误  <br/> |无法加入 IM MCU  <br/> |无法加入 IM MCU  <br/> 查看 IM MCU 是否在运行  <br/> |
|20022  <br/> |错误  <br/> |无法加入 AV MCU  <br/> |无法加入 AV MCU  <br/> 查看 AV MCU 是否在运行  <br/> |
|20023  <br/> |错误  <br/> |无法加入 AS MCU  <br/> |无法加入 AS MCU  <br/> 查看 AS MCU 是否在运行  <br/> |
|20024  <br/> |错误  <br/> |无法加入 Data MCU  <br/> |无法加入 Data MCU  <br/> 查看 Data MCU 是否在运行  <br/> |
|20025  <br/> |错误  <br/> |无法访问 Active Directory 获取照片  <br/> |与 Active Directory 的连接不可用  <br/> 确保与 Active Directory 的连接可用  <br/> |
|20026  <br/> |信息  <br/> |从无法访问 Active Directory 获取照片的故障中恢复  <br/> |不适用  <br/> |
|20027  <br/> |警告  <br/> |无法反序列化  <br/> |无法反序列化  <br/> 如果问题仍然存在，请联系产品支持人员  <br/> |
   

