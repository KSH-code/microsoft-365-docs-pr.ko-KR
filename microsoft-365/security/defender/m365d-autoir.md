---
title: Microsoft 365 Defender의 자동화된 조사 및 대응
description: Microsoft 365 Defender에서 자동 조사 및 응답 기능(자동 복구라고도 하는)에 대한 개요를 얻습니다.
keywords: 자동화, 조사, 경고, 트리거, 작업, 수정, 자동 복구
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: be0423b0af8251347420d9e970dcfe10db0bb72b
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591926"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="48250-104">Microsoft 365 Defender의 자동화된 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="48250-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="48250-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="48250-105">**Applies to:**</span></span>
- <span data-ttu-id="48250-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48250-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="48250-107">조직에서 Microsoft [365 Defender를](microsoft-365-defender.md)사용하는 경우 보안 운영 팀은 악의적 또는 의심스러운 아티팩트가 감지될 때마다 경고를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="48250-107">If your organization is using [Microsoft 365 Defender](microsoft-365-defender.md), your security operations team receives an alert whenever a malicious or suspicious artifact is detected.</span></span> <span data-ttu-id="48250-108">끝이 없는 것처럼 보이는 위협 흐름이 제공될 경우 보안 팀은 종종 많은 수의 경고를 해결해야 하는 과제에 직면합니다.</span><span class="sxs-lookup"><span data-stu-id="48250-108">Given the seemingly never-ending flow of threats that come in, security teams often face challenges in addressing the high volume of alerts.</span></span> <span data-ttu-id="48250-109">다행히 Microsoft 365 Defender에는 보안 운영 팀이 위협을 보다 효율적으로 처리하도록 도와주는 자동화된 조사 및 수정(AIR) 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48250-109">Fortunately, Microsoft 365 Defender includes automated investigation and remediation (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span>

<span data-ttu-id="48250-110">이 문서에서는 AIR에 대한 개요를 제공하며 다음 단계 및 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="48250-110">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="48250-111">Microsoft 365 Defender를 경험해 보고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="48250-111">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="48250-112">[랩 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48250-112">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="48250-113">자동화된 조사 및 자동 복구의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="48250-113">How automated investigation and self-healing works</span></span>

<span data-ttu-id="48250-114">보안 경고가 트리거되면 보안 운영 팀이 해당 경고를 보고 조직을 보호하기 위한 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48250-114">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="48250-115">조사가 진행되는 동안 새 경고를 계속해서 받는 경우 경고 우선 순위를 설정하고 검사하는 것은 매우 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48250-115">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="48250-116">보안 운영 팀은 모니터링하고 방어해야 하는 많은 위협 요소를 통해 압도될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48250-116">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="48250-117">Microsoft 365 Defender에서 자동 복구를 통해 자동화된 조사 및 대응 기능이 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48250-117">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="48250-118">다음 비디오를 시청하여 자동 복구가 작동하는 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48250-118">Watch the following video to see how self-healing works:</span></span> <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="48250-119">Microsoft 365 Defender에서 자동 치료 기능을 통해 자동화된 조사 및 대응이 장치, 전자 메일 & 및 ID에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="48250-119">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="48250-120">이 문서에서는 자동화된 조사 및 대응이 작동하는 방식에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48250-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="48250-121">이러한 기능을 구성하기 위해 [Microsoft 365 Defender에서](m365d-configure-auto-investigation-response.md)자동화된 조사 및 응답 기능 구성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="48250-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="48250-122">자체 가상 분석가</span><span class="sxs-lookup"><span data-stu-id="48250-122">Your own virtual analyst</span></span>

<span data-ttu-id="48250-123">계층 1 또는 계층 2 보안 운영 팀에 가상 분석가가 있는 경우를 상상해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48250-123">Imagine having a virtual analyst in your Tier 1 or Tier 2 security operations team.</span></span> <span data-ttu-id="48250-124">가상 분석가가 보안 운영에서 위협을 조사하고 수정하는 데 취하는 이상적인 단계를 모방합니다.</span><span class="sxs-lookup"><span data-stu-id="48250-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="48250-125">가상 도우미는 연중무휴, 무제한으로 작업하고, 상당한 양의 조사와 위협 수정을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48250-125">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="48250-126">이러한 가상 도우미는 대응 시간을 크게 줄이고 보안 운영팀이 다른 중요한 전략 프로젝트를 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="48250-126">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="48250-127">이 시나리오가 과학 소설처럼 들리면 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48250-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="48250-128">이러한 가상 분석가가 Microsoft 365 Defender 제품군의 일부로, 해당 이름은 자동화된 조사 및 *응답입니다.*</span><span class="sxs-lookup"><span data-stu-id="48250-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="48250-129">자동화된 조사 및 대응 기능을 통해 보안 운영 팀은 보안 경고 및 인시던트 처리를 위한 조직의 용량을 크게 늘려 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48250-129">Automated investigation and response capabilities enable your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="48250-130">자동화된 조사 및 대응을 통해 조사 및 수정 활동을 처리하고 위협 방지 제품군을 가장 많이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48250-130">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="48250-131">자동화된 조사 및 대응 기능은 보안 운영 팀에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48250-131">Automated investigation and response capabilities help your security operations team by:</span></span>

1. <span data-ttu-id="48250-132">위협이 조치를 요구하는지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="48250-132">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="48250-133">필요한 수정 작업 수행(또는 권장)</span><span class="sxs-lookup"><span data-stu-id="48250-133">Taking (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="48250-134">조사를 진행할지 여부 및 기타 조사를 진행할지 결정 및</span><span class="sxs-lookup"><span data-stu-id="48250-134">Determining whether and what other investigations should occur; and</span></span>
4. <span data-ttu-id="48250-135">다른 경고가 발생하면 필요한 프로세스를 반복</span><span class="sxs-lookup"><span data-stu-id="48250-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="48250-136">자동화된 조사 프로세스</span><span class="sxs-lookup"><span data-stu-id="48250-136">The automated investigation process</span></span>

<span data-ttu-id="48250-137">경고는 자동화된 조사를 시작할 수 있는 인시던트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="48250-137">An alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="48250-138">자동화된 조사는 각 증거 조각에 대한 결과를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="48250-138">The automated investigation results in a verdict for each piece of evidence.</span></span> <span data-ttu-id="48250-139">판정은 다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48250-139">Verdicts can be:</span></span>
- <span data-ttu-id="48250-140">*악성*;</span><span class="sxs-lookup"><span data-stu-id="48250-140">*Malicious*;</span></span>
- <span data-ttu-id="48250-141">*의심스러운 ;* 또는</span><span class="sxs-lookup"><span data-stu-id="48250-141">*Suspicious*; or</span></span> 
- <span data-ttu-id="48250-142">*위협이 없습니다.*</span><span class="sxs-lookup"><span data-stu-id="48250-142">*No threats found*.</span></span> 

<span data-ttu-id="48250-143">악의적 또는 의심스러운 엔터티에 대한 수정 작업이 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="48250-143">Remediation actions for malicious or suspicious entities are identified.</span></span> <span data-ttu-id="48250-144">수정 작업의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="48250-144">Examples of remediation actions include:</span></span>
- <span data-ttu-id="48250-145">파일을 검지로 보내기</span><span class="sxs-lookup"><span data-stu-id="48250-145">Sending a file to quarantine;</span></span>
- <span data-ttu-id="48250-146">프로세스 중지</span><span class="sxs-lookup"><span data-stu-id="48250-146">Stopping a process;</span></span>
- <span data-ttu-id="48250-147">디바이스를 고리로 설정</span><span class="sxs-lookup"><span data-stu-id="48250-147">Isolating a device;</span></span>
- <span data-ttu-id="48250-148">URL 차단 및</span><span class="sxs-lookup"><span data-stu-id="48250-148">Blocking a URL; and</span></span> 
- <span data-ttu-id="48250-149">기타 작업.</span><span class="sxs-lookup"><span data-stu-id="48250-149">other actions.</span></span> <span data-ttu-id="48250-150">(Microsoft [365 Defender의](m365d-remediation-actions.md)수정 작업을 참조합니다.)</span><span class="sxs-lookup"><span data-stu-id="48250-150">(See [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).)</span></span>

<span data-ttu-id="48250-151">조직에 [](m365d-configure-auto-investigation-response.md) 대해 자동화된 조사 및 대응 기능이 구성되는 방식에 따라 보안 운영 팀의 승인만 수행되거나 자동으로 수정 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="48250-151">Depending on [how automated investigation and response capabilities are configured](m365d-configure-auto-investigation-response.md) for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="48250-152">보류 중이든 완료 여부에 따라 모든 작업이 작업 센터 에 [나열됩니다.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="48250-152">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md).</span></span>

<span data-ttu-id="48250-153">조사가 실행되는 동안 발생하는 모든 관련 경고는 완료될 때까지 조사에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="48250-153">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="48250-154">다른 곳에서 인출된 엔터티가 있는 경우 자동화된 조사는 해당 엔터티를 포함하기 위해 범위를 확장하고 조사 프로세스가 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="48250-154">If an incriminated entity is seen elsewhere, the automated investigation expands its scope to include that entity, and the investigation process repeats.</span></span> 

<span data-ttu-id="48250-155">Microsoft 365 Defender에서 각 자동화된 조사는 다음 표에 요약된 ID, 끝점용 Microsoft Defender 및 Office 365용 Defender에 대한 Microsoft Defender의 신호와 상관 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48250-155">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="48250-156">엔터티</span><span class="sxs-lookup"><span data-stu-id="48250-156">Entities</span></span> |<span data-ttu-id="48250-157">위협 보호 서비스</span><span class="sxs-lookup"><span data-stu-id="48250-157">Threat protection services</span></span>  |
|:---------|:---------|
|<span data-ttu-id="48250-158">장치(끝점이라고도 하지만 컴퓨터라고도 불리며)</span><span class="sxs-lookup"><span data-stu-id="48250-158">Devices (also referred to as endpoints, and sometimes referred to as machines)</span></span>     |<span data-ttu-id="48250-159">[엔드포인트용 Microsoft Defender](../defender-endpoint/automated-investigations.md) </span><span class="sxs-lookup"><span data-stu-id="48250-159">[Microsoft Defender for Endpoint](../defender-endpoint/automated-investigations.md)</span></span><br/>[<span data-ttu-id="48250-160">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="48250-160">Microsoft Defender for Identity</span></span>](/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="48250-161">전자 메일 콘텐츠(파일 및 URL을 포함할 수 있는 전자 메일 메시지)</span><span class="sxs-lookup"><span data-stu-id="48250-161">Email content (email messages that can contain files and URLs)</span></span>     |[<span data-ttu-id="48250-162">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="48250-162">Microsoft Defender for Office 365</span></span>](../office-365-security/defender-for-office-365.md)         |

> [!NOTE]
> <span data-ttu-id="48250-163">모든 경고가 자동화된 조사를 트리거하는 것은 아니며, 모든 조사가 자동화된 수정 작업을 수행하지는 않습니다. 조직에 대해 자동화된 조사 및 응답이 구성되는 방식에 따라 달라 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48250-163">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; it depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="48250-164">[Microsoft 365 Defender에서](m365d-configure-auto-investigation-response.md)자동화된 조사 및 응답 기능 구성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="48250-164">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="viewing-a-list-of-investigations"></a><span data-ttu-id="48250-165">조사 목록 보기</span><span class="sxs-lookup"><span data-stu-id="48250-165">Viewing a list of investigations</span></span>

<span data-ttu-id="48250-166">조사를 보기 위해 인시던트 **페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="48250-166">To view investigations, go to the **Incidents** page.</span></span> <span data-ttu-id="48250-167">인시던트 를 선택한 다음 조사 **탭을** 선택합니다. 자세한 내용은 [자동화된 조사의 세부](m365d-autoir-results.md)정보 및 결과를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="48250-167">Select an incident, and then select the **Investigations** tab. To learn more, see [Details and results of an automated investigation](m365d-autoir-results.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="48250-168">다음 단계</span><span class="sxs-lookup"><span data-stu-id="48250-168">Next steps</span></span>

- [<span data-ttu-id="48250-169">Microsoft 365 Defender의 자동화된 조사 및 대응에 대한 선행 준비를 참조</span><span class="sxs-lookup"><span data-stu-id="48250-169">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="48250-170">조직에 대한 자동화된 조사 및 응답 구성</span><span class="sxs-lookup"><span data-stu-id="48250-170">Configure automated investigation and response for your organization</span></span>](m365d-configure-auto-investigation-response.md)
- [<span data-ttu-id="48250-171">알림 센터에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="48250-171">Learn more about the Action center</span></span>](m365d-action-center.md)
