---
title: Microsoft 365 보안 센터에서 사용자 조사
description: Microsoft 365 보안 센터에서 사용자 조사
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, 모니터링, 보고서, ID, 데이터, 장치, 앱
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
ms.openlocfilehash: 68fc924ee14932ebdf92ef76306ba00e352b6030
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861276"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="19d4b-104">Microsoft 365 보안 센터에서 사용자 조사</span><span class="sxs-lookup"><span data-stu-id="19d4b-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="19d4b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="19d4b-105">**Applies to:**</span></span>

- <span data-ttu-id="19d4b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19d4b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="19d4b-107">인시던트 조사의 일부에는 사용자 계정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="19d4b-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="19d4b-108">사용자 탭에서 인시던트  및 인시던트 & 인시던트에 대한 사용자 >*>* **합니다.** </span><span class="sxs-lookup"><span data-stu-id="19d4b-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="인시던트에 대한 사용자 페이지의 예":::

<span data-ttu-id="19d4b-110">인시던트에 대한 사용자 계정을 빠르게 요약하려면 사용자 계정 이름 옆의 확인 표시를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19d4b-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="19d4b-111">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="19d4b-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Microsoft 365 보안 센터의 인시던트에 대한 사용자 계정 요약 창의 예":::

<span data-ttu-id="19d4b-113">여기에서 사용자 페이지로  이동을 선택하여 사용자 계정의 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19d4b-113">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="19d4b-114">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="19d4b-114">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Microsoft 365 보안 센터의 인시던트에 대한 사용자 계정 페이지의 예":::

<span data-ttu-id="19d4b-116">사용자 페이지의 목록에서 사용자 계정의 이름을 선택하여 이 페이지를 볼 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19d4b-116">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="19d4b-117">Microsoft 365 보안 센터 사용자 페이지는 끝점용 Microsoft Defender, ID용 Microsoft Defender 및 Microsoft Cloud App Security의 정보를 결합합니다(사용중인 라이선스에 따라 다름).</span><span class="sxs-lookup"><span data-stu-id="19d4b-117">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="19d4b-118">이 페이지에는 사용자 계정의 보안 위험과 관련한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="19d4b-118">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="19d4b-119">여기에는 위험 및 최근 이벤트를 평가하는 데 도움이 되는 점수와 사용자의 전반적인 위험에 기여한 경고가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="19d4b-119">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="19d4b-120">이 페이지에서는 다음 추가 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19d4b-120">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="19d4b-121">사용자 계정을 손상된 것으로 표시</span><span class="sxs-lookup"><span data-stu-id="19d4b-121">Mark the user account as compromised</span></span>
- <span data-ttu-id="19d4b-122">사용자에게 다시 로그인하도록 요구</span><span class="sxs-lookup"><span data-stu-id="19d4b-122">Require the user to sign in again</span></span>
- <span data-ttu-id="19d4b-123">사용자 계정 일시 중단</span><span class="sxs-lookup"><span data-stu-id="19d4b-123">Suspend the user account</span></span>
- <span data-ttu-id="19d4b-124">Azure AD(Azure Active Directory) 사용자 계정 설정 참조</span><span class="sxs-lookup"><span data-stu-id="19d4b-124">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="19d4b-125">사용자 계정이 소유한 파일 보기</span><span class="sxs-lookup"><span data-stu-id="19d4b-125">View the files owned by the user account</span></span>
- <span data-ttu-id="19d4b-126">이 사용자와 공유된 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19d4b-126">View files shared with this user.</span></span> 

<span data-ttu-id="19d4b-127">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="19d4b-127">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 보안 센터에서 인시던트에 대한 사용자 계정의 작업 예":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="19d4b-129">관련 항목</span><span class="sxs-lookup"><span data-stu-id="19d4b-129">Related topics</span></span>

- [<span data-ttu-id="19d4b-130">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="19d4b-130">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="19d4b-131">인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="19d4b-131">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="19d4b-132">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="19d4b-132">Manage incidents</span></span>](manage-incidents.md)