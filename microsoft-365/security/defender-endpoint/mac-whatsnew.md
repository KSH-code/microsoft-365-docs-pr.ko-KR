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
ms.openlocfilehash: fc162939e12f0bd55da5847c6bc1bda4b3761fd7
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53276908"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="0366e-104">Mac의 끝점용 Microsoft Defender의 새로운</span><span class="sxs-lookup"><span data-stu-id="0366e-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0366e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0366e-105">**Applies to:**</span></span>
- [<span data-ttu-id="0366e-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0366e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0366e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0366e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0366e-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="0366e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0366e-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="0366e-110">macOS 11(Big Sur)에서는 끝점용 Microsoft Defender에 추가 구성 프로필이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="0366e-111">이전 버전의 macOS에서 업그레이드하는 기존 고객인 경우 이 페이지에 나열된 추가 구성 프로필을 [배포해야 합니다.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0366e-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1013420-20121051134200"></a><span data-ttu-id="0366e-112">101.34.20 (20.121051.13420.0)</span><span class="sxs-lookup"><span data-stu-id="0366e-112">101.34.20 (20.121051.13420.0)</span></span>

- <span data-ttu-id="0366e-113">macOS 11(Big Sur)의 상태 메뉴에서 빠른 검색을 시작할 수 없는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-113">Addressed an issue where a quick scan could not be started from the status menu on macOS 11 (Big Sur)</span></span>
- <span data-ttu-id="0366e-114">기타 버그 수정</span><span class="sxs-lookup"><span data-stu-id="0366e-114">Other bug fixes</span></span>

## <a name="1013269-20121042132690"></a><span data-ttu-id="0366e-115">101.32.69 (20.121042.13269.0)</span><span class="sxs-lookup"><span data-stu-id="0366e-115">101.32.69 (20.121042.13269.0)</span></span>

- <span data-ttu-id="0366e-116">끝점용 Microsoft Defender 및 기타 응용 프로그램에서 키채인에 동시 액세스하면 키채인 손상이 발생할 수 있는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-116">Addressed an issue where concurrent access to the keychain from Microsoft Defender for Endpoint and other applications can lead to keychain corruption.</span></span>

## <a name="1012964-20121042129640"></a><span data-ttu-id="0366e-117">101.29.64 (20.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="0366e-117">101.29.64 (20.121042.12964.0)</span></span>

- <span data-ttu-id="0366e-118">이 버전부터 명령줄 클라이언트를 통해 트리거된 요청 시 바이러스 백신 검사 중에 감지된 위협이 자동으로 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-118">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="0366e-119">사용자 인터페이스를 통해 트리거된 검사 중에 검색된 위협에는 여전히 수동 작업이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-119">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="0366e-120">`mdatp diagnostic real-time-protection-statistics` 이제 다음 두 가지 추가 스위치를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-120">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="0366e-121">`--sort`: 검색된 총 파일 수를 통해 출력의 내선 번호를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-121">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="0366e-122">`--top N`: 상위 N 결과를 표시하고(또한 지정한 `--sort` 경우만 작동)</span><span class="sxs-lookup"><span data-stu-id="0366e-122">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="0366e-123">YARN을 사용하는 경우의 성능 향상(특히& 수정</span><span class="sxs-lookup"><span data-stu-id="0366e-123">Performance improvements (specifically for when YARN is used) & bug fixes</span></span>

## <a name="1012750-20121022127500"></a><span data-ttu-id="0366e-124">101.27.50 (20.121022.12750.0)</span><span class="sxs-lookup"><span data-stu-id="0366e-124">101.27.50 (20.121022.12750.0)</span></span>

- <span data-ttu-id="0366e-125">MacOS 카탈로나 및 이전 버전의 Apple 인증서 만료를 수용하기 위해 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-125">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span></span> <span data-ttu-id="0366e-126">이 수정은 위협 요소 &(취약성 관리) 기능을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-126">This fix restores Threat & Vulnerability Management (TVM) functionality.</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="0366e-127">101.25.69 (20.121022.12569.0)</span><span class="sxs-lookup"><span data-stu-id="0366e-127">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="0366e-128">MacOS의 끝점용 Microsoft Defender는 이제 미국 정부 고객을 위해 미리 보기에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-128">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="0366e-129">자세한 내용은 미국 정부 고객용 [끝점용 Microsoft Defender를 참조하세요.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="0366e-129">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="0366e-130">성능 향상(특히 XCode 시뮬레이터 앱이 사용되는 상황용)은 버그 & 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-130">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes.</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="0366e-131">101.23.64 (20.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="0366e-131">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="0366e-132">마지막 명령줄 검사에 대한 정보를 볼 수 있는 새 옵션이 명령줄 도구에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-132">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="0366e-133">마지막 on-demand 검사에 대한 정보를 보기 위해 를 실행합니다. `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="0366e-133">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="0366e-134">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-134">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="0366e-135">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="0366e-135">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="0366e-136">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-136">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="0366e-137">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="0366e-137">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="0366e-138">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-138">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="0366e-139">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="0366e-139">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="0366e-140">이 릴리스에서는 이전 명령줄 도구 구문이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-140">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="0366e-141">새 구문에 대한 자세한 내용은 Resources 을 [참조하십시오.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="0366e-141">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="0366e-142">네트워크 확장을 사용하지 않도록 설정하는 새 명령줄 스위치가 `mdatp system-extension network-filter disable` 추가되었습니다. .</span><span class="sxs-lookup"><span data-stu-id="0366e-142">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="0366e-143">이 명령은 Mac의 끝점용 Microsoft Defender와 관련이 있을 수 있는 네트워킹 문제를 해결하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-143">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="0366e-144">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-144">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="0366e-145">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="0366e-145">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="0366e-146">버그 수정</span><span class="sxs-lookup"><span data-stu-id="0366e-146">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="0366e-147">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="0366e-147">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="0366e-148">macOS 11 Big Sur에서 실행될 때 에이전트의 안정성 향상</span><span class="sxs-lookup"><span data-stu-id="0366e-148">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="0366e-149">사용자 지정 검사 중에 AV 제외를 무시하는 새 명령줄 스위치()가 `--ignore-exclusions` 추가되었습니다. `mdatp scan custom`</span><span class="sxs-lookup"><span data-stu-id="0366e-149">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="0366e-150">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-150">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="0366e-151">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="0366e-151">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="0366e-152">끝점용 Microsoft Defender가 커널 창에 매니페스트되는 macOS 11(Big Sur) 버그를 트리거할 때 제거된 조건</span><span class="sxs-lookup"><span data-stu-id="0366e-152">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="0366e-153">Mac 11(Big Sur)에서 실행되는 경우 Endpoint 보안 시스템 확장의 메모리 누수 수정</span><span class="sxs-lookup"><span data-stu-id="0366e-153">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="0366e-154">버그 수정</span><span class="sxs-lookup"><span data-stu-id="0366e-154">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="0366e-155">101.10.72</span><span class="sxs-lookup"><span data-stu-id="0366e-155">101.10.72</span></span>

- <span data-ttu-id="0366e-156">버그 수정</span><span class="sxs-lookup"><span data-stu-id="0366e-156">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="0366e-157">101.09.61</span><span class="sxs-lookup"><span data-stu-id="0366e-157">101.09.61</span></span>

- <span data-ttu-id="0366e-158">피드백을 보내기 위한 옵션을 사용할 수 있도록 설정하기 위한 새로운 관리 기본 [설정이 추가되었습니다.](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="0366e-158">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="0366e-159">이제 상태 메뉴 아이콘은 제품 설정이 관리되는 경우 정상 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-159">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="0366e-160">이전에는 관리자가 제품 설정을 관리했어도 상태 메뉴 아이콘에 경고 또는 오류 상태가 표시했습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-160">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="0366e-161">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-161">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="0366e-162">101.09.50</span><span class="sxs-lookup"><span data-stu-id="0366e-162">101.09.50</span></span>

- <span data-ttu-id="0366e-163">이 제품 버전은 macOS Big Sur 11 베타 9에서 유효성이 검사되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-163">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="0366e-164">이제 명령줄 도구의 새 구문이 `mdatp` 기본 구문이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-164">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="0366e-165">새 구문에 대한 자세한 내용은 [MacOS의 끝점용 Microsoft Defender 리소스를 참조하세요.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="0366e-165">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="0366e-166">이전 명령줄 도구 구문은 **2021년 1월 1일** 제품에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-166">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="0366e-167">진단 로그를 다른 디렉터리에 저장할 수 있도록 하는 새 매개 변수()로 `mdatp diagnostic create` `--path [directory]` 확장</span><span class="sxs-lookup"><span data-stu-id="0366e-167">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="0366e-168">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-168">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="0366e-169">101.09.49</span><span class="sxs-lookup"><span data-stu-id="0366e-169">101.09.49</span></span>

- <span data-ttu-id="0366e-170">IT 관리자가 관리하는 제외와 로컬 사용자가 정의한 제외를 차별화하기 위한 사용자 인터페이스 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-170">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="0366e-171">필요한 검사 중 CPU 사용률 향상</span><span class="sxs-lookup"><span data-stu-id="0366e-171">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="0366e-172">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-172">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="0366e-173">101.07.23</span><span class="sxs-lookup"><span data-stu-id="0366e-173">101.07.23</span></span>

- <span data-ttu-id="0366e-174">수동 모드 및 수동 모드의 상태 확인을 위해 출력에 새 필드가 `mdatp --health` EDR 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-174">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="0366e-175">`mdatp --health` 는 향후 제품 업데이트에서 `mdatp health` 대체될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-175">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="0366e-176">자동 샘플 제출이 사용자 인터페이스에서 관리되는 것으로 표시되지 않는 버그가 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-176">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="0366e-177">바이러스 백신 검사 기록의 항목 보존을 제어하기 위한 새 설정이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-177">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="0366e-178">이제 검사 [기록에](mac-preferences.md#antivirus-scan-history-retention-in-days) 항목을 보존할 일 수를 지정하고 검사 기록의 최대 항목 수를 [지정할 수 있습니다.](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="0366e-178">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="0366e-179">버그 수정</span><span class="sxs-lookup"><span data-stu-id="0366e-179">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="0366e-180">101.06.63</span><span class="sxs-lookup"><span data-stu-id="0366e-180">101.06.63</span></span>

- <span data-ttu-id="0366e-181">버전 에 도입된 성능 회귀 문제를 `101.05.17` 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-181">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="0366e-182">회귀는 일부 고객이 SMB 공유에 액세스할 때 관찰한 커널 패니크를 제거하기 위해 수정과 함께 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-182">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="0366e-183">이 코드 변경을 되살리며 커널 패니를 제거하는 다른 방법을 조사하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-183">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="0366e-184">101.05.17</span><span class="sxs-lookup"><span data-stu-id="0366e-184">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0366e-185">명령줄 도구에 대한 새 구문과 향상된 구문을 `mdatp` 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-185">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="0366e-186">새 구문은 현재 Insider Fast 및 Insider Slow 업데이트 채널에서 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-186">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="0366e-187">이 새 구문을 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-187">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="0366e-188">계속해서 새 구문과 함께 이전 구문을 지원할 예정으로, 앞으로 몇 개월 후의 이전 구문에 대한 사용 안 하게 될 계획에 대해 좀 더 많은 통신을 제공할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-188">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="0366e-189">SMB 파일 공유에 액세스할 때 가끔 발생하는 커널 패니크 해결</span><span class="sxs-lookup"><span data-stu-id="0366e-189">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="0366e-190">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-190">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="0366e-191">101.05.16</span><span class="sxs-lookup"><span data-stu-id="0366e-191">101.05.16</span></span>

- <span data-ttu-id="0366e-192">검색된 파일 수를 크게 줄일 수 있는 빠른 검사 논리 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-192">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="0366e-193">명령줄 [도구에](mac-resources.md#how-to-enable-autocompletion) 대한 자동 보완 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-193">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="0366e-194">버그 수정</span><span class="sxs-lookup"><span data-stu-id="0366e-194">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="0366e-195">101.03.12</span><span class="sxs-lookup"><span data-stu-id="0366e-195">101.03.12</span></span>

- <span data-ttu-id="0366e-196">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-196">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="0366e-197">101.01.54</span><span class="sxs-lookup"><span data-stu-id="0366e-197">101.01.54</span></span>

- <span data-ttu-id="0366e-198">시간 컴퓨터와의 호환성 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-198">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="0366e-199">향상된 접근성</span><span class="sxs-lookup"><span data-stu-id="0366e-199">Accessibility improvements</span></span>
- <span data-ttu-id="0366e-200">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-200">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="0366e-201">101.00.31</span><span class="sxs-lookup"><span data-stu-id="0366e-201">101.00.31</span></span>

- <span data-ttu-id="0366e-202">[Intune 사용자에 대한](/mem/intune/apps/apps-advanced-threat-protection-macos) 향상된 제품 온보더링 환경</span><span class="sxs-lookup"><span data-stu-id="0366e-202">Improved [product onboarding experience for Intune users](/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="0366e-203">바이러스 [백신 제외에서 와일드카드 지원](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="0366e-203">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="0366e-204">macOS 상황에 맞는 메뉴에서 바이러스 백신 검색을 트리거하는 기능을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-204">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="0366e-205">이제 Finder에서 파일 또는 폴더를 마우스 오른쪽 단추로 클릭하고 **끝점용 Microsoft Defender로 스캔을** 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-205">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="0366e-206">현재 있는 제품 다운그레이드가 설치 관리자에 의해 명시적으로 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-206">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="0366e-207">다운그레이드해야 하는 경우 먼저 기존 버전을 제거하고 장치를 다시 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-207">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="0366e-208">버그 수정에 & 성능 향상</span><span class="sxs-lookup"><span data-stu-id="0366e-208">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="0366e-209">100.90.27</span><span class="sxs-lookup"><span data-stu-id="0366e-209">100.90.27</span></span>

- <span data-ttu-id="0366e-210">이제 시스템 [](mac-updates.md#set-the-channel-name) 전체 업데이트 채널과 다른 macOS의 끝점용 Microsoft Defender에 대한 업데이트 채널을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-210">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="0366e-211">새 제품 아이콘</span><span class="sxs-lookup"><span data-stu-id="0366e-211">New product icon</span></span>
- <span data-ttu-id="0366e-212">기타 사용자 환경 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-212">Other user experience improvements</span></span>
- <span data-ttu-id="0366e-213">버그 수정</span><span class="sxs-lookup"><span data-stu-id="0366e-213">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="0366e-214">100.86.92</span><span class="sxs-lookup"><span data-stu-id="0366e-214">100.86.92</span></span>

- <span data-ttu-id="0366e-215">시간 컴퓨터와의 호환성 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-215">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="0366e-216">제품이 제거 중에 일부 파일을 정리하지 않는 문제를 `/Library/Application Support/Microsoft/Defender` 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-216">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="0366e-217">Microsoft 자동 업데이트를 통해 Microsoft 제품이 업데이트될 때 제품의 CPU 사용률 감소</span><span class="sxs-lookup"><span data-stu-id="0366e-217">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="0366e-218">버그 수정에 & 성능 향상</span><span class="sxs-lookup"><span data-stu-id="0366e-218">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="0366e-219">100.86.91</span><span class="sxs-lookup"><span data-stu-id="0366e-219">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="0366e-220">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="0366e-220">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="0366e-221">Mac용 MDATP 업데이트 및 향상된 기능은 카탈로나[10.15], Mojave [10.14] 및 High Sierra [10.13]을 실행하는 장치에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-221">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="0366e-222">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span><span class="sxs-lookup"><span data-stu-id="0366e-222">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="0366e-223">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-223">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="0366e-224">100.83.73</span><span class="sxs-lookup"><span data-stu-id="0366e-224">100.83.73</span></span>

- <span data-ttu-id="0366e-225">제외 [관리,](mac-preferences.md#exclusion-merge-policy)위협 유형 설정 관리 및 금지된 [](mac-preferences.md#threat-type-settings-merge-policy)위협 작업과 같은 IT 관리자를 위한 더 많은 제어가 [추가되었습니다.](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="0366e-225">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="0366e-226">장치에서 전체 디스크 액세스를 사용하도록 설정하지 않은 경우 상태 메뉴에 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-226">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="0366e-227">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-227">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="0366e-228">100.82.60</span><span class="sxs-lookup"><span data-stu-id="0366e-228">100.82.60</span></span>

- <span data-ttu-id="0366e-229">정의 업데이트 후 제품이 시작되지 못하는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-229">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="0366e-230">100.80.42</span><span class="sxs-lookup"><span data-stu-id="0366e-230">100.80.42</span></span>

- <span data-ttu-id="0366e-231">버그 수정</span><span class="sxs-lookup"><span data-stu-id="0366e-231">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="0366e-232">100.79.42</span><span class="sxs-lookup"><span data-stu-id="0366e-232">100.79.42</span></span>

- <span data-ttu-id="0366e-233">Mac의 끝점용 Microsoft Defender가 때때로 시간 컴퓨터로 떨어졌다는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-233">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="0366e-234">백end 서비스와의 연결을 테스트하기 위한 명령줄 유틸리티에 새 스위치가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-234">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="0366e-235">사용자 인터페이스에서 전체 위협 기록을 볼 수 있는 기능 추가(보호 기록 보기에서 액세스할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-235">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="0366e-236">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-236">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="0366e-237">100.72.15</span><span class="sxs-lookup"><span data-stu-id="0366e-237">100.72.15</span></span>

- <span data-ttu-id="0366e-238">버그 수정</span><span class="sxs-lookup"><span data-stu-id="0366e-238">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="0366e-239">100.70.99</span><span class="sxs-lookup"><span data-stu-id="0366e-239">100.70.99</span></span>

- <span data-ttu-id="0366e-240">실시간 보호를 사용하는 경우 일부 사용자가 macOS 카탈로나로 업그레이드하는 능력에 영향을 미치는 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-240">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="0366e-241">이 소문자 문제는 카탈로나 업그레이드 패키지 내의 끝점 잠금 파일을 검사하는 동안 카탈로나 업그레이드 패키지 내의 끝점 잠금 파일에서 발생하여 업그레이드 순서에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-241">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="0366e-242">100.68.99</span><span class="sxs-lookup"><span data-stu-id="0366e-242">100.68.99</span></span>

- <span data-ttu-id="0366e-243">수동 모드에서 실행하도록 바이러스 백신 기능을 구성하는 [기능이 추가되었습니다.](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="0366e-243">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="0366e-244">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-244">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="0366e-245">100.65.28</span><span class="sxs-lookup"><span data-stu-id="0366e-245">100.65.28</span></span>

- <span data-ttu-id="0366e-246">MacOS 카탈로니아에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-246">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="0366e-247">macOS 10.15(카탈로니아)에는 새로운 보안 및 개인 정보 보호 향상 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-247">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="0366e-248">이 버전부터 응용 프로그램은 기본적으로 명시적 동의 없이 디스크의 특정 위치(예: 문서, 다운로드, 데스크톱 등)에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-248">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="0366e-249">이 동의가 없는 경우 끝점용 Microsoft Defender는 장치를 완전히 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-249">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="0366e-250">이 동의를 부여하는 메커니즘은 끝점용 Microsoft Defender를 배포한 방법에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="0366e-250">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="0366e-251">수동 배포에 대한 자세한 내용은 수동 배포 항목의 [업데이트된 지침을 참조하세요.](mac-install-manually.md#how-to-allow-full-disk-access)</span><span class="sxs-lookup"><span data-stu-id="0366e-251">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="0366e-252">관리되는 배포에 대한 자세한 내용은 [JAMF](mac-install-with-jamf.md) 기반 배포 및 Microsoft Intune 배포 항목의 업데이트된 [지침을 참조하세요.](mac-install-with-intune.md#create-system-configuration-profiles)</span><span class="sxs-lookup"><span data-stu-id="0366e-252">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="0366e-253">버그 수정을 & 성능 개선</span><span class="sxs-lookup"><span data-stu-id="0366e-253">Performance improvements & bug fixes</span></span>
