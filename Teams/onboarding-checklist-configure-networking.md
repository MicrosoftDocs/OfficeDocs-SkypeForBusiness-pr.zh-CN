---
title: 配置网络，对于 Microsoft 团队的入职培训清单
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 团队配置您的网络时，请按照的核心、 待办事项任务和此检查表中的活动。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 68ebb697cdd8469b8a9c373b4c90bb970b5c7ce5
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016314"
---
# <a name="configure-networking"></a>配置网络

| 否 | 活动或任务 | 说明 | 已完成？ | 其他信息 |
|----|--------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 查看团队的网络要求 | 转到网络的详细信息之前，有您的网络要求一个总体视图。 | | [为 Microsoft Teams 准备贵组织的网络](https://docs.microsoft.com/microsoftteams/prepare-network)                                                               |
| 2  | 提供网络准备研讨会 （英文） | 完成网络准备研讨会从 MyAdvisor，并使用您的团队能够标识为地址的关注区域作为修正工作的一部分。 | | [MyAdvisor 网络准备资产](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11) |
| 3  | 使用网络进度表 | 使用网络计划工具来计算所需的所有位置和网站范围内的带宽。 | | [MyAdvisor 网络计划程序](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)                                                                                   |
| 4  | 验证用户连接所需的 NAT 池大小 | 确保为 NAT 池分配足够的公共 IP 地址是以防止端口耗尽。 端口耗尽将参与内部用户和设备无法连接到 Office 365 服务。 <br/><br/>连接问题是有关云服务的用户认知问题前导原因。 | | [Office 365 的 NAT 支持](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9) |
| 5  | 实现最有效的路由到 Microsoft 数据中心 | 确定可以使用本地或区域出口点尽可能高效地连接到 Microsoft 网络的位置。 <br/><br/>**的其他信息**列中的文章介绍如何客户端可以利用 Office 365 名称解析和 IP 路由有效地连接到最近的区域数据中心中的功能。 | | [Office 365 客户端连接](https://support.office.com/article/Client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b) |
| 6  | 配置防火墙端口连接到团队的请求 | 查看 Office 365 Url 和 Ip 标识和测试所需的本地客户端和服务器与 Office 365 服务之间的连接的防火墙端口。 <br/><br/>为受支持的环境，必须在防火墙上打开所有端口。 未能打开一些端口或范围会产生负面影响的用户体验。 基于**的其他信息**列中的指导您防火墙上配置媒体端口。 | | [Office 365 Url 和 IP 地址 – Microsoft 团队](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) |
| 7  | 配置代理服务器 | 配置您的环境，以便绕过代理服务器，您可以用户直接连接到 Office 365 使用的最佳音频和视频质量 UDP。 时强制实时的媒体遍历代理服务器，团队中的媒体堆栈会强制进行故障回复到 TCP，对质量产生负面影响。 <br/><br/>为了最高品质用户体验，请始终通过 TCP 首选 UDP。 | | [规划服务管理和质量](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) |
| 8  | 配置拆分 VPN 隧道 | 我们建议您为绕过 VPN，通常称为*拆分隧道 VPN*的团队流量提供备用路径。 拆分隧道意味着 for Office 365 的流量不会遍历 VPN 但而直接转到 Office 365。 此改变不仅有利于提高质量，而且还带来额外的好处，即降低 VPN 设备和组织网络的负荷。 | | 若要实现拆分隧道 VPN，请咨询您 VPN 供应商联系以获取配置详情。 |
| 9  | 使用 QoS 配置数据包的优先顺序 | 应在所有托管网络段上实现 QoS。 即使时网络充足的带宽，QoS 提供风险缓解时无法预知的网络事件发生。 当实现 QoS 时，语音通信是确定其优先级，以便这些无法预知的事件不会产生负面影响质量。 | | [规划服务管理和质量](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) <br/><br/>[Microsoft Teams 中的服务质量](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams) |
| 10 | 优化 Wi-fi 网络质量和性能 | 若干因素会影响到您优化 Wi-fi 网络： <ul><li>实现 QoS 或 Wi-fi 多媒体 (WMM)，以确保该媒体流量通过 Wi-fi 网络确定优先级。</li><li>规划和优化 Wi-fi 区段和访问点位置。 为 2.4 GHz 范围可能提供足够的性能，具体取决于接入点放置。</li></ul> 有关特定的指南，请咨询您 Wi-fi 供应商。 | | [针对终结点的 Wi-Fi 建议](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#wi-fi-recommendations-for-endpoints) |
| 11 | 使用网络评估工具中验证网络连接 | 使用的业务和团队的 Skype 网络评估工具来测试连接到所有 IP 地址和端口中使用 Skype 业务联机和团队呼叫和会议。 下载该工具，以及有关如何使用工具和解释的测试结果的详细信息，请参阅 Usage.docx。 我们建议您从团队将使用其中每个位置中的客户端 PC 运行该工具。 | | [Skype 商业和团队网络评估工具](https://go.microsoft.com/fwlink/?linkid=855799) |