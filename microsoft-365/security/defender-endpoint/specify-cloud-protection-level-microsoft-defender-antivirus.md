---
title: 클라우드 제공 보호 수준을 Microsoft Defender 바이러스 백신
description: 사용자에 대한 클라우드 제공 보호 수준을 Microsoft Defender 바이러스 백신.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, Defender, 클라우드, 적극성, 보호 수준
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: fb4dd3114c411385f1a38cf7b0fd391a1b159b99
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924474"
---
# <a name="specify-the-cloud-delivered-protection-level"></a><span data-ttu-id="9fa16-104">클라우드 제공 보호 수준 지정</span><span class="sxs-lookup"><span data-stu-id="9fa16-104">Specify the cloud-delivered protection level</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9fa16-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9fa16-105">**Applies to:**</span></span>

- [<span data-ttu-id="9fa16-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9fa16-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9fa16-107">사용자 지정(권장) 또는 그룹 정책을 사용하여 Microsoft Defender 바이러스 백신 클라우드 제공 보호 수준을 Microsoft Endpoint Manager 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-107">You can specify your level of cloud-delivered protection offered by Microsoft Defender Antivirus by using Microsoft Endpoint Manager (recommended) or Group Policy.</span></span>

> [!TIP]
> <span data-ttu-id="9fa16-108">클라우드 보호는 단순히 클라우드에 저장된 파일에 대한 보호가 아니며,</span><span class="sxs-lookup"><span data-stu-id="9fa16-108">Cloud protection is not simply protection for files that are stored in the cloud.</span></span> <span data-ttu-id="9fa16-109">Microsoft Defender 바이러스 백신 클라우드 서비스는 네트워크 및 장치(끝점이라고도 하는)에 업데이트된 보호를 제공하는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-109">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and devices (also called endpoints).</span></span> <span data-ttu-id="9fa16-110">사용자 Microsoft Defender 바이러스 백신 클라우드 보호는 분산된 리소스와 기계 학습을 사용하여 기존 보안 인텔리전스 업데이트보다 훨씬 빠른 속도로 끝점에 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-110">Cloud protection with Microsoft Defender Antivirus uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional security intelligence updates.</span></span> <span data-ttu-id="9fa16-111">Microsoft Intune Microsoft Endpoint Manager 의 [일부로](/mem/endpoint-manager-overview)Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="9fa16-111">Microsoft Intune and Microsoft Endpoint Manager are now part of [Microsoft Endpoint Manager](/mem/endpoint-manager-overview).</span></span> 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="9fa16-112">이 Microsoft Endpoint Manager 사용하여 클라우드 제공 보호 수준 지정</span><span class="sxs-lookup"><span data-stu-id="9fa16-112">Use Microsoft Endpoint Manager to specify the level of cloud-delivered protection</span></span>

1. <span data-ttu-id="9fa16-113">Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-113">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="9fa16-114">끝점 **보안 바이러스 백신**  >  **을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa16-114">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="9fa16-115">바이러스 백신 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-115">Select an antivirus profile.</span></span> <span data-ttu-id="9fa16-116">(아직 프로필이 없는 경우 또는 새 프로필을 만들하려는 경우 에서 장치 제한 설정 [구성을 Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="9fa16-116">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="9fa16-117">속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa16-117">Select **Properties**.</span></span> <span data-ttu-id="9fa16-118">그런 다음 구성 설정 **옆에 있는** 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa16-118">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="9fa16-119">클라우드 **보호를 확장하고**  클라우드 제공 보호 수준 목록에서 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-119">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>

    1. <span data-ttu-id="9fa16-120">**높음:** 강력한 수준의 검색을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-120">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="9fa16-121">**High plus:** **높음** 수준을 사용하며 추가 보호 조치를 적용합니다(클라이언트 성능에 영향을 줄 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="9fa16-121">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="9fa16-122">**허용 오차** 없음: 알 수 없는 모든 실행을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-122">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="9fa16-123">검토 **+ 저장 을** 선택한 다음 저장 을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa16-123">Choose **Review + save**, and then choose **Save**.</span></span> 

> [!TIP]
> <span data-ttu-id="9fa16-124">도움이 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="9fa16-124">Need some help?</span></span> <span data-ttu-id="9fa16-125">다음 리소스를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9fa16-125">See the following resources:</span></span>
> - [<span data-ttu-id="9fa16-126">구성 Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="9fa16-126">Configure Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [<span data-ttu-id="9fa16-127">Intune에서 끝점 보호 설정 추가</span><span class="sxs-lookup"><span data-stu-id="9fa16-127">Add endpoint protection settings in Intune</span></span>](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="9fa16-128">그룹 정책을 사용하여 클라우드 제공 보호 수준 지정</span><span class="sxs-lookup"><span data-stu-id="9fa16-128">Use Group Policy to specify the level of cloud-delivered protection</span></span>

1.  <span data-ttu-id="9fa16-129">그룹 정책 관리 컴퓨터의 그룹 정책 관리 [콘솔 을 열 수 있습니다.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="9fa16-129">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="9fa16-130">구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa16-130">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

3.  <span data-ttu-id="9fa16-131">그룹 정책 **관리 편집기에서** 컴퓨터 구성 **관리**  >  **템플릿으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="9fa16-131">In the **Group Policy Management Editor** go to **Computer Configuration** > **Administrative templates**.</span></span>

4.  <span data-ttu-id="9fa16-132">트리를   >    >  **MpEngine** Windows 구성 Microsoft Defender 바이러스 백신 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-132">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

5.  <span data-ttu-id="9fa16-133">클라우드 보호 수준 **선택 설정을 두 번 클릭하고** 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa16-133">Double-click the **Select cloud protection level** setting and set it to **Enabled**.</span></span> <span data-ttu-id="9fa16-134">보호 수준을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-134">Select the level of protection:</span></span>
    - <span data-ttu-id="9fa16-135">**기본 차단 수준은** 합법적인 파일을 검색할 위험을 늘리지 않고 강력한 검색을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-135">**Default blocking level** provides strong detection without increasing the risk of detecting legitimate files.</span></span>
    - <span data-ttu-id="9fa16-136">**보통 차단 수준은** 높은 신뢰도 검색을 위한 보통만 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-136">**Moderate blocking level** provides moderate only for high confidence detections</span></span>
    - <span data-ttu-id="9fa16-137">**높은 차단 수준은** 클라이언트 성능을 최적화하는 동안 강력한 수준의 검색을 적용하지만 가음성의 가능성이 더 커질 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-137">**High blocking level** applies a strong level of detection while optimizing client performance (but can also give you a greater chance of false positives).</span></span>
    - <span data-ttu-id="9fa16-138">**높은 + 차단 수준은** 추가 보호 조치를 적용합니다(클라이언트 성능에 영향을 미치고 가음성의 가능성이 높아질 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="9fa16-138">**High + blocking level** applies additional protection measures (might impact client performance and increase your chance of false positives).</span></span>
    - <span data-ttu-id="9fa16-139">**허용 오차 차단 수준이 0이면** 알 수 없는 모든 실행이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-139">**Zero tolerance blocking level** blocks all unknown executables.</span></span>
    
    > [!WARNING]
    > <span data-ttu-id="9fa16-140">가능성은 낮지만 이 스위치를 **높음** 또는 **높음 +로** 설정하면 일부 합법적인 파일이 검색될 수 있습니다(해당 검색을 차단 해제하거나 분쟁할 수 있는 옵션이 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="9fa16-140">While unlikely, setting this switch to **High** or **High +** may cause some legitimate files to be detected (although you will have the option to unblock or dispute that detection).</span></span>

6. <span data-ttu-id="9fa16-141">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-141">Click **OK**.</span></span>

7. <span data-ttu-id="9fa16-142">업데이트된 그룹 정책 개체를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-142">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="9fa16-143">그룹 [정책 관리 콘솔 참조](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="9fa16-143">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy)</span></span>

> [!TIP]
> <span data-ttu-id="9fa16-144">그룹 정책 개체를 사용하는지 여부</span><span class="sxs-lookup"><span data-stu-id="9fa16-144">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="9fa16-145">클라우드에서 번역하는 방법을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa16-145">See how they translate in the cloud.</span></span> <span data-ttu-id="9fa16-146">미리 보기에서 그룹 정책 분석을 사용하여 Microsoft Endpoint Manager 그룹 정책 개체를 [분석합니다.](/mem/intune/configuration/group-policy-analytics)</span><span class="sxs-lookup"><span data-stu-id="9fa16-146">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="9fa16-147">관련 문서</span><span class="sxs-lookup"><span data-stu-id="9fa16-147">Related articles</span></span>

- [<span data-ttu-id="9fa16-148">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="9fa16-148">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="9fa16-149">클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="9fa16-149">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9fa16-150">맬웨어 방지 정책을 만들고 배포하는 방법: 클라우드 보호 서비스</span><span class="sxs-lookup"><span data-stu-id="9fa16-150">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)