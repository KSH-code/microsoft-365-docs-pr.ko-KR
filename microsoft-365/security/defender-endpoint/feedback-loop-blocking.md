---
title: 피드백-루프 차단
description: 신속한 보호라고도 하는 피드백 루프 차단은 끝점용 Microsoft Defender의 동작 차단 및 포함 기능의 일부입니다.
keywords: 동작 차단, 신속한 보호, 피드백 차단, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: 7319ff5a89a20529eed7d36aa0d0b1522013abd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842461"
---
# <a name="feedback-loop-blocking"></a><span data-ttu-id="36ea0-104">피드백-루프 차단</span><span class="sxs-lookup"><span data-stu-id="36ea0-104">Feedback-loop blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="36ea0-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="36ea0-105">**Applies to:**</span></span>
- [<span data-ttu-id="36ea0-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="36ea0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a><span data-ttu-id="36ea0-107">개요</span><span class="sxs-lookup"><span data-stu-id="36ea0-107">Overview</span></span>

<span data-ttu-id="36ea0-108">피드백 루프 차단은 신속한 보호라고도 하는 Microsoft [](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) [Defender for Endpoint의](/windows/security/threat-protection/)동작 차단 및 포함 기능의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="36ea0-108">Feedback-loop blocking, also referred to as rapid protection, is a component of [behavioral blocking and containment capabilities](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in [Microsoft Defender for Endpoint](/windows/security/threat-protection/).</span></span> <span data-ttu-id="36ea0-109">피드백 루프 차단을 통해 조직 전체의 장치를 공격으로부터 더 잘 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36ea0-109">With feedback-loop blocking, devices across your organization are better protected from attacks.</span></span> 

## <a name="how-feedback-loop-blocking-works"></a><span data-ttu-id="36ea0-110">피드백 루프 차단의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="36ea0-110">How feedback-loop blocking works</span></span>

<span data-ttu-id="36ea0-111">에 의해 의심스러운 동작이나 파일이 Microsoft Defender 바이러스 백신 [경우](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)해당 아티팩트에 대한 정보가 여러 분류자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="36ea0-111">When a suspicious behavior or file is detected, such as by [Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), information about that artifact is sent to multiple classifiers.</span></span> <span data-ttu-id="36ea0-112">신속한 보호 루프 엔진은 파일을 차단할지 여부에 대한 결정을 내리기 위해 정보를 다른 신호와 검사하고 관련합니다.</span><span class="sxs-lookup"><span data-stu-id="36ea0-112">The rapid protection loop engine inspects and correlates the information with other signals to arrive at a decision as to whether to block a file.</span></span> <span data-ttu-id="36ea0-113">아티팩트 확인 및 분류는 빠르게 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="36ea0-113">Checking and classifying artifacts happens quickly.</span></span> <span data-ttu-id="36ea0-114">확인된 맬웨어를 신속히 차단하고 전체 에코시스템을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="36ea0-114">It results in rapid blocking of confirmed malware, and drives protection across the entire ecosystem.</span></span> 

<span data-ttu-id="36ea0-115">신속한 보호를 통해 공격의 발판을 넓히기 위한 공격으로 장치, 조직의 다른 장치 및 다른 조직의 디바이스에서 공격을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36ea0-115">With rapid protection in place, an attack can be stopped on a device, other devices in the organization, and devices in other organizations, as an attack attempts to broaden its foothold.</span></span>


## <a name="configuring-feedback-loop-blocking"></a><span data-ttu-id="36ea0-116">피드백 루프 차단 구성</span><span class="sxs-lookup"><span data-stu-id="36ea0-116">Configuring feedback-loop blocking</span></span>

<span data-ttu-id="36ea0-117">조직에서 끝점에 Defender를 사용하는 경우 피드백 루프 차단은 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="36ea0-117">If your organization is using Defender for Endpoint, feedback-loop blocking is enabled by default.</span></span> <span data-ttu-id="36ea0-118">그러나 신속한 보호는 끝점 기능에 대한 Defender 기능, 기계 학습 보호 기능 및 Microsoft 보안 서비스 전반의 신호 공유를 통해 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="36ea0-118">However, rapid protection occurs through a combination of Defender for Endpoint capabilities, machine learning protection features, and signal-sharing across Microsoft security services.</span></span> <span data-ttu-id="36ea0-119">끝점용 Defender의 다음 기능을 사용하도록 설정하고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36ea0-119">Make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="36ea0-120">끝점 기준에 대한 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="36ea0-120">Microsoft Defender for Endpoint baselines</span></span>](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="36ea0-121">끝점용 Microsoft Defender에 온보딩된 장치</span><span class="sxs-lookup"><span data-stu-id="36ea0-121">Devices onboarded to Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="36ea0-122">차단 모드의 EDR</span><span class="sxs-lookup"><span data-stu-id="36ea0-122">EDR in block mode</span></span>](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="36ea0-123">공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="36ea0-123">Attack surface reduction</span></span>](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="36ea0-124">[차세대 보호(바이러스](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) 백신)</span><span class="sxs-lookup"><span data-stu-id="36ea0-124">[Next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="36ea0-125">관련 문서</span><span class="sxs-lookup"><span data-stu-id="36ea0-125">Related articles</span></span>

- [<span data-ttu-id="36ea0-126">동작 차단 및 제약</span><span class="sxs-lookup"><span data-stu-id="36ea0-126">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="36ea0-127">(블로그) 동작 차단 및 포함: 광학을 보호로 변환</span><span class="sxs-lookup"><span data-stu-id="36ea0-127">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="36ea0-128">엔드포인트 리소스에 대한 유용한 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="36ea0-128">Helpful Microsoft Defender for Endpoint resources</span></span>](/microsoft-365/security/defender-endpoint/helpful-resources)
