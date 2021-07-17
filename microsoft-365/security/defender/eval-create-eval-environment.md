---
title: Microsoft 365 Defender 환경 만들기 평가판 라이선스를 활성화하거나 활성화하고 Microsoft Defender for Identity(MDI)로 계속 진행합니다.
description: 평가판 Microsoft 365 Defender 활성화하여 평가판 랩 또는 파일럿 환경을 설정합니다. 그런 다음 Microsoft Defender for Identity(MDI) 및 기타 모든 M365D 평가를 설치합니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/19/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 04f7a746788ebcf67525020515cdc7bb20c41bb6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458266"
---
# <a name="create-the-microsoft-365-defender-evaluation-environment"></a><span data-ttu-id="04a4d-105">Microsoft 365 Defender 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="04a4d-105">Create the Microsoft 365 Defender Evaluation Environment</span></span>

<span data-ttu-id="04a4d-106">평가에서 이 다음 단계를 진행하는 두 가지 일반적인 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04a4d-106">There are two common ways to do this next step in evaluation.</span></span> <span data-ttu-id="04a4d-107">이 문서에서는 프로덕션 M365 테넌트가 이미 있는 것으로 가정하고 현재 환경에서 M365 Defender를 평가하기 위해 E5 평가판 라이선스를 *활성화합니다.*</span><span class="sxs-lookup"><span data-stu-id="04a4d-107">This document assumes you already have a production M365 tenant, and will activate E5 trial licenses to evaluate M365 Defender in *the current environment*.</span></span> <span data-ttu-id="04a4d-108">전제 평가를 통해 평가 기간이 지난 후 라이선스를 구입하는 보안 방법을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04a4d-108">An in-place evaluation will let you keep any security methods with the purchase of licenses after the evaluation period.</span></span>

<span data-ttu-id="04a4d-109">두 번째는 [](setup-m365deval.md) 평가 목적으로 Microsoft 365 Defender 테스트 랩 환경을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="04a4d-109">The second is to  [Set up your Microsoft 365 Defender trial lab environment](setup-m365deval.md) for the purpose of evaluation.</span></span> <span data-ttu-id="04a4d-110">비즈니스로부터의 실제 신호가 많지 않을 수 있으므로 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04a4d-110">It may not have many real signals from the business, so be aware of that caveat.</span></span>

## <a name="to-activate-e5-trial-licenses-to-evaluate-microsoft-365-defender"></a><span data-ttu-id="04a4d-111">E5 평가판 라이선스를 활성화하려면 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04a4d-111">To activate E5 trial licenses to evaluate Microsoft 365 Defender</span></span> 
1. <span data-ttu-id="04a4d-112">기존 M365 테넌트 관리 포털에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="04a4d-112">Log on to your existing M365 tenant administration portal.</span></span>
2. <span data-ttu-id="04a4d-113">탐색 *메뉴에서 서비스* 구매를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04a4d-113">Select *Purchase Services* from the navigation menu.</span></span>
3. <span data-ttu-id="04a4d-114">아래로 스크롤하여 *Office 365* 섹션으로 이동한 다음 라이선스에서 "세부 정보" Office 365 E5 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04a4d-114">Scroll down to the *Office 365* section and select "Details" button under Office 365 E5 license.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Office 365 섹션에는 클릭할 세부 정보 단추가 있습니다.":::

4. <span data-ttu-id="04a4d-116">무료 *평가판 시작 링크를* 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04a4d-116">Select *Start free trial* link.</span></span>

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="'무료 평가판 시작'을 클릭합니다(35$요금).":::

5. <span data-ttu-id="04a4d-118">요청을 확인하고 지금 시도 *단추를* 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04a4d-118">Confirm your request and click *Try now* button.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="'체크 아웃, 주문 확인' 패널에는 '지금 사용해 보시겠음' 단추가 있습니다(Office 365 E5 25명을 위한 한 달의 평가판).":::

## <a name="next-steps"></a><span data-ttu-id="04a4d-120">다음 단계</span><span class="sxs-lookup"><span data-stu-id="04a4d-120">Next steps</span></span>
[<span data-ttu-id="04a4d-121">ID에 Microsoft 365 사용</span><span class="sxs-lookup"><span data-stu-id="04a4d-121">Enable Microsoft 365 for Identity</span></span>](eval-defender-identity-overview.md)

<span data-ttu-id="04a4d-122">평가 및 파일럿 테스트 [개요로 Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="04a4d-122">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>