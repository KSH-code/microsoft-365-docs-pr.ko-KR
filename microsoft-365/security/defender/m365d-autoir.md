---
title: Defender의 자동화된 조사 Microsoft 365 대응
description: 자동 조사 및 응답 기능(자동 복구라고도 하는 자동 복구)에 대한 개요를 Microsoft 365 수 있습니다.
keywords: 자동화, 조사, 경고, 트리거, 작업, 수정, 자동 복구
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 976a79be98efcbb5d7fd3749ddb0cdb282b1e3e3
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274571"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="fd143-104">Defender의 자동화된 조사 Microsoft 365 대응</span><span class="sxs-lookup"><span data-stu-id="fd143-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="fd143-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="fd143-105">**Applies to:**</span></span>
- <span data-ttu-id="fd143-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd143-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fd143-107">조직에서 Microsoft 365 [Defender를](microsoft-365-defender.md)사용하는 경우 보안 운영 팀은 악의적 또는 의심스러운 활동 또는 아티팩트가 감지될 때마다 Microsoft 365 보안 센터 내에서 경고를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-107">If your organization is using [Microsoft 365 Defender](microsoft-365-defender.md), your security operations team receives an alert within the Microsoft 365 security center whenever a malicious or suspicious activity or artifact is detected.</span></span> <span data-ttu-id="fd143-108">발생될 수 있는 위협이 끝이 없는 것처럼 보이는 경우 보안 팀은 종종 많은 수의 경고를 해결해야 하는 과제에 직면합니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-108">Given the seemingly never-ending flow of threats that can come in, security teams often face the challenge of addressing the high volume of alerts.</span></span> <span data-ttu-id="fd143-109">다행히 Microsoft 365 Defender에는 보안 운영 팀이 위협을 보다 효율적으로 처리하도록 도와주는 자동화된 조사 및 대응(AIR) 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-109">Fortunately, Microsoft 365 Defender includes automated investigation and response (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span>

<span data-ttu-id="fd143-110">이 문서에서는 AIR에 대한 개요를 제공하며 다음 단계 및 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-110">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="fd143-111">Microsoft 365 Defender를 경험해 보고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="fd143-111">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="fd143-112">[랩 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-112">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="fd143-113">자동화된 조사 및 자동 복구의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="fd143-113">How automated investigation and self-healing works</span></span>

