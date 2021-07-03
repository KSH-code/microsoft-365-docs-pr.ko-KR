---
title: 끝점용 Microsoft Defender에서 경고 알림 구성
description: 끝점용 Microsoft Defender를 사용하여 심각도 및 기타 기준에 따라 보안 경고에 대한 전자 메일 알림 설정을 구성할 수 있습니다.
keywords: 전자 메일 알림, 경고 알림 구성, 끝점용 Microsoft Defender, 끝점 알림용 Microsoft Defender, 끝점 경고용 Microsoft Defender, Windows 10 Enterprise, Windows 10 Education
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9a7ad1241ce73bb9b68e173faa9433c7326e14e5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286936"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="95905-104">끝점용 Microsoft Defender에서 경고 알림 구성</span><span class="sxs-lookup"><span data-stu-id="95905-104">Configure alert notifications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="95905-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="95905-105">**Applies to:**</span></span>
- [<span data-ttu-id="95905-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="95905-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="95905-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95905-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="95905-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="95905-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="95905-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="95905-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

<span data-ttu-id="95905-110">새 경고에 대해 지정된 받는 사람에게 전자 메일 알림을 보내도록 끝점에 대한 Defender를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95905-110">You can configure Defender for Endpoint to send email notifications to specified recipients for new alerts.</span></span> <span data-ttu-id="95905-111">이 기능을 사용하면 즉시 알림을 보내고 심각도에 따라 경고에 대해 행동할 수 있는 개인 그룹을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95905-111">This feature enables you to identify a group of individuals who will immediately be informed and can act on alerts based on their severity.</span></span>

> [!NOTE]
> <span data-ttu-id="95905-112">'보안 설정 관리' 권한이 있는 사용자만 전자 메일 알림을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95905-112">Only users with 'Manage security settings' permissions can configure email notifications.</span></span> <span data-ttu-id="95905-113">기본 사용 권한 관리를 사용하도록 선택한 경우 보안 관리자 또는 전역 관리자 역할이 있는 사용자는 전자 메일 알림을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95905-113">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications.</span></span>

<span data-ttu-id="95905-114">알림을 트리거하는 경고 심각도 수준을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95905-114">You can set the alert severity levels that trigger notifications.</span></span> <span data-ttu-id="95905-115">전자 메일 알림의 받는 사람을 추가하거나 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95905-115">You can also add or remove recipients of the email notification.</span></span> <span data-ttu-id="95905-116">새 받는 사람은 추가된 후 트리거된 경고에 대한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95905-116">New recipients get notified about alerts triggered after they're added.</span></span> <span data-ttu-id="95905-117">경고에 대한 자세한 내용은 경고 큐 보기 및 [구성을 참조하세요.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="95905-117">For more information about alerts, see [View and organize the Alerts queue](alerts-queue.md).</span></span>

<span data-ttu-id="95905-118">RBAC(역할 기반 액세스 제어)를 사용하는 경우 받는 사람은 알림 규칙에 구성된 장치 그룹을 기반으로 하는 알림만 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95905-118">If you're using role-based access control (RBAC), recipients will only receive notifications based on the device groups that were configured in the notification rule.</span></span>
<span data-ttu-id="95905-119">적절한 권한이 있는 사용자는 장치 그룹 관리 범위로 제한되는 알림만 만들거나 편집하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95905-119">Users with the proper permission can only create, edit, or delete notifications that are limited to their device group management scope.</span></span>
<span data-ttu-id="95905-120">전역 관리자 역할에 할당된 사용자만 모든 장치 그룹에 대해 구성된 알림 규칙을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95905-120">Only users assigned to the Global administrator role can manage notification rules that are configured for all device groups.</span></span>

<span data-ttu-id="95905-121">전자 메일 알림에는 경고에 대한 기본 정보와 추가 조사를 할 수 있는 포털 링크가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95905-121">The email notification includes basic information about the alert and a link to the portal where you can do further investigation.</span></span>

## <a name="create-rules-for-alert-notifications"></a><span data-ttu-id="95905-122">경고 알림에 대한 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="95905-122">Create rules for alert notifications</span></span>
<span data-ttu-id="95905-123">장치 및 알림 심각도 및 알림 받는 사람에 대해 전자 메일 알림을 보내기 위한 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95905-123">You can create rules that determine the devices and alert severities to send email notifications for and the notification recipients.</span></span>


1. <span data-ttu-id="95905-124">탐색 창에서 전자 **메일 설정**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="95905-124">In the navigation pane, select **Settings** > **Email notifications**.</span></span>

2. <span data-ttu-id="95905-125">항목 **추가 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="95905-125">Click **Add item**.</span></span>

3. <span data-ttu-id="95905-126">일반 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95905-126">Specify the General information:</span></span>
    - <span data-ttu-id="95905-127">**규칙 이름** - 알림 규칙의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95905-127">**Rule name** - Specify a name for the notification rule.</span></span>
    - <span data-ttu-id="95905-128">**조직 이름 포함** - 전자 메일 알림에 나타나는 고객 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95905-128">**Include organization name** - Specify the customer name that appears on the email notification.</span></span>
    - <span data-ttu-id="95905-129">**테넌트별** 포털 링크 포함 - 테넌트 ID가 포함된 링크를 추가하여 특정 테넌트에 대한 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="95905-129">**Include tenant-specific portal link** - Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    - <span data-ttu-id="95905-130">**장치 정보 포함** - 전자 메일 경고 본문에 장치 이름을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="95905-130">**Include device information** - Includes the device name in the email alert body.</span></span>

        > [!NOTE]
        > <span data-ttu-id="95905-131">이 정보는 끝점 데이터용 Defender에 대해 선택한 지리적 위치에 없는 받는 사람 메일 서버에서 처리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95905-131">This information might be processed by recipient mail servers that ar not in the geographic location you have selected for your Defender for Endpoint data.</span></span>

    - <span data-ttu-id="95905-132">**장치** - 받는 사람에게 모든 장치(전역 관리자 역할에만 해당) 또는 선택한 장치 그룹의 경고를 받는 사람에게 알릴지 여부를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="95905-132">**Devices** - Choose whether to notify recipients for alerts on all devices (Global administrator role only) or on selected device groups.</span></span> <span data-ttu-id="95905-133">자세한 내용은 장치 그룹 [만들기 및 관리를 참조하세요.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="95905-133">For more information, see [Create and manage device groups](machine-groups.md).</span></span>
    - <span data-ttu-id="95905-134">**경고 심각도** - 경고 심각도 수준을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95905-134">**Alert severity** - Choose the alert severity level.</span></span>

4. <span data-ttu-id="95905-135">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="95905-135">Click **Next**.</span></span>

5. <span data-ttu-id="95905-136">받는 사람의 전자 메일 주소를 입력한 다음 받는 사람 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="95905-136">Enter the recipient's email address then click **Add recipient**.</span></span> <span data-ttu-id="95905-137">이메일 주소를 여러 개 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95905-137">You can add multiple email addresses.</span></span>

6. <span data-ttu-id="95905-138">테스트 전자 메일 보내기 를 선택하여 전자 메일 받는 사람이 전자 메일 알림을 **받을 수 있는지 확인**</span><span class="sxs-lookup"><span data-stu-id="95905-138">Check that email recipients can receive the email notifications by selecting **Send test email**.</span></span>

7. <span data-ttu-id="95905-139">알림 **규칙 저장을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="95905-139">Click **Save notification rule**.</span></span>

## <a name="edit-a-notification-rule"></a><span data-ttu-id="95905-140">알림 규칙 편집</span><span class="sxs-lookup"><span data-stu-id="95905-140">Edit a notification rule</span></span>

1. <span data-ttu-id="95905-141">편집할 알림 규칙을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="95905-141">Select the notification rule you'd like to edit.</span></span>

2. <span data-ttu-id="95905-142">일반 및 받는 사람 탭 정보를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="95905-142">Update the General and Recipient tab information.</span></span>

3. <span data-ttu-id="95905-143">알림 **규칙 저장을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="95905-143">Click **Save notification rule**.</span></span>

## <a name="delete-notification-rule"></a><span data-ttu-id="95905-144">알림 규칙 삭제</span><span class="sxs-lookup"><span data-stu-id="95905-144">Delete notification rule</span></span>

1. <span data-ttu-id="95905-145">삭제할 알림 규칙을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="95905-145">Select the notification rule you'd like to delete.</span></span>

2. <span data-ttu-id="95905-146">**삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="95905-146">Click **Delete**.</span></span>

## <a name="troubleshoot-email-notifications-for-alerts"></a><span data-ttu-id="95905-147">경고에 대한 전자 메일 알림 문제 해결</span><span class="sxs-lookup"><span data-stu-id="95905-147">Troubleshoot email notifications for alerts</span></span>

<span data-ttu-id="95905-148">이 섹션에는 경고에 대한 전자 메일 알림을 사용할 때 발생할 수 있는 다양한 문제가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="95905-148">This section lists various issues that you may encounter when using email notifications for alerts.</span></span>

<span data-ttu-id="95905-149">**문제:** 의도한 받는 사람은 알림을 받고 있지 않다고 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="95905-149">**Problem:** Intended recipients report they're not getting the notifications.</span></span>

<span data-ttu-id="95905-150">**해결 방법:** 알림이 전자 메일 필터에 의해 차단되지 않는지 확인:</span><span class="sxs-lookup"><span data-stu-id="95905-150">**Solution:** Make sure that the notifications aren't blocked by email filters:</span></span>

1. <span data-ttu-id="95905-151">끝점용 Defender 전자 메일 알림이 정크 메일 폴더로 전송되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="95905-151">Check that the Defender for Endpoint email notifications aren't sent to the Junk Email folder.</span></span> <span data-ttu-id="95905-152">정크 아님으로 표시</span><span class="sxs-lookup"><span data-stu-id="95905-152">Mark them as Not junk.</span></span>
2. <span data-ttu-id="95905-153">전자 메일 보안 제품이 끝점용 Defender의 전자 메일 알림을 차단하지 않는지 확인</span><span class="sxs-lookup"><span data-stu-id="95905-153">Check that your email security product isn't blocking the email notifications from Defender for Endpoint.</span></span>
3. <span data-ttu-id="95905-154">끝점 전자 메일 알림을 위해 Defender를 catch하고 이동하고 있을 수 있는 전자 메일 응용 프로그램 규칙을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="95905-154">Check your email application rules that might be catching and moving your Defender for Endpoint email notifications.</span></span>

## <a name="related-topics"></a><span data-ttu-id="95905-155">관련 항목</span><span class="sxs-lookup"><span data-stu-id="95905-155">Related topics</span></span>

- [<span data-ttu-id="95905-156">데이터 보존 설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="95905-156">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="95905-157">고급 기능 구성</span><span class="sxs-lookup"><span data-stu-id="95905-157">Configure advanced features</span></span>](advanced-features.md)
