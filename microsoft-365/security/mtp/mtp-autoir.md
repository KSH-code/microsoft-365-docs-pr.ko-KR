---
title: Microsoft 365 Defender의 자동화된 조사 및 대응
description: Microsoft 365 Defender에서 자동 조사 및 응답 기능(자동 복구라고도 하는)에 대한 개요를 얻습니다.
keywords: 자동화, 조사, 경고, 트리거, 작업, 수정, 자체 복구
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930333"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="b5303-104">Microsoft 365 Defender의 자동화된 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="b5303-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b5303-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b5303-105">**Applies to:**</span></span>
- <span data-ttu-id="b5303-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5303-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="b5303-107">Microsoft 365 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="b5303-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="b5303-108">랩 [환경에서 평가하거나](https://aka.ms/mtp-trial-lab) 프로덕션 [환경에서 파일럿](https://aka.ms/m365d-pilotplaybook)프로젝트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="b5303-109">자동화된 조사 및 자동 복구 작동 방식</span><span class="sxs-lookup"><span data-stu-id="b5303-109">How automated investigation and self-healing works</span></span>

<span data-ttu-id="b5303-110">보안 경고가 트리거되면 보안 운영 팀이 이러한 경고를 보고 조직을 보호하기 위한 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-110">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="b5303-111">조사가 진행되는 동안 새 경고를 계속해서 받는 경우 경고 우선 순위를 설정하고 검사하는 것은 매우 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-111">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="b5303-112">보안 운영 팀은 모니터링하고 방어해야 하는 많은 위협 요소를 통해 압도될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-112">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="b5303-113">Microsoft 365 Defender에서 자동 복구를 통해 자동화된 조사 및 대응 기능을 통해 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-113">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="b5303-114">다음 비디오를 시청하여 자동 복구가 작동하는 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-114">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="b5303-115">Microsoft 365 Defender에서 자동 조사 및 자동 복구 기능을 통해 장치, 전자 메일 & 및 ID에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-115">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="b5303-116">이 문서에서는 자동화된 조사 및 대응의 작동 방식에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-116">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="b5303-117">이러한 기능을 구성하는 내용은 [Microsoft 365 Defender에서](mtp-configure-auto-investigation-response.md)자동화된 조사 및 응답 기능 구성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-117">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="b5303-118">자체 가상 분석가</span><span class="sxs-lookup"><span data-stu-id="b5303-118">Your own virtual analyst</span></span>

<span data-ttu-id="b5303-119">계층 1/계층 2 보안 운영팀에 가상 분석가가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-119">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="b5303-120">가상 분석가가 보안 운영에서 위협을 조사하고 수정하는 데 취하는 이상적인 단계를 모방합니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-120">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="b5303-121">가상 도우미는 연중무휴, 무제한으로 작업하고, 상당한 양의 조사와 위협 수정을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-121">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="b5303-122">이러한 가상 도우미는 대응 시간을 크게 줄이고 보안 운영팀이 다른 중요한 전략 프로젝트를 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-122">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="b5303-123">이 시나리오가 공상 과학 소설처럼 들리면 그렇지 않습니다!</span><span class="sxs-lookup"><span data-stu-id="b5303-123">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="b5303-124">이러한 가상 분석가가 Microsoft 365 Defender 제품군의 일부이자 해당 이름은 자동화된 조사 및 *응답입니다.*</span><span class="sxs-lookup"><span data-stu-id="b5303-124">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="b5303-125">자동화된 조사 및 대응을 통해 보안 운영 팀이 보안 경고 및 인시던트 처리를 위한 조직의 용량을 크게 늘려 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-125">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="b5303-126">자동화된 조사 및 대응을 통해 조사 및 수정 활동을 다루는 비용을 줄이고 위협 방지 제품군을 가장 많이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-126">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="b5303-127">자동화된 조사 및 대응은 보안 운영 팀에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-127">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="b5303-128">위협이 조치를 요구하는지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="b5303-128">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="b5303-129">필수 수정 조치 수행(또는 권장)</span><span class="sxs-lookup"><span data-stu-id="b5303-129">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="b5303-130">어떤 추가 조사가 수행되어야 하는지 결정</span><span class="sxs-lookup"><span data-stu-id="b5303-130">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="b5303-131">다른 경고가 발생하면 필요한 프로세스를 반복</span><span class="sxs-lookup"><span data-stu-id="b5303-131">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="b5303-132">자동화된 조사 프로세스</span><span class="sxs-lookup"><span data-stu-id="b5303-132">The automated investigation process</span></span>

<span data-ttu-id="b5303-133">**경고** > **인시던트** > **자동화된 조사** > **판단** > **수정 작업**</span><span class="sxs-lookup"><span data-stu-id="b5303-133">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="b5303-134">트리거된 경고는 자동화된 조사를 시작할 수 있는 인시던트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-134">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="b5303-135">이 조사를 수행하면 하나 이상의 수정 작업이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-135">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="b5303-136">Microsoft 365 Defender에서 각 자동화된 조사는 다음 표에 요약된 ID용 Microsoft Defender, 끝점용 Microsoft Defender 및 Office 365용 Defender의 신호와 상관 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-136">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="b5303-137">엔터티</span><span class="sxs-lookup"><span data-stu-id="b5303-137">Entities</span></span> |<span data-ttu-id="b5303-138">위협 보호 서비스</span><span class="sxs-lookup"><span data-stu-id="b5303-138">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="b5303-139">장치(끝점이라고도 함)</span><span class="sxs-lookup"><span data-stu-id="b5303-139">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="b5303-140">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b5303-140">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="b5303-141">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b5303-141">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="b5303-142">전자 메일 콘텐츠(사서함의 파일 및 메시지)</span><span class="sxs-lookup"><span data-stu-id="b5303-142">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="b5303-143">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b5303-143">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="b5303-144">각 조사는 조사된각 증거에 대한 판정(악성, 의심스러운 또는 위협 없음)을 생성합니다. </span><span class="sxs-lookup"><span data-stu-id="b5303-144">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="b5303-145">위협 유형 및 결과 결과에 따라 수정 작업이 자동으로 수행되거나 조직의 보안 운영 팀의 승인에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-145">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="b5303-146">보류 중인 동작과 완료된 작업은 [알림 센터](mtp-action-center.md)에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-146">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="b5303-147">조사가 실행되는 동안 발생하는 모든 관련 경고는 완료될 때까지 조사에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-147">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="b5303-148">문제가 있는 엔터티가 다른 곳에서 발견되는 경우에는 자동화된 조사가 해당 엔터티를 포함하도록 범위를 확장하고 일반적인 보안 플레이 북이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-148">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="b5303-149">모든 경고가 자동화된 조사를 트리거하는 것은 아니며, 모든 조사에서 자동화된 수정 작업이 수행되지는 않습니다. 이 모든 구성은 조직에 대한 자동화된 조사 및 응답이 구성된 방식에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-149">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="b5303-150">[Microsoft 365 Defender에서](mtp-configure-auto-investigation-response.md)자동화된 조사 및 응답 기능 구성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b5303-150">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="b5303-151">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b5303-151">Next steps</span></span>

- [<span data-ttu-id="b5303-152">Microsoft 365 Defender의 자동화된 조사 및 대응을 위한 선행 준비를 참조</span><span class="sxs-lookup"><span data-stu-id="b5303-152">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="b5303-153">조직에 대한 자동화된 조사 및 대응 구성</span><span class="sxs-lookup"><span data-stu-id="b5303-153">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="b5303-154">알림 센터에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="b5303-154">Learn more about the Action center</span></span>](mtp-action-center.md)
