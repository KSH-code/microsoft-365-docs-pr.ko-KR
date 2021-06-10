---
title: Defender에서 전자 메일로 인시던트 Microsoft 365 확인
description: Defender에서 인시던트에 대한 전자 메일 알림을 받을 수 있는 규칙을 Microsoft 365 방법
keywords: 인시던트, 전자 메일, 전자 메일 알림, 구성, 사용자, 사서함, 전자 메일, 인시던트, 분석, 응답
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2e47b35646a1cd6e1075d80f9ed0550e8e1e819f
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651395"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="dfa14-104">전자 메일로 인시던트 알림 확인</span><span class="sxs-lookup"><span data-stu-id="dfa14-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dfa14-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="dfa14-105">**Applies to:**</span></span>
- <span data-ttu-id="dfa14-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dfa14-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="dfa14-107">Defender를 설정하여 Microsoft 365 인시던트 또는 기존 인시던트에 대한 업데이트에 대한 전자 메일을 직원에게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-107">You can set up Microsoft 365 Defender to notify your staff with an email about new incidents or updates to existing incidents.</span></span> <span data-ttu-id="dfa14-108">다음에 따라 알림을 하게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-108">You can choose to get notifications based on:</span></span>

- <span data-ttu-id="dfa14-109">인시던트 심각도.</span><span class="sxs-lookup"><span data-stu-id="dfa14-109">Incident severity.</span></span>
- <span data-ttu-id="dfa14-110">장치 그룹.</span><span class="sxs-lookup"><span data-stu-id="dfa14-110">Device group.</span></span>
- <span data-ttu-id="dfa14-111">인시던트당 첫 번째 업데이트에만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-111">Only on the first update per incident.</span></span>

<span data-ttu-id="dfa14-112">전자 메일 알림에는 인시던트 이름, 심각도, 범주 등 인시던트에 대한 중요한 세부 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="dfa14-113">인시던트로 바로 이동하여 분석을 바로 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-113">You can also go directly to the incident and start your analysis right away.</span></span> <span data-ttu-id="dfa14-114">자세한 내용은 인시던트 [조사를 참조하세요.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="dfa14-114">For more information, see [Investigate incidents](investigate-incidents.md).</span></span>

<span data-ttu-id="dfa14-115">전자 메일 알림에서 받는 사람을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-115">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="dfa14-116">새 받는 사람은 인시던트가 추가된 후 인시던트에 대한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-116">New recipients get notified about incidents after they're added.</span></span> 

>[!NOTE]
><span data-ttu-id="dfa14-117">전자 메일 알림 설정을 구성하려면 '보안 설정 관리' 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-117">You need the 'Manage security settings' permission to configure email notification settings.</span></span> <span data-ttu-id="dfa14-118">기본 사용 권한 관리를 사용하도록 선택한 경우 보안 관리자 또는 전역 관리자 역할이 있는 사용자는 자동으로 전자 메일 알림을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-118">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="dfa14-119">마찬가지로 조직에서 RBAC(역할 기반 액세스 제어)를 사용하는 경우 관리할 수 있는 장치 그룹에 따라 알림을 만들고, 편집하고, 삭제하고, 받을 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-119">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-a-rule-for-email-notifications"></a><span data-ttu-id="dfa14-120">전자 메일 알림에 대한 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="dfa14-120">Create a rule for email notifications</span></span>

