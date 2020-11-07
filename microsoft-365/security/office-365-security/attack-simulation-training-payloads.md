---
title: 공격 시뮬레이션 교육을 위한 페이로드 만들기
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Microsoft Defender for Office 365에서 공격 시뮬레이션 교육을 위한 사용자 지정 페이로드를 만드는 방법을 알아봅니다.
ms.openlocfilehash: ffb5397d9b39a35b4cb8bd0fdb3301cd156896e1
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944595"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="4dc03-103">공격 시뮬레이션 교육을 위한 사용자 지정 페이로드 만들기</span><span class="sxs-lookup"><span data-stu-id="4dc03-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="4dc03-104">Microsoft는 공격 시뮬레이션 교육을 통해 다양 한 소셜 엔지니어링 기술로 쌍을 두는 강력한 페이로드 카탈로그를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-104">Microsoft offer a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="4dc03-105">그러나 조직에 더 적합 한 방식으로 작동 하는 사용자 지정 페이로드를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="4dc03-106">다음은 Office 365 용 Microsoft Defender를 통한 공격 시뮬레이션 교육에서 페이로드를 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-106">The following describes how to create a payload in attack simulation training through Microsoft Defender for Office 365.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="4dc03-107">[전용 **페이로드** 탭](https://security.microsoft.com/attacksimulator?viewid=payload) 또는 [시뮬레이션 만들기 마법사](attack-simulation-training.md#selecting-a-payload)내에서 **페이로드 만들기** 를 클릭 하 여 페이로드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="4dc03-108">마법사의 첫 번째 단계에서는 페이로드 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="4dc03-109">**현재 전자 메일만 사용할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-109">**Currently only email is available**.</span></span>

<span data-ttu-id="4dc03-110">다음으로, 관련 기술을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-110">Next, select an associated technique.</span></span> <span data-ttu-id="4dc03-111">[소셜 엔지니어링 기법을 선택할](attack-simulation-training.md#selecting-a-social-engineering-technique)때의 자세한 기술 정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4dc03-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="4dc03-112">다음 단계에서 페이로드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-112">In the next step name your payload.</span></span> <span data-ttu-id="4dc03-113">원하는 경우 설명을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="4dc03-114">페이로드 구성</span><span class="sxs-lookup"><span data-stu-id="4dc03-114">Configure payload</span></span>

<span data-ttu-id="4dc03-115">이제 페이로드를 구축 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-115">Now it's time to build your payload.</span></span> <span data-ttu-id="4dc03-116">보낸 사람 **정보** 섹션에 보낸 사람의 이름, 전자 메일 및 전자 메일 제목을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-116">Input the sender's name, email and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="4dc03-117">제공 된 목록에서 피싱 URL을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-117">Pick a phishing URL from the the provided list.</span></span> <span data-ttu-id="4dc03-118">이 URL은 나중에 메시지 본문에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="4dc03-119">페이로드의 보낸 사람에 대 한 내부 전자 메일을 선택 하 여 페이로드가 회사의 다른 직원 으로부터 들어오는 것으로 표시 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="4dc03-120">이렇게 하면 susceptibility 증가 하 고 내부 위협의 위험에 대해 직원을 교육 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="4dc03-121">페이로드를 만들기 위해 서식 있는 텍스트 편집기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="4dc03-122">미리 만든 전자 메일을 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-122">You can also import an email you've created beforehand.</span></span> <span data-ttu-id="4dc03-123">전자 메일의 본문을 구성할 때 **동적 태그** 를 활용 하 여 대상에 전자 메일을 개인 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-123">As you structure the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="4dc03-124">**피싱 링크** 를 클릭 하 여 이전에 선택한 피싱 URL을 전자 메일의 본문에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-124">Click on **Phishing link** to add the previously selected phishing URL into the body of the email.</span></span>

![Microsoft Defender for Office 365에 대 한 페이로드 만들기에서 강조 표시 된 피싱 링크 및 동적 태그](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="4dc03-126">잠시 시간을 절약 하려면 **전자 메일 메시지에 포함 된 모든 링크를 피싱 링크로 바꾸려면** 옵션을 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-126">To save yourself some time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="4dc03-127">원하는 대로 페이로드를 작성 했으면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="4dc03-128">지표 추가</span><span class="sxs-lookup"><span data-stu-id="4dc03-128">Adding indicators</span></span>

<span data-ttu-id="4dc03-129">지표는 공격 시뮬레이션을 통해 직원 들이 향후 공격에 대해 확인할 수 있는 단서를 이해 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-129">Indicators will help employees going through the attack simulation understand clue they can look for in future attacks.</span></span> <span data-ttu-id="4dc03-130">시작 하려면 **지표 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="4dc03-131">드롭다운 목록에서 사용할 지표를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="4dc03-132">이 목록은 피싱 전자 메일 메시지에 표시 되는 가장 일반적인 단서를 포함 하는 맞게 조정 된입니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="4dc03-133">선택한 후 지표 배치가 **전자 메일 본문에서** 으로 설정 되어 있는지 확인 하 고 **텍스트 선택을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="4dc03-134">이 표시기가 표시 되는 페이로드의 부분을 강조 표시 하 고 **선택을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![메시지 본문에서 강조 표시 된 텍스트를 공격 시뮬레이션 교육의 지표에 추가할 수 있습니다.](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="4dc03-136">지표를 설명 하는 사용자 지정 설명을 추가 하 고 지표 미리 보기 프레임 내에서 클릭 하 여 지표의 미리 보기를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="4dc03-137">작업이 완료 되 면 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-137">Once done, click **Add**.</span></span> <span data-ttu-id="4dc03-138">페이로드의 모든 표시기를 다룰 때까지 이러한 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="4dc03-139">페이로드 검토</span><span class="sxs-lookup"><span data-stu-id="4dc03-139">Review payload</span></span>

<span data-ttu-id="4dc03-140">페이로드 작성이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-140">You're done building your payload.</span></span> <span data-ttu-id="4dc03-141">이제 세부 정보를 검토 하 고 페이로드 미리 보기를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="4dc03-142">미리 보기에는 사용자가 만든 모든 표시기가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-142">The preview will include all indicators you've created.</span></span> <span data-ttu-id="4dc03-143">이 단계에서 페이로드의 각 부분을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="4dc03-144">충족 되 면 페이로드를 **전송** 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-144">Once satisfied, **Submit** your payload.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4dc03-145">만든 페이로드에는 **테 넌 트** 집합이 원본으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-145">Payloads you've created will have **Tenant** set as their source.</span></span> <span data-ttu-id="4dc03-146">페이로드를 선택할 때 **테 넌 트가** 필터링 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dc03-146">When selecting payloads, make sure you don't have **Tenant** filtered out.</span></span>