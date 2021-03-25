---
title: 공격 시뮬레이션 교육을 위한 페이로드 만들기
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 Microsoft Defender for Office 365에서 공격 시뮬레이션 교육을 위한 사용자 지정 페이로드를 만드는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205192"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="8847a-103">공격 시뮬레이션 교육에 대한 사용자 지정 페이로드 만들기</span><span class="sxs-lookup"><span data-stu-id="8847a-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="8847a-104">Microsoft는 공격 시뮬레이션 교육과 쌍을 이을 수 있는 다양한 소셜 엔지니어링 기술에 대한 강력한 페이로드 카탈로그를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="8847a-105">그러나 조직에 더 잘 작동할 수 있는 사용자 지정 페이로드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="8847a-106">이 문서에서는 Microsoft Defender for Office 365의 공격 시뮬레이션 교육에서 페이로드를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="8847a-107">전용 페이로드 탭 또는 시뮬레이션  만들기 마법사 내에서 페이로드 만들기를 클릭하여 [페이로드를 만들 수 있습니다.](attack-simulation-training.md#selecting-a-payload) [  ](https://security.microsoft.com/attacksimulator?viewid=payload)</span><span class="sxs-lookup"><span data-stu-id="8847a-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="8847a-108">마법사의 첫 번째 단계에서 페이로드 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="8847a-109">**현재는 전자 메일만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8847a-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="8847a-110">그런 다음 관련 기술을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-110">Next, select an associated technique.</span></span> <span data-ttu-id="8847a-111">기술에 대한 자세한 내용은 소셜 엔지니어링 기술 [선택을 참조합니다.](attack-simulation-training.md#selecting-a-social-engineering-technique)</span><span class="sxs-lookup"><span data-stu-id="8847a-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="8847a-112">다음 단계에서 페이로드 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-112">In the next step name your payload.</span></span> <span data-ttu-id="8847a-113">원하는 경우 설명을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="8847a-114">페이로드 구성</span><span class="sxs-lookup"><span data-stu-id="8847a-114">Configure payload</span></span>

<span data-ttu-id="8847a-115">이제 페이로드를 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-115">Now it's time to build your payload.</span></span> <span data-ttu-id="8847a-116">보낸 사람 세부 정보 섹션에서 보낸 사람 이름, 전자 메일 주소 및 전자 메일 **제목을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="8847a-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="8847a-117">제공된 목록에서 피싱 URL을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="8847a-118">이 URL은 나중에 메시지 본문에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="8847a-119">페이로드의 보낸 사람에 대한 내부 전자 메일을 선택하면 페이로드가 회사의 다른 직원으로부터 보낸 것으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="8847a-120">이렇게 하면 페이로드에 대한 접근성이 높아지며 직원에게 내부 위협의 위험을 교육하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="8847a-121">페이로드를 만들 수 있는 텍스트 편집기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="8847a-122">또한 앞서 만든 전자 메일을 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="8847a-123">전자 메일 본문을 만들 때 동적  태그를 사용하여 전자 메일을 대상에 맞게 개인 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="8847a-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="8847a-124">피싱 **링크를 클릭하여** 메시지 본문에 이전에 선택한 피싱 URL을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Microsoft Defender for Office 365용 페이로드 만들기에서 강조 표시된 피싱 링크 및 동적 태그](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="8847a-126">시간을 절약하려면 전자 메일 메시지의 모든 링크를 피싱 링크로 바꾸는 옵션을 **토글합니다.**</span><span class="sxs-lookup"><span data-stu-id="8847a-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="8847a-127">원하는 페이로드를 구축한 후 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8847a-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="8847a-128">표시기 추가</span><span class="sxs-lookup"><span data-stu-id="8847a-128">Adding indicators</span></span>

<span data-ttu-id="8847a-129">지표는 공격 시뮬레이션을 진행하는 직원이 향후 공격에서 찾아야 할 단서를 이해하는 데 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="8847a-130">시작하려면 **표시기 추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8847a-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="8847a-131">드롭다운 목록에서 사용할 표시기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="8847a-132">이 목록은 피싱 전자 메일 메시지에 나타나는 가장 일반적인 단서를 포함하기 위해 큐레이터로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="8847a-133">선택한 후 표시기 배치가 전자 메일 **본문에서로** 설정되어 있는지 확인한 다음 텍스트 선택 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8847a-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="8847a-134">이 표시기가 나타나는 페이로드 부분을 강조 표시하고 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8847a-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![공격 시뮬레이션 교육의 지표에 추가할 메시지 본문의 강조 표시된 텍스트](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="8847a-136">사용자 지정 설명을 추가하여 표시기를 설명하고 표시기 미리 보기 프레임 내에서 클릭하여 표시기 미리 보기를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="8847a-137">완료되면 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8847a-137">Once done, click **Add**.</span></span> <span data-ttu-id="8847a-138">페이로드의 모든 표시기를 다를 때까지 이러한 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="8847a-139">페이로드 검토</span><span class="sxs-lookup"><span data-stu-id="8847a-139">Review payload</span></span>

<span data-ttu-id="8847a-140">페이로드를 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-140">You're done building your payload.</span></span> <span data-ttu-id="8847a-141">이제 세부 정보를 검토하고 페이로드의 미리 보기를 볼 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="8847a-142">미리 보기에는 만든 모든 표시기가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="8847a-143">이 단계에서 페이로드의 각 부분을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="8847a-144">충족하면 **페이로드를 제출할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-144">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8847a-145">만든 페이로드에는 **테넌트가** 원본으로 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8847a-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="8847a-146">페이로드를 선택할 때 테넌트 를 필터링하지 **않는지 확인 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8847a-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="8847a-147">관련 링크</span><span class="sxs-lookup"><span data-stu-id="8847a-147">Related links</span></span>

[<span data-ttu-id="8847a-148">공격의 신나는 교육 사용 시작</span><span class="sxs-lookup"><span data-stu-id="8847a-148">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="8847a-149">피싱 공격 시뮬레이션 만들기</span><span class="sxs-lookup"><span data-stu-id="8847a-149">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="8847a-150">공격 시뮬레이션 교육 활용</span><span class="sxs-lookup"><span data-stu-id="8847a-150">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
