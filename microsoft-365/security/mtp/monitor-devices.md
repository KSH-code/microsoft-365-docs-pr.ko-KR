---
title: 장치 모니터링 & 보고-보안 센터
description: 장치를 안전 하 고 최신 상태로 유지 하 고 조직에서 잠재적인 위협을 발견할 수 있는 방법에 대해 설명 합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, 모니터, 보고서, 장치
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 92760ef14fb1192e4462bab656e22f3595f9b449
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843867"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="89359-104">Microsoft 365 보안 센터의 장치 모니터링 및 보고</span><span class="sxs-lookup"><span data-stu-id="89359-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="89359-105">Microsoft 365 보안 센터에서 장치를 안전 하 고 최신 상태로 유지 하 고 잠재적인 위협을 발견할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="89359-106">장치 알림 보기</span><span class="sxs-lookup"><span data-stu-id="89359-106">View device alerts</span></span>

<span data-ttu-id="89359-107">끝점에 대 한 Microsoft Defender에서 장치에 대 한 위반 활동 및 기타 위협에 대 한 최신 알림을 받을 수 있습니다 (E5 라이선스 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="89359-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender for Endpoint (available with an E5 license).</span></span> <span data-ttu-id="89359-108">Microsoft 365 보안 센터는 기본 워크플로를 사용 하 여 높은 수준에서 이러한 경고를 효과적으로 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="89359-109">높은 영향을 주는 알림 모니터링</span><span class="sxs-lookup"><span data-stu-id="89359-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="89359-110">각 Microsoft Defender for Endpoint alert에는 해당 하는 심각도 (높음, 중간, 낮음 또는 정보)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-110">Each Microsoft Defender for Endpoint alert has a corresponding severity (high, medium, low, or informational).</span></span> <span data-ttu-id="89359-111">무인 모드로 유지 되는 경우 네트워크에 발생할 수 있는 잠재적 영향을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89359-111">It indicates potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="89359-112">**장치 경고 심각도** 카드를 사용 하 여 특히 더 심각 하 고 즉각적인 응답이 필요할 수 있는 경고에 초점을 집중 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-112">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="89359-113">이 카드에서 Microsoft Defender 보안 센터 포털에 대 한 추가 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-113">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![장치 경고 심각도 카드](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="89359-115">경고 원본 이해</span><span class="sxs-lookup"><span data-stu-id="89359-115">Understand sources of alerts</span></span>

<span data-ttu-id="89359-116">끝점에 대 한 Microsoft Defender는 광범위 한 보안 센서 및 인텔리전스 원본의 데이터를 활용 하 여 경고를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-116">Microsoft Defender for Endpoint leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="89359-117">예를 들어 Microsoft Defender 바이러스 백신 및 타사 맬웨어 방지 프로그램의 검색 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-117">For example, it can use detection information from Microsoft Defender Antivirus and third-party antimalware.</span></span> <span data-ttu-id="89359-118">또한 웹 서비스 API를 통해 제공 되는 자신만의 사용자 지정 위협 인텔리전스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-118">It can also use your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="89359-119">**장치 경고 검색** 원본 카드에는 원본에의 한 알림 배포가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89359-119">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="89359-120">특정 원본, 특히 사용자 지정 원본에 관련 된 활동을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-120">Track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="89359-121">또한 카드를 사용 하 여 악성 활동이 나 구성 요소를 자동으로 차단 하도록 구성 되지 않은 센서에서 들어오는 경고에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-121">You can also use the card to focus on alerts coming from sensors that aren't configured to automatically block malicious activity or components.</span></span>

![장치 경고 검색 원본 카드](../../media/device-alert-detection-sources.png)

<span data-ttu-id="89359-123">이 카드에서 Microsoft Defender 보안 센터 포털에 대 한 추가 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-123">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="89359-124">알림을 트리거하는 위협의 유형 이해</span><span class="sxs-lookup"><span data-stu-id="89359-124">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="89359-125">끝점에 대 한 Microsoft Defender는 각 알림을 공격 체인 또는 위협 구성 요소 유형에서 특정 단계를 나타내는 범주로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-125">Microsoft Defender for Endpoint sorts each alert into a category representing a certain stage in the attack chain or type of threat component.</span></span> <span data-ttu-id="89359-126">예를 들어 감지 된 위협 활동은 네트워크의 다른 장치에 연결할 수 있음을 나타내기 위해 "수평 이동"으로 분류 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-126">For example, a detected threat activity might be categorized as "lateral movement" to indicate there was an attempt to reach other devices on the network.</span></span> <span data-ttu-id="89359-127">이 활동은 공격자가 초기 foothold를 얻은 후에 발생 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-127">The activity has likely occurred after attackers gained an initial foothold.</span></span> <span data-ttu-id="89359-128">감지 되 면 위협 구성 요소는 특정 위협 유형 또는 맬웨어로 광범위 하 게 분류 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-128">When detected, a threat component might be classified broadly as malware or specifically as a specific threat type.</span></span> <span data-ttu-id="89359-129">자세한 내용은 랜 섬 웨어, 자격 증명 가로채기 또는 기타 악성 또는 원치 않는 소프트웨어 유형이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89359-129">Specifics include ransomware, credential stealing, or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="89359-130">**장치 위협 범주** 카드에는 이러한 범주에 대 한 경고 배포가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89359-130">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="89359-131">이 정보를 사용 하 여 자격 증명 도난 시도와 같이 사회 공학적 시도 보다 더 높은 영향을 받는 위협 활동을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-131">Use this information to identify threat activity, such as credential theft attempts, that usually have higher impact than social engineering attempts.</span></span> <span data-ttu-id="89359-132">또한 랜 섬 웨어와 같은 잠재적 파괴적인 위협에 대 한 모니터링이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-132">You can also to monitor for potentially destructive threats like ransomware.</span></span>

![장치 위협 범주 카드](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="89359-134">활성 경고 모니터링</span><span class="sxs-lookup"><span data-stu-id="89359-134">Monitor active alerts</span></span>

<span data-ttu-id="89359-135">**장치 경고 상태** 카드에는 해결 되지 않은 경고 수와 주의가 필요할 수 있는 알림 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89359-135">The **Device alert status** card indicates the number of alerts that haven't been resolved and may require attention.</span></span> <span data-ttu-id="89359-136">이 카드에서 Microsoft Defender 보안 센터 포털에 대 한 추가 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-136">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![장치 경고 상태 카드](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="89359-138">확인 된 알림의 분류 모니터링</span><span class="sxs-lookup"><span data-stu-id="89359-138">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="89359-139">끝점 알림을 위해 Microsoft Defender를 확인 하는 경우 보안 담당자는 다음과 같이 확인 된 경고를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-139">When resolving a Microsoft Defender for Endpoint alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="89359-140">실제 위반 활동 또는 위협 구성 요소를 식별 하는 진정한 경고</span><span class="sxs-lookup"><span data-stu-id="89359-140">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="89359-141">정상적인 활동이 잘못 검색 된 거짓 경고</span><span class="sxs-lookup"><span data-stu-id="89359-141">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="89359-142">**장치 경고 분류** 카드에는 해결 된 경고가 참 또는 거짓 알림으로 분류 되어 있는지 여부가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89359-142">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="89359-143">이 카드에서 Microsoft Defender 보안 센터 포털에 대 한 추가 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-143">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="89359-144">참고: 일부 경우에는 특정 알림에 대해 분류 정보를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-144">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![장치 경고 분류 카드](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="89359-146">해결 된 경고 확인 모니터링</span><span class="sxs-lookup"><span data-stu-id="89359-146">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="89359-147">해결 하는 동안 경고가 참 인지 거짓이를 분류 하는 것과 함께, 보안 담당자가 결정을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-147">Along with classifying whether an alert is true or false during resolution, your security staff can provide a determination.</span></span> <span data-ttu-id="89359-148">결정은 경고를 확인 하는 동안 발견 된 일반 또는 악의적인 활동의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89359-148">A determination indicates the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="89359-149">**장치 경고 결정** 카드에는 각 경고에 대해 제공 되는 결정이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89359-149">The **Device alert determination** card shows the determination provided for each alert.</span></span>

* <span data-ttu-id="89359-150">**APT** : 검색 된 활동 또는 위협 구성 요소가 영향을 받는 네트워크에서 foothold을 얻기 위해 설계 된 복잡 한 위반의 일부임을 나타내는 고급 영구 위협</span><span class="sxs-lookup"><span data-stu-id="89359-150">**APT** : advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="89359-151">**맬웨어** : 악성 파일 또는 코드</span><span class="sxs-lookup"><span data-stu-id="89359-151">**Malware** : malicious file or code</span></span>
* <span data-ttu-id="89359-152">**보안 담당자** : 보안 직원이 수행 하는 일반 활동</span><span class="sxs-lookup"><span data-stu-id="89359-152">**Security personnel** : normal activity performed by security staff</span></span>
* <span data-ttu-id="89359-153">**보안 테스트** : 실제 위협을 시뮬레이트하고 보안 센서를 트리거하고 알림을 생성 하도록 설계 된 활동 또는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="89359-153">**Security testing** : activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="89359-154">**원치 않는 소프트웨어** : 악성으로 간주 되지 않고 정책 또는 적절 한 사용 표준을 위반 하는 앱 및 기타 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="89359-154">**Unwanted software** : apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="89359-155">**기타** : 제공 된 형식에 포함 되지 않는 기타 모든 결정</span><span class="sxs-lookup"><span data-stu-id="89359-155">**Others** : any other determination that doesn't fall under the provided types</span></span>

<span data-ttu-id="89359-156">이 카드에서 Microsoft Defender 보안 센터의 추가 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-156">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![장치 경고 결정 카드](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="89359-158">위험에 처 한 장치 이해</span><span class="sxs-lookup"><span data-stu-id="89359-158">Understand which devices are at risk</span></span>

<span data-ttu-id="89359-159">**장치 보호** 장치에 대 한 위험 수준을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-159">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="89359-160">위험 수준은 장치에 대 한 알림 유형 및 심각도와 같은 요소를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-160">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![장치 보호 카드](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="89359-162">Intune 관리 장치에 대 한 상태 모니터링 및 보고</span><span class="sxs-lookup"><span data-stu-id="89359-162">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="89359-163">다음 보고서에는 Intune의 장치에 등록 된 데이터가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-163">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="89359-164">Unenrolled 장치의 데이터는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-164">Data from unenrolled devices isn't included.</span></span> <span data-ttu-id="89359-165">전역 관리자만 이러한 카드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-165">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="89359-166">Intune에서 등록 된 장치 데이터에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89359-166">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="89359-167">장치 준수</span><span class="sxs-lookup"><span data-stu-id="89359-167">Device compliance</span></span>
* <span data-ttu-id="89359-168">활성 맬웨어가 있는 장치</span><span class="sxs-lookup"><span data-stu-id="89359-168">Devices with active malware</span></span>
* <span data-ttu-id="89359-169">장치에 있는 맬웨어 유형</span><span class="sxs-lookup"><span data-stu-id="89359-169">Types of malware on devices</span></span>
* <span data-ttu-id="89359-170">장치에 대 한 맬웨어</span><span class="sxs-lookup"><span data-stu-id="89359-170">Malware on devices</span></span>
* <span data-ttu-id="89359-171">맬웨어 검색이 포함 된 장치</span><span class="sxs-lookup"><span data-stu-id="89359-171">Devices with malware detections</span></span>
* <span data-ttu-id="89359-172">맬웨어 검색이 포함 된 사용자</span><span class="sxs-lookup"><span data-stu-id="89359-172">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="89359-173">장치 준수 모니터링</span><span class="sxs-lookup"><span data-stu-id="89359-173">Monitor device compliance</span></span>

<span data-ttu-id="89359-174">**장치 준수** 는 구성 정책을 준수 하는 Intune의 장치 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89359-174">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![장치 준수 카드](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="89359-176">맬웨어 감지 장치 검색</span><span class="sxs-lookup"><span data-stu-id="89359-176">Discover devices with malware detections</span></span>

<span data-ttu-id="89359-177">**장치 맬웨어 감지** 는 완전히 확인 되지 않은 맬웨어가 있는 Intune 등록 장치 수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-177">**Device malware detections** provide the number of Intune enrolled devices with malware that hasn't been fully resolved.</span></span> <span data-ttu-id="89359-178">보류 중인 작업, 다시 시작, 전체 검색, 수동 사용자 작업 또는 업데이트 관리 작업이 성공적으로 완료 되지 않아 해결 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-178">A lack of resolution can be because of pending actions, a restart, a full scan, manual user actions, or if the remediation action was not successfully completed.</span></span>

![장치 맬웨어 감지 카드](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="89359-180">검색 된 맬웨어 유형 이해</span><span class="sxs-lookup"><span data-stu-id="89359-180">Understand the types of malware detected</span></span>

<span data-ttu-id="89359-181">**장치에 있는 맬웨어 유형은** Intune에서 등록 된 장치에서 감지 되는 다양 한 유형의 맬웨어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89359-181">**Types of malware on devices** show different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="89359-182">Microsoft 365 보안 센터에서 각 유형을 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-182">You can investigate each type in the Microsoft 365 security center.</span></span>

![장치 카드의 맬웨어 유형](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="89359-184">장치에서 검색 되는 특정 맬웨어 이해</span><span class="sxs-lookup"><span data-stu-id="89359-184">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="89359-185">**장치의 맬웨어** 장치에서 검색 되는 특정 맬웨어 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-185">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![장치 카드의 맬웨어](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="89359-187">맬웨어가 가장 많은 장치 이해</span><span class="sxs-lookup"><span data-stu-id="89359-187">Understand which devices have the most malware</span></span>

<span data-ttu-id="89359-188">**맬웨어 검색을 포함 하는 장치** 는 맬웨어가 탐지 된 장치를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-188">**Devices with malware detections** show which devices have the most malware detections.</span></span> <span data-ttu-id="89359-189">Microsoft 365 보안 센터에서는 맬웨어가 활성 상태 인지 여부, 해당 장치를 사용 하는 사람 및 Intune의 관리 상태를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-189">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![맬웨어 감지 카드가 포함 된 장치](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="89359-191">맬웨어가 가장 많은 장치를 보유 하는 사용자 이해</span><span class="sxs-lookup"><span data-stu-id="89359-191">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="89359-192">**맬웨어 검색을 사용** 하는 사용자에 게는 맬웨어가 탐지 된 장치를 사용한 사용자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89359-192">**Users with malware detections** show users with devices that had the most malware detections.</span></span> <span data-ttu-id="89359-193">Microsoft 365 보안 센터에서는 각 사용자에 게 할당 된 장치의 수와 각 장치에 대 한 추가 정보와 맬웨어 유형에 대 한 자세한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-193">In the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![맬웨어 검색 카드를 사용 하는 사용자](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a><span data-ttu-id="89359-195">Attack surface reduction 규칙 배포 및 감지 모니터링 및 관리</span><span class="sxs-lookup"><span data-stu-id="89359-195">Monitor and manage attack surface reduction rule deployment and detections</span></span>

<span data-ttu-id="89359-196">[ASR (Attack Surface Reduction) 규칙](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) 을 사용 하면 일반적으로 익스플로잇 맬웨어를 검색 하는 장치를 감염 시키는 작업과 앱을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-196">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="89359-197">이러한 규칙은 실행 파일을 실행하는 시기와 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-197">These rules control when and how executables can run.</span></span> <span data-ttu-id="89359-198">예를 들어 JavaScript나 VBScript가 다운로드 한 실행 파일을 시작하는 것을 방지하거나 Office 매크로에서 Win32 API 호출을 차단하거나 USB 드라이브에서 실행되는 프로세스를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-198">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![공격 노출 카드](../../media/attack-surface-reduction-rules.png)

<span data-ttu-id="89359-200">**공격 표면 감소 규칙** 카드는 장치 전체의 규칙 배포 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-200">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="89359-201">카드의 맨 위에 있는 막대에는 다음의 배포 모드에 있는 총 장치 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="89359-201">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="89359-202">**차단 모드** : 검색 된 활동을 차단 하도록 하나 이상의 규칙을 구성 하는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="89359-202">**Block mode** : devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="89359-203">**감사 모드** : 검색 된 활동을 차단 하도록 규칙이 설정 되어 있지 않지만 검색 작업을 감사 하도록 하나 이상의 규칙 집합이 있는 장치</span><span class="sxs-lookup"><span data-stu-id="89359-203">**Audit mode** : devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="89359-204">**해제** : 모든 ASR 규칙을 끈 장치</span><span class="sxs-lookup"><span data-stu-id="89359-204">**Off** : devices with all ASR rules turned off</span></span>

<span data-ttu-id="89359-205">이 카드의 아래쪽 부분에는 장치 전체의 규칙 설정이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="89359-205">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="89359-206">각 표시줄에는 차단 하거나, 감사를 감지 하거나, 규칙을 완전히 해제 한 상태로 설정 된 장치의 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89359-206">Each bar indicates the number of devices that are set to block, audit detection, or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="89359-207">ASR 검색 보기</span><span class="sxs-lookup"><span data-stu-id="89359-207">View ASR detections</span></span>

<span data-ttu-id="89359-208">네트워크에서 ASR 규칙 감지에 대 한 자세한 정보를 보려면 **Attack surface reduction** 카드에서 검색 **보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-208">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="89359-209">자세한 보고서 **페이지의 검색 탭이** 열립니다.</span><span class="sxs-lookup"><span data-stu-id="89359-209">The **Detections** tab in the detailed report page will open.</span></span>

![탐지 탭](../../media/detections-tab.png)

<span data-ttu-id="89359-211">페이지 맨 위에 있는 차트에는 차단 되거나 감사 된 시간 단위 누적 검색에 따른 검색 내용이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89359-211">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="89359-212">하단의 표에는 최근 검색이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-212">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="89359-213">표에서 다음의 정보를 사용하여 검색 특성을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-213">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="89359-214">**검색 된 파일** : 해당 내용이 의심 스러운 공격 활동을 트리거한 파일 (대개 스크립트나 문서)입니다.</span><span class="sxs-lookup"><span data-stu-id="89359-214">**Detected file** : the file, typically a script or document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="89359-215">**규칙** :이 규칙은 catch 하도록 설계 된 공격 활동을 설명 하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="89359-215">**Rule** : name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="89359-216">기존 ASR 규칙에 대 한 정보 검토</span><span class="sxs-lookup"><span data-stu-id="89359-216">Read about existing ASR rules</span></span>
* <span data-ttu-id="89359-217">**원본 앱** : 콘텐츠를 로드 하거나 실행 하 여 의심 스러운 공격 활동을 트리거한 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="89359-217">**Source app** : the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="89359-218">웹 브라우저, Office 응용 프로그램 또는 PowerShell과 같은 시스템 도구와 같은 합법적인 응용 프로그램이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-218">It could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="89359-219">**Publisher** : 원본 앱을 릴리스된 공급 업체</span><span class="sxs-lookup"><span data-stu-id="89359-219">**Publisher** : the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="89359-220">장치 ASR 규칙 설정 검토</span><span class="sxs-lookup"><span data-stu-id="89359-220">Review device ASR rule settings</span></span>

<span data-ttu-id="89359-221">**Attack surface reduction 규칙** 보고서 페이지에서 **구성** 탭으로 이동 하 여 개별 장치에 대 한 규칙 설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-221">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="89359-222">각 규칙이 차단 모드, 감사 모드 또는 전체 해제에 대 한 세부 정보를 가져올 장치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-222">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![구성 탭](../../media/configuration-tab.png)

<span data-ttu-id="89359-224">Microsoft Intune은 ASR 규칙에 대 한 관리 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-224">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="89359-225">설정을 업데이트 하려면 탭의 **장치 구성** 아래에서 **시작** 을 선택 하 여 Intune에서 장치 관리를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="89359-225">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="89359-226">ASR 규칙에서 파일 제외</span><span class="sxs-lookup"><span data-stu-id="89359-226">Exclude files from ASR rules</span></span>

<span data-ttu-id="89359-227">Microsoft 365 보안 센터는 공격 노출 범위 규칙에 따라 검색에서 [제외 하려는 파일](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) 의 이름을 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-227">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="89359-228">파일을 제외 하면 가양성 검색을 줄이고 차단 모드에서 더 안전 하 게 공격 표면 축소 규칙을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-228">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="89359-229">제외는 Microsoft Intune에서 관리 되지만 Microsoft 365 보안 센터에서는 파일을 이해 하는 데 도움이 되는 분석 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-229">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="89359-230">제외할 파일 수집을 시작 하려면 **Attack surface reduction 규칙** 보고서 페이지의 **제외 항목 추가** 탭으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-230">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="89359-231">이 도구는 모든 attack surface reduction 규칙에 따라 검색을 분석 하지만 [일부 규칙만 제외를 지원](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-231">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span></span>

![제외 항목 추가 탭](../../media/add-exclusions-tab.png)

<span data-ttu-id="89359-233">이 표에서는 공격 노출 범위 규칙에 의해 검색 된 모든 파일 이름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89359-233">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="89359-234">파일을 선택 하 여 제외로 인 한 영향을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-234">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="89359-235">검색의 수 감소</span><span class="sxs-lookup"><span data-stu-id="89359-235">How many fewer detections</span></span>
* <span data-ttu-id="89359-236">검색을 보고 하는 장치 수는 얼마나 적습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-236">How many fewer devices report the detections</span></span>

<span data-ttu-id="89359-237">제외할 전체 경로를 사용 하 여 선택한 파일 목록을 가져오려면 **제외 경로 가져오기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-237">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="89359-238">**Windows 로컬 보안 기관 하위 시스템 (lsass.exe)에서 ASR 규칙 차단 자격 증명 가로채기** 에 대 한 로그 원본 앱 **lsass.exe** 를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-238">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**.</span></span> <span data-ttu-id="89359-239">이 파일은 일반 시스템 파일이 며 검색 된 파일로 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="89359-239">It is a normal system file, but captured as the detected file.</span></span> <span data-ttu-id="89359-240">따라서이 파일은 제외 경로의 생성 된 목록에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89359-240">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="89359-241">**lsass.exe** 대신이 규칙을 트리거한 파일을 제외 하려면 검색 된 파일 대신 원본 앱 경로를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-241">To exclude the file that triggered this rule instead of **lsass.exe** , use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="89359-242">원본 앱을 찾으려면이 특정 규칙에 대해 다음 [고급 구하기 쿼리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) 를 실행 합니다 (규칙 ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2으로 식별 됨).</span><span class="sxs-lookup"><span data-stu-id="89359-242">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="89359-243">파일 제외 확인</span><span class="sxs-lookup"><span data-stu-id="89359-243">Check files for exclusion</span></span>

<span data-ttu-id="89359-244">ASR에서 파일을 제외 하기 전에 해당 파일을 검사 하 여 해당 파일이 실제로 유해한 인지 여부를 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-244">Before excluding a file from ASR, we recommend that you inspect the file to determine if it's indeed not malicious.</span></span>

<span data-ttu-id="89359-245">파일을 검토 하려면 Microsoft Defender 보안 센터의 [파일 정보 페이지](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-245">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="89359-246">이 페이지에서는 전파 정보 및 VirusTotal 바이러스 검사 비율을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-246">The page provides prevalence information and the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="89359-247">페이지를 사용 하 여 심층 분석을 위해 파일을 전송할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-247">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="89359-248">Microsoft Defender 보안 센터에서 검색 된 파일을 찾으려면 다음 고급 검색 쿼리를 사용 하 여 모든 ASR 검색을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="89359-248">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="89359-249">Microsoft Defender 보안 센터의 유니버설 검색 표시줄을 사용 하 여 파일을 검색 하려면 결과에서 **SHA1** 또는 **InitiatingProcessSHA1** 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89359-249">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
