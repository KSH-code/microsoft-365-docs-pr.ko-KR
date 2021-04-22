---
title: Microsoft 365 보안 센터에서 사용자 분석
description: Microsoft 365 보안 센터에서 사용자 분석
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
ms.openlocfilehash: 1fb5a4eee41384ef1afc9b46e5bf538344718fe9
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939733"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a><span data-ttu-id="07c0d-104">Microsoft 365 보안 센터에서 사용자 분석</span><span class="sxs-lookup"><span data-stu-id="07c0d-104">Analyze users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="07c0d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="07c0d-105">**Applies to:**</span></span>

- <span data-ttu-id="07c0d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07c0d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="07c0d-107">인시던트 분석의 일부로 사용자 계정을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c0d-107">Part of your incident analysis can include user accounts.</span></span> <span data-ttu-id="07c0d-108">사용자 탭에서 인시던트  및 인시던트 & 인시던트에 대한 사용자 >*>* **합니다.** </span><span class="sxs-lookup"><span data-stu-id="07c0d-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="인시던트에 대한 사용자 페이지의 예":::

<span data-ttu-id="07c0d-110">인시던트에 대한 사용자 계정을 빠르게 요약하려면 사용자 계정 이름 옆의 확인 표시를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07c0d-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="07c0d-111">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="07c0d-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Microsoft 365 보안 센터의 인시던트에 대한 사용자 계정 요약 창의 예":::

<span data-ttu-id="07c0d-113">여기에서 사용자 페이지로  이동을 선택하여 사용자 계정의 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c0d-113">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="07c0d-114">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="07c0d-114">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Microsoft 365 보안 센터의 인시던트에 대한 사용자 계정 페이지의 예":::

<span data-ttu-id="07c0d-116">사용자 페이지의 목록에서 사용자 계정의 이름을 선택하여 이 페이지를 볼 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c0d-116">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="07c0d-117">Microsoft 365 보안 센터 사용자 페이지는 끝점용 Microsoft Defender, ID용 Microsoft Defender 및 Microsoft Cloud App Security의 정보를 결합합니다(사용중인 라이선스에 따라 다름).</span><span class="sxs-lookup"><span data-stu-id="07c0d-117">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="07c0d-118">이 페이지에는 사용자 계정의 보안 위험과 관련한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c0d-118">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="07c0d-119">여기에는 위험 및 최근 이벤트를 평가하는 데 도움이 되는 점수와 사용자의 전반적인 위험에 기여한 경고가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c0d-119">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="07c0d-120">이 페이지에서는 다음 추가 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c0d-120">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="07c0d-121">사용자 계정을 손상된 것으로 표시</span><span class="sxs-lookup"><span data-stu-id="07c0d-121">Mark the user account as compromised</span></span>
- <span data-ttu-id="07c0d-122">사용자에게 다시 로그인하도록 요구</span><span class="sxs-lookup"><span data-stu-id="07c0d-122">Require the user to sign in again</span></span>
- <span data-ttu-id="07c0d-123">사용자 계정 일시 중단</span><span class="sxs-lookup"><span data-stu-id="07c0d-123">Suspend the user account</span></span>
- <span data-ttu-id="07c0d-124">Azure AD(Azure Active Directory) 사용자 계정 설정 참조</span><span class="sxs-lookup"><span data-stu-id="07c0d-124">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="07c0d-125">사용자 계정이 소유한 파일 보기</span><span class="sxs-lookup"><span data-stu-id="07c0d-125">View the files owned by the user account</span></span>
- <span data-ttu-id="07c0d-126">이 사용자와 공유된 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c0d-126">View files shared with this user.</span></span> 

<span data-ttu-id="07c0d-127">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="07c0d-127">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 보안 센터에서 인시던트에 대한 사용자 계정의 작업 예":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="07c0d-129">관련 항목</span><span class="sxs-lookup"><span data-stu-id="07c0d-129">Related topics</span></span>

- [<span data-ttu-id="07c0d-130">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="07c0d-130">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="07c0d-131">인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="07c0d-131">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="07c0d-132">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="07c0d-132">Manage incidents</span></span>](manage-incidents.md)