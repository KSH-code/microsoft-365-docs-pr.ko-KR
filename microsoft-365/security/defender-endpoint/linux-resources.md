---
title: Linux 리소스의 끝점용 Microsoft Defender
ms.reviewer: ''
description: Linux의 끝점용 Microsoft Defender에 대한 리소스( 제거 방법, 진단 로그 수집 방법, CLI 명령 및 제품에 대한 알려진 문제 포함)에 대해 설명
keywords: microsoft, defender, Endpoint용 Microsoft Defender, linux, 설치, 배포, 제거, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aaf9c0a8eef4e050ca034d1aee69d24c5adb909d
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930370"
---
# <a name="resources"></a><span data-ttu-id="33581-104">리소스</span><span class="sxs-lookup"><span data-stu-id="33581-104">Resources</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="33581-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="33581-105">**Applies to:**</span></span>

- [<span data-ttu-id="33581-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="33581-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="33581-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33581-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="33581-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="33581-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="33581-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="33581-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a><span data-ttu-id="33581-110">진단 정보 수집</span><span class="sxs-lookup"><span data-stu-id="33581-110">Collect diagnostic information</span></span>

<span data-ttu-id="33581-111">문제를 재현할 수 있는 경우 먼저 로깅 수준을 높이고, 시스템을 어느 정도 실행한 다음 로깅 수준을 기본값으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="33581-111">If you can reproduce a problem, first increase the logging level, run the system for some time, and then restore the logging level to the default.</span></span>

1. <span data-ttu-id="33581-112">로깅 수준 증가:</span><span class="sxs-lookup"><span data-stu-id="33581-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="33581-113">문제를 재현합니다.</span><span class="sxs-lookup"><span data-stu-id="33581-113">Reproduce the problem.</span></span>

3. <span data-ttu-id="33581-114">다음 명령을 실행하여 끝점 로그에 대한 Defender를 백업합니다.</span><span class="sxs-lookup"><span data-stu-id="33581-114">Run the following command to back up Defender for Endpoint's logs.</span></span> <span data-ttu-id="33581-115">파일은 보관 파일 내부에 .zip 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="33581-115">The files will be stored inside of a .zip archive.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

    <span data-ttu-id="33581-116">또한 이 명령은 작업이 성공한 후 백업에 대한 파일 경로를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="33581-116">This command will also print out the file path to the backup after the operation succeeds:</span></span>

   ```Output
   Diagnostic file created: <path to file>
   ```

4. <span data-ttu-id="33581-117">로깅 수준 복원:</span><span class="sxs-lookup"><span data-stu-id="33581-117">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```

   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a><span data-ttu-id="33581-118">로그 설치 문제</span><span class="sxs-lookup"><span data-stu-id="33581-118">Log installation issues</span></span>

<span data-ttu-id="33581-119">설치 중에 오류가 발생하면 설치 관리자에서 일반적인 오류만 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="33581-119">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="33581-120">자세한 로그는 에 `/var/log/microsoft/mdatp/install.log` 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="33581-120">The detailed log will be saved to `/var/log/microsoft/mdatp/install.log`.</span></span>
<span data-ttu-id="33581-121">설치 중에 문제가 발생하면 이 파일을 보내 원인을 진단하는 데 도움을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33581-121">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstall"></a><span data-ttu-id="33581-122">제거</span><span class="sxs-lookup"><span data-stu-id="33581-122">Uninstall</span></span>

<span data-ttu-id="33581-123">Linux에서 끝점용 Defender를 제거하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33581-123">There are several ways to uninstall Defender for Endpoint on Linux.</span></span> <span data-ttu-id="33581-124">Puppet과 같은 구성 도구를 사용하는 경우 구성 도구에 대한 패키지 제거 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="33581-124">If you are using a configuration tool such as Puppet, follow the package uninstallation instructions for the configuration tool.</span></span>

### <a name="manual-uninstallation"></a><span data-ttu-id="33581-125">수동 제거</span><span class="sxs-lookup"><span data-stu-id="33581-125">Manual uninstallation</span></span>

- <span data-ttu-id="33581-126">`sudo yum remove mdatp` RHEL 및 variants(CentOS 및 Oracle Linux)의 경우</span><span class="sxs-lookup"><span data-stu-id="33581-126">`sudo yum remove mdatp` for RHEL and variants(CentOS and Oracle Linux).</span></span>
- <span data-ttu-id="33581-127">`sudo zypper remove mdatp` SLES 및 변형의 경우</span><span class="sxs-lookup"><span data-stu-id="33581-127">`sudo zypper remove mdatp` for SLES and variants.</span></span>
- <span data-ttu-id="33581-128">`sudo apt-get purge mdatp` Ubuntu 및 데비안 시스템용입니다.</span><span class="sxs-lookup"><span data-stu-id="33581-128">`sudo apt-get purge mdatp` for Ubuntu and Debian systems.</span></span>

## <a name="configure-from-the-command-line"></a><span data-ttu-id="33581-129">명령줄에서 구성</span><span class="sxs-lookup"><span data-stu-id="33581-129">Configure from the command line</span></span>

<span data-ttu-id="33581-130">명령줄에서 제품 설정 제어 및 명령 시 검사 트리거와 같은 중요한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33581-130">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line.</span></span>

### <a name="global-options"></a><span data-ttu-id="33581-131">전역 옵션</span><span class="sxs-lookup"><span data-stu-id="33581-131">Global options</span></span>

<span data-ttu-id="33581-132">기본적으로 명령줄 도구는 결과를 사람이 읽을 수 있는 형식으로 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="33581-132">By default, the command-line tool outputs the result in human-readable format.</span></span> <span data-ttu-id="33581-133">또한 이 도구는 결과를 JSON으로 출력할 수 있습니다. 이는 자동화 시나리오에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="33581-133">In addition, the tool also supports outputting the result as JSON, which is useful for automation scenarios.</span></span> <span data-ttu-id="33581-134">출력을 JSON으로 변경하기 위해 다음 명령 `--output json` 중 한 개를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="33581-134">To change the output to JSON, pass `--output json` to any of the below commands.</span></span>

### <a name="supported-commands"></a><span data-ttu-id="33581-135">지원되는 명령</span><span class="sxs-lookup"><span data-stu-id="33581-135">Supported commands</span></span>

<span data-ttu-id="33581-136">다음 표에는 가장 일반적인 몇 가지 시나리오에 대한 명령이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="33581-136">The following table lists commands for some of the most common scenarios.</span></span> <span data-ttu-id="33581-137">터미널에서 `mdatp help` 실행하여 지원되는 명령의 전체 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33581-137">Run `mdatp help` from the Terminal to view the full list of supported commands.</span></span>

|<span data-ttu-id="33581-138">Group</span><span class="sxs-lookup"><span data-stu-id="33581-138">Group</span></span>                 |<span data-ttu-id="33581-139">시나리오</span><span class="sxs-lookup"><span data-stu-id="33581-139">Scenario</span></span>                                                |<span data-ttu-id="33581-140">명령</span><span class="sxs-lookup"><span data-stu-id="33581-140">Command</span></span>                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|<span data-ttu-id="33581-141">구성</span><span class="sxs-lookup"><span data-stu-id="33581-141">Configuration</span></span>         |<span data-ttu-id="33581-142">실시간 보호 켜기/끄기</span><span class="sxs-lookup"><span data-stu-id="33581-142">Turn on/off real-time protection</span></span>                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|<span data-ttu-id="33581-143">구성</span><span class="sxs-lookup"><span data-stu-id="33581-143">Configuration</span></span>         |<span data-ttu-id="33581-144">동작 모니터링 켜기/끄기</span><span class="sxs-lookup"><span data-stu-id="33581-144">Turn on/off behavior monitoring</span></span>                         |`mdatp config behavior-monitoring --value [enabled\|disabled]`
|<span data-ttu-id="33581-145">구성</span><span class="sxs-lookup"><span data-stu-id="33581-145">Configuration</span></span>         |<span data-ttu-id="33581-146">클라우드 보호 켜기/끄기</span><span class="sxs-lookup"><span data-stu-id="33581-146">Turn on/off cloud protection</span></span>                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|<span data-ttu-id="33581-147">구성</span><span class="sxs-lookup"><span data-stu-id="33581-147">Configuration</span></span>         |<span data-ttu-id="33581-148">제품 진단 켜기/끄기</span><span class="sxs-lookup"><span data-stu-id="33581-148">Turn on/off product diagnostics</span></span>                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|<span data-ttu-id="33581-149">구성</span><span class="sxs-lookup"><span data-stu-id="33581-149">Configuration</span></span>         |<span data-ttu-id="33581-150">자동 샘플 제출 켜기/끄기</span><span class="sxs-lookup"><span data-stu-id="33581-150">Turn on/off automatic sample submission</span></span>                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|<span data-ttu-id="33581-151">구성</span><span class="sxs-lookup"><span data-stu-id="33581-151">Configuration</span></span>         |<span data-ttu-id="33581-152">AV 수동 모드 켜기/끄기</span><span class="sxs-lookup"><span data-stu-id="33581-152">Turn on/off AV passive mode</span></span>                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|<span data-ttu-id="33581-153">구성</span><span class="sxs-lookup"><span data-stu-id="33581-153">Configuration</span></span>         |<span data-ttu-id="33581-154">파일 확장명에 대한 바이러스 백신 제외 추가/제거</span><span class="sxs-lookup"><span data-stu-id="33581-154">Add/remove an antivirus exclusion for a file extension</span></span>  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|<span data-ttu-id="33581-155">구성</span><span class="sxs-lookup"><span data-stu-id="33581-155">Configuration</span></span>         |<span data-ttu-id="33581-156">파일에 대한 바이러스 백신 제외 추가/제거</span><span class="sxs-lookup"><span data-stu-id="33581-156">Add/remove an antivirus exclusion for a file</span></span>            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|<span data-ttu-id="33581-157">구성</span><span class="sxs-lookup"><span data-stu-id="33581-157">Configuration</span></span>         |<span data-ttu-id="33581-158">디렉터리에 대한 바이러스 백신 제외 추가/제거</span><span class="sxs-lookup"><span data-stu-id="33581-158">Add/remove an antivirus exclusion for a directory</span></span>       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|<span data-ttu-id="33581-159">구성</span><span class="sxs-lookup"><span data-stu-id="33581-159">Configuration</span></span>         |<span data-ttu-id="33581-160">프로세스에 대한 바이러스 백신 제외 추가/제거</span><span class="sxs-lookup"><span data-stu-id="33581-160">Add/remove an antivirus exclusion for a process</span></span>         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|<span data-ttu-id="33581-161">구성</span><span class="sxs-lookup"><span data-stu-id="33581-161">Configuration</span></span>         |<span data-ttu-id="33581-162">모든 바이러스 백신 제외 목록</span><span class="sxs-lookup"><span data-stu-id="33581-162">List all antivirus exclusions</span></span>                           |`mdatp exclusion list`                                                 |
|<span data-ttu-id="33581-163">구성</span><span class="sxs-lookup"><span data-stu-id="33581-163">Configuration</span></span>         |<span data-ttu-id="33581-164">허용 목록에 위협 이름 추가</span><span class="sxs-lookup"><span data-stu-id="33581-164">Add a threat name to the allowed list</span></span>                   |`mdatp threat allowed add --name [threat-name]`                        |
|<span data-ttu-id="33581-165">구성</span><span class="sxs-lookup"><span data-stu-id="33581-165">Configuration</span></span>         |<span data-ttu-id="33581-166">허용된 목록에서 위협 이름 제거</span><span class="sxs-lookup"><span data-stu-id="33581-166">Remove a threat name from the allowed list</span></span>              |`mdatp threat allowed remove --name [threat-name]`                     |
|<span data-ttu-id="33581-167">구성</span><span class="sxs-lookup"><span data-stu-id="33581-167">Configuration</span></span>         |<span data-ttu-id="33581-168">허용된 모든 위협 이름 나열</span><span class="sxs-lookup"><span data-stu-id="33581-168">List all allowed threat names</span></span>                           |`mdatp threat allowed list`                                            |
|<span data-ttu-id="33581-169">구성</span><span class="sxs-lookup"><span data-stu-id="33581-169">Configuration</span></span>         |<span data-ttu-id="33581-170">PUA 보호 켜기</span><span class="sxs-lookup"><span data-stu-id="33581-170">Turn on PUA protection</span></span>                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|<span data-ttu-id="33581-171">구성</span><span class="sxs-lookup"><span data-stu-id="33581-171">Configuration</span></span>         |<span data-ttu-id="33581-172">PUA 보호 끄기</span><span class="sxs-lookup"><span data-stu-id="33581-172">Turn off PUA protection</span></span>                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|<span data-ttu-id="33581-173">구성</span><span class="sxs-lookup"><span data-stu-id="33581-173">Configuration</span></span>         |<span data-ttu-id="33581-174">PUA 보호에 대한 감사 모드 켜기</span><span class="sxs-lookup"><span data-stu-id="33581-174">Turn on audit mode for PUA protection</span></span>                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|<span data-ttu-id="33581-175">진단</span><span class="sxs-lookup"><span data-stu-id="33581-175">Diagnostics</span></span>           |<span data-ttu-id="33581-176">로그 수준 변경</span><span class="sxs-lookup"><span data-stu-id="33581-176">Change the log level</span></span>                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|<span data-ttu-id="33581-177">진단</span><span class="sxs-lookup"><span data-stu-id="33581-177">Diagnostics</span></span>           |<span data-ttu-id="33581-178">진단 로그 생성</span><span class="sxs-lookup"><span data-stu-id="33581-178">Generate diagnostic logs</span></span>                                |`mdatp diagnostic create --path [directory]`                           |
|<span data-ttu-id="33581-179">상태</span><span class="sxs-lookup"><span data-stu-id="33581-179">Health</span></span>                |<span data-ttu-id="33581-180">제품의 상태 확인</span><span class="sxs-lookup"><span data-stu-id="33581-180">Check the product's health</span></span>                              |`mdatp health`                                                         |
|<span data-ttu-id="33581-181">보호</span><span class="sxs-lookup"><span data-stu-id="33581-181">Protection</span></span>            |<span data-ttu-id="33581-182">경로 검사</span><span class="sxs-lookup"><span data-stu-id="33581-182">Scan a path</span></span>                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|<span data-ttu-id="33581-183">보호</span><span class="sxs-lookup"><span data-stu-id="33581-183">Protection</span></span>            |<span data-ttu-id="33581-184">빠른 검사 실행</span><span class="sxs-lookup"><span data-stu-id="33581-184">Do a quick scan</span></span>                                         |`mdatp scan quick`                                                     |
|<span data-ttu-id="33581-185">보호</span><span class="sxs-lookup"><span data-stu-id="33581-185">Protection</span></span>            |<span data-ttu-id="33581-186">전체 검사 실행</span><span class="sxs-lookup"><span data-stu-id="33581-186">Do a full scan</span></span>                                          |`mdatp scan full`                                                      |
|<span data-ttu-id="33581-187">보호</span><span class="sxs-lookup"><span data-stu-id="33581-187">Protection</span></span>            |<span data-ttu-id="33581-188">지속적인 주문형 검사 취소</span><span class="sxs-lookup"><span data-stu-id="33581-188">Cancel an ongoing on-demand scan</span></span>                        |`mdatp scan cancel`                                                    |
|<span data-ttu-id="33581-189">보호</span><span class="sxs-lookup"><span data-stu-id="33581-189">Protection</span></span>            |<span data-ttu-id="33581-190">보안 인텔리전스 업데이트 요청</span><span class="sxs-lookup"><span data-stu-id="33581-190">Request a security intelligence update</span></span>                  |`mdatp definitions update`                                             |
|<span data-ttu-id="33581-191">보호 기록</span><span class="sxs-lookup"><span data-stu-id="33581-191">Protection history</span></span>    |<span data-ttu-id="33581-192">전체 보호 기록 인쇄</span><span class="sxs-lookup"><span data-stu-id="33581-192">Print the full protection history</span></span>                       |`mdatp threat list`                                                    |
|<span data-ttu-id="33581-193">보호 기록</span><span class="sxs-lookup"><span data-stu-id="33581-193">Protection history</span></span>    |<span data-ttu-id="33581-194">위협 세부 정보 확인</span><span class="sxs-lookup"><span data-stu-id="33581-194">Get threat details</span></span>                                      |`mdatp threat get --id [threat-id]`                                    |
|<span data-ttu-id="33581-195">Quarantine management</span><span class="sxs-lookup"><span data-stu-id="33581-195">Quarantine management</span></span> |<span data-ttu-id="33581-196">모든 고지된 파일 나열</span><span class="sxs-lookup"><span data-stu-id="33581-196">List all quarantined files</span></span>                              |`mdatp threat quarantine list`                                         |
|<span data-ttu-id="33581-197">Quarantine management</span><span class="sxs-lookup"><span data-stu-id="33581-197">Quarantine management</span></span> |<span data-ttu-id="33581-198">Quarantine에서 모든 파일 제거</span><span class="sxs-lookup"><span data-stu-id="33581-198">Remove all files from the quarantine</span></span>                    |`mdatp threat quarantine remove-all`                                   |
|<span data-ttu-id="33581-199">Quarantine management</span><span class="sxs-lookup"><span data-stu-id="33581-199">Quarantine management</span></span> |<span data-ttu-id="33581-200">위협으로 감지된 파일 추가</span><span class="sxs-lookup"><span data-stu-id="33581-200">Add a file detected as a threat to the quarantine</span></span>       |`mdatp threat quarantine add --id [threat-id]`                         |
|<span data-ttu-id="33581-201">Quarantine management</span><span class="sxs-lookup"><span data-stu-id="33581-201">Quarantine management</span></span> |<span data-ttu-id="33581-202">위협으로 감지된 파일 제거</span><span class="sxs-lookup"><span data-stu-id="33581-202">Remove a file detected as a threat from the quarantine</span></span>  |`mdatp threat quarantine remove --id [threat-id]`                      |
|<span data-ttu-id="33581-203">Quarantine management</span><span class="sxs-lookup"><span data-stu-id="33581-203">Quarantine management</span></span> |<span data-ttu-id="33581-204">Quarantine에서 파일 복원</span><span class="sxs-lookup"><span data-stu-id="33581-204">Restore a file from the quarantine</span></span>                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|<span data-ttu-id="33581-205">끝점 검색 및 응답</span><span class="sxs-lookup"><span data-stu-id="33581-205">Endpoint Detection and Response</span></span> |<span data-ttu-id="33581-206">초기 미리 보기 설정(사용되지 않은)</span><span class="sxs-lookup"><span data-stu-id="33581-206">Set early preview (unused)</span></span>                    |`mdatp edr early-preview [enable|disable]`                             |
|<span data-ttu-id="33581-207">끝점 검색 및 응답</span><span class="sxs-lookup"><span data-stu-id="33581-207">Endpoint Detection and Response</span></span> |<span data-ttu-id="33581-208">group-id 설정</span><span class="sxs-lookup"><span data-stu-id="33581-208">Set group-id</span></span>                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|<span data-ttu-id="33581-209">끝점 검색 및 응답</span><span class="sxs-lookup"><span data-stu-id="33581-209">Endpoint Detection and Response</span></span> |<span data-ttu-id="33581-210">태그 설정/제거(지원되는 `GROUP` 태그만)</span><span class="sxs-lookup"><span data-stu-id="33581-210">Set/Remove tag, only `GROUP` supported</span></span>        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|<span data-ttu-id="33581-211">끝점 검색 및 응답</span><span class="sxs-lookup"><span data-stu-id="33581-211">Endpoint Detection and Response</span></span> |<span data-ttu-id="33581-212">목록 제외(루트)</span><span class="sxs-lookup"><span data-stu-id="33581-212">list exclusions (root)</span></span>                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="33581-213">끝점 포털 정보용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="33581-213">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="33581-214">끝점용 Defender 포털에는 다음과 같은 두 가지 범주의 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33581-214">In the Defender for Endpoint portal, you'll see two categories of information:</span></span>

- <span data-ttu-id="33581-215">다음을 비롯한 바이러스 백신 경고</span><span class="sxs-lookup"><span data-stu-id="33581-215">Antivirus alerts, including:</span></span>
  - <span data-ttu-id="33581-216">심각도</span><span class="sxs-lookup"><span data-stu-id="33581-216">Severity</span></span>
  - <span data-ttu-id="33581-217">검사 유형</span><span class="sxs-lookup"><span data-stu-id="33581-217">Scan type</span></span>
  - <span data-ttu-id="33581-218">장치 정보(호스트 이름, 장치 식별자, 테넌트 식별자, 앱 버전 및 OS 유형)</span><span class="sxs-lookup"><span data-stu-id="33581-218">Device information (hostname, device identifier, tenant identifier, app version, and OS type)</span></span>
  - <span data-ttu-id="33581-219">파일 정보(이름, 경로, 크기 및 해시)</span><span class="sxs-lookup"><span data-stu-id="33581-219">File information (name, path, size, and hash)</span></span>
  - <span data-ttu-id="33581-220">위협 정보(이름, 유형 및 상태)</span><span class="sxs-lookup"><span data-stu-id="33581-220">Threat information (name, type, and state)</span></span>
- <span data-ttu-id="33581-221">다음을 비롯한 장치 정보</span><span class="sxs-lookup"><span data-stu-id="33581-221">Device information, including:</span></span>
  - <span data-ttu-id="33581-222">장치 식별자</span><span class="sxs-lookup"><span data-stu-id="33581-222">Device identifier</span></span>
  - <span data-ttu-id="33581-223">테넌트 식별자</span><span class="sxs-lookup"><span data-stu-id="33581-223">Tenant identifier</span></span>
  - <span data-ttu-id="33581-224">앱 버전</span><span class="sxs-lookup"><span data-stu-id="33581-224">App version</span></span>
  - <span data-ttu-id="33581-225">Hostname(호스트 이름)</span><span class="sxs-lookup"><span data-stu-id="33581-225">Hostname</span></span>
  - <span data-ttu-id="33581-226">OS 유형</span><span class="sxs-lookup"><span data-stu-id="33581-226">OS type</span></span>
  - <span data-ttu-id="33581-227">OS 버전</span><span class="sxs-lookup"><span data-stu-id="33581-227">OS version</span></span>
  - <span data-ttu-id="33581-228">컴퓨터 모델</span><span class="sxs-lookup"><span data-stu-id="33581-228">Computer model</span></span>
  - <span data-ttu-id="33581-229">프로세서 아키텍처</span><span class="sxs-lookup"><span data-stu-id="33581-229">Processor architecture</span></span>
  - <span data-ttu-id="33581-230">디바이스가 가상 컴퓨터인지 여부</span><span class="sxs-lookup"><span data-stu-id="33581-230">Whether the device is a virtual machine</span></span>

### <a name="known-issues"></a><span data-ttu-id="33581-231">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="33581-231">Known issues</span></span>

- <span data-ttu-id="33581-232">제품이 예상대로 작동하고 있도 Microsoft Defender 보안 센터 정보 페이지에 "센서 데이터 없음, 통신 장애가 있습니다."가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33581-232">You might see "No sensor data, impaired communications" in the machine information page of the Microsoft Defender Security Center portal, even though the product is working as expected.</span></span> <span data-ttu-id="33581-233">We are working on addressing this issue.</span><span class="sxs-lookup"><span data-stu-id="33581-233">We are working on addressing this issue.</span></span>
- <span data-ttu-id="33581-234">로그온한 사용자가 로그인 포털에 Microsoft Defender 보안 센터 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33581-234">Logged on users do not appear in the Microsoft Defender Security Center portal.</span></span>
- <span data-ttu-id="33581-235">SUSE 배포에서 *libatomic1* 설치가 실패하면 OS가 등록되어 있는지 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33581-235">In SUSE distributions, if the installation of *libatomic1* fails, you should validate that your OS is registered:</span></span>

   ```bash
   sudo SUSEConnect --status-text
   ```
