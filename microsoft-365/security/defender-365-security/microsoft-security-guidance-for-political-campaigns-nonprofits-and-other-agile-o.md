---
title: Microsoft 보안 지침 - 정치적 캠페인 및 비영리 조직
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MET150
ms.custom:
- Strat_O365_Enterprise
- seo-marvel-apr2020
ms.assetid: 10d1004b-42b6-4e2b-aaa2-18ddd9118f64
description: '요약: 증가된 위협 프로필을 가진 빠르게 변화하는 조직에 대한 계획 및 구현 지침입니다.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac278103caf5d4d70b303b50b73db1b4b3571e6b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069972"
---
# <a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizations"></a><span data-ttu-id="929c5-103">정치적 캠페인, 비영리 조직 및 기타 기밀 조직에 대한 Microsoft 보안 지침</span><span class="sxs-lookup"><span data-stu-id="929c5-103">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="929c5-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="929c5-104">**Applies to**</span></span>
- [<span data-ttu-id="929c5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="929c5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="929c5-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="929c5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="929c5-107">**요약:** 증가된 위협 프로필을 가진 빠르게 변화하는 조직에 대한 계획 및 구현 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="929c5-107">**Summary:** Planning and implementation guidance for fast-moving organizations that have an increased threat profile.</span></span>

<span data-ttu-id="929c5-p101">기밀 조직으로서 작은 IT 팀을 보유하고 위협 프로필이 평균보다 더 높은 경우 이 지침이 적용됩니다. 이 솔루션은 처음부터 보안 컨트롤을 포함한 필수 클라우드 서비스를 포함하는 환경을 빨리 구축하는 방법을 보여 줍니다. 이 지침은 데이터, ID, 메일 및 액세스를 모바일 장치로부터 보호하기 위한 규정 보안 권장 사항을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="929c5-p101">If your organization is agile, you have a small IT team, and your threat profile is higher than average, this guidance is designed for you. This solution demonstrates how to quickly build an environment with essential cloud services that include secure controls from the start. This guidance includes prescriptive security recommendations for protecting data, identities, email, and access from mobile devices.</span></span>

## <a name="security-solution-guidance"></a><span data-ttu-id="929c5-111">보안 솔루션 지침</span><span class="sxs-lookup"><span data-stu-id="929c5-111">Security solution guidance</span></span>

<span data-ttu-id="929c5-p102">이 지침은 보안 클라우드 환경을 구현하는 방법에 대해 설명합니다. 이 솔루션 지침을 어떤 조직에서도 사용할 수 있습니다. 이 지침은 BYOD 액세스 및 게스트 계정을 가진 기밀 조직에 도움이 되는 내용을 포함합니다. 이 지침을 자신의 환경 설계를 위한 시작점으로 사용할 수 있습니다. 의견이 있으시면 언제든지 보내주세요[CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="929c5-p102">This guidance describes how to implement a secure cloud environment. The solution guidance can be used by any organization. It includes extra help for agile organizations with BYOD access and guest accounts. You can use this guidance as a starting-point for designing your own environment. We welcome your feedback at [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span></span>

****

|<span data-ttu-id="929c5-117">항목</span><span class="sxs-lookup"><span data-stu-id="929c5-117">Item</span></span>|<span data-ttu-id="929c5-118">설명</span><span class="sxs-lookup"><span data-stu-id="929c5-118">Description</span></span>|
|---|---|
|<span data-ttu-id="929c5-119">**정치적 캠페인을 위한 Microsoft 보안 지침**</span><span class="sxs-lookup"><span data-stu-id="929c5-119">**Microsoft Security Guidance for Political Campaigns**</span></span> <br> <span data-ttu-id="929c5-120">[![미니 포스터 집합에 대한 미리 보기입니다.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span><span class="sxs-lookup"><span data-stu-id="929c5-120">[![Thumbnail for mini poster set.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span></span> <br> <span data-ttu-id="929c5-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span><span class="sxs-lookup"><span data-stu-id="929c5-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span></span>|<span data-ttu-id="929c5-p103">이 지침에서는 정치적 캠페인 조직을 보기로 사용합니다. 이 지침을 어떤 환경에 대해서도 시작점으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929c5-p103">This guidance uses a political campaign organization as an example. Use this guidance as a starting point for any environment.</span></span>|
|<span data-ttu-id="929c5-124">**비영리 조직을 위한 Microsoft 보안 지침**</span><span class="sxs-lookup"><span data-stu-id="929c5-124">**Microsoft Security Guidance for Nonprofits**</span></span> <br> <span data-ttu-id="929c5-125">[![다운로드 가능한 파일에 대한 미리 보기 이미지](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span><span class="sxs-lookup"><span data-stu-id="929c5-125">[![Thumbnail image for downloadable file](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span></span> <br> <span data-ttu-id="929c5-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span><span class="sxs-lookup"><span data-stu-id="929c5-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span></span>|<span data-ttu-id="929c5-p104">이 지침은 비영리 조직을 위해 약간 수정하였습니다. 예를 들어 Office 365 비영리 조직 계획을 참조합니다. 기술 지침은 정치적 캠페인 솔루션 가이드와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="929c5-p104">This guide is slightly revised for nonprofit organizations. For example, it references Office 365 Nonprofit plans. The technical guidance is the same as the political campaign solution guide.</span></span>|
|

## <a name="test-lab-guides"></a><span data-ttu-id="929c5-130">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="929c5-130">Test Lab Guides</span></span>

<span data-ttu-id="929c5-131">이 솔루션에 대한 개발/테스트 환경을 만들려면 다음 테스트 랩 가이드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="929c5-131">To create a dev/test environment for this solution, use the following test lab guides:</span></span>

- [<span data-ttu-id="929c5-132">정치적 캠페인 개발/테스트 환경에 대해 그룹 및 사용자 구성</span><span class="sxs-lookup"><span data-stu-id="929c5-132">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="929c5-133">Office 365 및 EMS용 평가판 구독을 만들고 대표적인 정치적 캠페인에 대한 그룹 및 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="929c5-133">Create trial subscriptions for Office 365 and EMS and then create groups and users for a representative political campaign.</span></span>

- [<span data-ttu-id="929c5-134">정치적 캠페인 개발/테스트 환경에서 팀 사이트 만들기</span><span class="sxs-lookup"><span data-stu-id="929c5-134">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="929c5-135">내부, 개인, 중요 및 극비 보안 수준으로 SharePoint Online 팀 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="929c5-135">Create four SharePoint Online team sites with Internal, Private, Sensitive, and Highly Confidential levels of security.</span></span>

<span data-ttu-id="929c5-136">데모 또는 개념 증명을 위한 추가 보안 기능에 대해서는 [Office 365 테스트 랩 가이드](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="929c5-136">For additional security features for demonstration or proof of concept, see [Office 365 Test Lab Guides](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="929c5-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="929c5-137">See Also</span></span>

[<span data-ttu-id="929c5-138">Microsoft 클라우드 IT 아키텍처 리소스</span><span class="sxs-lookup"><span data-stu-id="929c5-138">Microsoft Cloud IT architecture resources</span></span>](../../solutions/cloud-architecture-models.md)
