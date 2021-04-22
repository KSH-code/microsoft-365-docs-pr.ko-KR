---
title: 자동화된 조사를 사용하여 위협 조사 및 수정
description: 끝점용 Microsoft Defender의 자동화된 조사 흐름을 이해합니다.
keywords: 자동화, 조사, 검색, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: 5ea869d4016cc794b3046a664c1519f6b3250c67
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933976"
---
# <a name="overview-of-automated-investigations"></a><span data-ttu-id="f9561-104">자동화된 조사 개요</span><span class="sxs-lookup"><span data-stu-id="f9561-104">Overview of automated investigations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f9561-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f9561-105">**Applies to:**</span></span>
- [<span data-ttu-id="f9561-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f9561-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f9561-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9561-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="f9561-108">작동 방법을 보고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f9561-108">Want to see how it works?</span></span> <span data-ttu-id="f9561-109">다음 비디오를 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-109">Watch the following video:</span></span> <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

<span data-ttu-id="f9561-110">자동화된 조사의 기술은 다양한 검사 알고리즘을 사용하며 보안 분석가가 사용하는 프로세스를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-110">The technology in automated investigation uses various inspection algorithms and is based on processes that are used by security analysts.</span></span> <span data-ttu-id="f9561-111">AIR 기능은 경고를 검사하고 위반을 해결하기 위해 즉각적인 조치를 취하도록 고안되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-111">AIR capabilities are designed to examine alerts and take immediate action to resolve breaches.</span></span> <span data-ttu-id="f9561-112">AIR 기능은 경고 볼륨을 크게 줄여 보안 운영이 보다 정교한 위협 및 기타 고가치 이니셔티브에 집중할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-112">AIR capabilities significantly reduce alert volume, allowing security operations to focus on more sophisticated threats and other high-value initiatives.</span></span> <span data-ttu-id="f9561-113">보류 중인지 완료 여부에 따라 모든 수정 작업은 관리 센터에서 [추적됩니다.](auto-investigation-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="f9561-113">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="f9561-114">작업 센터에서 보류 중인 작업이 승인되거나 거부될 수 있으며, 필요한 경우 완료된 작업을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-114">In the Action center, pending actions are approved (or rejected), and completed actions can be undone if needed.</span></span>

<span data-ttu-id="f9561-115">이 문서에서는 AIR에 대한 개요를 제공하며 다음 단계 및 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-115">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="f9561-116">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f9561-116">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="f9561-117">[무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="f9561-117">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink).</span></span>

## <a name="how-the-automated-investigation-starts"></a><span data-ttu-id="f9561-118">자동화된 조사 시작 방법</span><span class="sxs-lookup"><span data-stu-id="f9561-118">How the automated investigation starts</span></span>

<span data-ttu-id="f9561-119">경고가 트리거되거나 보안 운영자가 조사를 시작할 때 자동화된 조사가 시작될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-119">An automated investigation can start when an alert is triggered or when a security operator initiates the investigation.</span></span>

|<span data-ttu-id="f9561-120">상황</span><span class="sxs-lookup"><span data-stu-id="f9561-120">Situation</span></span>  |<span data-ttu-id="f9561-121">진행 작업</span><span class="sxs-lookup"><span data-stu-id="f9561-121">What happens</span></span>  |
|---------|---------|
|<span data-ttu-id="f9561-122">경고가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-122">An alert is triggered</span></span>     | <span data-ttu-id="f9561-123">일반적으로 경고가 트리거되면 자동화된 [](review-alerts.md) 조사가 시작되고 [인시던트가](view-incidents-queue.md) 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-123">In general, an automated investigation starts when an [alert](review-alerts.md) is triggered, and an [incident](view-incidents-queue.md) is created.</span></span> <span data-ttu-id="f9561-124">예를 들어 악성 파일이 장치에 있는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-124">For example, suppose a malicious file resides on a device.</span></span> <span data-ttu-id="f9561-125">해당 파일이 검색되면 경고가 트리거되고 인시던트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-125">When that file is detected, an alert is triggered, and incident is created.</span></span> <span data-ttu-id="f9561-126">자동화된 조사 프로세스가 디바이스에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-126">An automated investigation process begins on the device.</span></span> <span data-ttu-id="f9561-127">다른 장치에서 동일한 파일로 인시던트가 생성되는 다른 경고는 관련 인시던트 및 자동화된 조사에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-127">As other alerts are generated because of the same file on other devices, they are added to the associated incident and to the automated investigation.</span></span>         |
|<span data-ttu-id="f9561-128">조사가 수동으로 시작</span><span class="sxs-lookup"><span data-stu-id="f9561-128">An investigation is started manually</span></span>     | <span data-ttu-id="f9561-129">보안 운영 팀에서 자동화된 조사를 수동으로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-129">An automated investigation can be started manually by your security operations team.</span></span> <span data-ttu-id="f9561-130">예를 들어 보안 운영자가 장치 목록을 검토하고 장치에 높은 위험 수준이 있는 것으로 표시하는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-130">For example, suppose a security operator is reviewing a list of devices and notices that a device has a high risk level.</span></span> <span data-ttu-id="f9561-131">보안 운영자는 목록에서 디바이스를 선택하여 플라이아웃을 연 다음 자동화된 조사 **시작을 선택할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f9561-131">The security operator can select the device in the list to open its flyout, and then select **Initiate Automated Investigation**.</span></span> |

## <a name="how-an-automated-investigation-expands-its-scope"></a><span data-ttu-id="f9561-132">자동화된 조사가 범위를 확장하는 방법</span><span class="sxs-lookup"><span data-stu-id="f9561-132">How an automated investigation expands its scope</span></span>

<span data-ttu-id="f9561-133">조사가 실행되는 동안 장치에서 생성된 다른 모든 경고는 해당 조사가 완료될 때까지 진행 중인 자동화된 조사에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-133">While an investigation is running, any other alerts generated from the device are added to an ongoing automated investigation until that investigation is completed.</span></span> <span data-ttu-id="f9561-134">또한 다른 장치에서 동일한 위협이 있는 경우 해당 장치가 조사에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-134">In addition, if the same threat is seen on other devices, those devices are added to the investigation.</span></span>

<span data-ttu-id="f9561-135">다른 디바이스에서 인출된 엔터티가 볼 수 있는 경우 자동화된 조사 프로세스는 해당 장치를 포함하기 위해 해당 범위를 확장하고 해당 장치에서 일반 보안 플레이북이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-135">If an incriminated entity is seen in another device, the automated investigation process expands its scope to include that device, and a general security playbook starts on that device.</span></span> <span data-ttu-id="f9561-136">동일한 엔터티에서 이 확장 프로세스 중에 10개 이상의 장치가 발견되는 경우 해당 확장 작업을 수행하려면 승인이 필요하며 보류 중인 작업 **탭에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-136">If 10 or more devices are found during this expansion process from the same entity, then that expansion action requires an approval, and is visible on the **Pending actions** tab.</span></span>

## <a name="how-threats-are-remediated"></a><span data-ttu-id="f9561-137">위협을 수정하는 방법</span><span class="sxs-lookup"><span data-stu-id="f9561-137">How threats are remediated</span></span>

<span data-ttu-id="f9561-138">경고가 트리거되고 자동화된 조사가 실행되면 조사된 각 증거 조각에 대한 판결이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-138">As alerts are triggered, and an automated investigation runs, a verdict is generated for each piece of evidence investigated.</span></span> <span data-ttu-id="f9561-139">판정은 다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-139">Verdicts can be</span></span> 
- <span data-ttu-id="f9561-140">*악성*;</span><span class="sxs-lookup"><span data-stu-id="f9561-140">*Malicious*;</span></span>
- <span data-ttu-id="f9561-141">*의심스러운 ;* 또는</span><span class="sxs-lookup"><span data-stu-id="f9561-141">*Suspicious*; or</span></span> 
- <span data-ttu-id="f9561-142">*위협이 없습니다.*</span><span class="sxs-lookup"><span data-stu-id="f9561-142">*No threats found*.</span></span> 

<span data-ttu-id="f9561-143">결과가 도달하면 자동화된 조사를 통해 하나 이상의 수정 작업이 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-143">As verdicts are reached, automated investigations can result in one or more remediation actions.</span></span> <span data-ttu-id="f9561-144">수정 작업의 예로는 파일을 검지로 보내기, 서비스 중지, 예약된 작업 제거 등입니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-144">Examples of remediation actions include sending a file to quarantine, stopping a service, removing a scheduled task, and more.</span></span> <span data-ttu-id="f9561-145">자세한 내용은 재구성 [작업 을 참조합니다.](manage-auto-investigation.md#remediation-actions)</span><span class="sxs-lookup"><span data-stu-id="f9561-145">To learn more, see [Remediation actions](manage-auto-investigation.md#remediation-actions).</span></span>  

<span data-ttu-id="f9561-146">조직에 설정된 [](automation-levels.md) 자동화 수준 및 기타 보안 설정에 따라 수정 작업은 자동으로 또는 보안 운영 팀의 승인 시에만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-146">Depending on the [level of automation](automation-levels.md) set for your organization, as well as other security settings, remediation actions can occur automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="f9561-147">자동 수정에 영향을 줄 수 있는 추가 보안 설정에는 잠재적으로 원치 않는 응용 프로그램(PUA)으로부터의 [보호가](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-147">Additional security settings that can affect automatic remediation include [protection from potentially unwanted applications](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA).</span></span> 

<span data-ttu-id="f9561-148">보류 중인지 완료 여부에 따라 모든 수정 작업은 관리 센터에서 [추적됩니다.](auto-investigation-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="f9561-148">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="f9561-149">필요한 경우 보안 운영 팀에서 수정 작업을 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-149">If necessary, your security operations team can undo a remediation action.</span></span> <span data-ttu-id="f9561-150">자세한 내용은 자동화된 조사 후 재구성 작업 검토 및 [승인을 참조합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)</span><span class="sxs-lookup"><span data-stu-id="f9561-150">To learn more, see [Review and approve remediation actions following an automated investigation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation).</span></span>

> [!TIP]
> <span data-ttu-id="f9561-151">Microsoft 365 보안 센터에서 새로운 통합 조사 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9561-151">Check out the new, unified investigation page in the Microsoft 365 security center.</span></span> <span data-ttu-id="f9561-152">자세한 내용은 [(NEW!)를 참조하세요. 통합 조사 페이지.](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page)</span><span class="sxs-lookup"><span data-stu-id="f9561-152">To learn more, see [(NEW!) Unified investigation page](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).</span></span>


## <a name="requirements-for-air"></a><span data-ttu-id="f9561-153">AIR에 대한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9561-153">Requirements for AIR</span></span>

<span data-ttu-id="f9561-154">조직에 끝점용 Defender가 있어야 합니다(끝점용 [Microsoft Defender에 대한 최소](minimum-requirements.md)요구 사항 참조).</span><span class="sxs-lookup"><span data-stu-id="f9561-154">Your organization must have Defender for Endpoint (see [Minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)).</span></span>

<span data-ttu-id="f9561-155">현재 AIR은 다음 OS 버전만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9561-155">Currently, AIR only supports the following OS versions:</span></span>
- <span data-ttu-id="f9561-156">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="f9561-156">Windows Server 2019</span></span>
- <span data-ttu-id="f9561-157">Windows 10 버전 1709(OS 빌드 [16299.1085(KB4493441)](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)이상</span><span class="sxs-lookup"><span data-stu-id="f9561-157">Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) or later</span></span>
- <span data-ttu-id="f9561-158">Windows 10 버전 1803(OS 빌드 17134.704 [및 KB4493464)](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)이상</span><span class="sxs-lookup"><span data-stu-id="f9561-158">Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) or later</span></span>
- <span data-ttu-id="f9561-159">Windows 10 버전 [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) 이상</span><span class="sxs-lookup"><span data-stu-id="f9561-159">Windows 10, version [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) or later</span></span>

## <a name="next-steps"></a><span data-ttu-id="f9561-160">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f9561-160">Next steps</span></span>

- [<span data-ttu-id="f9561-161">자동화 수준에 대해 자세히 알아보시다</span><span class="sxs-lookup"><span data-stu-id="f9561-161">Learn more about automation levels</span></span>](automation-levels.md)
- [<span data-ttu-id="f9561-162">대화형 가이드를 참조하세요. Endpoint용 Microsoft Defender로 위협 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="f9561-162">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
- [<span data-ttu-id="f9561-163">끝점용 Microsoft Defender에서 자동화된 조사 및 수정 기능 구성</span><span class="sxs-lookup"><span data-stu-id="f9561-163">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>](configure-automated-investigations-remediation.md)

## <a name="see-also"></a><span data-ttu-id="f9561-164">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9561-164">See also</span></span>

- [<span data-ttu-id="f9561-165">PUA 보호</span><span class="sxs-lookup"><span data-stu-id="f9561-165">PUA protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="f9561-166">Office 365용 Microsoft Defender의 자동화된 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="f9561-166">Automated investigation and response in Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [<span data-ttu-id="f9561-167">Microsoft 365 Defender의 자동화된 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="f9561-167">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-autoir)
