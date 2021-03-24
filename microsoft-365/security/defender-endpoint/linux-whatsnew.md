---
title: Linux용 끝점용 Microsoft Defender의 새로운
description: Linux용 Microsoft Defender ATP에 대한 주요 변경 사항 목록입니다.
keywords: microsoft, defender, atp, linux, whatsnew, release
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
ms.openlocfilehash: 43324b0f3a0d5d351d7164bb05415899bf7d181c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070487"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="c6c99-104">Linux용 끝점용 Microsoft Defender의 새로운</span><span class="sxs-lookup"><span data-stu-id="c6c99-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1011853"></a><span data-ttu-id="c6c99-105">101.18.53</span><span class="sxs-lookup"><span data-stu-id="c6c99-105">101.18.53</span></span>

- <span data-ttu-id="c6c99-106">Linux용 EDR은 이제 일반적으로 [사용할 수 있습니다.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="c6c99-106">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="c6c99-107">사용자 지정 검사 중에 AV 제외를 무시하는 새 명령줄 스위치()가 `--ignore-exclusions` 추가되었습니다. `mdatp scan custom`</span><span class="sxs-lookup"><span data-stu-id="c6c99-107">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="c6c99-108">진단 로그를 다른 디렉터리에 저장할 수 있도록 하는 새 매개 변수()로 `mdatp diagnostic create` `--path [directory]` 확장</span><span class="sxs-lookup"><span data-stu-id="c6c99-108">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="c6c99-109">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="c6c99-109">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="c6c99-110">101.12.99</span><span class="sxs-lookup"><span data-stu-id="c6c99-110">101.12.99</span></span>

- <span data-ttu-id="c6c99-111">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="c6c99-111">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="c6c99-112">101.04.76</span><span class="sxs-lookup"><span data-stu-id="c6c99-112">101.04.76</span></span>

- <span data-ttu-id="c6c99-113">버그 수정</span><span class="sxs-lookup"><span data-stu-id="c6c99-113">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="c6c99-114">101.03.48</span><span class="sxs-lookup"><span data-stu-id="c6c99-114">101.03.48</span></span>

- <span data-ttu-id="c6c99-115">버그 수정</span><span class="sxs-lookup"><span data-stu-id="c6c99-115">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="c6c99-116">101.02.55</span><span class="sxs-lookup"><span data-stu-id="c6c99-116">101.02.55</span></span>

- <span data-ttu-id="c6c99-117">제품이 때때로 재부팅/업그레이드 후 시작되지 않는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c99-117">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="c6c99-118">제품 업그레이드에서 프록시 설정이 유지되지 않는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c99-118">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="c6c99-119">101.00.75</span><span class="sxs-lookup"><span data-stu-id="c6c99-119">101.00.75</span></span>

- <span data-ttu-id="c6c99-120">, , , , , , , , , , 및 파일 시스템 유형에 대한 `ecryptfs` `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` 지원이 추가되었습니다. `vfat`</span><span class="sxs-lookup"><span data-stu-id="c6c99-120">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="c6c99-121">명령줄 도구에 대한 새 [구문입니다.](linux-resources.md#configure-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="c6c99-121">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="c6c99-122">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="c6c99-122">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="c6c99-123">100.90.70</span><span class="sxs-lookup"><span data-stu-id="c6c99-123">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="c6c99-124">설치된 패키지를 100.90.70 이전 제품 버전에서 업그레이드하는 경우 Red Hat 기반 및 SLES 배포에서 업데이트가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c99-124">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="c6c99-125">이는 파일 경로가 대대적인 변경된 것이기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="c6c99-125">This is because of a major change in a file path.</span></span> <span data-ttu-id="c6c99-126">임시 솔루션은 이전 패키지를 제거한 다음 새 패키지를 설치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c6c99-126">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="c6c99-127">이 문제는 최신 버전에 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c99-127">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="c6c99-128">바이러스 [백신 제외에서 와일드카드 지원](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="c6c99-128">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="c6c99-129">명령줄 도구를 [통해](linux-support-perf.md) 성능 문제를 해결하는 `mdatp` 기능을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c99-129">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="c6c99-130">패키지 설치를 보다 강력하게 만들기 위한 개선된 기능</span><span class="sxs-lookup"><span data-stu-id="c6c99-130">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="c6c99-131">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="c6c99-131">Performance improvements & bug fixes</span></span>
