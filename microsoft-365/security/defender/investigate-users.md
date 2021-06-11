---
title: Defender에서 Microsoft 365 조사
description: 보안 센터에서 인시던트가 Microsoft 365 조사합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, 모니터링, 보고서, ID, 데이터, 장치, 앱, 인시던트, 분석, 응답
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572804"
---
# <a name="investigate-users-in-microsoft-365-defender"></a><span data-ttu-id="f392c-104">Defender에서 Microsoft 365 조사</span><span class="sxs-lookup"><span data-stu-id="f392c-104">Investigate users in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f392c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f392c-105">**Applies to:**</span></span>

- <span data-ttu-id="f392c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f392c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f392c-107">인시던트 조사의 일부에는 사용자 계정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f392c-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="f392c-108">사용자 탭에서 인시던트  및 인시던트 & 인시던트에 대한 사용자 >*>* **합니다.** </span><span class="sxs-lookup"><span data-stu-id="f392c-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="인시던트에 대한 사용자 페이지의 예":::

<span data-ttu-id="f392c-110">인시던트에 대한 사용자 계정을 빠르게 요약하려면 사용자 계정 이름 옆의 확인 표시를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f392c-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="f392c-111">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f392c-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="보안 센터의 인시던트에 대한 사용자 계정 Microsoft 365 창의 예":::

> [!NOTE]
> <span data-ttu-id="f392c-113">사용자 페이지에 Azure Active Directory(Azure AD) 조직 및 그룹이 표시되어 사용자와 연결된 그룹 및 사용 권한을 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f392c-113">The User page shows Azure Active Directory (Azure AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="f392c-114">이 플라이아웃 페이지에서 현재 인시던트, 활성 경고, 위험 수준, 사용자 노출, 계정, 장치 등을 비롯한 사용자 위협 정보를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f392c-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="f392c-115">또한 보안 센터에서 직접 Microsoft 365 조치를 취하여 손상된 사용자를 해결하고, 사용자가 손상된 것을 확인하거나 다시 로그인하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f392c-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="f392c-116">여기에서 사용자 페이지로  이동을 선택하여 사용자 계정의 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f392c-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="f392c-117">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f392c-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="보안 센터의 인시던트에 대한 사용자 계정 Microsoft 365 예":::

<span data-ttu-id="f392c-119">사용자 페이지의 목록에서 사용자 계정의 이름을 선택하여 이 페이지를 볼 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f392c-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="f392c-120">Microsoft 365 보안 센터 사용자 페이지는 끝점용 Microsoft Defender, ID용 Microsoft Defender 및 Microsoft Cloud App Security 정보를 결합합니다(사용중인 라이선스에 따라 다를 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="f392c-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="f392c-121">이 페이지에는 사용자 계정의 보안 위험과 관련한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f392c-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="f392c-122">여기에는 위험 및 최근 이벤트를 평가하는 데 도움이 되는 점수와 사용자의 전반적인 위험에 기여한 경고가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f392c-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="f392c-123">이 페이지에서는 다음 추가 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f392c-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="f392c-124">사용자 계정을 손상된 것으로 표시</span><span class="sxs-lookup"><span data-stu-id="f392c-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="f392c-125">사용자에게 다시 로그인하도록 요구</span><span class="sxs-lookup"><span data-stu-id="f392c-125">Require the user to sign in again</span></span>
- <span data-ttu-id="f392c-126">사용자 계정 일시 중단</span><span class="sxs-lookup"><span data-stu-id="f392c-126">Suspend the user account</span></span>
- <span data-ttu-id="f392c-127">Azure AD(Azure Active Directory 계정 설정) 참조</span><span class="sxs-lookup"><span data-stu-id="f392c-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="f392c-128">사용자 계정이 소유한 파일 보기</span><span class="sxs-lookup"><span data-stu-id="f392c-128">View the files owned by the user account</span></span>
- <span data-ttu-id="f392c-129">이 사용자와 공유된 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f392c-129">View files shared with this user.</span></span> 

<span data-ttu-id="f392c-130">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f392c-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 보안 센터에서 인시던트에 대한 사용자 계정에 대한 작업의 예":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a><span data-ttu-id="f392c-132">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f392c-132">Next steps</span></span>

<span data-ttu-id="f392c-133">In-process 인시던트에 필요한 경우 조사를 [계속합니다.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="f392c-133">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f392c-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f392c-134">See also</span></span>

- [<span data-ttu-id="f392c-135">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="f392c-135">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f392c-136">인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="f392c-136">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="f392c-137">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="f392c-137">Manage incidents</span></span>](manage-incidents.md)