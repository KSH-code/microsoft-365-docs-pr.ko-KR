---
title: 장치 모니터링 & 보고 - 보안 센터
description: 조직에서 장치를 안전하고 최신으로 유지하며 잠재적인 위협을 발견하는 방법에 대해 설명
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, 모니터링, 보고서, 장치
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: b9580f904f9cc5043fa3e825007339ce66daaa72
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930501"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="a9ea0-104">Microsoft 365 보안 센터의 장치 모니터링 및 보고</span><span class="sxs-lookup"><span data-stu-id="a9ea0-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a9ea0-105">Microsoft 365 보안 센터에서 장치를 안전하고 최신으로 유지하며 잠재적인 위협을 발견합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="a9ea0-106">장치 경고 보기</span><span class="sxs-lookup"><span data-stu-id="a9ea0-106">View device alerts</span></span>

<span data-ttu-id="a9ea0-107">끝점용 Microsoft Defender에서 장치에 대한 위반 활동 및 기타 위협에 대한 최신 경고를 얻습니다(E5 라이선스에서 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="a9ea0-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender for Endpoint (available with an E5 license).</span></span> <span data-ttu-id="a9ea0-108">Microsoft 365 보안 센터는 기본 설정 워크플로를 사용하여 이러한 경고를 높은 수준에서 효과적으로 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="a9ea0-109">영향이 큰 경고 모니터링</span><span class="sxs-lookup"><span data-stu-id="a9ea0-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="a9ea0-110">각 끝점용 Microsoft Defender 경고에는 해당하는 심각도(높음, 중간, 낮음 또는 정보)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-110">Each Microsoft Defender for Endpoint alert has a corresponding severity (high, medium, low, or informational).</span></span> <span data-ttu-id="a9ea0-111">무인으로 남아 있는 경우 네트워크에 잠재적인 영향을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-111">It indicates potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="a9ea0-112">장치 경고 **심각도** 카드를 사용하여 특히 심각하고 즉각적인 응답이 필요할 수 있는 경고에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-112">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="a9ea0-113">이 카드에서 Microsoft Defender 보안 센터 포털에서 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-113">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![장치 경고 심각도 카드](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="a9ea0-115">경고 원본 이해</span><span class="sxs-lookup"><span data-stu-id="a9ea0-115">Understand sources of alerts</span></span>

<span data-ttu-id="a9ea0-116">끝점용 Microsoft Defender는 광범위한 보안 센서 및 인텔리전스 원본의 데이터를 활용하여 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-116">Microsoft Defender for Endpoint leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="a9ea0-117">예를 들어 Microsoft Defender 바이러스 백신 및 타사 맬웨어 방지의 검색 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-117">For example, it can use detection information from Microsoft Defender Antivirus and third-party antimalware.</span></span> <span data-ttu-id="a9ea0-118">또한 웹 서비스 API를 통해 제공되는 사용자 지정 위협 인텔리전스를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-118">It can also use your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="a9ea0-119">장치 **경고 검색** 원본 카드는 소스로 경고 배포를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-119">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="a9ea0-120">특정 원본, 특히 사용자 지정 원본과 관련된 활동을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-120">Track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="a9ea0-121">또한 이 카드를 사용하여 악의적인 활동이나 구성 요소를 자동으로 차단하도록 구성되지 않은 센서에서 오는 경고에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-121">You can also use the card to focus on alerts coming from sensors that aren't configured to automatically block malicious activity or components.</span></span>

![장치 경고 감지 소스 카드](../../media/device-alert-detection-sources.png)

<span data-ttu-id="a9ea0-123">이 카드에서 Microsoft Defender 보안 센터 포털에서 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-123">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="a9ea0-124">경고를 트리거하는 위협 유형 이해</span><span class="sxs-lookup"><span data-stu-id="a9ea0-124">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="a9ea0-125">끝점용 Microsoft Defender는 공격 체인의 특정 단계 또는 위협 구성 요소 유형을 나타내는 범주로 각 경고를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-125">Microsoft Defender for Endpoint sorts each alert into a category representing a certain stage in the attack chain or type of threat component.</span></span> <span data-ttu-id="a9ea0-126">예를 들어 감지된 위협 활동은 네트워크의 다른 장치에 연결하려고 시도했다는 것을 나타내기 위해 "측면 이동"으로 분류될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-126">For example, a detected threat activity might be categorized as "lateral movement" to indicate there was an attempt to reach other devices on the network.</span></span> <span data-ttu-id="a9ea0-127">공격자가 초기 발자국을 얻은 후에 활동이 발생한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-127">The activity has likely occurred after attackers gained an initial foothold.</span></span> <span data-ttu-id="a9ea0-128">검색된 위협 구성 요소는 광범위하게 맬웨어로 분류되거나 특정 위협 유형으로 분류될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-128">When detected, a threat component might be classified broadly as malware or specifically as a specific threat type.</span></span> <span data-ttu-id="a9ea0-129">랜섬웨어, 자격 증명 도용 또는 기타 유형의 악성 또는 원치 않는 소프트웨어가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-129">Specifics include ransomware, credential stealing, or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="a9ea0-130">Device **threat categories** card shows the distribution of alerts into these categories.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-130">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="a9ea0-131">이 정보를 사용하여 일반적으로 소셜 엔지니어링 시도보다 영향을 더 많이 미치는 자격 증명 도난 시도와 같은 위협 활동을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-131">Use this information to identify threat activity, such as credential theft attempts, that usually have higher impact than social engineering attempts.</span></span> <span data-ttu-id="a9ea0-132">랜섬웨어와 같은 잠재적으로 파괴적인 위협을 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-132">You can also to monitor for potentially destructive threats like ransomware.</span></span>

![장치 위협 범주 카드](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="a9ea0-134">활성 경고 모니터링</span><span class="sxs-lookup"><span data-stu-id="a9ea0-134">Monitor active alerts</span></span>

<span data-ttu-id="a9ea0-135">장치 **경고 상태** 카드는 해결되지 않은 경고 수를 나타내며 주의가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-135">The **Device alert status** card indicates the number of alerts that haven't been resolved and may require attention.</span></span> <span data-ttu-id="a9ea0-136">이 카드에서 Microsoft Defender 보안 센터 포털에서 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-136">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![장치 경고 상태 카드](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="a9ea0-138">해결된 경고 분류 모니터링</span><span class="sxs-lookup"><span data-stu-id="a9ea0-138">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="a9ea0-139">끝점에 대한 Microsoft Defender 경고를 확인할 때 보안 직원은 경고가 확인된지 여부를 다음으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-139">When resolving a Microsoft Defender for Endpoint alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="a9ea0-140">실제 위반 활동 또는 위협 구성 요소를 식별하는 실제 경고</span><span class="sxs-lookup"><span data-stu-id="a9ea0-140">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="a9ea0-141">정상적인 활동을 잘못 감지한 거짓 경고</span><span class="sxs-lookup"><span data-stu-id="a9ea0-141">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="a9ea0-142">장치 **경고 분류** 카드는 해결된 경고가 참 또는 거짓 경고로 분류된지 여부를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-142">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="a9ea0-143">이 카드에서 Microsoft Defender 보안 센터 포털에서 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-143">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="a9ea0-144">참고: 특정 경고에 대해 분류 정보를 사용할 수 없는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-144">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![장치 경고 분류 카드](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="a9ea0-146">해결된 경고 결정 모니터링</span><span class="sxs-lookup"><span data-stu-id="a9ea0-146">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="a9ea0-147">보안 직원은 해결 중에 경고가 참인지 또는 거짓인지를 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-147">Along with classifying whether an alert is true or false during resolution, your security staff can provide a determination.</span></span> <span data-ttu-id="a9ea0-148">결정은 경고 유효성을 검사하는 동안 발견된 일반 또는 악의적인 활동의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-148">A determination indicates the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="a9ea0-149">장치 **경고 결정 카드에는** 각 경고에 대해 제공된 결정이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-149">The **Device alert determination** card shows the determination provided for each alert.</span></span>

* <span data-ttu-id="a9ea0-150">**APT**: 검색된 활동 또는 위협 구성 요소가 영향을 받는 네트워크에서 발판을 확보하도록 설계된 정교한 위반의 일부임을 나타내는 고급 영구 위협</span><span class="sxs-lookup"><span data-stu-id="a9ea0-150">**APT**: advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="a9ea0-151">**맬웨어**: 악성 파일 또는 코드</span><span class="sxs-lookup"><span data-stu-id="a9ea0-151">**Malware**: malicious file or code</span></span>
* <span data-ttu-id="a9ea0-152">**보안 담당자**: 보안 담당자가 수행한 정상적인 활동</span><span class="sxs-lookup"><span data-stu-id="a9ea0-152">**Security personnel**: normal activity performed by security staff</span></span>
* <span data-ttu-id="a9ea0-153">**보안 테스트**: 실제 위협을 시뮬레이션하도록 디자인된 활동 또는 구성 요소로, 보안 센서를 트리거하고 경고를 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-153">**Security testing**: activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="a9ea0-154">**원치** 않는 소프트웨어 : 악성으로 간주되지 않지만 정책 또는 허용되는 사용 표준을 위반하는 앱 및 기타 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="a9ea0-154">**Unwanted software**: apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="a9ea0-155">**기타**: 제공된 형식에 속하지 않는 기타 결정</span><span class="sxs-lookup"><span data-stu-id="a9ea0-155">**Others**: any other determination that doesn't fall under the provided types</span></span>

<span data-ttu-id="a9ea0-156">이 카드에서 Microsoft Defender 보안 센터에서 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-156">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![장치 경고 결정 카드](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="a9ea0-158">위험에 노출된 장치 이해</span><span class="sxs-lookup"><span data-stu-id="a9ea0-158">Understand which devices are at risk</span></span>

<span data-ttu-id="a9ea0-159">**장치 보호는** 디바이스의 위험 수준을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-159">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="a9ea0-160">위험 수준은 장치의 경고 유형 및 심각도와 같은 요인을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-160">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![장치 보호 카드](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="a9ea0-162">Intune 관리 장치의 상태 모니터링 및 보고</span><span class="sxs-lookup"><span data-stu-id="a9ea0-162">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="a9ea0-163">다음 보고서에는 Intune에 등록된 장치의 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-163">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="a9ea0-164">미가용 장치의 데이터는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-164">Data from unenrolled devices isn't included.</span></span> <span data-ttu-id="a9ea0-165">전역 관리자만 이러한 카드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-165">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="a9ea0-166">Intune 등록된 장치 데이터에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-166">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="a9ea0-167">장치 준수</span><span class="sxs-lookup"><span data-stu-id="a9ea0-167">Device compliance</span></span>
* <span data-ttu-id="a9ea0-168">활성 맬웨어가 있는 장치</span><span class="sxs-lookup"><span data-stu-id="a9ea0-168">Devices with active malware</span></span>
* <span data-ttu-id="a9ea0-169">장치의 맬웨어 유형</span><span class="sxs-lookup"><span data-stu-id="a9ea0-169">Types of malware on devices</span></span>
* <span data-ttu-id="a9ea0-170">장치의 맬웨어</span><span class="sxs-lookup"><span data-stu-id="a9ea0-170">Malware on devices</span></span>
* <span data-ttu-id="a9ea0-171">맬웨어 감지가 있는 장치</span><span class="sxs-lookup"><span data-stu-id="a9ea0-171">Devices with malware detections</span></span>
* <span data-ttu-id="a9ea0-172">맬웨어 검색이 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="a9ea0-172">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="a9ea0-173">장치 준수 모니터링</span><span class="sxs-lookup"><span data-stu-id="a9ea0-173">Monitor device compliance</span></span>

<span data-ttu-id="a9ea0-174">**장치 준수는** Intune에 등록된 장치 수가 구성 정책을 준수하는지 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-174">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![장치 준수 카드](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="a9ea0-176">맬웨어 검색을 통해 장치 검색</span><span class="sxs-lookup"><span data-stu-id="a9ea0-176">Discover devices with malware detections</span></span>

<span data-ttu-id="a9ea0-177">**장치 맬웨어 검색은** 완전히 해결되지 않은 맬웨어가 있는 Intune 등록 장치의 수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-177">**Device malware detections** provide the number of Intune enrolled devices with malware that hasn't been fully resolved.</span></span> <span data-ttu-id="a9ea0-178">보류 중인 작업, 다시 시작, 전체 검사, 수동 사용자 작업 또는 수정 작업이 성공적으로 완료되지 않은 경우 해결이 부족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-178">A lack of resolution can be because of pending actions, a restart, a full scan, manual user actions, or if the remediation action was not successfully completed.</span></span>

![장치 맬웨어 감지 카드](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="a9ea0-180">검색된 맬웨어 유형 이해</span><span class="sxs-lookup"><span data-stu-id="a9ea0-180">Understand the types of malware detected</span></span>

<span data-ttu-id="a9ea0-181">**장치의 맬웨어 유형은** Intune에 등록된 장치에서 감지된 다양한 종류의 맬웨어를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="a9ea0-181">**Types of malware on devices** show different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="a9ea0-182">Microsoft 365 보안 센터에서 각 유형을 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-182">You can investigate each type in the Microsoft 365 security center.</span></span>

![장치 카드의 맬웨어 유형](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="a9ea0-184">장치에서 검색된 특정 맬웨어 이해</span><span class="sxs-lookup"><span data-stu-id="a9ea0-184">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="a9ea0-185">**장치의 맬웨어는** 장치에서 감지된 특정 맬웨어 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-185">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![장치 카드의 맬웨어](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="a9ea0-187">맬웨어가 가장 많은 장치 이해</span><span class="sxs-lookup"><span data-stu-id="a9ea0-187">Understand which devices have the most malware</span></span>

<span data-ttu-id="a9ea0-188">**맬웨어 검색이 있는 장치는** 맬웨어 검색이 가장 많은 장치를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="a9ea0-188">**Devices with malware detections** show which devices have the most malware detections.</span></span> <span data-ttu-id="a9ea0-189">Microsoft 365 보안 센터에서 맬웨어가 활성 상태인지, 장치를 사용하는 사용자 및 Intune의 관리 상태를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-189">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![맬웨어 감지 카드가 있는 장치](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="a9ea0-191">맬웨어가 가장 많은 장치가 있는 사용자 이해</span><span class="sxs-lookup"><span data-stu-id="a9ea0-191">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="a9ea0-192">**맬웨어 검색이 있는 사용자는** 맬웨어 검색이 가장 많은 장치를 사용자에게 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-192">**Users with malware detections** show users with devices that had the most malware detections.</span></span> <span data-ttu-id="a9ea0-193">Microsoft 365 보안 센터에서 각 사용자에게 할당된 장치 수와 각 장치 및 맬웨어 유형에 대한 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-193">In the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![맬웨어 검색 카드가 있는 사용자](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a><span data-ttu-id="a9ea0-195">공격 표면 감소 규칙 배포 및 검색 모니터링 및 관리</span><span class="sxs-lookup"><span data-stu-id="a9ea0-195">Monitor and manage attack surface reduction rule deployment and detections</span></span>

<span data-ttu-id="a9ea0-196">[ASR(공격](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) 취약성 축소) 규칙은 일반적으로 악용 검색 맬웨어가 장치를 감염시킬 때 사용하는 작업 및 앱을 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-196">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="a9ea0-197">이러한 규칙은 실행 파일을 실행하는 시기와 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-197">These rules control when and how executables can run.</span></span> <span data-ttu-id="a9ea0-198">예를 들어 JavaScript나 VBScript가 다운로드 한 실행 파일을 시작하는 것을 방지하거나 Office 매크로에서 Win32 API 호출을 차단하거나 USB 드라이브에서 실행되는 프로세스를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-198">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![공격 표면 감소 카드](../../media/attack-surface-reduction-rules.png)

<span data-ttu-id="a9ea0-200">**공격 표면 감소 규칙** 카드는 장치 전체의 규칙 배포 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-200">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="a9ea0-201">카드의 맨 위에 있는 막대에는 다음의 배포 모드에 있는 총 장치 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-201">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="a9ea0-202">**차단 모드:** 검색된 활동을 차단하도록 구성된 규칙이 하나 이상 있는 장치</span><span class="sxs-lookup"><span data-stu-id="a9ea0-202">**Block mode**: devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="a9ea0-203">**감사 모드:** 검색된 활동을 차단하기 위해 설정된 규칙이 없지만 검색된 활동을 감사하기 위해 하나 이상의 규칙이 설정된 장치</span><span class="sxs-lookup"><span data-stu-id="a9ea0-203">**Audit mode**: devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="a9ea0-204">**끄기**: 모든 ASR 규칙이 꺼진 장치</span><span class="sxs-lookup"><span data-stu-id="a9ea0-204">**Off**: devices with all ASR rules turned off</span></span>

<span data-ttu-id="a9ea0-205">이 카드의 아래쪽 부분에는 장치 전체의 규칙 설정이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-205">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="a9ea0-206">각 막대는 차단, 감사 검색 또는 규칙이 완전히 꺼져 있는 장치 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-206">Each bar indicates the number of devices that are set to block, audit detection, or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="a9ea0-207">ASR 검색 보기</span><span class="sxs-lookup"><span data-stu-id="a9ea0-207">View ASR detections</span></span>

<span data-ttu-id="a9ea0-208">네트워크에서 ASR 규칙 검색에 대한 자세한 정보를  확인하려면 공격 표면 축소 규칙 카드에서 검색 **보기를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-208">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="a9ea0-209">자세한 **보고서** 페이지의 검색 탭이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-209">The **Detections** tab in the detailed report page will open.</span></span>

![검색 탭](../../media/detections-tab.png)

<span data-ttu-id="a9ea0-211">페이지 맨 위에 있는 차트에는 차단되거나 감사된 검색을 누적하는 시간의에 대한 검색이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-211">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="a9ea0-212">하단의 표에는 최근 검색이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-212">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="a9ea0-213">표에서 다음의 정보를 사용하여 검색 특성을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-213">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="a9ea0-214">**검색된 파일:** 파일, 일반적으로 스크립트 또는 문서로, 해당 콘텐츠가 의심되는 공격 활동을 트리거한 경우</span><span class="sxs-lookup"><span data-stu-id="a9ea0-214">**Detected file**: the file, typically a script or document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="a9ea0-215">**규칙:** 규칙이 catch하도록 디자인된 공격 활동을 설명하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-215">**Rule**: name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="a9ea0-216">기존 ASR 규칙에 대한 읽기</span><span class="sxs-lookup"><span data-stu-id="a9ea0-216">Read about existing ASR rules</span></span>
* <span data-ttu-id="a9ea0-217">**원본 앱**: 의심되는 공격 활동을 트리거하는 콘텐츠를 로드하거나 실행한 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-217">**Source app**: the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="a9ea0-218">웹 브라우저, Office 응용 프로그램 또는 PowerShell과 같은 시스템 도구와 같은 합법적인 응용 프로그램일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-218">It could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="a9ea0-219">**게시자**: 원본 앱을 릴리스한 공급업체</span><span class="sxs-lookup"><span data-stu-id="a9ea0-219">**Publisher**: the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="a9ea0-220">장치 ASR 규칙 설정 검토</span><span class="sxs-lookup"><span data-stu-id="a9ea0-220">Review device ASR rule settings</span></span>

<span data-ttu-id="a9ea0-221">공격 표면 **감소 규칙** 보고서 페이지에서  구성 탭으로 이동하여 개별 장치에 대한 규칙 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-221">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="a9ea0-222">장치를 선택하여 각 규칙이 차단 모드인지, 감사 모드인지 또는 완전히 해제되어 있는지에 대한 자세한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-222">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![구성 탭](../../media/configuration-tab.png)

<span data-ttu-id="a9ea0-224">Microsoft Intune은 ASR 규칙에 대한 관리 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-224">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="a9ea0-225">설정을 업데이트하려면 탭의 장치  구성에서  시작을 선택하여 Intune에서 장치 관리를 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-225">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="a9ea0-226">ASR 규칙에서 파일 제외</span><span class="sxs-lookup"><span data-stu-id="a9ea0-226">Exclude files from ASR rules</span></span>

<span data-ttu-id="a9ea0-227">Microsoft 365 보안 센터는 공격 [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) 표면 축소 규칙에 의해 검색에서 제외할 수 있는 파일의 이름을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-227">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="a9ea0-228">파일을 제외하면 가중치 검색을 줄이고 차단 모드에서 공격 표면 축소 규칙을 보다 확신 있게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-228">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="a9ea0-229">제외는 Microsoft Intune에서 관리되지만 Microsoft 365 보안 센터에서는 파일을 이해하는 데 도움이 되는 분석 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-229">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="a9ea0-230">제외를 위해 파일 수집을 시작하려면 공격  표면 축소 규칙 보고서 페이지의 제외 추가 **탭으로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-230">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="a9ea0-231">이 도구는 모든 공격 표면 축소 규칙의 검색을 분석하지만 일부 규칙만 제외를 [지원합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)</span><span class="sxs-lookup"><span data-stu-id="a9ea0-231">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span></span>

![제외 탭 추가](../../media/add-exclusions-tab.png)

<span data-ttu-id="a9ea0-233">이 표에는 공격 표면 축소 규칙에서 검색된 모든 파일 이름이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-233">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="a9ea0-234">파일을 선택하여 제외가 미치는 영향을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-234">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="a9ea0-235">검색 수 감소</span><span class="sxs-lookup"><span data-stu-id="a9ea0-235">How many fewer detections</span></span>
* <span data-ttu-id="a9ea0-236">검색을 보고하는 장치 수</span><span class="sxs-lookup"><span data-stu-id="a9ea0-236">How many fewer devices report the detections</span></span>

<span data-ttu-id="a9ea0-237">제외에 대한 전체 경로가 있는 선택한 파일 목록을 표시하려면 제외 경로 다운로드를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a9ea0-237">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="a9ea0-238">Windows 로컬 보안 기관 하위 체제(lsass.exe)에서 자격 증명을 도용하지 못하게 하는 ASR 규칙에 대한 로그를 **lsass.exe.** </span><span class="sxs-lookup"><span data-stu-id="a9ea0-238">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**.</span></span> <span data-ttu-id="a9ea0-239">일반적인 시스템 파일이지만 검색된 파일로 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-239">It is a normal system file, but captured as the detected file.</span></span> <span data-ttu-id="a9ea0-240">따라서 생성된 제외 경로 목록에 이 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-240">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="a9ea0-241">검색된 파일 대신 이 규칙을 트리거한 파일을lsass.exe검색된 파일 **대신** 원본 앱의 경로를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-241">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="a9ea0-242">원본 앱을 찾으기 위해 [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) 이 특정 규칙에 대해 다음 고급 헌팅 쿼리를 실행합니다(규칙 ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2로 식별됨).</span><span class="sxs-lookup"><span data-stu-id="a9ea0-242">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="a9ea0-243">파일 제외 확인</span><span class="sxs-lookup"><span data-stu-id="a9ea0-243">Check files for exclusion</span></span>

<span data-ttu-id="a9ea0-244">ASR에서 파일을 제외하기 전에 파일을 검사하여 악성 파일이 아닌지 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-244">Before excluding a file from ASR, we recommend that you inspect the file to determine if it's indeed not malicious.</span></span>

<span data-ttu-id="a9ea0-245">파일을 검토하기 위해 Microsoft Defender [보안](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) 센터의 파일 정보 페이지를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-245">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="a9ea0-246">이 페이지에서는 보전 정보와 VirusTotal 바이러스 백신 검색 비율을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-246">The page provides prevalence information and the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="a9ea0-247">페이지를 사용하여 심층 분석을 위해 파일을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-247">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="a9ea0-248">Microsoft Defender 보안 센터에서 검색된 파일을 찾으기 위해 다음 고급 헌팅 쿼리를 사용하여 모든 ASR 검색을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-248">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="a9ea0-249">결과에 **SHA1** 또는 **InitiatingProcessSHA1을** 사용하여 Microsoft Defender 보안 센터의 유니버설 검색 창을 사용하여 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ea0-249">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
