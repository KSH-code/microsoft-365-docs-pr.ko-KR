---
title: Microsoft Threat Protection의 자동화된 조사 및 대응
description: Microsoft Threat Protection에서 자동 조사 및 응답 기능의 개요 (자동 복구 라고도 함)에 대해 알아봅니다.
keywords: 자동화, 조사, 경고, 트리거, 작업, 재구성, 자동 복구
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: f2a0a439996f13cea3823815aceb9dd1c235e2f2
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962668"
---
# <a name="automated-investigation-and-response-in-microsoft-threat-protection"></a><span data-ttu-id="485cf-104">Microsoft Threat Protection의 자동화된 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="485cf-104">Automated investigation and response in Microsoft Threat Protection</span></span>

<span data-ttu-id="485cf-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="485cf-105">**Applies to:**</span></span>
- <span data-ttu-id="485cf-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="485cf-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="485cf-107">보안 알림이 트리거되면 해당 경고를 확인 하 고 조직을 보호 하기 위한 단계를 수행 하는 보안 운영 팀이 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-107">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="485cf-108">조사가 진행되는 동안 새 경고를 계속해서 받는 경우 경고 우선 순위를 설정하고 검사하는 것은 매우 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-108">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="485cf-109">보안 운영 팀은 모니터링하고 방어해야 하는 많은 위협 요소를 통해 압도될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-109">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="485cf-110">Microsoft Threat Protection에서 자가 치유를 통해 자동화 된 조사 및 응답 기능은 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-110">Automated investigation and response capabilities, with self-healing, in Microsoft Threat Protection can help.</span></span>

