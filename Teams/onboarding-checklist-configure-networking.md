---
title: 用于在 Microsoft Teams 中配置网络的上线清单
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 当您为团队配置网络时, 请按照本清单中的核心、待办任务和活动进行操作。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 885e483c6f0c2d79f850cdb78ff401cef15ff3a7
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2019
ms.locfileid: "35198242"
---
# <a name="configure-networking"></a>配置网络

| 否 | 活动或任务 | 说明 | 已完成？ | 其他信息 |
|----|--------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 查看团队的网络要求 | 在进入网络详细信息之前, 先对您的网络要求有全面的了解。 | | [为 Microsoft Teams 准备组织的网络](https://docs.microsoft.com/microsoftteams/prepare-network)                                                               |
| 2  | 提供网络准备工作研讨会 | 执行网络准备情况评估。 | |  |
| 3  | 使用网络 Planner | 执行网络带宽规划。 | | |
| 4  | 验证用户连接所需的 NAT 池大小 | 确保为 NAT 池分配了足够的公共 IP 地址以防止端口耗尽。 端口耗尽将对内部用户和无法连接到 Office 365 服务的设备造成影响。 <br/><br/>连接问题是用户对云服务的感知问题的主要原因。 | | [NAT 支持 Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9) |
| 5  | 实现最高效的路由到 Microsoft 数据中心 | 确定可使用本地或区域传出点尽可能高效地连接到 Microsoft 网络的位置。 <br/><br/>"**其他信息**" 列中的文章介绍了客户如何利用 Office 365 名称解析和 IP 路由中的功能有效地连接到距离最近的区域数据中心。 | | [Office 365 客户端连接](https://support.office.com/article/Client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b) |
| 6  | 配置与团队的连接性请求的防火墙端口 | 查看 Office 365 Url 和 IPs, 识别和测试本地客户端和服务器与 Office 365 服务之间的连接所需的防火墙端口。 <br/><br/>对于受支持的环境, 必须打开防火墙上的所有端口。 无法打开某些端口或范围将对用户体验产生负面影响。 根据 "**其他信息**" 列中的指南配置防火墙上的媒体端口。 | | [Office 365 Url 和 IP 地址-Microsoft 团队](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) |
| 7  | 配置代理服务器 | 配置你的环境, 以便跳过代理服务器, 并且可以使用 UDP 将用户直接连接到 Office 365, 以获得最佳音频和视频质量。 当实时媒体强制遍历代理服务器时, 团队中的媒体堆栈被强制故障回复到 TCP, 从而对质量产生负面影响。 <br/><br/>为了获得最高质量的用户体验, 始终首选通过 TCP 进行 UDP。 | | [规划服务管理和质量](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) |
| 个  | 配置拆分隧道 VPN | 我们建议你为团队流量 (通常称为*拆分隧道 VPN*) 提供备用路径。 拆分隧道意味着 Office 365 的流量不会遍历 VPN, 而是直接转到 Office 365。 此改变不仅有利于提高质量，而且还带来额外的好处，即降低 VPN 设备和组织网络的负荷。 | | 要实施拆分隧道的 VPN, 请向您的 VPN 供应商咨询配置详细信息。 |
| db-9  | 使用 QoS 配置数据包优先级 | 应在托管网络的所有段中实现 QoS。 即使已为带宽设置了充足的网络, QoS 在网络事件发生时也会带来风险降低。 当实现 QoS 时, 将优先排列语音流量, 以便这些意外事件不会对质量产生负面影响。 | | [规划服务管理和质量](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) <br/><br/>[Microsoft Teams 中的服务质量](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams) |
| 10 | 优化 Wi-fi 网络的质量和性能 | 优化 Wi-fi 网络时, 有几个因素会被扮演: <ul><li>实现 QoS 或 Wi-fi 多媒体 (WMM) 以确保已确定通过 Wi-fi 网络的媒体流量的优先级。</li><li>规划和优化 Wi-fi 频带和接入点放置。 2.4 GHz 范围可能会提供充足的性能, 具体取决于接入点的位置。</li></ul> 有关特定指南, 请咨询您的 Wi-fi 供应商。 | | [针对终结点的 Wi-Fi 建议](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#wi-fi-recommendations-for-endpoints) |
| 11 | 使用网络评估工具验证网络连接 | 使用适用于 Skype for Business 和团队的网络评估工具测试与 Skype for Business Online 和团队通话和会议中使用的所有 IP 地址和端口的连接。 下载该工具, 并查看用法 .docx, 了解有关如何使用该工具和解释测试结果的详细信息。 我们建议你在将使用团队的每个位置从客户端电脑运行该工具。 | | [Skype for Business 和团队网络评估工具](https://go.microsoft.com/fwlink/?linkid=855799) |
