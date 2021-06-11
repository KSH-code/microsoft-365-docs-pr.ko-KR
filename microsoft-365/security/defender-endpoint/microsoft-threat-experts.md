---
title: Microsoft 위협 전문가
ms.reviewer: ''
description: Microsoft 위협 전문가 Microsoft Defender for Endpoint에 대한 추가 전문 지식 계층을 제공합니다.
keywords: 관리되는 위협 헌팅 서비스, 관리되는 위협 헌팅, MDR(관리되는 감지 및 응답) 서비스, MTE, Microsoft 위협 전문가, MTE-TAN, 대상 공격 알림, 대상 공격 알림
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 956fb591154df374c8010d875645e1122f3419b2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879243"
---
# <a name="microsoft-threat-experts"></a><span data-ttu-id="91db4-104">Microsoft 위협 전문가</span><span class="sxs-lookup"><span data-stu-id="91db4-104">Microsoft Threat Experts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="91db4-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="91db4-105">**Applies to:**</span></span>
- [<span data-ttu-id="91db4-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="91db4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="91db4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91db4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="91db4-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="91db4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="91db4-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="91db4-110">Microsoft 위협 전문가 SOC(보안 운영 센터)에 전문가 수준의 모니터링 및 분석을 제공하는 관리되는 위협 헌팅 서비스로, 고유한 환경의 중요한 위협이 누락되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-110">Microsoft Threat Experts is a managed threat hunting service that provides your Security Operation Centers (SOCs) with expert level monitoring and analysis to help them ensure that critical threats in your unique environments don’t get missed.</span></span>
  
<span data-ttu-id="91db4-111">이 관리되는 위협 헌팅 서비스는 대상 공격 알림 및 요구 시 전문가 액세스의 두 가지 기능을 통해 전문가 중심의 인사이트 및 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-111">This managed threat hunting service provides expert-driven insights and data through these two capabilities: targeted attack notification and access to experts on demand.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="91db4-112">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="91db4-112">Before you begin</span></span> 
> [!NOTE]
> <span data-ttu-id="91db4-113">관리되는 위협 헌팅 서비스에 적용하기 전에 Microsoft 기술 서비스 공급자 및 계정 팀과 자격 요구 사항을 논의합니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-113">Discuss the eligibility requirements with your Microsoft Technical Service provider and account team before you apply to the managed threat hunting service.</span></span>

<span data-ttu-id="91db4-114">Endpoint용 Microsoft Defender 고객인 경우 사용자 환경에서 가장 **중요한 위협을** 식별하여 신속하게 대응할 수 있도록 Microsoft 위협 전문가 - 대상 지정 공격 알림을 신청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-114">If you're a Microsoft Defender for Endpoint customer, you need to apply for **Microsoft Threat Experts - Targeted Attack Notifications** to get special insights and analysis that help identify the most critical threats in your environment so you can respond to them quickly.</span></span>

<span data-ttu-id="91db4-115">대상이 Microsoft 위협 전문가 - 대상 공격 알림 혜택에 등록하기 위해 설정 끝점 일반 고급 Microsoft 위협 전문가 - 적용할 대상 공격   >    >    >    >  **알림으로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-115">To enroll to Microsoft Threat Experts - Targeted Attack Notifications benefits, go to **Settings** > **Endpoints** > **General** > **Advanced features** > **Microsoft Threat Experts - Targeted Attack Notifications** to apply.</span></span> <span data-ttu-id="91db4-116">일단 수락되면 대상 공격 알림의 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-116">Once accepted, you will get the benefits of Targeted Attack Notifications.</span></span>

<span data-ttu-id="91db4-117">계정 팀 또는 Microsoft 담당자에게 문의하여 Microsoft 위협 전문가 **-** 요구 전문가에게 문의하여 위협 전문가에게 조직이 직면하고 있는 관련 탐지 및 가해자에 대한 자문을 구하세요.</span><span class="sxs-lookup"><span data-stu-id="91db4-117">Contact your account team or Microsoft representative to subscribe to **Microsoft Threat Experts - Experts on Demand** to consult with our threat experts on relevant detections and adversaries that your organization is facing.</span></span>

<span data-ttu-id="91db4-118">자세한 [Microsoft 위협 전문가 기능 구성을](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-118">See [Configure Microsoft Threat Experts capabilities](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) for details.</span></span> 

## <a name="microsoft-threat-experts---targeted-attack-notification"></a><span data-ttu-id="91db4-119">Microsoft 위협 전문가 - 대상 공격 알림</span><span class="sxs-lookup"><span data-stu-id="91db4-119">Microsoft Threat Experts - Targeted attack notification</span></span> 
<span data-ttu-id="91db4-120">Microsoft 위협 전문가 - 대상이 지정 된 공격 알림은 악의적인 공격, 실습 키보드 공격 또는 사이버-에스피니지와 같은 고급 공격을 포함하여 네트워크에 대한 가장 중요한 위협에 대한 사전 헌팅을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-120">Microsoft Threat Experts - Targeted attack notification provides proactive hunting for the most important threats to your network, including human adversary intrusions, hands-on-keyboard attacks, or advanced attacks like cyber-espionage.</span></span> <span data-ttu-id="91db4-121">이러한 알림은 새 경고로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-121">These notifications shows up as a new alert.</span></span> <span data-ttu-id="91db4-122">관리되는 헌팅 서비스에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-122">The managed hunting service includes:</span></span>  
- <span data-ttu-id="91db4-123">위협 모니터링 및 분석, 비즈니스에 대한 DWELL 시간 및 위험 감소</span><span class="sxs-lookup"><span data-stu-id="91db4-123">Threat monitoring and analysis, reducing dwell time and risk to the business</span></span> 
- <span data-ttu-id="91db4-124">알려진 공격과 알 수 없는 공격을 모두 검색하고 우선 순위를 지정하기 위해 헌터가 학습한 인공 지능</span><span class="sxs-lookup"><span data-stu-id="91db4-124">Hunter-trained artificial intelligence to discover and prioritize both known and unknown attacks</span></span>  
- <span data-ttu-id="91db4-125">가장 중요한 위험을 식별하여 SOC가 시간 및 에너지 최대화</span><span class="sxs-lookup"><span data-stu-id="91db4-125">Identifying the most important risks, helping SOCs maximize time and energy</span></span> 
- <span data-ttu-id="91db4-126">손상 범위 및 빠른 SOC 응답을 위해 빠르게 전달될 수 있는 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-126">Scope of compromise and as much context as can be quickly delivered to enable fast SOC response.</span></span> 
 
## <a name="microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="91db4-127">Microsoft 위협 전문가 - 전문가</span><span class="sxs-lookup"><span data-stu-id="91db4-127">Microsoft Threat Experts - Experts on Demand</span></span>
<span data-ttu-id="91db4-128">고객은 적시에 정확한 대응을 위해 보안 전문가와 직접 Microsoft Defender 보안 센터 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-128">Customers can engage our security experts directly from within Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="91db4-129">전문가는 경고 문의, 잠재적으로 손상된 장치, 의심스러운 네트워크 연결의 근본 원인, 지속적인 고급 영구 위협 캠페인과 관련한 추가 위협 인텔리전스까지 조직에 영향을 주는 복잡한 위협을 더 잘 이해하는 데 필요한 인사이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-129">Experts provide insights needed to better understand the complex threats affecting your organization, from alert inquiries, potentially compromised devices, root cause of a suspicious network connection, to additional threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="91db4-130">이 기능을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-130">With this capability, you can:</span></span>
- <span data-ttu-id="91db4-131">인시던트의 근본 원인 또는 범위를 포함하여 경고에 대한 추가 설명을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-131">Get additional clarification on alerts including root cause or scope of the incident</span></span> 
- <span data-ttu-id="91db4-132">고급 공격자가 직면한 경우 의심스러운 장치 동작 및 다음 단계에 대한 명확성 확보</span><span class="sxs-lookup"><span data-stu-id="91db4-132">Gain clarity into suspicious device behavior and next steps if faced with an advanced attacker</span></span>  
- <span data-ttu-id="91db4-133">위협 공격자, 캠페인 또는 새로운 공격자 기술에 관한 위험 및 보호 결정</span><span class="sxs-lookup"><span data-stu-id="91db4-133">Determine risk and protection regarding threat actors, campaigns, or emerging attacker techniques</span></span> 

<span data-ttu-id="91db4-134">위협 **전문가에게 문의하는** 옵션은 포털의 여러 장소에서 사용할 수 있으므로 조사 컨텍스트에서 전문가와 함께 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-134">The option to **Consult a threat expert** is available in several places in the portal so you can engage with experts in the context of your investigation:</span></span>

- <span data-ttu-id="91db4-135"><i>**도움말 및 지원 메뉴**</i></span><span class="sxs-lookup"><span data-stu-id="91db4-135"><i>**Help and support menu**</i></span></span><BR>
<span data-ttu-id="91db4-136">![MTE-EOD 메뉴 옵션 스크린샷](images/mte-eod-menu.png)</span><span class="sxs-lookup"><span data-stu-id="91db4-136">![Screenshot of MTE-EOD menu option](images/mte-eod-menu.png)</span></span>

- <span data-ttu-id="91db4-137"><i>**장치 페이지 작업 메뉴**</i></span><span class="sxs-lookup"><span data-stu-id="91db4-137"><i>**Device page actions menu**</i></span></span><BR>
<span data-ttu-id="91db4-138">![MTE-EOD 장치 페이지 작업 메뉴 옵션 스크린샷](images/mte-eod-machines.png)</span><span class="sxs-lookup"><span data-stu-id="91db4-138">![Screenshot of MTE-EOD device page action menu option](images/mte-eod-machines.png)</span></span>

- <span data-ttu-id="91db4-139"><i>**경고 페이지 작업 메뉴**</i></span><span class="sxs-lookup"><span data-stu-id="91db4-139"><i>**Alerts page actions menu**</i></span></span><BR>
<span data-ttu-id="91db4-140">![MTE-EOD 경고 페이지 작업 메뉴 옵션 스크린샷](images/mte-eod-alerts.png)</span><span class="sxs-lookup"><span data-stu-id="91db4-140">![Screenshot of MTE-EOD alert page action menu option](images/mte-eod-alerts.png)</span></span>

- <span data-ttu-id="91db4-141"><i>**파일 페이지 작업 메뉴**</i></span><span class="sxs-lookup"><span data-stu-id="91db4-141"><i>**File page actions menu**</i></span></span><BR>
<span data-ttu-id="91db4-142">![MTE-EOD 파일 페이지 작업 메뉴 옵션 스크린샷](images/mte-eod-file.png)</span><span class="sxs-lookup"><span data-stu-id="91db4-142">![Screenshot of MTE-EOD file page action menu option](images/mte-eod-file.png)</span></span>

> [!NOTE]
> <span data-ttu-id="91db4-143">Microsoft 서비스 허브를 통해 전문가 관련 사례의 상태를 추적하려면 기술 계정 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="91db4-143">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your Technical Account Manager.</span></span> 

<span data-ttu-id="91db4-144">이 비디오를 시청하여 Microsoft 서비스 허브에 대한 간략한 개요를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91db4-144">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 

   
## <a name="related-topic"></a><span data-ttu-id="91db4-145">관련 항목</span><span class="sxs-lookup"><span data-stu-id="91db4-145">Related topic</span></span>
- [<span data-ttu-id="91db4-146">Microsoft 위협 전문가 기능 구성</span><span class="sxs-lookup"><span data-stu-id="91db4-146">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md)