<span data-ttu-id="485cf-111">다음 비디오를 시청 하 여 자동 복구 작동 방식을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-111">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="485cf-112">Microsoft Threat Protection에서는 장치, 전자 메일 & 콘텐츠 및 id에 대해 자동 조사 및 자동 복구 기능이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-112">In Microsoft Threat Protection, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span> <span data-ttu-id="485cf-113">Microsoft Threat Protection은 다음과 같은 기능을 함께 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-113">Microsoft Threat Protection brings together capabilities from:</span></span> 
- [<span data-ttu-id="485cf-114">Microsoft Defender Advanced Threat Protection의 자동화 된 조사 및 재구성</span><span class="sxs-lookup"><span data-stu-id="485cf-114">Automated investigation and remediation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [<span data-ttu-id="485cf-115">Office 365 Advanced Threat Protection의 자동화 된 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="485cf-115">Automated investigation and response in Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [<span data-ttu-id="485cf-116">Azure advanced threat detection</span><span class="sxs-lookup"><span data-stu-id="485cf-116">Azure advanced threat detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [<span data-ttu-id="485cf-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="485cf-117">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
<span data-ttu-id="485cf-118">이 문서에서는 자동화 된 조사 및 응답이 작동 하는 방식을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-118">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="485cf-119">이러한 기능을 구성 하려면 [Microsoft Threat Protection의 자동 조사 및 응답 기능 구성을](mtp-configure-auto-investigation-response.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="485cf-119">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft Threat Protection](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-virtual-analyst"></a><span data-ttu-id="485cf-120">가상 분석가</span><span class="sxs-lookup"><span data-stu-id="485cf-120">Your virtual analyst</span></span>

<span data-ttu-id="485cf-121">계층 1/계층 2 보안 운영팀에 가상 분석가가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-121">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="485cf-122">가상 분석가가 보안 운영에서 위협을 조사하고 수정하는 데 취하는 이상적인 단계를 모방합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-122">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="485cf-123">가상 도우미는 연중무휴, 무제한으로 작업하고, 상당한 양의 조사와 위협 수정을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-123">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="485cf-124">이러한 가상 도우미는 대응 시간을 크게 줄이고 보안 운영팀이 다른 중요한 전략 프로젝트를 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-124">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="485cf-125">이 시나리오는 과학 fiction 같이 보이지만 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-125">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="485cf-126">이러한 가상 분석가는 Microsoft Threat Protection 제품군의 일부로, 해당 이름은 *자동 조사 및 응답*입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-126">Such a virtual analyst is part of your Microsoft Threat Protection suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="485cf-127">자동화 된 조사 및 응답을 통해 보안 운영 팀에서 보안 경고 및 인시던트를 처리 하기 위해 조직의 용량을 대폭 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-127">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="485cf-128">자동 조사 및 응답을 통해 조사 및 업데이트 관리 작업을 처리 하는 비용을 줄이고 위협 방지 제품군을 최대한 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-128">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="485cf-129">자동화 된 조사 및 응답은 보안 운영 팀에 게 다음과 같은 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-129">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="485cf-130">위협이 조치를 요구하는지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="485cf-130">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="485cf-131">필수 수정 조치 수행(또는 권장)</span><span class="sxs-lookup"><span data-stu-id="485cf-131">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="485cf-132">어떤 추가 조사가 수행되어야 하는지 결정</span><span class="sxs-lookup"><span data-stu-id="485cf-132">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="485cf-133">다른 경고가 발생하면 필요한 프로세스를 반복</span><span class="sxs-lookup"><span data-stu-id="485cf-133">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="485cf-134">자동화된 조사 프로세스</span><span class="sxs-lookup"><span data-stu-id="485cf-134">The automated investigation process</span></span>

<span data-ttu-id="485cf-135">**경고** > **인시던트** > **자동화된 조사** > **판단** > **수정 작업**</span><span class="sxs-lookup"><span data-stu-id="485cf-135">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="485cf-136">트리거된 경고는 자동화 된 조사를 시작할 수 있는 인시던트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-136">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="485cf-137">이 조사를 수행하면 하나 이상의 수정 작업이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-137">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="485cf-138">다음 표에 요약된대로 Microsoft Threat Protection에서 각각의 자동화된 조사는 Azure ATP(Advanced Threat Protection), Microsoft Defender online(Microsoft Defender ATP) 및 Office 365 Advanced Threat Protection(Office 365 ATP)간 신호의 연관성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-138">In Microsoft Threat Protection, each automated investigation correlates signals across Azure Advanced Threat Protection (Azure ATP), Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP), and Office 365 Advanced Threat Protection (Office 365 ATP), as summarized in the following table:</span></span> 

|<span data-ttu-id="485cf-139">엔터티</span><span class="sxs-lookup"><span data-stu-id="485cf-139">Entities</span></span> |<span data-ttu-id="485cf-140">위협 보호 서비스</span><span class="sxs-lookup"><span data-stu-id="485cf-140">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="485cf-141">장치(끝점이라고도 함)</span><span class="sxs-lookup"><span data-stu-id="485cf-141">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="485cf-142">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="485cf-142">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="485cf-143">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="485cf-143">Azure ATP</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="485cf-144">전자 메일 콘텐츠(사서함의 파일 및 메시지)</span><span class="sxs-lookup"><span data-stu-id="485cf-144">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="485cf-145">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="485cf-145">Office 365 ATP</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="485cf-146">각 조사에서는 조사 되는 각 증거 조각에 대해 verdicts (*악의적*이 고 *의심 스러운*또는 *위협이 되지 않음*)을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-146">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="485cf-147">위협 유형 및 결과 결과에 따라 업데이트 관리 작업은 조직의 보안 운영 팀의 승인을 받을 때 자동으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-147">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="485cf-148">보류 중인 동작과 완료된 작업은 [알림 센터](mtp-action-center.md)에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-148">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="485cf-149">조사가 실행되는 동안 발생하는 모든 관련 경고는 완료될 때까지 조사에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-149">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="485cf-150">문제가 있는 엔터티가 다른 곳에서 발견되는 경우에는 자동화된 조사가 해당 엔터티를 포함하도록 범위를 확장하고 일반적인 보안 플레이 북이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-150">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="485cf-151">모든 경고가 자동 조사를 트리거하는 것은 아니며, 자동 재구성 작업의 모든 조사 결과에 해당 되지 않습니다. 이러한 모든 방식은 조직에 대해 자동화 된 조사 및 응답이 구성 되는 방식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-151">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="485cf-152">[Microsoft Threat Protection에서 자동 조사 및 응답 기능 구성을](mtp-configure-auto-investigation-response.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="485cf-152">See [Configure automated investigation and response capabilities in Microsoft Threat Protection](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="485cf-153">다음 단계</span><span class="sxs-lookup"><span data-stu-id="485cf-153">Next steps</span></span>

- [<span data-ttu-id="485cf-154">Microsoft Threat Protection의 자동화 된 조사 및 응답에 대 한 필수 구성 요소 확인</span><span class="sxs-lookup"><span data-stu-id="485cf-154">See the prerequisites for automated investigation and response in Microsoft Threat Protection</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection)
- [<span data-ttu-id="485cf-155">조직에 대 한 자동화 된 조사 및 응답 구성</span><span class="sxs-lookup"><span data-stu-id="485cf-155">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="485cf-156">알림 센터에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="485cf-156">Learn more about the Action center</span></span>](mtp-action-center.md)