<span data-ttu-id="fd143-114">보안 경고가 트리거되면 보안 운영 팀이 해당 경고를 보고 조직을 보호하기 위한 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-114">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="fd143-115">조사가 진행되는 동안 새 경고를 계속해서 받는 경우 경고 우선 순위를 설정하고 검사하는 것은 매우 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-115">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="fd143-116">보안 운영 팀은 모니터링하고 방어해야 하는 많은 위협 요소를 통해 압도될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-116">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="fd143-117">자동 복구를 통해 자동화된 조사 및 대응 Microsoft 365 Defender가 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-117">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="fd143-118">다음 비디오를 시청하여 자동 복구가 작동하는 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-118">Watch the following video to see how self-healing works:</span></span> <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="fd143-119">Microsoft 365 Defender에서 자동 치료 기능을 통해 자동화된 조사 및 대응이 장치, 전자 메일 & 및 ID에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-119">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="fd143-120">이 문서에서는 자동화된 조사 및 대응이 작동하는 방식에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="fd143-121">이러한 기능을 구성하는 내용은 [Configure automated investigation and response capabilities in Microsoft 365 Defender을 참조합니다.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="fd143-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="fd143-122">자체 가상 분석가</span><span class="sxs-lookup"><span data-stu-id="fd143-122">Your own virtual analyst</span></span>

<span data-ttu-id="fd143-123">Imagine 계층 1 또는 계층 2 보안 운영 팀에 가상 분석가가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="fd143-123">Imagine having a virtual analyst in your Tier 1 or Tier 2 security operations team.</span></span> <span data-ttu-id="fd143-124">가상 분석가가 보안 운영에서 위협을 조사하고 수정하는 데 취하는 이상적인 단계를 모방합니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="fd143-125">가상 분석가가 무제한의 용량으로 24x7을 작업할 수 있으며 많은 수의 조사 및 위협 수정 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-125">The virtual analyst could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="fd143-126">이러한 가상 분석가가 응답 시간을 크게 줄여 보안 운영 팀이 다른 중요한 위협이나 전략적 프로젝트에 대한 정보를 제공하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-126">Such a virtual analyst could significantly reduce the time to respond, freeing up your security operations team for other important threats or strategic projects.</span></span> <span data-ttu-id="fd143-127">이 시나리오가 과학 소설처럼 들리면 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="fd143-128">이러한 가상 분석가는 Microsoft 365 Defender 제품군의 일부로, 해당 이름은 자동화된 조사 및 *응답입니다.*</span><span class="sxs-lookup"><span data-stu-id="fd143-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="fd143-129">자동화된 조사 및 대응 기능을 통해 보안 운영 팀은 보안 경고 및 인시던트 처리를 위한 조직의 용량을 크게 늘려 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-129">Automated investigation and response capabilities enable your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="fd143-130">자동화된 조사 및 대응을 통해 조사 및 대응 활동을 처리하고 위협 방지 제품군을 가장 많이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-130">With automated investigation and response, you can reduce the cost of dealing with investigation and response activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="fd143-131">자동화된 조사 및 대응 기능은 보안 운영 팀에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-131">Automated investigation and response capabilities help your security operations team by:</span></span>

1. <span data-ttu-id="fd143-132">위협에 조치가 필요한지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-132">Determining whether a threat requires action.</span></span>
2. <span data-ttu-id="fd143-133">필요한 수정 작업을 수행(또는 권장)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-133">Taking (or recommending) any necessary remediation actions.</span></span>
3. <span data-ttu-id="fd143-134">다른 조사를 진행할지 여부와 그 외의 조사를 진행할지 결정</span><span class="sxs-lookup"><span data-stu-id="fd143-134">Determining whether and what other investigations should occur.</span></span>
4. <span data-ttu-id="fd143-135">다른 경고가 발생하면 필요한 프로세스를 반복</span><span class="sxs-lookup"><span data-stu-id="fd143-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="fd143-136">자동화된 조사 프로세스</span><span class="sxs-lookup"><span data-stu-id="fd143-136">The automated investigation process</span></span>

<span data-ttu-id="fd143-137">경고는 자동화된 조사를 시작할 수 있는 인시던트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-137">An alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="fd143-138">자동화된 조사는 각 증거 조각에 대한 결과를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-138">The automated investigation results in a verdict for each piece of evidence.</span></span> <span data-ttu-id="fd143-139">판정은 다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-139">Verdicts can be:</span></span>
- <span data-ttu-id="fd143-140">*악의적*</span><span class="sxs-lookup"><span data-stu-id="fd143-140">*Malicious*</span></span>
- <span data-ttu-id="fd143-141">*피싱*</span><span class="sxs-lookup"><span data-stu-id="fd143-141">*Suspicious*</span></span> 
- <span data-ttu-id="fd143-142">*위협을 찾을 수 없음*</span><span class="sxs-lookup"><span data-stu-id="fd143-142">*No threats found*</span></span> 

<span data-ttu-id="fd143-143">악의적 또는 의심스러운 엔터티에 대한 수정 작업이 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-143">Remediation actions for malicious or suspicious entities are identified.</span></span> <span data-ttu-id="fd143-144">수정 작업의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-144">Examples of remediation actions include:</span></span>

- <span data-ttu-id="fd143-145">파일을 검지로 보내기</span><span class="sxs-lookup"><span data-stu-id="fd143-145">Sending a file to quarantine</span></span>
- <span data-ttu-id="fd143-146">프로세스 중지</span><span class="sxs-lookup"><span data-stu-id="fd143-146">Stopping a process</span></span>
- <span data-ttu-id="fd143-147">장치 고리</span><span class="sxs-lookup"><span data-stu-id="fd143-147">Isolating a device</span></span>
- <span data-ttu-id="fd143-148">URL 차단</span><span class="sxs-lookup"><span data-stu-id="fd143-148">Blocking a URL</span></span> 
- <span data-ttu-id="fd143-149">기타 작업</span><span class="sxs-lookup"><span data-stu-id="fd143-149">Other actions</span></span>

<span data-ttu-id="fd143-150">자세한 내용은 Defender의 수정 Microsoft 365 [참조하세요.](m365d-remediation-actions.md)</span><span class="sxs-lookup"><span data-stu-id="fd143-150">For more information, see See [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).</span></span>

<span data-ttu-id="fd143-151">조직에 [](m365d-configure-auto-investigation-response.md) 대해 자동화된 조사 및 대응 기능이 구성되는 방식에 따라 보안 운영 팀의 승인만 수행되거나 자동으로 수정 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-151">Depending on [how automated investigation and response capabilities are configured](m365d-configure-auto-investigation-response.md) for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="fd143-152">보류 중이든 완료 여부에 따라 모든 작업이 작업 센터 에 [나열됩니다.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="fd143-152">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md).</span></span>

<span data-ttu-id="fd143-153">조사가 실행되는 동안 발생하는 모든 관련 경고는 완료될 때까지 조사에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-153">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="fd143-154">영향을 받는 엔터티가 다른 곳에서 볼 수 있는 경우 자동화된 조사는 해당 엔터티를 포함하기 위해 해당 범위를 확장하고 조사 프로세스가 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-154">If an affected entity is seen elsewhere, the automated investigation expands its scope to include that entity, and the investigation process repeats.</span></span> 

<span data-ttu-id="fd143-155">Microsoft 365 Defender에서 각 자동화된 조사는 다음 표에 요약된 ID용 Microsoft Defender, Endpoint용 Microsoft Defender 및 Office 365 Microsoft Defender의 신호와 상관 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-155">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="fd143-156">엔터티</span><span class="sxs-lookup"><span data-stu-id="fd143-156">Entities</span></span> |<span data-ttu-id="fd143-157">위협 보호 서비스</span><span class="sxs-lookup"><span data-stu-id="fd143-157">Threat protection services</span></span>  |
|:---------|:---------|
|<span data-ttu-id="fd143-158">장치(끝점 또는 컴퓨터라고도 지칭)</span><span class="sxs-lookup"><span data-stu-id="fd143-158">Devices (also referred to as endpoints or machines)</span></span> |[<span data-ttu-id="fd143-159">Endpoint용 Defender</span><span class="sxs-lookup"><span data-stu-id="fd143-159">Defender for Endpoint</span></span>](../defender-endpoint/automated-investigations.md) |      
|<span data-ttu-id="fd143-160">On-premises Active Directory users, entity behavior, and activities</span><span class="sxs-lookup"><span data-stu-id="fd143-160">On-premises Active Directory users, entity behavior, and activities</span></span>     |[<span data-ttu-id="fd143-161">ID용 Defender</span><span class="sxs-lookup"><span data-stu-id="fd143-161">Defender for Identity</span></span>](/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="fd143-162">전자 메일 콘텐츠(파일 및 URL을 포함할 수 있는 전자 메일 메시지)</span><span class="sxs-lookup"><span data-stu-id="fd143-162">Email content (email messages that can contain files and URLs)</span></span>     |[<span data-ttu-id="fd143-163">Office 365용 Defender</span><span class="sxs-lookup"><span data-stu-id="fd143-163">Defender for Office 365</span></span>](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> <span data-ttu-id="fd143-164">모든 경고가 자동화된 조사를 트리거하는 것은 아니며, 모든 조사가 자동화된 수정 작업을 수행하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-164">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions.</span></span> <span data-ttu-id="fd143-165">조직에 대해 자동화된 조사 및 응답이 구성되는 방식에 따라 달라 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-165">It depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="fd143-166">자동화된 [조사 및 응답 기능 구성을 참조합니다.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="fd143-166">See [Configure automated investigation and response capabilities](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="viewing-a-list-of-investigations"></a><span data-ttu-id="fd143-167">조사 목록 보기</span><span class="sxs-lookup"><span data-stu-id="fd143-167">Viewing a list of investigations</span></span>

<span data-ttu-id="fd143-168">조사를 보기 위해 인시던트 **페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-168">To view investigations, go to the **Incidents** page.</span></span> <span data-ttu-id="fd143-169">인시던트 를 선택한 다음 조사 **탭을** 선택합니다. 자세한 내용은 [자동화된 조사의 세부](m365d-autoir-results.md)정보 및 결과를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="fd143-169">Select an incident, and then select the **Investigations** tab. To learn more, see [Details and results of an automated investigation](m365d-autoir-results.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="fd143-170">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fd143-170">Next steps</span></span>

- [<span data-ttu-id="fd143-171">자동화된 조사 및 응답을 위한 선행 준비를 참조</span><span class="sxs-lookup"><span data-stu-id="fd143-171">See the prerequisites for automated investigation and response</span></span>](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="fd143-172">조직에 대한 자동화된 조사 및 응답 구성</span><span class="sxs-lookup"><span data-stu-id="fd143-172">Configure automated investigation and response for your organization</span></span>](m365d-configure-auto-investigation-response.md)
- [<span data-ttu-id="fd143-173">알림 센터에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="fd143-173">Learn more about the Action center</span></span>](m365d-action-center.md)
