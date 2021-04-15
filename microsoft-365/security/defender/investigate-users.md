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
ms.openlocfilehash: 6535493efb844f1413c569a28ebf36ddb05c167d
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760203"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="4139b-104">Microsoft 365 보안 센터에서 사용자 조사</span><span class="sxs-lookup"><span data-stu-id="4139b-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="4139b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4139b-105">**Applies to:**</span></span>

- <span data-ttu-id="4139b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4139b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4139b-107">조사 과정에서 사용자가 손상된 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4139b-107">As part of your investigation, you might find that a user has been compromised.</span></span>

<span data-ttu-id="4139b-108">Microsoft 365 보안 센터 사용자 페이지는 끝점용 Microsoft Defender, ID용 Microsoft Defender 및 Microsoft Cloud App Security의 정보를 결합합니다(사용중인 라이선스에 따라 다름).</span><span class="sxs-lookup"><span data-stu-id="4139b-108">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> <span data-ttu-id="4139b-109">이 페이지는 사용자 및 잠재적인 인시던트 조사를 위한 이상적인 시작 장소입니다.</span><span class="sxs-lookup"><span data-stu-id="4139b-109">This page is the ideal starting place for investigating users and potential incidents.</span></span>
<span data-ttu-id="4139b-110">![사용자 페이지](../../media/m3d-userpage.png)</span><span class="sxs-lookup"><span data-stu-id="4139b-110">![User page](../../media/m3d-userpage.png)</span></span>

<span data-ttu-id="4139b-111">이 페이지에는 사용자의 보안 위험과 관련한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4139b-111">This page shows information specific to the security risk of a user.</span></span> <span data-ttu-id="4139b-112">여기에는 위험을 평가하는 데 도움이 되는 점수, 사용자의 전반적인 위험에 기여한 최근 이벤트 및 경고가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4139b-112">This includes a score that helps assess risk, recent events and alerts that contributed to the overall risk of the user, and more.</span></span>

<span data-ttu-id="4139b-113">Microsoft 365 보안 센터의 여러 영역에서 이 페이지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4139b-113">You can access this page from multiple areas in the Microsoft 365 security center.</span></span> <span data-ttu-id="4139b-114">사용자 탭의 특정 인시던트에서 이 페이지에 액세스할 **수** 있습니다. 일부 경고에는 영향을 받는 특정 자산으로 사용자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4139b-114">You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset.</span></span> <span data-ttu-id="4139b-115">사용자를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4139b-115">You can also search for users.</span></span>  

<span data-ttu-id="4139b-116">이 Cloud App Security 자습서에서 사용자 및 잠재적인 위험을 조사하는 [방법에 대해 자세히 알아보십시오.](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them)</span><span class="sxs-lookup"><span data-stu-id="4139b-116">Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4139b-117">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4139b-117">Related topics</span></span>

- [<span data-ttu-id="4139b-118">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="4139b-118">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="4139b-119">인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="4139b-119">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="4139b-120">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="4139b-120">Manage incidents</span></span>](manage-incidents.md)