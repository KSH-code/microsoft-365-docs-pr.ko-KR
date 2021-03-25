---
title: Mac용 끝점용 Microsoft Defender의 새로운
description: Mac용 끝점용 Microsoft Defender의 이전 버전에 대한 주요 변경 내용에 대해 자세히 알아보습니다.
keywords: microsoft, defender, atp, mac, installation, macos, whatsnew
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
ms.openlocfilehash: f1cd2221ab07caeab341447ebd19824d7476fb52
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187377"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="622c1-104">Mac용 끝점용 Microsoft Defender의 새로운</span><span class="sxs-lookup"><span data-stu-id="622c1-104">What's new in Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="622c1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="622c1-105">**Applies to:**</span></span>
- [<span data-ttu-id="622c1-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="622c1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="622c1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="622c1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="622c1-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="622c1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="622c1-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="622c1-110">macOS 11(Big Sur)에서는 끝점용 Microsoft Defender에 추가 구성 프로필이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="622c1-111">이전 버전의 macOS에서 업그레이드하는 기존 고객인 경우 이 페이지에 나열된 추가 구성 프로필을 [배포해야 합니다.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="622c1-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="622c1-112">MacOS 10.13(High Sierra)에 대한 지원은 2021년 2월 15일부터 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-112">Support for macOS 10.13 (High Sierra) will be discontinued on February 15th, 2021.</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="622c1-113">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="622c1-113">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="622c1-114">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-114">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="622c1-115">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="622c1-115">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="622c1-116">이 릴리스에서는 이전 명령줄 도구 구문이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-116">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="622c1-117">새 구문에 대한 자세한 내용은 Resources 을 [참조하십시오.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="622c1-117">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="622c1-118">네트워크 확장을 사용하지 않도록 설정하는 새 명령줄 스위치가 `mdatp system-extension network-filter disable` 추가되었습니다. .</span><span class="sxs-lookup"><span data-stu-id="622c1-118">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="622c1-119">이 명령은 Mac용 끝점용 Microsoft Defender와 관련이 있을 수 있는 네트워킹 문제를 해결하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-119">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="622c1-120">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-120">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="622c1-121">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="622c1-121">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="622c1-122">버그 수정</span><span class="sxs-lookup"><span data-stu-id="622c1-122">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="622c1-123">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="622c1-123">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="622c1-124">macOS 11 Big Sur에서 실행될 때 에이전트의 안정성 향상</span><span class="sxs-lookup"><span data-stu-id="622c1-124">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="622c1-125">사용자 지정 검사 중에 AV 제외를 무시하는 새 명령줄 스위치()가 `--ignore-exclusions` 추가되었습니다. `mdatp scan custom`</span><span class="sxs-lookup"><span data-stu-id="622c1-125">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="622c1-126">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-126">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="622c1-127">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="622c1-127">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="622c1-128">끝점용 Microsoft Defender가 커널 창에 매니페스트되는 macOS 11(Big Sur) 버그를 트리거할 때 제거된 조건</span><span class="sxs-lookup"><span data-stu-id="622c1-128">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="622c1-129">Mac 11(Big Sur)에서 실행되는 경우 Endpoint 보안 시스템 확장의 메모리 누수 수정</span><span class="sxs-lookup"><span data-stu-id="622c1-129">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="622c1-130">버그 수정</span><span class="sxs-lookup"><span data-stu-id="622c1-130">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="622c1-131">101.10.72</span><span class="sxs-lookup"><span data-stu-id="622c1-131">101.10.72</span></span>

- <span data-ttu-id="622c1-132">버그 수정</span><span class="sxs-lookup"><span data-stu-id="622c1-132">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="622c1-133">101.09.61</span><span class="sxs-lookup"><span data-stu-id="622c1-133">101.09.61</span></span>

- <span data-ttu-id="622c1-134">피드백을 보내기 위한 옵션을 사용할 수 있도록 설정하기 위한 새로운 관리 기본 [설정이 추가되었습니다.](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="622c1-134">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="622c1-135">이제 상태 메뉴 아이콘은 제품 설정이 관리되는 경우 정상 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-135">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="622c1-136">이전에는 관리자가 제품 설정을 관리했어도 상태 메뉴 아이콘에 경고 또는 오류 상태가 표시했습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-136">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="622c1-137">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-137">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="622c1-138">101.09.50</span><span class="sxs-lookup"><span data-stu-id="622c1-138">101.09.50</span></span>

- <span data-ttu-id="622c1-139">이 제품 버전은 macOS Big Sur 11 베타 9에서 유효성이 검사되었습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-139">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="622c1-140">이제 명령줄 도구의 새 구문이 `mdatp` 기본 구문이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-140">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="622c1-141">새 구문에 대한 자세한 내용은 [Mac용 끝점용 Microsoft Defender 리소스를 참조하세요.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="622c1-141">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="622c1-142">이전 명령줄 도구 구문은 **2021년 1월 1일** 제품에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-142">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="622c1-143">진단 로그를 다른 디렉터리에 저장할 수 있도록 하는 새 매개 변수()로 `mdatp diagnostic create` `--path [directory]` 확장</span><span class="sxs-lookup"><span data-stu-id="622c1-143">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="622c1-144">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-144">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="622c1-145">101.09.49</span><span class="sxs-lookup"><span data-stu-id="622c1-145">101.09.49</span></span>

- <span data-ttu-id="622c1-146">IT 관리자가 관리하는 제외와 로컬 사용자가 정의한 제외를 차별화하기 위한 사용자 인터페이스 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-146">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="622c1-147">필요한 검사 중 CPU 사용률 향상</span><span class="sxs-lookup"><span data-stu-id="622c1-147">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="622c1-148">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-148">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="622c1-149">101.07.23</span><span class="sxs-lookup"><span data-stu-id="622c1-149">101.07.23</span></span>

- <span data-ttu-id="622c1-150">수동 모드 및 EDR 그룹 ID의 상태를 확인할 수 있는 새 필드가 출력에 `mdatp --health` 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-150">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="622c1-151">`mdatp --health` 는 향후 제품 업데이트에서 `mdatp health` 대체될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-151">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="622c1-152">자동 샘플 제출이 사용자 인터페이스에서 관리되는 것으로 표시되지 않는 버그가 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-152">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="622c1-153">바이러스 백신 검사 기록의 항목 보존을 제어하기 위한 새 설정이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-153">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="622c1-154">이제 검사 [기록에](mac-preferences.md#antivirus-scan-history-retention-in-days) 항목을 보존할 일 수를 지정하고 검사 기록의 최대 항목 수를 [지정할 수 있습니다.](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="622c1-154">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="622c1-155">버그 수정</span><span class="sxs-lookup"><span data-stu-id="622c1-155">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="622c1-156">101.06.63</span><span class="sxs-lookup"><span data-stu-id="622c1-156">101.06.63</span></span>

- <span data-ttu-id="622c1-157">버전 에 도입된 성능 회귀 문제를 `101.05.17` 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-157">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="622c1-158">회귀는 일부 고객이 SMB 공유에 액세스할 때 관찰한 커널 패니크를 제거하기 위해 수정과 함께 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-158">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="622c1-159">이 코드 변경을 되살리며 커널 패니를 제거하는 다른 방법을 조사하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-159">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="622c1-160">101.05.17</span><span class="sxs-lookup"><span data-stu-id="622c1-160">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="622c1-161">명령줄 도구에 대한 새 구문과 향상된 구문을 `mdatp` 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-161">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="622c1-162">새 구문은 현재 Insider Fast 및 Insider Slow 업데이트 채널에서 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-162">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="622c1-163">이 새 구문을 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-163">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="622c1-164">계속해서 새 구문과 함께 이전 구문을 지원할 예정으로, 앞으로 몇 개월 후의 이전 구문에 대한 사용 안 하게 될 계획에 대해 좀 더 많은 통신을 제공할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-164">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="622c1-165">SMB 파일 공유에 액세스할 때 가끔 발생하는 커널 패니크 해결</span><span class="sxs-lookup"><span data-stu-id="622c1-165">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="622c1-166">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-166">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="622c1-167">101.05.16</span><span class="sxs-lookup"><span data-stu-id="622c1-167">101.05.16</span></span>

- <span data-ttu-id="622c1-168">검색된 파일 수를 크게 줄일 수 있는 빠른 검사 논리 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-168">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="622c1-169">명령줄 [도구에](mac-resources.md#how-to-enable-autocompletion) 대한 자동 보완 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-169">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="622c1-170">버그 수정</span><span class="sxs-lookup"><span data-stu-id="622c1-170">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="622c1-171">101.03.12</span><span class="sxs-lookup"><span data-stu-id="622c1-171">101.03.12</span></span>

- <span data-ttu-id="622c1-172">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-172">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="622c1-173">101.01.54</span><span class="sxs-lookup"><span data-stu-id="622c1-173">101.01.54</span></span>

- <span data-ttu-id="622c1-174">시간 컴퓨터와의 호환성 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-174">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="622c1-175">향상된 접근성</span><span class="sxs-lookup"><span data-stu-id="622c1-175">Accessibility improvements</span></span>
- <span data-ttu-id="622c1-176">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-176">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="622c1-177">101.00.31</span><span class="sxs-lookup"><span data-stu-id="622c1-177">101.00.31</span></span>

- <span data-ttu-id="622c1-178">[Intune 사용자에 대한](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos) 향상된 제품 온보더링 환경</span><span class="sxs-lookup"><span data-stu-id="622c1-178">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="622c1-179">바이러스 [백신 제외에서 와일드카드 지원](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="622c1-179">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="622c1-180">macOS 상황에 맞는 메뉴에서 바이러스 백신 검색을 트리거하는 기능을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-180">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="622c1-181">이제 Finder에서 파일 또는 폴더를 마우스 오른쪽 단추로 클릭하고 **끝점용 Microsoft Defender로 스캔을** 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-181">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="622c1-182">현재 있는 제품 다운그레이드가 설치 관리자에 의해 명시적으로 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-182">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="622c1-183">다운그레이드해야 하는 경우 먼저 기존 버전을 제거하고 장치를 다시 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-183">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="622c1-184">버그 수정에 & 성능 향상</span><span class="sxs-lookup"><span data-stu-id="622c1-184">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="622c1-185">100.90.27</span><span class="sxs-lookup"><span data-stu-id="622c1-185">100.90.27</span></span>

- <span data-ttu-id="622c1-186">이제 시스템 [전체 업데이트](mac-updates.md#set-the-channel-name) 채널과 다른 Mac용 끝점용 Microsoft Defender에 대한 업데이트 채널을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-186">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint for Mac that is different from the system-wide update channel</span></span>
- <span data-ttu-id="622c1-187">새 제품 아이콘</span><span class="sxs-lookup"><span data-stu-id="622c1-187">New product icon</span></span>
- <span data-ttu-id="622c1-188">기타 사용자 환경 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-188">Other user experience improvements</span></span>
- <span data-ttu-id="622c1-189">버그 수정</span><span class="sxs-lookup"><span data-stu-id="622c1-189">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="622c1-190">100.86.92</span><span class="sxs-lookup"><span data-stu-id="622c1-190">100.86.92</span></span>

- <span data-ttu-id="622c1-191">시간 컴퓨터와의 호환성 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-191">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="622c1-192">제품이 제거 중에 일부 파일을 정리하지 않는 문제를 `/Library/Application Support/Microsoft/Defender` 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-192">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="622c1-193">Microsoft 자동 업데이트를 통해 Microsoft 제품이 업데이트될 때 제품의 CPU 사용률 감소</span><span class="sxs-lookup"><span data-stu-id="622c1-193">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="622c1-194">버그 수정에 & 성능 향상</span><span class="sxs-lookup"><span data-stu-id="622c1-194">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="622c1-195">100.86.91</span><span class="sxs-lookup"><span data-stu-id="622c1-195">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="622c1-196">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="622c1-196">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="622c1-197">Mac용 MDATP 업데이트 및 향상된 기능은 카탈로나[10.15], Mojave [10.14] 및 High Sierra [10.13]을 실행하는 장치에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-197">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="622c1-198">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span><span class="sxs-lookup"><span data-stu-id="622c1-198">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="622c1-199">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-199">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="622c1-200">100.83.73</span><span class="sxs-lookup"><span data-stu-id="622c1-200">100.83.73</span></span>

- <span data-ttu-id="622c1-201">제외 [관리,](mac-preferences.md#exclusion-merge-policy)위협 유형 설정 관리 및 금지된 [](mac-preferences.md#threat-type-settings-merge-policy)위협 작업과 같은 IT 관리자를 위한 더 많은 제어가 [추가되었습니다.](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="622c1-201">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="622c1-202">장치에서 전체 디스크 액세스를 사용하도록 설정하지 않은 경우 상태 메뉴에 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-202">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="622c1-203">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-203">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="622c1-204">100.82.60</span><span class="sxs-lookup"><span data-stu-id="622c1-204">100.82.60</span></span>

- <span data-ttu-id="622c1-205">정의 업데이트 후 제품이 시작되지 못하는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-205">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="622c1-206">100.80.42</span><span class="sxs-lookup"><span data-stu-id="622c1-206">100.80.42</span></span>

- <span data-ttu-id="622c1-207">버그 수정</span><span class="sxs-lookup"><span data-stu-id="622c1-207">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="622c1-208">100.79.42</span><span class="sxs-lookup"><span data-stu-id="622c1-208">100.79.42</span></span>

- <span data-ttu-id="622c1-209">Mac용 끝점용 Microsoft Defender가 때때로 시간 컴퓨터로 떨어졌다는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-209">Fixed an issue where Microsoft Defender for Endpoint for Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="622c1-210">백end 서비스와의 연결을 테스트하기 위한 명령줄 유틸리티에 새 스위치가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-210">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="622c1-211">사용자 인터페이스에서 전체 위협 기록을 볼 수 있는 기능 추가(보호 기록 보기에서 액세스할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-211">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="622c1-212">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-212">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="622c1-213">100.72.15</span><span class="sxs-lookup"><span data-stu-id="622c1-213">100.72.15</span></span>

- <span data-ttu-id="622c1-214">버그 수정</span><span class="sxs-lookup"><span data-stu-id="622c1-214">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="622c1-215">100.70.99</span><span class="sxs-lookup"><span data-stu-id="622c1-215">100.70.99</span></span>

- <span data-ttu-id="622c1-216">실시간 보호를 사용하는 경우 일부 사용자가 macOS 카탈로나로 업그레이드하는 능력에 영향을 미치는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-216">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="622c1-217">이 소문자 문제는 카탈로나 업그레이드 패키지 내의 끝점 잠금 파일을 검사하는 동안 카탈로나 업그레이드 패키지 내의 끝점 잠금 파일에서 발생하여 업그레이드 순서에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-217">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="622c1-218">100.68.99</span><span class="sxs-lookup"><span data-stu-id="622c1-218">100.68.99</span></span>

- <span data-ttu-id="622c1-219">수동 모드에서 실행하도록 바이러스 백신 기능을 구성하는 [기능이 추가되었습니다.](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="622c1-219">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="622c1-220">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-220">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="622c1-221">100.65.28</span><span class="sxs-lookup"><span data-stu-id="622c1-221">100.65.28</span></span>

- <span data-ttu-id="622c1-222">MacOS 카탈로니아에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-222">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="622c1-223">macOS 10.15(카탈로니아)에는 새로운 보안 및 개인 정보 보호 향상 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-223">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="622c1-224">이 버전부터 응용 프로그램은 기본적으로 명시적 동의 없이 디스크의 특정 위치(예: 문서, 다운로드, 데스크톱 등)에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-224">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="622c1-225">이 동의가 없는 경우 끝점용 Microsoft Defender는 장치를 완전히 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-225">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="622c1-226">이 동의를 부여하는 메커니즘은 끝점용 Microsoft Defender를 배포한 방법에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="622c1-226">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="622c1-227">수동 배포에 대한 자세한 내용은 수동 배포 항목의 [업데이트된 지침을 참조하세요.](mac-install-manually.md#how-to-allow-full-disk-access)</span><span class="sxs-lookup"><span data-stu-id="622c1-227">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="622c1-228">관리되는 배포에 대한 자세한 내용은 [JAMF 기반](mac-install-with-jamf.md) 배포 및 [Microsoft Intune](mac-install-with-intune.md#create-system-configuration-profiles) 기반 배포 항목의 업데이트된 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="622c1-228">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="622c1-229">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="622c1-229">Performance improvements & bug fixes</span></span>
