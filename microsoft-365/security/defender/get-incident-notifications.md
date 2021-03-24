---
title: Microsoft 365 Defender에서 인시던트 알림 다운로드
description: Microsoft 365 Defender에서 인시던트에 대한 전자 메일 알림을 받을 수 있는 규칙을 만드는 방법을 배우기
keywords: 인시던트, 전자 메일, 전자 메일 알림, 구성, 사용자, 사서함, 전자 메일, 인시던트
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
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
ms.openlocfilehash: 42600b360061626938aa13a09f1ed1b42fdfe48c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070063"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="36521-104">전자 메일로 인시던트 알림 확인</span><span class="sxs-lookup"><span data-stu-id="36521-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="36521-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="36521-105">**Applies to:**</span></span>
- <span data-ttu-id="36521-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36521-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="36521-107">기존 인시던트에 대한 새로운 인시던트 또는 새 업데이트가 될 때마다 전자 메일로 알리도록 Microsoft 365 Defender를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36521-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="36521-108">인시던트 심각도에 따라 또는 장치 그룹으로 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36521-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="36521-109">인시던트당 첫 번째 업데이트에만 알림을 하게 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36521-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="36521-110">전자 메일 알림에서 받는 사람을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36521-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="36521-111">새로 추가된 받는 사람은 인시던트가 추가된 후 인시던트에 대한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36521-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="36521-112">전자 메일 알림에는 인시던트 이름, 심각도, 범주 등 인시던트에 대한 중요한 세부 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36521-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="36521-113">인시던트로 직접 이동하여 조사를 바로 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36521-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="36521-114">인시던트 조사에 대한 자세한 내용은 [Microsoft 365 Defender에서](./investigate-incidents.md)인시던트 조사를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="36521-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](./investigate-incidents.md).</span></span>

>[!NOTE]
><span data-ttu-id="36521-115">전자 메일 알림 설정을 구성하려면 '보안 설정 관리' 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="36521-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="36521-116">기본 사용 권한 관리를 사용하도록 선택한 경우 보안 관리자 또는 전역 관리자 역할이 있는 사용자는 자동으로 전자 메일 알림을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36521-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="36521-117">마찬가지로 조직에서 RBAC(역할 기반 액세스 제어)를 사용하는 경우 관리할 수 있는 장치 그룹에 따라 알림을 만들고, 편집하고, 삭제하고, 받을 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36521-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="36521-118">인시던트 알림에 대한 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="36521-118">Create rules for incident notifications</span></span>

<span data-ttu-id="36521-119">인시던트에 대한 첫 번째 전자 메일 알림을 설정하려면 새 규칙을 만들고 전자 메일 알림 설정을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="36521-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="36521-120">탐색 창에서 설정 **인시던트**  >  **전자 메일 알림 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="36521-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="36521-121">항목 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="36521-121">Select **Add item**.</span></span>
3. <span data-ttu-id="36521-122">이름에 규칙 이름을 지정하고 **설명을** **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="36521-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![문제 전자 메일 알림에 대한 규칙 창 만들기](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="36521-124">**다음을** 선택하여 알림 **설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="36521-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="36521-125">여기서 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36521-125">Here you can specify:</span></span>
    - <span data-ttu-id="36521-126">**경고 심각도** - 인시던트 알림을 트리거하는 경고 심각도 선택.</span><span class="sxs-lookup"><span data-stu-id="36521-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="36521-127">예를 들어 심각도 높음 인시던트에 대한 정보만 원할 경우 높음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36521-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="36521-128">**장치 그룹 범위** - 이 드롭다운에는 사용자가 액세스할 수 있는 모든 장치 그룹이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="36521-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="36521-129">인시던트 알림 규칙을 만들 장치 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36521-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="36521-130">**인시던트당 첫** 번째 발생 시만 알림 - 이 옵션을 선택하면 다른 선택과 일치하는 첫 번째 경고에만 전자 메일 알림이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="36521-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="36521-131">나중에 인시던트와 관련된 업데이트 또는 경고는 알림을 트리거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36521-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="36521-132">**조직 이름 포함** - 고객 이름이 전자 메일 알림에 나타나는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36521-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="36521-133">**테넌트별** 포털 링크 포함 - 테넌트 ID가 포함된 링크를 추가하여 특정 테넌트에 대한 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="36521-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![인시던트 전자 메일 알림 설정 창에 알림](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="36521-135">다음을 선택하여 받는 **사람 섹션으로** 이동하십시오. </span><span class="sxs-lookup"><span data-stu-id="36521-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="36521-136">여기서 인시던트 전자 메일 알림을 받을 전자 메일 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36521-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="36521-137">모든 **전자 메일 주소를 입력한** 후 받는 사람 추가를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36521-137">Select **Add a recipient** after typing every email address.</span></span>

    ![인시던트 전자 메일 알림에 대한 받는 사람 창 추가](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="36521-139">마지막으로 **다음을** 선택하여 새  규칙과 연결된 모든 설정을 볼 수 있도록 규칙 검토로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="36521-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="36521-140">받는 사람은 설정에 따라 전자 메일을 통해 인시던트 알림을 수신하기 시작할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="36521-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="36521-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36521-141">See also</span></span>
- [<span data-ttu-id="36521-142">Microsoft 365 Defender의 인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="36521-142">Incidents overview in Microsoft 365 Defender</span></span>](./incidents-overview.md)
- [<span data-ttu-id="36521-143">Microsoft 365 Defender에서 인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="36521-143">Prioritize incidents in Microsoft 365 Defender</span></span>](./incident-queue.md)
- [<span data-ttu-id="36521-144">Microsoft 365 Defender에서 인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="36521-144">Investigate incidents in Microsoft 365 Defender</span></span>](./investigate-incidents.md)
