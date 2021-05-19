---
title: Linux의 끝점용 Microsoft Defender의 새로운
description: Linux의 끝점용 Microsoft Defender에 대한 주요 변경 사항 목록입니다.
keywords: microsoft, defender, Endpoint용 Microsoft Defender, linux, whatsnew, release
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 21eaf1c0e0d3f61bb5798c8a4de6fe8f97ce4a0b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538798"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="92c8b-104">Linux의 끝점용 Microsoft Defender의 새로운</span><span class="sxs-lookup"><span data-stu-id="92c8b-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012964-30121042129640"></a><span data-ttu-id="92c8b-105">101.29.64 (30.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="92c8b-105">101.29.64 (30.121042.12964.0)</span></span>

- <span data-ttu-id="92c8b-106">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="92c8b-106">Performance improvements & bug fixes</span></span>

## <a name="1012572-30121022125630"></a><span data-ttu-id="92c8b-107">101.25.72 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="92c8b-107">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="92c8b-108">Linux의 끝점용 Microsoft Defender는 이제 미국 정부 고객을 위해 미리 보기에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c8b-108">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="92c8b-109">자세한 내용은 미국 정부 고객용 [끝점용 Microsoft Defender를 참조하세요.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="92c8b-109">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="92c8b-110">FUSE 파일 시스템과 함께 Linux에서 Endpoint용 Microsoft Defender를 OS 중단으로 이어지는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="92c8b-110">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="92c8b-111">기타 버그 & 개선</span><span class="sxs-lookup"><span data-stu-id="92c8b-111">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="92c8b-112">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="92c8b-112">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="92c8b-113">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="92c8b-113">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="92c8b-114">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="92c8b-114">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="92c8b-115">전체 탑재 지점이 바이러스 백신 제외 목록에 추가되는 상황에 대한 성능 향상.</span><span class="sxs-lookup"><span data-stu-id="92c8b-115">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="92c8b-116">이 버전 이전에는 탑재 지점에서 시작된 파일 활동이 제품에 의해 계속 처리되었습니다.</span><span class="sxs-lookup"><span data-stu-id="92c8b-116">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="92c8b-117">이 버전부터 제외된 탑재 지점에 대한 파일 활동이 억제되고 제품 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c8b-117">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="92c8b-118">마지막 명령줄 검사에 대한 정보를 볼 수 있는 새 옵션이 명령줄 도구에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="92c8b-118">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="92c8b-119">마지막 on-demand 검사에 대한 정보를 보기 위해 를 실행합니다. `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="92c8b-119">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="92c8b-120">버그 수정에 & 성능 향상</span><span class="sxs-lookup"><span data-stu-id="92c8b-120">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="92c8b-121">101.18.53</span><span class="sxs-lookup"><span data-stu-id="92c8b-121">101.18.53</span></span>

- <span data-ttu-id="92c8b-122">EDR Linux용 배포판을 이제 [일반적으로 사용할 수 있습니다.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="92c8b-122">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="92c8b-123">사용자 지정 검사 중에 AV 제외를 무시하는 새 명령줄 스위치()가 `--ignore-exclusions` 추가되었습니다. `mdatp scan custom`</span><span class="sxs-lookup"><span data-stu-id="92c8b-123">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="92c8b-124">진단 로그를 다른 디렉터리에 저장할 수 있도록 하는 새 매개 변수()로 `mdatp diagnostic create` `--path [directory]` 확장</span><span class="sxs-lookup"><span data-stu-id="92c8b-124">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="92c8b-125">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="92c8b-125">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="92c8b-126">101.12.99</span><span class="sxs-lookup"><span data-stu-id="92c8b-126">101.12.99</span></span>

- <span data-ttu-id="92c8b-127">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="92c8b-127">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="92c8b-128">101.04.76</span><span class="sxs-lookup"><span data-stu-id="92c8b-128">101.04.76</span></span>

- <span data-ttu-id="92c8b-129">버그 수정</span><span class="sxs-lookup"><span data-stu-id="92c8b-129">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="92c8b-130">101.03.48</span><span class="sxs-lookup"><span data-stu-id="92c8b-130">101.03.48</span></span>

- <span data-ttu-id="92c8b-131">버그 수정</span><span class="sxs-lookup"><span data-stu-id="92c8b-131">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="92c8b-132">101.02.55</span><span class="sxs-lookup"><span data-stu-id="92c8b-132">101.02.55</span></span>

- <span data-ttu-id="92c8b-133">제품이 때때로 재부팅/업그레이드 후 시작되지 않는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="92c8b-133">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="92c8b-134">제품 업그레이드에서 프록시 설정이 유지되지 않는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="92c8b-134">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="92c8b-135">101.00.75</span><span class="sxs-lookup"><span data-stu-id="92c8b-135">101.00.75</span></span>

- <span data-ttu-id="92c8b-136">, , , , , , , , , , 및 파일 시스템 유형에 대한 `ecryptfs` `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` 지원이 추가되었습니다. `vfat`</span><span class="sxs-lookup"><span data-stu-id="92c8b-136">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="92c8b-137">명령줄 도구에 대한 새 [구문입니다.](linux-resources.md#configure-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="92c8b-137">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="92c8b-138">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="92c8b-138">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="92c8b-139">100.90.70</span><span class="sxs-lookup"><span data-stu-id="92c8b-139">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="92c8b-140">설치된 패키지를 100.90.70 이전 제품 버전에서 업그레이드하는 경우 Red Hat 기반 및 SLES 배포에서 업데이트가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c8b-140">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="92c8b-141">이는 파일 경로가 대대적인 변경된 것이기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="92c8b-141">This is because of a major change in a file path.</span></span> <span data-ttu-id="92c8b-142">임시 솔루션은 이전 패키지를 제거한 다음 새 패키지를 설치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="92c8b-142">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="92c8b-143">이 문제는 최신 버전에 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92c8b-143">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="92c8b-144">바이러스 [백신 제외에서 와일드카드 지원](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="92c8b-144">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="92c8b-145">명령줄 도구를 [통해](linux-support-perf.md) 성능 문제를 해결하는 `mdatp` 기능을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="92c8b-145">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="92c8b-146">패키지 설치를 보다 강력하게 만들기 위한 개선된 기능</span><span class="sxs-lookup"><span data-stu-id="92c8b-146">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="92c8b-147">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="92c8b-147">Performance improvements & bug fixes</span></span>
