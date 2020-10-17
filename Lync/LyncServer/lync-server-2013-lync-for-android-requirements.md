---
title: Lync Server 2013： Lync for Android 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync for Android requirements
ms:assetid: 4ff53e03-0c1f-4a2b-9cec-1131c2a48563
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690980(v=OCS.15)
ms:contentKeyID: 53312965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cca08828dd91a7b6c26e11330f0e8839f4677be4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506049"
---
# <a name="lync-for-android-requirements-in-lync-server-2013"></a><span data-ttu-id="0a814-102">Lync Server 2013 中的 lync for Android 要求</span><span class="sxs-lookup"><span data-stu-id="0a814-102">Lync for Android requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a814-103">_**上次修改的主题：** 2014-04-24_</span><span class="sxs-lookup"><span data-stu-id="0a814-103">_**Topic Last Modified:** 2014-04-24_</span></span>

<span data-ttu-id="0a814-104">Microsoft lync 2013 Microsoft Lync 2013 for Android 为组织中从 Android 设备进行连接的用户提供即时消息 (IM) 、增强状态和 Lync 会议加入功能。</span><span class="sxs-lookup"><span data-stu-id="0a814-104">Microsoft Lync 2013 Microsoft Lync 2013 for Android provides instant messaging (IM), enhanced presence, and Lync meeting join capabilities for users in your organization who are connecting from an Android device.</span></span> <span data-ttu-id="0a814-105">本主题介绍了适用于 Android 的 Lync 2013 的注意事项，其中包括先决条件、技术要求和必备组件。</span><span class="sxs-lookup"><span data-stu-id="0a814-105">This topic describes considerations for Lync 2013 for Android, including prerequisites, technical requirements, and required components.</span></span>

<div>

## <a name="lync-for-android-prerequisite"></a><span data-ttu-id="0a814-106">Lync for Android 必备组件</span><span class="sxs-lookup"><span data-stu-id="0a814-106">Lync for Android Prerequisite</span></span>

<span data-ttu-id="0a814-107">若要支持适用于 Android 的 Lync 2013，Android 设备必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="0a814-107">To support Lync 2013 for Android, the Android device must meet the following requirements:</span></span>

  - <span data-ttu-id="0a814-108">Android 设备必须运行 Android 4.0 或更高版本的面向电话或平板电脑的操作系统（包括平板电脑），Tegra2 芯片附带的操作系统除外。</span><span class="sxs-lookup"><span data-stu-id="0a814-108">The Android device must be running Android 4.0 or a later phone- or tablet-oriented operating system, including tablets, except those with the Tegra2 chip.</span></span>

  - <span data-ttu-id="0a814-109">设备必须具有 1.2 GHz 双核或更高的 CPU。</span><span class="sxs-lookup"><span data-stu-id="0a814-109">The device must have a 1.2 GHz dual core or higher CPU.</span></span>

  - <span data-ttu-id="0a814-110">设备摄像头 (前/后) 分辨率应为 VGA 或更高。</span><span class="sxs-lookup"><span data-stu-id="0a814-110">The device camera (front/rear) resolution should be VGA or higher.</span></span>

  - <span data-ttu-id="0a814-111">其他硬件要求应与 Android 4.0 兼容性定义文档相一致。</span><span class="sxs-lookup"><span data-stu-id="0a814-111">Other hardware requirements should be aligned with Android 4.0 Compatibility Definition Document.</span></span>

</div>

<div>

## <a name="other-technical-considerations"></a><span data-ttu-id="0a814-112">其他技术注意事项</span><span class="sxs-lookup"><span data-stu-id="0a814-112">Other Technical Considerations</span></span>

<span data-ttu-id="0a814-113">在 Android 设备平台上，Lync 应用程序可以在后台运行。</span><span class="sxs-lookup"><span data-stu-id="0a814-113">On the Android device platform, the Lync application can run in the background.</span></span> <span data-ttu-id="0a814-114">因此，与其他移动设备平台不同的是，Android 设备不需要推送通知。</span><span class="sxs-lookup"><span data-stu-id="0a814-114">Therefore, unlike other mobile device platforms, push notifications are not required for Android devices.</span></span> <span data-ttu-id="0a814-115">在 Android 设备上退出 Lync 应用程序的唯一方法是，显式注销 Lync。</span><span class="sxs-lookup"><span data-stu-id="0a814-115">The only way to exit the Lync application on an Android device is to explicitly sign out of Lync.</span></span> <span data-ttu-id="0a814-116">此版本的 Lync 应用程序在带 Tegra 2 芯片组的设备上不受支持。</span><span class="sxs-lookup"><span data-stu-id="0a814-116">This version of the Lync application is not supported on devices with Tegra 2 chipsets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

