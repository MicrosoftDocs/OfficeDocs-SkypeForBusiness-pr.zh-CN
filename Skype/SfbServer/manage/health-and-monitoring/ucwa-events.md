---
title: UCWA 事件在Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 摘要：了解统一通信 Web API (UCWA) 中Skype for Business Server。
ms.openlocfilehash: f4e1cfb344d8b27f2fef63f0c1c45ce1e4639627
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853016"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>UCWA 事件在Skype for Business Server
 
**摘要：** 了解统一通信 Web API (UCWA) 中Skype for Business Server。
  
Skype for Business Server统一通信 Web API (UCWA) 用于许多目的，从访问 Microsoft Exchange 进行联系人搜索到更新移动客户端状态。
  
UCWA 将操作行为记录编写为事件类型信息、警告和错误。 下表介绍了 UCWA 组件可以写入的事件。
  
|**事件 ID**|**事件类型**|**摘要**|**原因和解决方法**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |信息  <br/> |UCWA 初始化  <br/> |不适用  <br/> 不适用  <br/> |
|20002  <br/> |Error  <br/> |UCWA 在初始化期间遇到意外异常  <br/> |初始化期间发生意外错误  <br/> 检查关联事件日志条目中的异常详细信息以确定可能的原因  <br/> |
|20003  <br/> |Error  <br/> |UCWA 遇到未处理异常  <br/> |发生未处理异常  <br/> 重新启动服务器。 如果问题仍然存在，请联系产品支持人员  <br/> |
|20004  <br/> |Error  <br/> |无法访问Exchange照片的分辨率  <br/> |与 Exchange的连接不可用  <br/> 确保连接到 Exchange可用  <br/> |
|20005  <br/> |信息  <br/> |从无法访问高清照片Exchange恢复  <br/> |不适用  <br/> |
|20006  <br/> |Error  <br/> |无法访问Exchange搜索的联系人  <br/> |与 Exchange的连接不可用  <br/> 确保连接到 Exchange可用  <br/> |
|20007  <br/> |信息  <br/> |从无法搜索联系人中恢复Exchange  <br/> |不适用  <br/> |
|20008  <br/> |警告  <br/> |尝试订阅超过每个应用程序的允许状态订阅数  <br/> |尝试订阅超过每个应用程序的允许状态订阅数  <br/> 检查客户端中不必要的订阅  <br/> |
|20009  <br/> |警告  <br/> |尝试订阅超过每个批次允许状态订阅数  <br/> |尝试订阅超过每个批次允许状态订阅数  <br/> 检查客户端中不必要的订阅  <br/> |
|20010  <br/> |Error  <br/> |无法检索带内数据  <br/> |无法检索带内数据  <br/> 如果问题仍然存在，请联系产品支持人员  <br/> |
|20011  <br/> |Error  <br/> |无法订阅状态  <br/> |无法订阅状态  <br/> 如果问题仍然存在，请联系产品支持人员  <br/> |
|20012  <br/> |Error  <br/> |注册终结点失败  <br/> |注册终结点失败  <br/> 如果问题仍然存在，请联系产品支持人员  <br/> |
|20013  <br/> |Error  <br/> |IM MCU 不可用  <br/> |IM MCU 不可用  <br/> 查看 IM MCU 是否正在运行  <br/> |
|20014  <br/> |信息  <br/> |从无法连接到 IM MCU 中恢复  <br/> |不适用  <br/> |
|20015  <br/> |Error  <br/> |AV MCU 不可用  <br/> |AV MCU 不可用  <br/> 查看 AV MCU 是否正在运行  <br/> |
|20016  <br/> |信息  <br/> |从无法连接到 AV MCU 中恢复  <br/> |不适用  <br/> |
|20017  <br/> |Error  <br/> |AS MCU 不可用  <br/> |AS MCU 不可用  <br/> 查看 AS MCU 是否正在运行  <br/> |
|20018  <br/> |信息  <br/> |从无法连接到 AS MCU 中恢复  <br/> |不适用  <br/> |
|20019  <br/> |Error  <br/> |Data MCU 不可用  <br/> |Data MCU 不可用  <br/> 查看 Data MCU 是否正在运行  <br/> |
|20020  <br/> |信息  <br/> |从无法连接到 Data MCU 中恢复  <br/> |不适用  <br/> |
|20021  <br/> |Error  <br/> |无法加入 IM MCU  <br/> |无法加入 IM MCU  <br/> 查看 IM MCU 是否正在运行  <br/> |
|20022  <br/> |Error  <br/> |无法加入 AV MCU  <br/> |无法加入 AV MCU  <br/> 查看 AV MCU 是否正在运行  <br/> |
|20023  <br/> |Error  <br/> |无法加入 AS MCU  <br/> |无法加入 AS MCU  <br/> 查看 AS MCU 是否正在运行  <br/> |
|20024  <br/> |Error  <br/> |无法联接 Data MCU  <br/> |无法联接 Data MCU  <br/> 查看 Data MCU 是否正在运行  <br/> |
|20025  <br/> |Error  <br/> |无法访问照片的 Active Directory  <br/> |与 Active Directory 的连接不可用  <br/> 确保与 Active Directory 的连接可用  <br/> |
|20026  <br/> |信息  <br/> |从无法访问 Active Directory 获取照片的故障中恢复  <br/> |不适用  <br/> |
|20027  <br/> |警告  <br/> |无法反初始化  <br/> |无法反初始化  <br/> 如果问题仍然存在，请联系产品支持人员  <br/> |
   