<span data-ttu-id="dfa14-121">다음 단계에 따라 새 규칙을 만들고 전자 메일 알림 설정을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-121">Follow these steps to create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="dfa14-122">탐색 창에서 Defender 설정 > Microsoft 365 인시던트 > **알림을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfa14-122">In the navigation pane, select **Settings > Microsoft 365 Defender > Incident email notifications**.</span></span>
2. <span data-ttu-id="dfa14-123">항목 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfa14-123">Select **Add item**.</span></span>
3. <span data-ttu-id="dfa14-124">기본 **페이지에서** 규칙 이름과 설명을 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfa14-124">On the **Basics** page, type the rule name and a description, and then select **Next**.</span></span>
4. <span data-ttu-id="dfa14-125">알림 **설정 페이지에서** 다음을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-125">On the **Notification settings** page, configure:</span></span>
    - <span data-ttu-id="dfa14-126">**경고 심각도** - 인시던트 알림을 트리거하는 경고 심각도 선택.</span><span class="sxs-lookup"><span data-stu-id="dfa14-126">**Alert severity** - Choose the alert severities that will trigger an incident notification.</span></span> <span data-ttu-id="dfa14-127">예를 들어 심각도 높은 인시던트에 대한 정보만 원할 경우 높음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfa14-127">For example, if you only want to be informed about high-severity incidents, select **High**.</span></span>
    - <span data-ttu-id="dfa14-128">**장치 그룹 범위** - 모든 장치 그룹을 지정하거나 테넌트의 장치 그룹 목록에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-128">**Device group scope** - You can specify all device groups or select from the list of device groups in your tenant.</span></span>
    - <span data-ttu-id="dfa14-129">**인시던트당 첫** 번째 발생에만 알림 - 다른 선택과 일치하는 첫 번째 경고에만 알림을 하려는 경우를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-129">**Only notify on first occurrence per incident** - Select if you want a notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="dfa14-130">이후 업데이트 또는 인시던트와 관련된 경고는 추가 알림을 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-130">Later updates or alerts related to the incident won't send additional notifications.</span></span>
    - <span data-ttu-id="dfa14-131">**전자 메일에** 조직 이름 포함 - 전자 메일 알림에 조직 이름을 표시하려면 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-131">**Include organization name in the email** - Select if you want your organization name to appear in the email notification.</span></span>
    - <span data-ttu-id="dfa14-132">**테넌트별** 포털 링크 포함 - 특정 테넌트에 대한 액세스를 위해 전자 메일 알림에 테넌트 ID가 포함된 링크를 Microsoft 365 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-132">**Include tenant-specific portal link** - Select if you want to add a link with the tenant ID in the email notification for access to a specific Microsoft 365 tenant.</span></span>

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="인시던트 전자 메일 알림에 대한 알림 설정":::

5. <span data-ttu-id="dfa14-134">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-134">Select **Next**.</span></span> <span data-ttu-id="dfa14-135">받는 **사람 페이지에서** 인시던트 알림을 받을 전자 메일 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-135">On the **Recipients** page, add the email addresses that will receive the incident notifications.</span></span> <span data-ttu-id="dfa14-136">각 **새 전자** 메일 주소를 입력한 후 추가를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-136">Select **Add** after typing each new email address.</span></span> <span data-ttu-id="dfa14-137">알림을 테스트하고 받는 사람이 받은 편지함으로 받는지 확인하려면 테스트 전자 메일 **보내기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfa14-137">To test notifications and ensure that the recipients receive them in the inboxes, select **Send test email**.</span></span> 
6. <span data-ttu-id="dfa14-138">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-138">Select **Next**.</span></span> <span data-ttu-id="dfa14-139">규칙 **검토 페이지에서** 규칙 설정을 검토한 다음 규칙 만들기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfa14-139">On the **Review rule** page, review the settings of the rule, and then select **Create rule**.</span></span> <span data-ttu-id="dfa14-140">받는 사람은 설정에 따라 전자 메일을 통해 인시던트 알림을 수신하기 시작할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

<span data-ttu-id="dfa14-141">기존 규칙을 편집하려면 규칙 목록에서 해당 규칙을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-141">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="dfa14-142">규칙 이름이 있는 창에서 규칙  편집을 선택하고 **기본,** 알림 설정 및 받는 사람 페이지에서 **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfa14-142">On the pane with the rule name, select **Edit rule** and make your changes on the **Basics**, **Notification settings**, and **Recipients** pages.</span></span>

<span data-ttu-id="dfa14-143">규칙을 삭제하려면 규칙 목록에서 규칙을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa14-143">To delete a rule, select it from the list of rules.</span></span> <span data-ttu-id="dfa14-144">규칙 이름이 있는 창에서 삭제를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfa14-144">On the pane with the rule name, select **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="dfa14-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfa14-145">See also</span></span>
- [<span data-ttu-id="dfa14-146">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="dfa14-146">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="dfa14-147">인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="dfa14-147">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="dfa14-148">인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="dfa14-148">Investigate incidents</span></span>](investigate-incidents.md)
