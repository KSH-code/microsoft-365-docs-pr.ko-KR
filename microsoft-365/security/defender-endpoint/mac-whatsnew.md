---
title: Mac의 끝점용 Microsoft Defender의 새로운
description: Mac의 끝점용 Microsoft Defender 이전 버전에 대한 주요 변경 내용에 대해 자세히 알아보습니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, mac, 설치, macos, whatsnew
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
ms.openlocfilehash: edbabf83c7bf1ac8dbe1ca9451ad191b45a862ac
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932730"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="3dd21-104">Mac의 끝점용 Microsoft Defender의 새로운</span><span class="sxs-lookup"><span data-stu-id="3dd21-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3dd21-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3dd21-105">**Applies to:**</span></span>
- [<span data-ttu-id="3dd21-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3dd21-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3dd21-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3dd21-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3dd21-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3dd21-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3dd21-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="3dd21-110">macOS 11(Big Sur)에서는 끝점용 Microsoft Defender에 추가 구성 프로필이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="3dd21-111">이전 버전의 macOS에서 업그레이드하는 기존 고객인 경우 이 페이지에 나열된 추가 구성 프로필을 [배포해야 합니다.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3dd21-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="3dd21-112">101.25.69 (20.121022.12569.0)</span><span class="sxs-lookup"><span data-stu-id="3dd21-112">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="3dd21-113">MacOS의 끝점용 Microsoft Defender는 이제 미국 정부 고객을 위해 미리 보기에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-113">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="3dd21-114">자세한 내용은 미국 정부 고객용 [끝점용 Microsoft Defender를 참조하세요.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="3dd21-114">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="3dd21-115">성능 향상(특히 XCode 시뮬레이터 앱이 사용되는 상황용)은 & 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-115">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="3dd21-116">101.23.64 (20.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="3dd21-116">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="3dd21-117">마지막 명령줄 검사에 대한 정보를 볼 수 있는 새 옵션이 명령줄 도구에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-117">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="3dd21-118">마지막 on-demand 검사에 대한 정보를 보기 위해 를 실행합니다. `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="3dd21-118">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="3dd21-119">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-119">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="3dd21-120">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="3dd21-120">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="3dd21-121">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-121">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="3dd21-122">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="3dd21-122">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="3dd21-123">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-123">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="3dd21-124">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="3dd21-124">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="3dd21-125">이 릴리스에서는 이전 명령줄 도구 구문이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-125">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="3dd21-126">새 구문에 대한 자세한 내용은 Resources 을 [참조하십시오.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="3dd21-126">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="3dd21-127">네트워크 확장을 사용하지 않도록 설정하는 새 명령줄 스위치가 `mdatp system-extension network-filter disable` 추가되었습니다. .</span><span class="sxs-lookup"><span data-stu-id="3dd21-127">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="3dd21-128">이 명령은 Mac의 끝점용 Microsoft Defender와 관련이 있을 수 있는 네트워킹 문제를 해결하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-128">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="3dd21-129">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-129">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="3dd21-130">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="3dd21-130">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="3dd21-131">버그 수정</span><span class="sxs-lookup"><span data-stu-id="3dd21-131">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="3dd21-132">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="3dd21-132">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="3dd21-133">macOS 11 Big Sur에서 실행될 때 에이전트의 안정성 향상</span><span class="sxs-lookup"><span data-stu-id="3dd21-133">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="3dd21-134">사용자 지정 검사 중에 AV 제외를 무시하는 새 명령줄 스위치()가 `--ignore-exclusions` 추가되었습니다. `mdatp scan custom`</span><span class="sxs-lookup"><span data-stu-id="3dd21-134">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="3dd21-135">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-135">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="3dd21-136">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="3dd21-136">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="3dd21-137">끝점용 Microsoft Defender가 커널 창에 매니페스트되는 macOS 11(Big Sur) 버그를 트리거할 때 제거된 조건</span><span class="sxs-lookup"><span data-stu-id="3dd21-137">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="3dd21-138">Mac 11(Big Sur)에서 실행되는 경우 Endpoint 보안 시스템 확장의 메모리 누수 수정</span><span class="sxs-lookup"><span data-stu-id="3dd21-138">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="3dd21-139">버그 수정</span><span class="sxs-lookup"><span data-stu-id="3dd21-139">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="3dd21-140">101.10.72</span><span class="sxs-lookup"><span data-stu-id="3dd21-140">101.10.72</span></span>

- <span data-ttu-id="3dd21-141">버그 수정</span><span class="sxs-lookup"><span data-stu-id="3dd21-141">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="3dd21-142">101.09.61</span><span class="sxs-lookup"><span data-stu-id="3dd21-142">101.09.61</span></span>

- <span data-ttu-id="3dd21-143">피드백을 보내기 위한 옵션을 사용할 수 있도록 설정하기 위한 새로운 관리 기본 [설정이 추가되었습니다.](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="3dd21-143">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="3dd21-144">이제 상태 메뉴 아이콘은 제품 설정이 관리되는 경우 정상 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-144">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="3dd21-145">이전에는 관리자가 제품 설정을 관리했어도 상태 메뉴 아이콘에 경고 또는 오류 상태가 표시했습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-145">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="3dd21-146">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-146">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="3dd21-147">101.09.50</span><span class="sxs-lookup"><span data-stu-id="3dd21-147">101.09.50</span></span>

- <span data-ttu-id="3dd21-148">이 제품 버전은 macOS Big Sur 11 베타 9에서 유효성이 검사되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-148">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="3dd21-149">이제 명령줄 도구의 새 구문이 `mdatp` 기본 구문이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-149">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="3dd21-150">새 구문에 대한 자세한 내용은 [MacOS의 끝점용 Microsoft Defender 리소스를 참조하세요.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="3dd21-150">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="3dd21-151">이전 명령줄 도구 구문은 **2021년 1월 1일** 제품에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-151">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="3dd21-152">진단 로그를 다른 디렉터리에 저장할 수 있도록 하는 새 매개 변수()로 `mdatp diagnostic create` `--path [directory]` 확장</span><span class="sxs-lookup"><span data-stu-id="3dd21-152">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="3dd21-153">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-153">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="3dd21-154">101.09.49</span><span class="sxs-lookup"><span data-stu-id="3dd21-154">101.09.49</span></span>

- <span data-ttu-id="3dd21-155">IT 관리자가 관리하는 제외와 로컬 사용자가 정의한 제외를 차별화하기 위한 사용자 인터페이스 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-155">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="3dd21-156">필요한 검사 중 CPU 사용률 향상</span><span class="sxs-lookup"><span data-stu-id="3dd21-156">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="3dd21-157">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-157">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="3dd21-158">101.07.23</span><span class="sxs-lookup"><span data-stu-id="3dd21-158">101.07.23</span></span>

- <span data-ttu-id="3dd21-159">수동 모드 및 EDR 그룹 ID의 상태를 확인할 수 있는 새 필드가 출력에 `mdatp --health` 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-159">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="3dd21-160">`mdatp --health` 는 향후 제품 업데이트에서 `mdatp health` 대체될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-160">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="3dd21-161">자동 샘플 제출이 사용자 인터페이스에서 관리되는 것으로 표시되지 않는 버그가 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-161">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="3dd21-162">바이러스 백신 검사 기록의 항목 보존을 제어하기 위한 새 설정이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-162">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="3dd21-163">이제 검사 [기록에](mac-preferences.md#antivirus-scan-history-retention-in-days) 항목을 보존할 일 수를 지정하고 검사 기록의 최대 항목 수를 [지정할 수 있습니다.](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="3dd21-163">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="3dd21-164">버그 수정</span><span class="sxs-lookup"><span data-stu-id="3dd21-164">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="3dd21-165">101.06.63</span><span class="sxs-lookup"><span data-stu-id="3dd21-165">101.06.63</span></span>

- <span data-ttu-id="3dd21-166">버전 에 도입된 성능 회귀 문제를 `101.05.17` 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-166">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="3dd21-167">회귀는 일부 고객이 SMB 공유에 액세스할 때 관찰한 커널 패니크를 제거하기 위해 수정과 함께 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-167">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="3dd21-168">이 코드 변경을 되살리며 커널 패니를 제거하는 다른 방법을 조사하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-168">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="3dd21-169">101.05.17</span><span class="sxs-lookup"><span data-stu-id="3dd21-169">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3dd21-170">명령줄 도구에 대한 새 구문과 향상된 구문을 `mdatp` 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-170">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="3dd21-171">새 구문은 현재 Insider Fast 및 Insider Slow 업데이트 채널에서 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-171">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="3dd21-172">이 새 구문을 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-172">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="3dd21-173">계속해서 새 구문과 함께 이전 구문을 지원할 예정으로, 앞으로 몇 개월 후의 이전 구문에 대한 사용 안 하게 될 계획에 대해 좀 더 많은 통신을 제공할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-173">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="3dd21-174">SMB 파일 공유에 액세스할 때 가끔 발생하는 커널 패니크 해결</span><span class="sxs-lookup"><span data-stu-id="3dd21-174">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="3dd21-175">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-175">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="3dd21-176">101.05.16</span><span class="sxs-lookup"><span data-stu-id="3dd21-176">101.05.16</span></span>

- <span data-ttu-id="3dd21-177">검색된 파일 수를 크게 줄일 수 있는 빠른 검사 논리 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-177">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="3dd21-178">명령줄 [도구에](mac-resources.md#how-to-enable-autocompletion) 대한 자동 보완 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-178">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="3dd21-179">버그 수정</span><span class="sxs-lookup"><span data-stu-id="3dd21-179">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="3dd21-180">101.03.12</span><span class="sxs-lookup"><span data-stu-id="3dd21-180">101.03.12</span></span>

- <span data-ttu-id="3dd21-181">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-181">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="3dd21-182">101.01.54</span><span class="sxs-lookup"><span data-stu-id="3dd21-182">101.01.54</span></span>

- <span data-ttu-id="3dd21-183">시간 컴퓨터와의 호환성 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-183">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="3dd21-184">향상된 접근성</span><span class="sxs-lookup"><span data-stu-id="3dd21-184">Accessibility improvements</span></span>
- <span data-ttu-id="3dd21-185">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-185">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="3dd21-186">101.00.31</span><span class="sxs-lookup"><span data-stu-id="3dd21-186">101.00.31</span></span>

- <span data-ttu-id="3dd21-187">[Intune 사용자에 대한](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos) 향상된 제품 온보더링 환경</span><span class="sxs-lookup"><span data-stu-id="3dd21-187">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="3dd21-188">바이러스 [백신 제외에서 와일드카드 지원](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="3dd21-188">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="3dd21-189">macOS 상황에 맞는 메뉴에서 바이러스 백신 검색을 트리거하는 기능을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-189">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="3dd21-190">이제 Finder에서 파일 또는 폴더를 마우스 오른쪽 단추로 클릭하고 **끝점용 Microsoft Defender로 스캔을** 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-190">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="3dd21-191">현재 있는 제품 다운그레이드가 설치 관리자에 의해 명시적으로 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-191">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="3dd21-192">다운그레이드해야 하는 경우 먼저 기존 버전을 제거하고 장치를 다시 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-192">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="3dd21-193">버그 수정에 & 성능 향상</span><span class="sxs-lookup"><span data-stu-id="3dd21-193">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="3dd21-194">100.90.27</span><span class="sxs-lookup"><span data-stu-id="3dd21-194">100.90.27</span></span>

- <span data-ttu-id="3dd21-195">이제 시스템 [](mac-updates.md#set-the-channel-name) 전체 업데이트 채널과 다른 macOS의 끝점용 Microsoft Defender에 대한 업데이트 채널을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-195">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="3dd21-196">새 제품 아이콘</span><span class="sxs-lookup"><span data-stu-id="3dd21-196">New product icon</span></span>
- <span data-ttu-id="3dd21-197">기타 사용자 환경 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-197">Other user experience improvements</span></span>
- <span data-ttu-id="3dd21-198">버그 수정</span><span class="sxs-lookup"><span data-stu-id="3dd21-198">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="3dd21-199">100.86.92</span><span class="sxs-lookup"><span data-stu-id="3dd21-199">100.86.92</span></span>

- <span data-ttu-id="3dd21-200">시간 컴퓨터와의 호환성 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-200">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="3dd21-201">제품이 제거 중에 일부 파일을 정리하지 않는 문제를 `/Library/Application Support/Microsoft/Defender` 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-201">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="3dd21-202">Microsoft 자동 업데이트를 통해 Microsoft 제품이 업데이트될 때 제품의 CPU 사용률 감소</span><span class="sxs-lookup"><span data-stu-id="3dd21-202">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="3dd21-203">버그 수정에 & 성능 향상</span><span class="sxs-lookup"><span data-stu-id="3dd21-203">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="3dd21-204">100.86.91</span><span class="sxs-lookup"><span data-stu-id="3dd21-204">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="3dd21-205">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="3dd21-205">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="3dd21-206">Mac용 MDATP 업데이트 및 향상된 기능은 카탈로나[10.15], Mojave [10.14] 및 High Sierra [10.13]을 실행하는 장치에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-206">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="3dd21-207">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span><span class="sxs-lookup"><span data-stu-id="3dd21-207">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="3dd21-208">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-208">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="3dd21-209">100.83.73</span><span class="sxs-lookup"><span data-stu-id="3dd21-209">100.83.73</span></span>

- <span data-ttu-id="3dd21-210">제외 [관리,](mac-preferences.md#exclusion-merge-policy)위협 유형 설정 관리 및 금지된 [](mac-preferences.md#threat-type-settings-merge-policy)위협 작업과 같은 IT 관리자를 위한 더 많은 제어가 [추가되었습니다.](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="3dd21-210">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="3dd21-211">장치에서 전체 디스크 액세스를 사용하도록 설정하지 않은 경우 상태 메뉴에 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-211">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="3dd21-212">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-212">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="3dd21-213">100.82.60</span><span class="sxs-lookup"><span data-stu-id="3dd21-213">100.82.60</span></span>

- <span data-ttu-id="3dd21-214">정의 업데이트 후 제품이 시작되지 못하는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-214">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="3dd21-215">100.80.42</span><span class="sxs-lookup"><span data-stu-id="3dd21-215">100.80.42</span></span>

- <span data-ttu-id="3dd21-216">버그 수정</span><span class="sxs-lookup"><span data-stu-id="3dd21-216">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="3dd21-217">100.79.42</span><span class="sxs-lookup"><span data-stu-id="3dd21-217">100.79.42</span></span>

- <span data-ttu-id="3dd21-218">Mac의 끝점용 Microsoft Defender가 때때로 시간 컴퓨터로 떨어졌다는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-218">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="3dd21-219">백end 서비스와의 연결을 테스트하기 위한 명령줄 유틸리티에 새 스위치가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-219">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="3dd21-220">사용자 인터페이스에서 전체 위협 기록을 볼 수 있는 기능 추가(보호 기록 보기에서 액세스할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-220">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="3dd21-221">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-221">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="3dd21-222">100.72.15</span><span class="sxs-lookup"><span data-stu-id="3dd21-222">100.72.15</span></span>

- <span data-ttu-id="3dd21-223">버그 수정</span><span class="sxs-lookup"><span data-stu-id="3dd21-223">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="3dd21-224">100.70.99</span><span class="sxs-lookup"><span data-stu-id="3dd21-224">100.70.99</span></span>

- <span data-ttu-id="3dd21-225">실시간 보호를 사용하는 경우 일부 사용자가 macOS 카탈로나로 업그레이드하는 능력에 영향을 미치는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-225">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="3dd21-226">이 소문자 문제는 카탈로나 업그레이드 패키지 내의 끝점 잠금 파일을 검사하는 동안 카탈로나 업그레이드 패키지 내의 끝점 잠금 파일에서 발생하여 업그레이드 순서에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-226">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="3dd21-227">100.68.99</span><span class="sxs-lookup"><span data-stu-id="3dd21-227">100.68.99</span></span>

- <span data-ttu-id="3dd21-228">수동 모드에서 실행하도록 바이러스 백신 기능을 구성하는 [기능이 추가되었습니다.](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="3dd21-228">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="3dd21-229">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-229">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="3dd21-230">100.65.28</span><span class="sxs-lookup"><span data-stu-id="3dd21-230">100.65.28</span></span>

- <span data-ttu-id="3dd21-231">MacOS 카탈로니아에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-231">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="3dd21-232">macOS 10.15(카탈로니아)에는 새로운 보안 및 개인 정보 보호 향상 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-232">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="3dd21-233">이 버전부터 응용 프로그램은 기본적으로 명시적 동의 없이 디스크의 특정 위치(예: 문서, 다운로드, 데스크톱 등)에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-233">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="3dd21-234">이 동의가 없는 경우 끝점용 Microsoft Defender는 장치를 완전히 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-234">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="3dd21-235">이 동의를 부여하는 메커니즘은 끝점용 Microsoft Defender를 배포한 방법에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd21-235">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="3dd21-236">수동 배포에 대한 자세한 내용은 수동 배포 항목의 [업데이트된 지침을 참조하세요.](mac-install-manually.md#how-to-allow-full-disk-access)</span><span class="sxs-lookup"><span data-stu-id="3dd21-236">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="3dd21-237">관리되는 배포에 대한 자세한 내용은 [JAMF 기반](mac-install-with-jamf.md) 배포 및 [Microsoft Intune](mac-install-with-intune.md#create-system-configuration-profiles) 기반 배포 항목의 업데이트된 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3dd21-237">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="3dd21-238">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="3dd21-238">Performance improvements & bug fixes</span></span>
