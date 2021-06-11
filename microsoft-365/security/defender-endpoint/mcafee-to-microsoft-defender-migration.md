---
title: McAfee에서 끝점용 Microsoft Defender로 마이그레이션
description: McAfee에서 끝점용 Microsoft Defender로 전환합니다. 개요는 이 문서를 읽어 읽습니다.
keywords: migration, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-mcafeemigrate
- m365solution-overview
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 5bbcf885ec160204916507aee60398aee35e470b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538054"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="b8f61-105">McAfee에서 끝점용 Microsoft Defender로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="b8f61-105">Migrate from McAfee to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="b8f61-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b8f61-106">**Applies to:**</span></span>
- [<span data-ttu-id="b8f61-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b8f61-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b8f61-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8f61-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="b8f61-109">McAfee Endpoint Security(McAfee)에서 [끝점용 Microsoft Defender(끝점용 Microsoft Defender)로](microsoft-defender-endpoint.md) 전환할 계획이면 올바른 장소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-109">If you are planning to switch from McAfee Endpoint Security (McAfee) to [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Microsoft Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="b8f61-110">이 문서를 가이드로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="b8f61-110">Use this article as a guide.</span></span>


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="McAfee에서 끝점용 Defender로 마이그레이션 개요":::

<span data-ttu-id="b8f61-112">McAfee에서 Endpoint용 Defender로 전환하는 경우 활성 모드에서 McAfee 솔루션으로 시작하고, 수동 모드에서 끝점용 Defender를 구성하고, 끝점용 Defender에 온보딩한 다음 Endpoint용 Defender를 활성 모드로 설정하고 McAfee를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-112">When you make the switch from McAfee to Defender for Endpoint, you begin with your McAfee solution in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, and then set Defender for Endpoint to active mode and remove McAfee.</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="b8f61-113">마이그레이션 프로세스</span><span class="sxs-lookup"><span data-stu-id="b8f61-113">The migration process</span></span>

<span data-ttu-id="b8f61-114">McAfee에서 끝점용 Microsoft Defender로 전환하는 경우 준비, 설치 및 온보딩의 세 단계로 나눌 수 있는 프로세스를 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-114">When you switch from McAfee to Microsoft Defender for Endpoint, you follow a process that can be divided into three phases: Prepare, Setup, and Onboard.</span></span> 

![마이그레이션 단계 - 설치 온보드 준비](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="b8f61-116">단계</span><span class="sxs-lookup"><span data-stu-id="b8f61-116">Phase</span></span> |<span data-ttu-id="b8f61-117">설명</span><span class="sxs-lookup"><span data-stu-id="b8f61-117">Description</span></span> |
|--|--|
|[<span data-ttu-id="b8f61-118">마이그레이션 준비</span><span class="sxs-lookup"><span data-stu-id="b8f61-118">Prepare for your migration</span></span>](mcafee-to-microsoft-defender-prepare.md) |<span data-ttu-id="b8f61-119">준비 [**단계에서는**](mcafee-to-microsoft-defender-prepare.md) 조직의 장치를 업데이트하고, 끝점용 Microsoft Defender를 다운로드하고, 역할 및 권한을 계획하고, 조직에 대한 액세스 권한을 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="b8f61-119">During the [**Prepare**](mcafee-to-microsoft-defender-prepare.md) phase, you update your organization's devices, get Microsoft Defender for Endpoint, plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="b8f61-120">또한 조직의 장치와 끝점용 Microsoft Defender 간의 통신을 사용하도록 장치 프록시 및 인터넷 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-120">You also configure your device proxy and internet settings to enable communication between your organization's devices and Microsoft Defender for Endpoint.</span></span> |
|[<span data-ttu-id="b8f61-121">끝점에 대한 Microsoft Defender 설정</span><span class="sxs-lookup"><span data-stu-id="b8f61-121">Set up Microsoft Defender for Endpoint</span></span>](mcafee-to-microsoft-defender-setup.md) |<span data-ttu-id="b8f61-122">설치 [**단계에서는**](mcafee-to-microsoft-defender-setup.md) 설정을 사용하도록 Microsoft Defender 바이러스 백신 수동 모드로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-122">During the [**Setup**](mcafee-to-microsoft-defender-setup.md) phase, you enable Microsoft Defender Antivirus and set it to passive mode.</span></span> <span data-ttu-id="b8f61-123">또한 기존 끝점 & 솔루션에 Microsoft Defender 바이러스 백신 제외에 대한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-123">You also configure settings & exclusions for Microsoft Defender Antivirus and your existing endpoint protection solution.</span></span> <span data-ttu-id="b8f61-124">그런 다음 장치 그룹, 컬렉션 및 조직 구성 단위를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-124">Then, you create your device groups, collections, and organizational units.</span></span> <span data-ttu-id="b8f61-125">마지막으로 맬웨어 방지 정책 및 실시간 보호 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-125">Finally, you configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="b8f61-126">끝점용 Microsoft Defender에 온보딩</span><span class="sxs-lookup"><span data-stu-id="b8f61-126">Onboard to Microsoft Defender for Endpoint</span></span>](mcafee-to-microsoft-defender-onboard.md) |<span data-ttu-id="b8f61-127">[**온보딩**](mcafee-to-microsoft-defender-onboard.md) 단계에서는 디바이스를 끝점용 Microsoft Defender에 온보딩하고, Microsoft Defender 바이러스 백신 모드로 실행 중인지 확인하고, 끝점이 끝점용 Defender와 통신하고 있는지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-127">During the [**Onboard**](mcafee-to-microsoft-defender-onboard.md) phase, you onboard your devices to Microsoft Defender for Endpoint, confirm that Microsoft Defender Antivirus is running in passive mode, and verify that your endpoints are communicating with Defender for Endpoint.</span></span> <span data-ttu-id="b8f61-128">그런 다음 McAfee를 제거하고 끝점용 Defender가 제대로 작동하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-128">Then, you uninstall McAfee and make sure that Defender for Endpoint is working correctly.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="b8f61-129">끝점용 Microsoft Defender에는 무엇이 포함되어 있나요?</span><span class="sxs-lookup"><span data-stu-id="b8f61-129">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="b8f61-130">이 마이그레이션 가이드에서는 끝점용 Microsoft [](overview-endpoint-detection-response.md) Defender로 이동하기 위한 시작점으로 차세대 보호 및 끝점 감지 및 응답 기능에 중점을 두고 있습니다. [](microsoft-defender-antivirus-in-windows-10.md)</span><span class="sxs-lookup"><span data-stu-id="b8f61-130">In this migration guide, we focus on [next-generation protection](microsoft-defender-antivirus-in-windows-10.md) and [endpoint detection and response](overview-endpoint-detection-response.md) capabilities as a starting point for moving to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b8f61-131">그러나 끝점용 Microsoft Defender에는 바이러스 백신 및 끝점 보호보다 훨씬 더 많은 보호가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-131">However, Microsoft Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="b8f61-132">엔드포인트용 Microsoft Defender는 예방적 보호, 침해 후 감지, 자동화된 조사 및 대응을 위한 통합 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-132">Microsoft Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="b8f61-133">다음 표에는 끝점용 Microsoft Defender의 기능이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-133">The following table summarizes features and capabilities in Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="b8f61-134">기능/기능</span><span class="sxs-lookup"><span data-stu-id="b8f61-134">Feature/Capability</span></span> | <span data-ttu-id="b8f61-135">설명</span><span class="sxs-lookup"><span data-stu-id="b8f61-135">Description</span></span> |
|---|---|
| [<span data-ttu-id="b8f61-136">위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="b8f61-136">Threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md) | <span data-ttu-id="b8f61-137">위협 & 취약성 관리 기능은 끝점(예: 장치)에서 약점을 식별, 평가 및 수정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-137">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="b8f61-138">공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="b8f61-138">Attack surface reduction</span></span>](overview-attack-surface-reduction.md) | <span data-ttu-id="b8f61-139">공격 표면 감소 규칙은 사이버 위협 및 공격으로부터 조직의 장치 및 응용 프로그램을 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-139">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="b8f61-140">차세대 보호</span><span class="sxs-lookup"><span data-stu-id="b8f61-140">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md) | <span data-ttu-id="b8f61-141">차세대 보호에는 위협 Microsoft Defender 바이러스 백신 맬웨어를 차단하는 데 도움이 되는 여러 가지 기능도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-141">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="b8f61-142">엔드포인트 검색 및 대응</span><span class="sxs-lookup"><span data-stu-id="b8f61-142">Endpoint detection and response</span></span>](overview-endpoint-detection-response.md) | <span data-ttu-id="b8f61-143">끝점 감지 및 응답 기능은 침입 시도 및 활성 위반을 감지, 조사 및 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-143">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="b8f61-144">지능형 헌팅</span><span class="sxs-lookup"><span data-stu-id="b8f61-144">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="b8f61-145">고급 헌팅 기능을 통해 보안 운영 팀은 알려진 위협 또는 잠재적인 위협의 지표와 엔터티를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-145">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="b8f61-146">동작 차단 및 제약</span><span class="sxs-lookup"><span data-stu-id="b8f61-146">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md) | <span data-ttu-id="b8f61-147">동작 차단 및 포함 기능은 위협이 실행을 시작한 경우에도 동작 및 처리 트리를 기반으로 위협을 식별하고 중지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-147">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="b8f61-148">자동화된 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="b8f61-148">Automated investigation and remediation</span></span>](automated-investigations.md) | <span data-ttu-id="b8f61-149">자동화된 조사 및 대응 기능은 경고를 검사하고 위반을 해결하기 위해 즉시 수정 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-149">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="b8f61-150">[위협 헌팅](microsoft-threat-experts.md) 서비스(Microsoft 위협 전문가)</span><span class="sxs-lookup"><span data-stu-id="b8f61-150">[Threat hunting service](microsoft-threat-experts.md) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="b8f61-151">위협 헌팅 서비스는 보안 운영 팀에 전문가 수준의 모니터링 및 분석을 제공하고 중요한 위협이 누락되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f61-151">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="b8f61-152">**자세한 내용을 원하세요? [끝점용 Microsoft Defender를 참조합니다.](microsoft-defender-endpoint.md)**</span><span class="sxs-lookup"><span data-stu-id="b8f61-152">**Want to learn more? See [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).**</span></span>

## <a name="next-step"></a><span data-ttu-id="b8f61-153">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b8f61-153">Next step</span></span>

- <span data-ttu-id="b8f61-154">마이그레이션 [준비로 진행합니다.](mcafee-to-microsoft-defender-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="b8f61-154">Proceed to [Prepare for your migration](mcafee-to-microsoft-defender-prepare.md).</span></span>
