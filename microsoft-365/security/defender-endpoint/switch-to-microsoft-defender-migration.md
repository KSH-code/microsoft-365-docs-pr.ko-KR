---
title: Microsoft가 아닌 다른 끝점 솔루션에서 끝점용 Microsoft Defender로 전환
description: 끝점용 Microsoft Defender로 전환합니다. 개요는 이 문서를 읽어 읽습니다.
keywords: migration, windows defender advanced endpoint protection, for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365solution-migratetomdatp
- m365solution-overview
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 013205a1b5b9db204f626a6fe6ab76ad07378558
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538006"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="f095e-105">Microsoft가 아닌 다른 끝점 솔루션에서 끝점용 Microsoft Defender로 전환</span><span class="sxs-lookup"><span data-stu-id="f095e-105">Make the switch from a non-Microsoft endpoint solution to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="f095e-106">Microsoft가 아닌 끝점 보호 솔루션에서 [끝점용 Microsoft Defender(Endpoint용 Defender)로](microsoft-defender-endpoint.md) 전환할 계획이면 올바른 장소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-106">If you are planning to switch from a non-Microsoft endpoint protection solution to [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="f095e-107">이 문서를 가이드로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f095e-107">Use this article as a guide.</span></span>

:::image type="content" source="images/nonms-mde-migration.png" alt-text="끝점용 Defender로의 마이그레이션 개요":::

<span data-ttu-id="f095e-109">Endpoint용 Defender로 전환할 때 활성 모드에서 Microsoft가 아닌 솔루션으로 시작하고, 수동 모드에서 끝점에 대한 Defender를 구성하고, 끝점용 Defender에 온보딩한 다음 끝점용 Defender를 활성 모드로 설정하고 Microsoft가 아닌 솔루션을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-109">When you make the switch to Defender for Endpoint, you begin with your non-Microsoft solution in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, and then set Defender for Endpoint to active mode and remove the non-Microsoft solution.</span></span>

> [!TIP]
> - <span data-ttu-id="f095e-110">현재 McAfee 끝점 보안(McAfee)을 사용 중인 경우 [Migrate from McAfee to Defender for Endpoint를 참조합니다.](mcafee-to-microsoft-defender-migration.md)</span><span class="sxs-lookup"><span data-stu-id="f095e-110">If you're currently using McAfee Endpoint Security (McAfee), see [Migrate from McAfee to Defender for Endpoint](mcafee-to-microsoft-defender-migration.md).</span></span>
> - <span data-ttu-id="f095e-111">현재 Symantec Endpoint Protection(Symantec)를 사용하는 경우 [Migrate from Symantec to Defender for Endpoint를 참조합니다.](symantec-to-microsoft-defender-endpoint-migration.md)</span><span class="sxs-lookup"><span data-stu-id="f095e-111">If you're currently using Symantec Endpoint Protection (Symantec), see [Migrate from Symantec to Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md).</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="f095e-112">마이그레이션 프로세스</span><span class="sxs-lookup"><span data-stu-id="f095e-112">The migration process</span></span>

<span data-ttu-id="f095e-113">Endpoint용 Defender로 전환할 때 다음 표에 설명된 세 단계로 나눌 수 있는 프로세스를 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-113">When you switch to Defender for Endpoint, you follow a process that can be divided into three phases, as described in the following table:</span></span>

![마이그레이션 단계 - 준비, 설정, 온보드](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="f095e-115">단계</span><span class="sxs-lookup"><span data-stu-id="f095e-115">Phase</span></span> |<span data-ttu-id="f095e-116">설명</span><span class="sxs-lookup"><span data-stu-id="f095e-116">Description</span></span> |
|--|--|
|[<span data-ttu-id="f095e-117">마이그레이션 준비</span><span class="sxs-lookup"><span data-stu-id="f095e-117">Prepare for your migration</span></span>](switch-to-microsoft-defender-prepare.md) |<span data-ttu-id="f095e-118">준비 [ **단계에서는**](switch-to-microsoft-defender-prepare.md)조직의 장치를 업데이트하고, 끝점에 대한 Defender를 다운로드하고, 역할 및 권한을 계획하고, 조직에 대한 액세스 권한을 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="f095e-118">During [the **Prepare** phase](switch-to-microsoft-defender-prepare.md), you update your organization's devices, get Defender for Endpoint, plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="f095e-119">또한 조직의 장치와 Endpoint용 Defender 간의 통신을 사용하도록 장치 프록시 및 인터넷 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-119">You also configure your device proxy and internet settings to enable communication between your organization's devices and Defender for Endpoint.</span></span> |
|[<span data-ttu-id="f095e-120">끝점에 대한 Defender 설정</span><span class="sxs-lookup"><span data-stu-id="f095e-120">Set up Defender for Endpoint</span></span>](switch-to-microsoft-defender-setup.md) |<span data-ttu-id="f095e-121">설치 [ **단계 중에는**](switch-to-microsoft-defender-setup.md)를 사용하도록 Microsoft Defender 바이러스 백신 수동 모드로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-121">During [the **Setup** phase](switch-to-microsoft-defender-setup.md), you enable Microsoft Defender Antivirus and set it to passive mode.</span></span> <span data-ttu-id="f095e-122">또한 기존 끝점 & 솔루션에 Microsoft Defender 바이러스 백신 제외에 대한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-122">You also configure settings & exclusions for Microsoft Defender Antivirus and your existing endpoint protection solution.</span></span> <span data-ttu-id="f095e-123">그런 다음 장치 그룹, 컬렉션 및 조직 구성 단위를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-123">Then, you create your device groups, collections, and organizational units.</span></span> <span data-ttu-id="f095e-124">마지막으로 맬웨어 방지 정책 및 실시간 보호 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-124">Finally, you configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="f095e-125">끝점용 Defender에 온보딩</span><span class="sxs-lookup"><span data-stu-id="f095e-125">Onboard to Defender for Endpoint</span></span>](switch-to-microsoft-defender-onboard.md) |<span data-ttu-id="f095e-126">[ **온보딩**](switch-to-microsoft-defender-onboard.md)단계에서 끝점용 Defender에 장치를 온보딩하고, Microsoft Defender 바이러스 백신 모드로 실행 중인지 확인하고, 끝점이 끝점용 Defender와 통신하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-126">During [the **Onboard** phase](switch-to-microsoft-defender-onboard.md), you onboard your devices to Defender for Endpoint, confirm that Microsoft Defender Antivirus is running in passive mode, and verify that your endpoints are communicating with Defender for Endpoint.</span></span> <span data-ttu-id="f095e-127">그런 다음 기존 끝점 보호 솔루션을 제거하고 끝점용 Defender가 제대로 작동하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-127">Then, you uninstall your existing endpoint protection solution and make sure that Defender for Endpoint working correctly.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="f095e-128">끝점용 Microsoft Defender에는 무엇이 포함되어 있나요?</span><span class="sxs-lookup"><span data-stu-id="f095e-128">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="f095e-129">이 마이그레이션 가이드에서는 엔드포인트용 Defender로 이동하기 위한 시작점으로 차세대 보호 및 끝점 감지 및 응답 기능에 중점을 두고 있습니다. [](microsoft-defender-antivirus-in-windows-10.md) [](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="f095e-129">In this migration guide, we focus on [next-generation protection](microsoft-defender-antivirus-in-windows-10.md) and [endpoint detection and response](overview-endpoint-detection-response.md) capabilities as a starting point for moving to Defender for Endpoint.</span></span> <span data-ttu-id="f095e-130">그러나 Endpoint용 Defender에는 바이러스 백신 및 끝점 보호보다 훨씬 더 많은 보호가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-130">However, Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="f095e-131">Endpoint용 Defender는 예방적 보호, 위반 후 감지, 자동화된 조사 및 대응을 위한 통합 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-131">Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="f095e-132">다음 표에는 끝점용 Defender의 기능이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-132">The following table summarizes features and capabilities in Defender for Endpoint.</span></span> 

| <span data-ttu-id="f095e-133">기능/기능</span><span class="sxs-lookup"><span data-stu-id="f095e-133">Feature/Capability</span></span> | <span data-ttu-id="f095e-134">설명</span><span class="sxs-lookup"><span data-stu-id="f095e-134">Description</span></span> |
|---|---|
| [<span data-ttu-id="f095e-135">위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="f095e-135">Threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md) | <span data-ttu-id="f095e-136">위협 & 취약성 관리 기능은 끝점(예: 장치)에서 약점을 식별, 평가 및 수정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-136">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="f095e-137">공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="f095e-137">Attack surface reduction</span></span>](overview-attack-surface-reduction.md) | <span data-ttu-id="f095e-138">공격 표면 감소 규칙은 사이버 위협 및 공격으로부터 조직의 장치 및 응용 프로그램을 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-138">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="f095e-139">차세대 보호</span><span class="sxs-lookup"><span data-stu-id="f095e-139">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md) | <span data-ttu-id="f095e-140">차세대 보호에는 위협 Microsoft Defender 바이러스 백신 맬웨어를 차단하는 데 도움이 되는 여러 가지 기능도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-140">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="f095e-141">엔드포인트 검색 및 대응</span><span class="sxs-lookup"><span data-stu-id="f095e-141">Endpoint detection and response</span></span>](overview-endpoint-detection-response.md) | <span data-ttu-id="f095e-142">끝점 감지 및 응답 기능은 침입 시도 및 활성 위반을 감지, 조사 및 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-142">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="f095e-143">지능형 헌팅</span><span class="sxs-lookup"><span data-stu-id="f095e-143">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="f095e-144">고급 헌팅 기능을 통해 보안 운영 팀은 알려진 위협 또는 잠재적인 위협의 지표와 엔터티를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-144">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="f095e-145">동작 차단 및 제약</span><span class="sxs-lookup"><span data-stu-id="f095e-145">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md) | <span data-ttu-id="f095e-146">동작 차단 및 포함 기능은 위협이 실행을 시작한 경우에도 동작 및 처리 트리를 기반으로 위협을 식별하고 중지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-146">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="f095e-147">자동화된 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="f095e-147">Automated investigation and remediation</span></span>](automated-investigations.md) | <span data-ttu-id="f095e-148">자동화된 조사 및 대응 기능은 경고를 검사하고 위반을 해결하기 위해 즉시 수정 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-148">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="f095e-149">[위협 헌팅](microsoft-threat-experts.md) 서비스(Microsoft 위협 전문가)</span><span class="sxs-lookup"><span data-stu-id="f095e-149">[Threat hunting service](microsoft-threat-experts.md) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="f095e-150">위협 헌팅 서비스는 보안 운영 팀에 전문가 수준의 모니터링 및 분석을 제공하고 중요한 위협이 누락되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f095e-150">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="f095e-151">**자세한 내용을 원하세요? [끝점에 대한 Defender를 참조합니다.](microsoft-defender-endpoint.md)**</span><span class="sxs-lookup"><span data-stu-id="f095e-151">**Want to learn more? See [Defender for Endpoint](microsoft-defender-endpoint.md).**</span></span>

## <a name="next-step"></a><span data-ttu-id="f095e-152">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f095e-152">Next step</span></span>

- <span data-ttu-id="f095e-153">마이그레이션 [준비로 진행합니다.](switch-to-microsoft-defender-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="f095e-153">Proceed to [Prepare for your migration](switch-to-microsoft-defender-prepare.md).</span></span>
