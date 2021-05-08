---
title: 使用管理中心创建Microsoft 365帐户
description: 如果希望使用图形用户界面，可以使用管理中心为 Microsoft Teams 会议室 和协作Microsoft Teams创建Microsoft 365帐户。
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: 创建设备帐户、Microsoft 365 UI、Microsoft 365管理中心
ms.sitesec: library
ms.service: msteams
author: flinchbot
ms.author: mitressl
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1137f462b9c21455f3a65a87075fd653b5c081b9
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268012"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a><span data-ttu-id="d74c6-104">使用 Microsoft 365 管理中心创建Microsoft 365资源帐户</span><span class="sxs-lookup"><span data-stu-id="d74c6-104">Create a Microsoft 365 resource account using the Microsoft 365 admin center</span></span>

<span data-ttu-id="d74c6-105">Microsoft 365资源帐户是Teams资源（如会议室、投影仪等）的邮箱帐户和专用帐户。</span><span class="sxs-lookup"><span data-stu-id="d74c6-105">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="d74c6-106">这些资源帐户可以使用创建会议邀请时定义的规则自动响应会议邀请。</span><span class="sxs-lookup"><span data-stu-id="d74c6-106">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="d74c6-107">例如，如果您有一个公用资源（如会议室），您可以为该会议室设置一个资源帐户，该资源帐户将自动接受或拒绝会议邀请，具体取决于其日历可用性。</span><span class="sxs-lookup"><span data-stu-id="d74c6-107">For example, if you have a common resource such as a conference room, you can set up a resource account for that conference room that will automatically accept or decline meeting invites depending on its calendar availability.</span></span>

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a><span data-ttu-id="d74c6-108">许可</span><span class="sxs-lookup"><span data-stu-id="d74c6-108">Licensing</span></span>

<span data-ttu-id="d74c6-109">创建资源Microsoft 365之前，请检查它所需的许可证类型。</span><span class="sxs-lookup"><span data-stu-id="d74c6-109">Before you create a Microsoft 365 resource account, check to see what kind of license it needs.</span></span> <span data-ttu-id="d74c6-110">如果您仅使用资源帐户预订资源 (即邀请资源加入您的会议，并自动接受或拒绝邀请) ，则无需向资源帐户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="d74c6-110">If you'll only use a resource account to book a resource (that is, invite the resource to your meeting and have it automatically accept or decline the invitation), you don't need to assign a license to a resource account.</span></span> <span data-ttu-id="d74c6-111">在以下情况中，需要向资源帐户分配许可证：</span><span class="sxs-lookup"><span data-stu-id="d74c6-111">You'll need to assign a license to the resource account in the following situations:</span></span>

- <span data-ttu-id="d74c6-112">**Teams会议** 如果希望 (（如 Microsoft Teams 会议室 控制台、协作栏等）) 加入 Teams 会议，以便与会者可以使用它通过它演示视频和音频，则需要 会议室 许可证。</span><span class="sxs-lookup"><span data-stu-id="d74c6-112">**Teams meeting** If you want the resource (such as a Microsoft Teams Rooms console, collaboration bar, and so on) to join a Teams meeting so attendees can use it to present video and audio through it, you need a Meeting Room license.</span></span> 
- <span data-ttu-id="d74c6-113">**PSTN 呼叫** 如果您希望资源拨打或接听外部电话号码（称为公用电话交换网 (PSTN 呼叫) ）的呼叫，则需要 Microsoft 365 电话系统 或 Microsoft 365 商务语音 许可证。</span><span class="sxs-lookup"><span data-stu-id="d74c6-113">**PSTN calls** If you want the resource to make or receive calls to or from an external phone numbers (called a Public Switched Telephone Network or PSTN call), you need a Microsoft 365 Phone System or Microsoft 365 Business Voice license.</span></span>

