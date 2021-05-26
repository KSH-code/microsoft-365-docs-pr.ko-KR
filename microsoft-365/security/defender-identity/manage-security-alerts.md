---
title: Microsoft Defender for Identity security alerts in Microsoft 365 Defender
description: Microsoft Defender에서 ID에 대해 Microsoft Defender에서 발행한 보안 경고를 관리하고 검토하는 Microsoft 365 정보
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: 0c48c9076d05cd352229477acc28b32185eef54f
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657853"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a><span data-ttu-id="8eb38-103">Defender의 ID 보안 경고에 대한 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8eb38-103">Defender for Identity security alerts in Microsoft 365 Defender</span></span>

<span data-ttu-id="8eb38-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8eb38-104">**Applies to:**</span></span>

- <span data-ttu-id="8eb38-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8eb38-105">Microsoft 365 Defender</span></span>
- <span data-ttu-id="8eb38-106">ID용 Defender</span><span class="sxs-lookup"><span data-stu-id="8eb38-106">Defender for Identity</span></span>

<span data-ttu-id="8eb38-107">이 문서에서는 보안 센터에서 Microsoft [Defender for Identity](/defender-for-identity) 보안 경고를 Microsoft 365 [방법을 설명합니다.](/microsoft-365/security/defender/overview-security-center)</span><span class="sxs-lookup"><span data-stu-id="8eb38-107">This article explains the basics of how to work with [Microsoft Defender for Identity](/defender-for-identity) security alerts in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="8eb38-108">ID 경고에 대한 Defender는 기본적으로 전용 ID [Microsoft 365](https://security.microsoft.com) 페이지 형식으로 보안 센터에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-108">Defender for Identity alerts are natively integrated into the [Microsoft 365 security center](https://security.microsoft.com) with a dedicated Identity alert page format.</span></span> <span data-ttu-id="8eb38-109">이는 Id에 대한 전체 Microsoft Defender 환경을 Microsoft 365 [단계를 표시하는 것입니다.](/defender-for-identity/defender-for-identity-in-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="8eb38-109">This marks the first step in the journey to [introduce the full Microsoft Defender for Identity experience into Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span></span>

<span data-ttu-id="8eb38-110">새 ID 경고 페이지에서는 Microsoft Defender for Identity 고객에게 도메인 간 신호 향상 및 새로운 자동화된 ID 응답 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-110">The new Identity alert page gives Microsoft Defender for Identity customers better cross-domain signal enrichment and new automated identity response capabilities.</span></span> <span data-ttu-id="8eb38-111">보안 유지를 보장하고 보안 작업의 효율성을 개선하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-111">It ensures that you stay secure and helps improve the efficiency of your security operations.</span></span>

<span data-ttu-id="8eb38-112">[Microsoft 365 Defender를](/microsoft-365/security/defender/microsoft-365-defender) 통해 경고를 조사할 때의 이점 중 하나는 ID에 대한 Microsoft Defender 경고가 제품군의 각 다른 제품에서 얻은 정보와 추가로 상호 관련되어 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-112">One of the benefits of investigating alerts through [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) is that Microsoft Defender for Identity alerts are further correlated with information obtained from each of the other products in the suite.</span></span> <span data-ttu-id="8eb38-113">이러한 향상된 경고는 Microsoft Defender for Microsoft 365 및 끝점용 [Microsoft Defender에서](/microsoft-365/security/office-365-security) Office 365 Defender 경고 형식과 [일치합니다.](/microsoft-365/security/defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="8eb38-113">These enhanced alerts are consistent with the other Microsoft 365 Defender alert formats originating from [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security) and [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span> <span data-ttu-id="8eb38-114">새 페이지에서는 ID와 관련된 경고를 조사하기 위해 다른 제품 포털로 이동할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-114">The new page effectively eliminates the need to navigate to another product portal to investigate alerts associated with identity.</span></span>

<span data-ttu-id="8eb38-115">ID에 대한 [Defender에서](/microsoft-365/security/defender/m365d-autoir) 시작된 경고는 이제 경고를 자동으로 수정하고 의심스러운 활동에 기여할 수 있는 도구 및 프로세스의 완화를 포함하여 Microsoft 365 Defender 자동화된 조사 및 대응(AIR) 기능을 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-115">Alerts originating from Defender for Identity can now trigger the [Microsoft 365 Defender automated investigation and response (AIR)](/microsoft-365/security/defender/m365d-autoir) capabilities, including automatically remediating alerts and the mitigation of tools and processes that can contribute to the suspicious activity.</span></span>

>[!IMPORTANT]
><span data-ttu-id="8eb38-116">Microsoft 365 Defender와의 수렴의 일부로 일부 옵션 및 세부 사항은 ID용 Defender 포털의 해당 위치에서 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-116">As part of the convergence with Microsoft 365 Defender, some options and details have changed from their location in the Defender for Identity portal.</span></span> <span data-ttu-id="8eb38-117">익숙한 기능과 새로운 기능을 모두 찾을 수 있는 위치를 확인하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-117">Please read the details below to discover where to find both the familiar and new features.</span></span>

## <a name="review-security-alerts"></a><span data-ttu-id="8eb38-118">보안 경고 검토</span><span class="sxs-lookup"><span data-stu-id="8eb38-118">Review security alerts</span></span>

<span data-ttu-id="8eb38-119">경고 페이지, 인시던트 페이지,  개별 장치의  페이지 및 고급 헌팅 페이지를 비롯한 여러 위치에서 경고에 액세스할 **수** 있습니다. </span><span class="sxs-lookup"><span data-stu-id="8eb38-119">Alerts can be accessed from multiple locations, including the **Alerts** page, the **Incidents** page, the pages of individual **Devices**, and from the **Advanced hunting** page.</span></span> <span data-ttu-id="8eb38-120">이 예제에서는 경고 페이지를 **검토합니다.**</span><span class="sxs-lookup"><span data-stu-id="8eb38-120">In this example, we'll review the **Alerts page**.</span></span>  

<span data-ttu-id="8eb38-121">보안 [Microsoft 365 에서](https://security.microsoft.com/) **인시던트** & 경고로 이동한 다음 **경고로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="8eb38-121">In the [Microsoft 365 security center](https://security.microsoft.com/), go to **Incidents & alerts** and then to **Alerts**.</span></span>

![인시던트 및 경고로 이동한 다음 경고](../../media/defender-identity/incidents-alerts.png)

<span data-ttu-id="8eb38-123">ID에 대한 Defender의 경고를 확인하려면 오른쪽 위에 있는  필터를 선택한 다음 서비스 원본에서 ID에 **대한 Microsoft Defender를** 선택하고 **적용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8eb38-123">To see alerts from Defender for Identity, on the top-right select **Filter**, and then under **Service sources** select **Microsoft Defender for Identity**, and select **Apply**:</span></span>

![ID 이벤트에 대한 Defender에 대한 필터](../../media/defender-identity/filter-defender-for-identity.png)

<span data-ttu-id="8eb38-125">경고는 경고 이름, 태그, **심각도,** 조사  **상태,** **상태,** **범주,** 검색 **원본,** 영향 있는 **자산,** 첫 번째 활동 및 마지막 활동 열의 정보와 함께 **표시됩니다.** </span><span class="sxs-lookup"><span data-stu-id="8eb38-125">The alerts are displayed with information in the following columns: **Alert name**, **Tags**, **Severity**, **Investigation state**, **Status**, **Category**, **Detection source**, **Impacted assets**, **First activity**, and **Last activity**.</span></span>

![ID에 대한 Defender 이벤트](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a><span data-ttu-id="8eb38-127">경고 관리</span><span class="sxs-lookup"><span data-stu-id="8eb38-127">Manage alerts</span></span>

<span data-ttu-id="8eb38-128">경고 중 하나에 대한 **경고** 이름을 클릭하면 경고에 대한 세부 정보가 있는 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-128">If you click the **Alert name** for one of the alerts, you'll go to the page with details about the alert.</span></span> <span data-ttu-id="8eb38-129">왼쪽 창에는 발생된 일에 대한 **요약이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8eb38-129">In the left pane, you'll see a summary of **What happened**:</span></span>

![경고에서 발생된 일](../../media/defender-identity/what-happened.png)

<span data-ttu-id="8eb38-131">진행 **중 상자** 위에는 경고의 **계정,** **대상** 호스트 및 원본 호스트에 **대한** 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-131">Above the **What happened** box are buttons for the **Accounts**, **Destination Host** and **Source Host** of the alert.</span></span> <span data-ttu-id="8eb38-132">다른 경고의 경우 추가 호스트, 계정, IP 주소, 도메인 및 보안 그룹에 대한 자세한 내용은 단추가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-132">For other alerts, you might see buttons for details about additional hosts, accounts, IP addresses, domains, and security groups.</span></span> <span data-ttu-id="8eb38-133">관련된 엔터티에 대한 자세한 내용을 확인하려면 해당 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-133">Select any of them to get more details about the entities involved.</span></span>

<span data-ttu-id="8eb38-134">오른쪽 창에 경고 세부 정보가 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="8eb38-134">On the right pane, you'll see the **Alert details**.</span></span> <span data-ttu-id="8eb38-135">여기에서 자세한 내용을 보고 여러 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-135">Here you can see more details and perform several tasks:</span></span>

- <span data-ttu-id="8eb38-136">**이 경고 분류** - 여기에서 이 경고를 True 경고 또는 거짓 **경고로 지정할** **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8eb38-136">**Classify this alert** - Here you can designate this alert as a **True alert** or **False alert**</span></span>

    ![경고 분류](../../media/defender-identity/classify-alert.png)

- <span data-ttu-id="8eb38-138">**경고 상태** - **분류 설정에서** 경고를 True 또는 **False로** 분류할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8eb38-138">**Alert state** - In **Set Classification**, you can classify the alert as **True** or **False**.</span></span> <span data-ttu-id="8eb38-139">할당된 **에서** 경고를 직접 할당하거나 할당을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-139">In **Assigned to**, you can assign the alert to yourself or unassign it.</span></span>

    ![경고 상태](../../media/defender-identity/alert-state.png)

- <span data-ttu-id="8eb38-141">**경고** 세부 정보 - 경고 세부 정보에서 특정 경고에 대한 자세한 정보를 찾고, 경고 유형에 대한 설명서 링크를 따라가고, 경고가 연결된 인시던트 확인, 이 경고 유형에 연결된 자동화된 조사를 검토하고, 영향을 미치는 장치 및 사용자를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-141">**Alert details** - Under **Alert details**, you can find more information about the specific alert, follow a link to documentation about the type of alert, see which incident the alert is associated with, review any automated investigations linked to this alert type, and see the impacted devices and users.</span></span>

    ![경고 세부 정보](../../media/defender-identity/alert-details.png)

- <span data-ttu-id="8eb38-143">**설명 &** 기록 - 여기에서 경고에 의견을 추가하고 경고와 연결된 모든 작업의 기록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-143">**Comments & history** - Here you can add your comments to the alert, and see the history of all actions associated with the alert.</span></span>

    ![설명 및 기록](../../media/defender-identity/comments-history.png)

- <span data-ttu-id="8eb38-145">경고 관리 - 경고 관리를 선택하면 다음을 편집할 수 있는 창으로 이동하게 **됩니다.**</span><span class="sxs-lookup"><span data-stu-id="8eb38-145">**Manage alert** - If you select **Manage alert**, you'll go to a pane that will allow you to edit the:</span></span>
  - <span data-ttu-id="8eb38-146">**상태** - 새로, 해결 **또는** 진행 **중 을 선택할 수 있습니다.** </span><span class="sxs-lookup"><span data-stu-id="8eb38-146">**Status** - You can choose **New**, **Resolved** or **In progress**.</span></span>
  - <span data-ttu-id="8eb38-147">**분류** - True 경고 **또는 거짓 경고를** **선택할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8eb38-147">**Classification** - You can choose **True alert** or **False alert**.</span></span>
  - <span data-ttu-id="8eb38-148">**설명** - 경고에 대한 설명을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-148">**Comment** - You can add a comment about the alert.</span></span>

    <span data-ttu-id="8eb38-149">경고 관리 옆에 있는 세 개의 점을 선택하면 위협 전문가에게 **문의,** 경고를 Excel 파일로 내보내기 또는 다른 인시던트에 연결 을 선택할 **수 있습니다.** </span><span class="sxs-lookup"><span data-stu-id="8eb38-149">If you select the three dots next to **Manage alert**, you can **Consult a threat expert**, **Export** the alert to an Excel file, or **Link to another incident**.</span></span>

    ![경고 관리](../../media/defender-identity/manage-alert.png)

    >[!NOTE]
    ><span data-ttu-id="8eb38-151">이제 Excel 두 개의 링크를 사용할 수 있습니다. **Id에 대한 Microsoft Defender의** 보기 및 Microsoft 365 **Defender의 보기.**</span><span class="sxs-lookup"><span data-stu-id="8eb38-151">In the Excel file, you now have two links available: **View in Microsoft Defender for Identity** and **View in Microsoft 365 Defender**.</span></span> <span data-ttu-id="8eb38-152">각 링크는 관련 포털로 이동하고 경고에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb38-152">Each link will bring you to the relevant portal, and provide information about the alert there.</span></span>

## <a name="see-also"></a><span data-ttu-id="8eb38-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8eb38-153">See also</span></span>

- [<span data-ttu-id="8eb38-154">Defender에서 경고 Microsoft 365 조사</span><span class="sxs-lookup"><span data-stu-id="8eb38-154">Investigate alerts in Microsoft 365 Defender</span></span>](../defender/investigate-alerts.md)
