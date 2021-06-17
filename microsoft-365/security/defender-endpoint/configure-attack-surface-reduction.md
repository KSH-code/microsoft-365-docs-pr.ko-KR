---
title: 공격 표면 감소 기능 구성
description: 공격 Microsoft Intune, Microsoft Endpoint Configuration Manager, PowerShell cmdlet 및 그룹 정책을 사용하여 공격 표면 감소를 구성합니다.
keywords: asr, 공격 표면 감소, windows defender, microsoft defender, 바이러스 백신, av
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 948b5dc201526bf54aae0e857cfd40dcc9fe1e19
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984451"
---
# <a name="configure-attack-surface-reduction-capabilities"></a><span data-ttu-id="51b51-104">공격 표면 감소 기능 구성</span><span class="sxs-lookup"><span data-stu-id="51b51-104">Configure attack surface reduction capabilities</span></span>

<span data-ttu-id="51b51-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="51b51-105">**Applies to:**</span></span>

- [<span data-ttu-id="51b51-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="51b51-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="51b51-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51b51-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="51b51-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="51b51-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="51b51-109">[무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="51b51-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="51b51-110">Endpoint용 Defender에는 여러 공격 표면 감소 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b51-110">Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="51b51-111">자세한 내용은 공격 표면 감소 [기능 개요를 참조하세요.](overview-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="51b51-111">To learn more, see [Overview of attack surface reduction capabilities](overview-attack-surface-reduction.md).</span></span> <span data-ttu-id="51b51-112">사용자 환경에서 공격 표면 감소를 구성하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="51b51-112">To configure attack surface reduction in your environment, follow these steps:</span></span>

1. <span data-ttu-id="51b51-113">[에 대해](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)하드웨어 기반 Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="51b51-113">[Enable hardware-based isolation for Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span></span>

2. <span data-ttu-id="51b51-114">응용 프로그램 제어를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="51b51-114">Enable application control.</span></span>

   1. <span data-ttu-id="51b51-115">기본 정책은 Windows.</span><span class="sxs-lookup"><span data-stu-id="51b51-115">Review base policies in Windows.</span></span> <span data-ttu-id="51b51-116">예제 [기본 정책 을 참조합니다.](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)</span><span class="sxs-lookup"><span data-stu-id="51b51-116">See [Example Base Policies](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).</span></span>
   2. <span data-ttu-id="51b51-117">응용 [Windows Defender 디자인 가이드를 참조하세요.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)</span><span class="sxs-lookup"><span data-stu-id="51b51-117">See the [Windows Defender Application Control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).</span></span>
   3. <span data-ttu-id="51b51-118">[WDAC(응용 Windows Defender) 정책 배포를 참조합니다.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)</span><span class="sxs-lookup"><span data-stu-id="51b51-118">Refer to [Deploying Windows Defender Application Control (WDAC) policies](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).</span></span>

3. <span data-ttu-id="51b51-119">[제어된 폴더 액세스를 사용하도록 설정 .](enable-controlled-folders.md)</span><span class="sxs-lookup"><span data-stu-id="51b51-119">[Enable controlled folder access](enable-controlled-folders.md).</span></span>

4. <span data-ttu-id="51b51-120">[네트워크 보호 켜기.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="51b51-120">[Turn on Network protection](enable-network-protection.md).</span></span>

5. <span data-ttu-id="51b51-121">[Exploit Protection을 사용하도록 설정](enable-exploit-protection.md).</span><span class="sxs-lookup"><span data-stu-id="51b51-121">[Enable exploit protection](enable-exploit-protection.md).</span></span>

6. <span data-ttu-id="51b51-122">[공격 표면 축소 규칙을 구성합니다.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="51b51-122">[Configure attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

7. <span data-ttu-id="51b51-123">네트워크 방화벽을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="51b51-123">Set up your network firewall.</span></span>

   1. <span data-ttu-id="51b51-124">고급 보안이 [있는 Windows Defender 방화벽에 대한 개요를 얻습니다.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)</span><span class="sxs-lookup"><span data-stu-id="51b51-124">Get an overview of [Windows Defender Firewall with advanced security](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span>
   2. <span data-ttu-id="51b51-125">방화벽 Windows Defender 디자인 [가이드를](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) 사용하여 방화벽 정책을 디자인할 방법을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b51-125">Use the [Windows Defender Firewall design guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) to decide how you want to design your firewall policies.</span></span>
   3. <span data-ttu-id="51b51-126">고급 [Windows Defender](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) 방화벽 배포 가이드를 사용하여 조직의 방화벽을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b51-126">Use the [Windows Defender Firewall deployment guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) to set up your organization's firewall with advanced security.</span></span>

> [!TIP]
> <span data-ttu-id="51b51-127">대부분의 경우 공격 표면 감소 기능을 구성할 때 다음 여러 방법 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b51-127">In most cases, when you configure attack surface reduction capabilities, you can choose from among several methods:</span></span>

> - <span data-ttu-id="51b51-128">Microsoft Endpoint Manager(현재 Microsoft Intune 및 Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="51b51-128">Microsoft Endpoint Manager (which now includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
> - <span data-ttu-id="51b51-129">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="51b51-129">Group Policy</span></span>
> - <span data-ttu-id="51b51-130">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="51b51-130">PowerShell cmdlets</span></span>