<span data-ttu-id="d74c6-114">有关用户、会议室电话系统和 Business Voice 许可证[Microsoft Teams，请参阅附加许可证](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="d74c6-114">For more information about Meeting Room, Phone System, and Business Voice licenses, see [Microsoft Teams add-on licenses](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a><span data-ttu-id="d74c6-115">在管理中心Microsoft 365帐户</span><span class="sxs-lookup"><span data-stu-id="d74c6-115">Create a resource account in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="d74c6-116">通过访问 Microsoft 365登录到https://admin.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d74c6-116">Sign in to Microsoft 365 by visiting https://admin.microsoft.com</span></span>
2. <span data-ttu-id="d74c6-117">为租户提供管理员Microsoft 365凭据。</span><span class="sxs-lookup"><span data-stu-id="d74c6-117">Provide the admin credentials for your Microsoft 365 tenant.</span></span> <span data-ttu-id="d74c6-118">这会将你Microsoft 365管理中心。</span><span class="sxs-lookup"><span data-stu-id="d74c6-118">This will take you to your Microsoft 365 admin center.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365管理中心":::
3. <span data-ttu-id="d74c6-120">在管理中心中，导航到左侧面板中的"资源 (可能需要选择"显示所有第一) "，然后选择"会议室&**设备"。** </span><span class="sxs-lookup"><span data-stu-id="d74c6-120">In the admin center, navigate to **Resources** in the left panel (you might need to select **Show all** first), and then select **Rooms & equipment**.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365管理中心 - 资源":::
4. <span data-ttu-id="d74c6-122">选择 **"添加资源邮箱** "以创建新的聊天室帐户。</span><span class="sxs-lookup"><span data-stu-id="d74c6-122">Select **Add a resource mailbox** to create a new room account.</span></span> <span data-ttu-id="d74c6-123">输入帐户显示名称电子邮件地址，选择"**添加"，** 然后选择"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="d74c6-123">Enter a display name and email address for the account, select **Add**, and then select **Close**.</span></span> <span data-ttu-id="d74c6-124">建议标准化所有资源帐户的命名约定。</span><span class="sxs-lookup"><span data-stu-id="d74c6-124">We recommend you standardize on a naming convention for all of your resource accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="d74c6-125">默认情况下，资源帐户设置如下设置。</span><span class="sxs-lookup"><span data-stu-id="d74c6-125">By default, resource accounts are set up with the following settings.</span></span> <span data-ttu-id="d74c6-126">如果要更改它们，请在选择"关闭 **"之前选择**"设置计划 **选项"。**</span><span class="sxs-lookup"><span data-stu-id="d74c6-126">If you want to change them, select **Set scheduling options** before you select **Close**.</span></span> <span data-ttu-id="d74c6-127">如果以后想要更改它们，请导航到"资源&  >  **设备"，** 选择资源帐户，然后选择"预订选项"下的"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="d74c6-127">If you want to change them later, navigate to **Resources** > **Rooms & equipment**, select the resource account and then select **Edit** under **Booking options**.</span></span>
>
> - <span data-ttu-id="d74c6-128">允许重复会议</span><span class="sxs-lookup"><span data-stu-id="d74c6-128">Allow repeat meetings</span></span>
> - <span data-ttu-id="d74c6-129">自动拒绝超出以下限制的会议</span><span class="sxs-lookup"><span data-stu-id="d74c6-129">Automatically decline meetings outside of the following limits</span></span>
>   - <span data-ttu-id="d74c6-130">预订时段 (天) ：180</span><span class="sxs-lookup"><span data-stu-id="d74c6-130">Booking window (days): 180</span></span>
>   - <span data-ttu-id="d74c6-131">最长持续时间 (小时) ：24</span><span class="sxs-lookup"><span data-stu-id="d74c6-131">Maximum duration (hours): 24</span></span>
> - <span data-ttu-id="d74c6-132">自动接受会议请求</span><span class="sxs-lookup"><span data-stu-id="d74c6-132">Auto accept meeting requests</span></span>

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365管理中心 - 添加资源":::
5. <span data-ttu-id="d74c6-134">导航到 **管理中心** 中的"用户"部分，在" **活动** 用户"列表中，你将看到刚创建的聊天室。</span><span class="sxs-lookup"><span data-stu-id="d74c6-134">Navigate to the **Users** section in admin center and, in the **Active users** list, you will see the room you just created.</span></span>

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365管理中心 - 查看活动用户":::
6. <span data-ttu-id="d74c6-136">选择聊天室的名称，右侧会显示帐户属性面板。</span><span class="sxs-lookup"><span data-stu-id="d74c6-136">Select on the name of the room and an account properties panel will appear on the right.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365管理中心 - 用户属性":::
7. <span data-ttu-id="d74c6-138">现在，需要为资源帐户分配密码。</span><span class="sxs-lookup"><span data-stu-id="d74c6-138">Now you need to assign a password to the resource account.</span></span> <span data-ttu-id="d74c6-139">在面板中，可以看到帐户属性和多个可选操作。</span><span class="sxs-lookup"><span data-stu-id="d74c6-139">In the panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="d74c6-140">选择 **用户名下的** "重置密码密钥"图标以更改密码。</span><span class="sxs-lookup"><span data-stu-id="d74c6-140">Select the **Reset password** key icon under the username to change the password.</span></span> <span data-ttu-id="d74c6-141">取消选择 **"要求此用户在首次登录时更改其密码"。**</span><span class="sxs-lookup"><span data-stu-id="d74c6-141">Unselect **Require this user to change their password when they first sign in**.</span></span> <span data-ttu-id="d74c6-142">无法通过设备登录过程更改密码。</span><span class="sxs-lookup"><span data-stu-id="d74c6-142">It is not possible to change the password via the device sign-in process.</span></span> <span data-ttu-id="d74c6-143">选择"**重置"。**</span><span class="sxs-lookup"><span data-stu-id="d74c6-143">Select **Reset**.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365管理中心 - 重置密码":::
8. <span data-ttu-id="d74c6-145">在" **许可证和应用"** 部分中 **，将"** 选择位置"设置为要安装设备的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="d74c6-145">In the **Licenses and Apps** section, set **Select location** to the country or region where the device will be installed.</span></span> <span data-ttu-id="d74c6-146">向下滚动并选中要分配的许可证旁边的框（例如"会议室"，然后选择"保存 **更改"。**</span><span class="sxs-lookup"><span data-stu-id="d74c6-146">Scroll down and check the box next to the license to be assigned - such as Meeting Room - and then select **Save changes**.</span></span> <span data-ttu-id="d74c6-147">许可证可能因组织而异。</span><span class="sxs-lookup"><span data-stu-id="d74c6-147">The license may vary depending on your organization.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365管理中心 - 分配许可证":::
