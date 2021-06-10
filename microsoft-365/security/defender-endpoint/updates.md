---
title: Microsoft Defender 업데이트에 대한 서진적 출시 프로세스 관리
description: 서진 업데이트 프로세스 및 컨트롤에 대한 자세한 정보
keywords: 업데이트, 업데이트 프로세스, 컨트롤, 릴리스
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 435a77432caa9d7335a22993f85cae69eff6cd38
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52862033"
---
#  <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a><span data-ttu-id="d1a8e-104">Microsoft Defender 업데이트에 대한 서진적 출시 프로세스 관리</span><span class="sxs-lookup"><span data-stu-id="d1a8e-104">Manage the gradual rollout process for Microsoft Defender updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d1a8e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d1a8e-105">**Applies to:**</span></span>

- [<span data-ttu-id="d1a8e-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d1a8e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


<span data-ttu-id="d1a8e-107">중요한 보호 기능을 전달하고 공격을 방지하기 위해 클라이언트 구성 요소를 최신으로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-107">It is important to ensure that client components are up-to-date to deliver critical protection capabilities and prevent attacks.</span></span>

<span data-ttu-id="d1a8e-108">기능은 여러 구성 요소를 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-108">Capabilities are provided through several components:</span></span> 

- [<span data-ttu-id="d1a8e-109">끝점 검색 & 응답</span><span class="sxs-lookup"><span data-stu-id="d1a8e-109">Endpoint Detection & Response</span></span>](overview-endpoint-detection-response.md) 
- <span data-ttu-id="d1a8e-110">[클라우드 제공 보호를](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection) 통해 [차세대 보호](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-110">[Next-generation protection](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection) with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md)</span></span> 
- [<span data-ttu-id="d1a8e-111">공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="d1a8e-111">Attack Surface Reduction</span></span>](overview-attack-surface-reduction.md)

<span data-ttu-id="d1a8e-112">업데이트는 서진 릴리스 프로세스를 사용하여 월별 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-112">Updates are released monthly using a gradual release process.</span></span> <span data-ttu-id="d1a8e-113">이 프로세스는 조기 오류 검색이 발생할 때 영향을 catch하고 더 큰 롤아웃 전에 빠르게 해결할 수 있도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-113">This process helps to enable early failure detection to catch impact as it occurs and address it quickly before a larger rollout.</span></span> 

> [!NOTE]
> <span data-ttu-id="d1a8e-114">일별 정의 업데이트를 제어하는 방법에 대한 자세한 내용은 일정 Microsoft Defender 바이러스 백신 정의 업데이트 - Windows [보안 업데이트를 | Microsoft Docs.](manage-protection-update-schedule-microsoft-defender-antivirus.md) 정의 업데이트는 클라우드 제공 보호를 끝점에서 사용할 수 없는 경우에도 차세대 보호가 새로운 위협으로부터 보호할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-114">For more information on how to control daily definition updates, see [Schedule Microsoft Defender Antivirus definition updates - Windows security | Microsoft Docs](manage-protection-update-schedule-microsoft-defender-antivirus.md). Definition updates ensure that next-generation protection can defend against new threats, even if cloud-delivered protection is not available to the endpoint.</span></span>

## <a name="microsoft-gradual-rollout-model"></a><span data-ttu-id="d1a8e-115">Microsoft의 서진적 출시 모델</span><span class="sxs-lookup"><span data-stu-id="d1a8e-115">Microsoft gradual rollout model</span></span>

<span data-ttu-id="d1a8e-116">다음과 같은 단계적 출시 모델이 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-116">The following gradual rollout model is followed:</span></span>

1. <span data-ttu-id="d1a8e-117">첫 번째 릴리스는 베타 채널 구독자에게 공개됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-117">The first release goes out to Beta channel subscribers.</span></span>
2. <span data-ttu-id="d1a8e-118">유효성 검사, 피드백 및 수정 후 제한된 방식으로 먼저 미리 보기 채널 구독자에게 서서한 롤아웃 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-118">After validation, feedback, and fixes, we start the gradual rollout process in a throttled way and to Preview channel subscribers first.</span></span>
3. <span data-ttu-id="d1a8e-119">그런 다음 나머지 전역 인구에 대한 업데이트를 계속 릴리스하여 10~100%로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-119">We then proceed to release the update to the rest of the global population, scaling out from 10-100%.</span></span>

<span data-ttu-id="d1a8e-120">엔지니어는 지속적으로 영향을 모니터링하고 문제를 에스컬레이터하여 필요한 경우 수정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-120">Our engineers continuously monitor impact and escalate any issues to create a fix as needed.</span></span>

## <a name="how-to-customize-your-internal-deployment-process"></a><span data-ttu-id="d1a8e-121">내부 배포 프로세스를 사용자 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="d1a8e-121">How to customize your internal deployment process</span></span>

<span data-ttu-id="d1a8e-122">컴퓨터는 Windows 업데이트에서 Defender 업데이트를 수신하는 경우 일부 컴퓨터는 다른 컴퓨터보다 더 빨리 Defender 업데이트를 수신하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-122">If your machines are receiving Defender updates from Windows Update, the gradual rollout process may result in some of your machines receiving Defender updates sooner than others.</span></span> <span data-ttu-id="d1a8e-123">다음 섹션에서는 업데이트 채널 구성을 활용하여 자동 업데이트가 특정 장치 그룹으로 다르게 흐를 수 있도록 하는 전략을 정의하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-123">The following section explains how to define a strategy that will allow automatic updates to flow differently to specific groups of devices by leveraging update channel configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="d1a8e-124">자체의 단계적 릴리스를 계획할 때 미리 보기 및 미리 보기 채널에 구독된 디바이스를 항상 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-124">When planning for your own gradual release, please make sure to always have a selection of devices subscribed to the preview and staged channels.</span></span> <span data-ttu-id="d1a8e-125">이렇게 하면 조직뿐만 아니라 Microsoft도 사용자 환경과 관련한 문제를 방지하거나 찾아 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-125">This will provide your organization as well as Microsoft the opportunity to prevent or find and fix issues specific to your environment.</span></span>

<span data-ttu-id="d1a8e-126">WSUS(Windows Server Update Services) 또는 MECM(Microsoft Endpoint Configuration Manager)과 같은 업데이트를 받는 컴퓨터의 경우 끝점용 Microsoft Defender 옵션을 포함하여 모든 Windows 업데이트에 더 많은 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-126">For machines receiving updates through, for example, Windows Server Update Services (WSUS) or Microsoft Endpoint Configuration Manager (MECM), more options are available to all Windows updates, including options  for Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="d1a8e-127">WSUS, MECM과 같은 솔루션을 사용하여 업데이트 배포 및 응용 프로그램을 관리하는 방법에 대한 자세한 내용은 [Manage Microsoft Defender 바이러스 백신 updates and apply baselines - Windows security | Microsoft Docs.](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-127">Read more about how to use a solution like WSUS, MECM to manage the distribution and application of updates at [Manage Microsoft Defender Antivirus updates and apply baselines - Windows security | Microsoft Docs](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates).</span></span>

## <a name="update-channels-for-monthly-updates"></a><span data-ttu-id="d1a8e-128">월별 업데이트 채널 업데이트</span><span class="sxs-lookup"><span data-stu-id="d1a8e-128">Update channels for monthly updates</span></span>

<span data-ttu-id="d1a8e-129">업데이트 채널에 컴퓨터 할당을 통해 컴퓨터는 월별 엔진 및 플랫폼 업데이트를 받는 케이던스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-129">You can assign a machine to an update channel to define the cadence in which a machine receives monthly engine and platform updates.</span></span>

<span data-ttu-id="d1a8e-130">업데이트를 구성하는 방법에 대한 자세한 내용은 Microsoft Defender 업데이트에 대한 사용자 지정점적 출시 프로세스 [만들기를 참조하세요.](configure-updates.md)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-130">For more information on how to configure updates, see [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).</span></span>

<span data-ttu-id="d1a8e-131">다음 업데이트 채널을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-131">The following update channels are available:</span></span>

| <span data-ttu-id="d1a8e-132">채널 이름</span><span class="sxs-lookup"><span data-stu-id="d1a8e-132">Channel name</span></span>  | <span data-ttu-id="d1a8e-133">설명</span><span class="sxs-lookup"><span data-stu-id="d1a8e-133">Description</span></span>  | <span data-ttu-id="d1a8e-134">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d1a8e-134">Application</span></span>  |
|-|-|-|
| <span data-ttu-id="d1a8e-135">베타 채널 - 시험 출시</span><span class="sxs-lookup"><span data-stu-id="d1a8e-135">Beta Channel - Prerelease</span></span>  | <span data-ttu-id="d1a8e-136">다른 사람 앞에 업데이트 테스트</span><span class="sxs-lookup"><span data-stu-id="d1a8e-136">Test updates before others</span></span>  | <span data-ttu-id="d1a8e-137">이 채널로 설정된 장치는 새 월별 업데이트를 수신하는 첫 번째 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-137">Devices set to this channel will be the first to receive new monthly updates.</span></span> <span data-ttu-id="d1a8e-138">베타 채널을 선택하여 문제를 식별하고 Microsoft에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-138">Select Beta Channel to participate in identifying and reporting issues to Microsoft.</span></span> <span data-ttu-id="d1a8e-139">Windows 프로그램의 장치는 기본적으로 이 채널을 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-139">Devices in the Windows Insider Program are subscribed to this channel by default.</span></span> <span data-ttu-id="d1a8e-140">테스트 환경에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-140">For use in test environments only.</span></span>  |
| <span data-ttu-id="d1a8e-141">현재 채널(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-141">Current Channel (Preview)</span></span>  | <span data-ttu-id="d1a8e-142">서서한 **릴리스의** 이전 현재 채널 업데이트 다운로드</span><span class="sxs-lookup"><span data-stu-id="d1a8e-142">Get Current Channel updates **earlier** during gradual release</span></span>  | <span data-ttu-id="d1a8e-143">이 채널로 설정된 장치는 서서한 릴리스 주기 동안 가장 빠른 시기에 업데이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-143">Devices set to this channel will be offered updates earliest during the gradual release cycle.</span></span> <span data-ttu-id="d1a8e-144">프로덕션 전/유효성 검사 환경에 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-144">Suggested for pre-production/validation environments.</span></span>  |
| <span data-ttu-id="d1a8e-145">현재 채널(단계적)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-145">Current Channel (Staged)</span></span>  | <span data-ttu-id="d1a8e-146">나중에 서서한 릴리스 동안 현재 채널 업데이트 다운로드</span><span class="sxs-lookup"><span data-stu-id="d1a8e-146">Get Current Channel updates later during gradual release</span></span>  | <span data-ttu-id="d1a8e-147">디바이스는 나중에 서서한 릴리스 주기 동안 업데이트가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-147">Devices will be offered updates later during the gradual release cycle.</span></span> <span data-ttu-id="d1a8e-148">디바이스 인구의 대표적인 소규모 부분에 적용하는 것이 좋습니다(~10%).</span><span class="sxs-lookup"><span data-stu-id="d1a8e-148">Suggested to apply to a small, representative part of your device population (~10%).</span></span>  |
| <span data-ttu-id="d1a8e-149">현재 채널(광범위)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-149">Current Channel (Broad)</span></span> | <span data-ttu-id="d1a8e-150">서서한 릴리스가 끝날 때 업데이트 다운로드</span><span class="sxs-lookup"><span data-stu-id="d1a8e-150">Get updates at the end of gradual release</span></span>  | <span data-ttu-id="d1a8e-151">디바이스는 서서한 릴리스 주기가 완료된 후에만 업데이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-151">Devices will be offered updates only after the gradual release cycle completes.</span></span> <span data-ttu-id="d1a8e-152">프로덕션 인구의 광범위한 디바이스 집합(~10-100%)에 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-152">Suggested to apply to a broad set of devices in your production population (~10-100%).</span></span>  |
| <span data-ttu-id="d1a8e-153">기본값</span><span class="sxs-lookup"><span data-stu-id="d1a8e-153">(default)</span></span>  |   | <span data-ttu-id="d1a8e-154">해당 정책을 사용하지 않도록 설정하거나 구성하지 않는 경우 장치는 현재 채널(기본값)에 남아 있습니다. 서서히 릴리스 주기 동안 자동으로 최신 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-154">If you disable or do not configure this policy, the device will remain in Current Channel (Default): Stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="d1a8e-155">대부분의 장치에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-155">Suitable for most devices.</span></span>  |

### <a name="update-channels-for-daily-definition-updates"></a><span data-ttu-id="d1a8e-156">일별 정의 업데이트 채널 업데이트</span><span class="sxs-lookup"><span data-stu-id="d1a8e-156">Update channels for daily definition updates</span></span>

<span data-ttu-id="d1a8e-157">업데이트 채널에 컴퓨터 할당을 통해 컴퓨터의 일별 정의 업데이트를 받는 케이던스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-157">You can assign a machine to an update channel to define the cadence in which a machine receives daily definition updates.</span></span>
  
| <span data-ttu-id="d1a8e-158">채널 이름</span><span class="sxs-lookup"><span data-stu-id="d1a8e-158">Channel name</span></span>  | <span data-ttu-id="d1a8e-159">설명</span><span class="sxs-lookup"><span data-stu-id="d1a8e-159">Description</span></span>  | <span data-ttu-id="d1a8e-160">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d1a8e-160">Application</span></span>  |
|-|-|-|
| <span data-ttu-id="d1a8e-161">현재 채널(단계적)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-161">Current Channel (Staged)</span></span>  | <span data-ttu-id="d1a8e-162">나중에 서서한 릴리스 동안 현재 채널 업데이트 다운로드</span><span class="sxs-lookup"><span data-stu-id="d1a8e-162">Get Current Channel updates later during gradual release</span></span>  | <span data-ttu-id="d1a8e-163">디바이스는 나중에 서서한 릴리스 주기 동안 업데이트가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-163">Devices will be offered updates later during the gradual release cycle.</span></span> <span data-ttu-id="d1a8e-164">디바이스 인구의 대표적인 소규모 부분에 적용하는 것이 좋습니다(~10%).</span><span class="sxs-lookup"><span data-stu-id="d1a8e-164">Suggested to apply to a small, representative part of your device population (~10%).</span></span>  |
| <span data-ttu-id="d1a8e-165">현재 채널(광범위)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-165">Current Channel (Broad)</span></span> | <span data-ttu-id="d1a8e-166">서서한 릴리스가 끝날 때 업데이트 다운로드</span><span class="sxs-lookup"><span data-stu-id="d1a8e-166">Get updates at the end of gradual release</span></span>  | <span data-ttu-id="d1a8e-167">디바이스는 서서한 릴리스 주기 후 업데이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-167">Devices will be offered updates after the gradual release cycle.</span></span> <span data-ttu-id="d1a8e-168">제한된 업데이트만 수신하는 데이터 센터 머신에 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-168">Best for datacenter machines that only receive limited updates.</span></span> <span data-ttu-id="d1a8e-169">참고: 이 설정은 모든 Defender 업데이트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-169">Note: this setting applies to all Defender updates.</span></span>  |
| <span data-ttu-id="d1a8e-170">기본값</span><span class="sxs-lookup"><span data-stu-id="d1a8e-170">(default)</span></span>  |   | <span data-ttu-id="d1a8e-171">해당 정책을 사용하지 않도록 설정하거나 구성하지 않는 경우 장치는 현재 채널(기본값)에 남아 있습니다. 서서히 릴리스 주기 동안 자동으로 최신 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-171">If you disable or do not configure this policy, the device will remain in Current Channel (Default): Stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="d1a8e-172">대부분의 장치에 적합</span><span class="sxs-lookup"><span data-stu-id="d1a8e-172">Suitable for most devices</span></span>  |

> [!NOTE]
> <span data-ttu-id="d1a8e-173">시간 지연을 활용하는 대신 최신 서명을 강제로 업데이트하려면 먼저 이 정책을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-173">In case you wish to force an update to the newest signature instead of leveraging the time delay, you will need to remove this policy first.</span></span>

## <a name="update-guidance"></a><span data-ttu-id="d1a8e-174">업데이트 지침</span><span class="sxs-lookup"><span data-stu-id="d1a8e-174">Update guidance</span></span>

<span data-ttu-id="d1a8e-175">대부분의 경우 Windows 업데이트 사용 시 권장되는 구성은 끝점이 도착할 때 월별 Defender 업데이트를 수신하고 적용할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-175">In most cases, the recommended configuration when using Windows Update is to allow endpoints to receive and apply monthly Defender updates as they arrive.</span></span> <span data-ttu-id="d1a8e-176">이렇게 하면 보호와 적용될 수 있는 변경 내용과 관련된 가능한 영향 간의 최상의 균형을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-176">This provides the best balance between protection and possible impact associated with the changes they can introduce.</span></span>

<span data-ttu-id="d1a8e-177">자동 Defender 업데이트의 보다 제어된 단계적 배포가 필요한 환경에서는 배포 그룹을 사용할 수 있는 방법을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-177">For environments where there is a need for a more controlled gradual rollout of automatic Defender updates, consider an approach with deployment groups:</span></span>

1. <span data-ttu-id="d1a8e-178">베타 Windows 프로그램에 참여하거나 디바이스 그룹을 베타 채널에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-178">Participate in the Windows Insider program or assign a group of devices to the Beta Channel.</span></span>
2. <span data-ttu-id="d1a8e-179">미리 보기 채널(일반적으로 유효성 검사 환경)에 옵트인(opt in)하는 파일럿 그룹을 지정하여 새 업데이트를 조기에 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-179">Designate a pilot group that opts-in to Preview Channel, typically validation environments, to receive new updates early.</span></span>
3. <span data-ttu-id="d1a8e-180">단계적 채널의 단계적 출시 중에 나중에 업데이트를 받는 컴퓨터 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-180">Designate a group of machines that receive updates later during the gradual rollout from Staged channel.</span></span> <span data-ttu-id="d1a8e-181">일반적으로 이 개체는 인구의 10%를 대표하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-181">Typically, this would be a representative ~10% of the population.</span></span>
4. <span data-ttu-id="d1a8e-182">서서히 릴리스 주기가 완료된 후 업데이트를 받는 컴퓨터 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-182">Designate a group of machines that receive updates after the gradual release cycle completes.</span></span> <span data-ttu-id="d1a8e-183">이는 일반적으로 중요한 프로덕션 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-183">These are typically important production systems.</span></span>

<span data-ttu-id="d1a8e-184">나머지 장치의 경우 기본 설정은 Microsoft의 서서히 출시 프로세스 중에 도착할 때 새 업데이트를 수신하고 추가 구성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-184">For the remainder of devices, the default setting is to receive new updates as they arrive during the Microsoft gradual rollout process and no further configuration is required.</span></span> 

<span data-ttu-id="d1a8e-185">이 모델 채택:</span><span class="sxs-lookup"><span data-stu-id="d1a8e-185">Adopting this model:</span></span>
- <span data-ttu-id="d1a8e-186">프로덕션 환경에 도달하기 전에 초기 릴리스를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-186">Allows you to test early releases before they reach a production environment</span></span> 
- <span data-ttu-id="d1a8e-187">프로덕션 환경이 정기적인 업데이트를 계속 받는지 확인하여 중요한 위협으로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-187">Ensure the production environment still receives regular updates and ensure protection against critical threats.</span></span>

## <a name="management-tools"></a><span data-ttu-id="d1a8e-188">관리 도구</span><span class="sxs-lookup"><span data-stu-id="d1a8e-188">Management tools</span></span>
<span data-ttu-id="d1a8e-189">월별 업데이트에 대해 사용자 지정 서서히 출시 프로세스를 직접 만들 수 있는 도구는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a8e-189">To create your own custom gradual rollout process for monthly updates, you can use the following tools:</span></span>

- <span data-ttu-id="d1a8e-190">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="d1a8e-190">Group policy</span></span>
- <span data-ttu-id="d1a8e-191">Microsoft Endpoint Manager </span><span class="sxs-lookup"><span data-stu-id="d1a8e-191">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="d1a8e-192">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1a8e-192">PowerShell</span></span>

<span data-ttu-id="d1a8e-193">이러한 도구를 사용하는 방법에 대한 자세한 내용은 Microsoft Defender 업데이트에 대한 사용자 지정점적 출시 프로세스 [만들기를 참조하세요.](configure-updates.md)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-193">For details on how to use these tools, see [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).</span></span>
