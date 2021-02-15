---
title: Microsoft 365에서 음성 배포
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-voice
- M365-voice
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: 조직에 적합한 Teams 음성 솔루션을 선택하고 배포하는 방법을 알아보십시오.
ms.openlocfilehash: b5dda0ed3d9310c3c43052b9bac4996802e0ed2f
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580914"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="6d198-103">Teams 음성 솔루션 계획 및 배포</span><span class="sxs-lookup"><span data-stu-id="6d198-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="6d198-104">Teams 음성 솔루션을 사용하면 조직의 사용자가 조직 내부 및 외부에서 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d198-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="6d198-105">완전한 음성 솔루션은 Teams, Microsoft 전화 시스템 및 PSTN(Public Switched Telephone Network)에 연결하는 옵션 선택으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d198-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Teams 음성 솔루션 개요](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="6d198-107">전화 시스템은 조직에 대한 완전한 PBX(Private Branch Exchange) 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6d198-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="6d198-108">조직의 사용자 간 통화는 지리적 위치에 상관없이 전화 시스템 내에서 내부적으로 처리되므로 이러한 내부 통화에 대한 장거리 비용이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d198-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="6d198-109">전화 시스템을 PSTN(Public Switched Telephone Network)에 연결하면 Teams 사용자가 조직 외부에서 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d198-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="6d198-110">이 솔루션 지침은 다음을 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d198-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="6d198-111">조직에 적합한 음성 솔루션 선택</span><span class="sxs-lookup"><span data-stu-id="6d198-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="6d198-112">선택한 음성 솔루션 배포</span><span class="sxs-lookup"><span data-stu-id="6d198-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="6d198-113">다음 단계에 따라 음성 솔루션을 선택, 계획 및 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6d198-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![음성 솔루션을 선택합니다.](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="6d198-115">음성 솔루션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6d198-115">Choose your voice solution</span></span>](https://docs.microsoft.com/MicrosoftTeams/cloud-voice-landing-page?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

2. [<span data-ttu-id="6d198-116">전화 시스템 설정</span><span class="sxs-lookup"><span data-stu-id="6d198-116">Set up Phone System</span></span>](https://docs.microsoft.com/microsoftteams/setting-up-your-phone-system?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

3. <span data-ttu-id="6d198-117">다음 중 하나 또는 조합을 선택하여 PSTN 연결을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d198-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="6d198-118">[통화 계획](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - PSTN 통신 사업자인 Microsoft와 함께 Microsoft의 모든 클라우드 솔루션</span><span class="sxs-lookup"><span data-stu-id="6d198-118">[Calling Plan](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="6d198-119">[직접 라우팅](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - 직접 라우팅을 사용하여 자체 PSTN 통신업체를 Teams에 연결</span><span class="sxs-lookup"><span data-stu-id="6d198-119">[Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="6d198-120">또한 Contoso 사례 연구에서 대규모 다국적 기업이 Teams 음성 솔루션으로 마이그레이션된 방식에 대해 [읽어보는 것이 도움이](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d198-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span></span>

<span data-ttu-id="6d198-121">필수 라이선스에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d198-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="6d198-122">Teams 추가 기능 라이선스</span><span class="sxs-lookup"><span data-stu-id="6d198-122">Teams add-on licenses</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

- [<span data-ttu-id="6d198-123">직접 라우팅 라이선싱 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d198-123">Direct Routing licensing requirements</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)
