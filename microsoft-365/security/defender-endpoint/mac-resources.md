---
title: Mac의 끝점용 Microsoft Defender 리소스
description: Mac의 끝점용 Microsoft Defender 리소스(제거 방법, 진단 로그 수집 방법, CLI 명령 및 제품에서 알려진 문제 포함)
keywords: microsoft, defender, Endpoint용 Microsoft Defender, mac, 설치, 배포, 제거, intune, jamf, macos, catalina, mojave, high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 34feeec0f8c34748678862b9aa7b20f84087eb5e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934528"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="0e1ff-104">macOS의 끝점용 Microsoft Defender 리소스</span><span class="sxs-lookup"><span data-stu-id="0e1ff-104">Resources for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0e1ff-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0e1ff-105">**Applies to:**</span></span>
- [<span data-ttu-id="0e1ff-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0e1ff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0e1ff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e1ff-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0e1ff-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="0e1ff-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0e1ff-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a><span data-ttu-id="0e1ff-110">진단 정보 수집</span><span class="sxs-lookup"><span data-stu-id="0e1ff-110">Collecting diagnostic information</span></span>

<span data-ttu-id="0e1ff-111">문제를 재현할 수 있는 경우 로깅 수준을 높이고, 시스템을 어느 정도 실행하고, 로깅 수준을 기본값으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-111">If you can reproduce a problem, increase the logging level, run the system for some time, and restore the logging level to the default.</span></span>

1. <span data-ttu-id="0e1ff-112">로깅 수준 증가:</span><span class="sxs-lookup"><span data-stu-id="0e1ff-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="0e1ff-113">문제 재현</span><span class="sxs-lookup"><span data-stu-id="0e1ff-113">Reproduce the problem</span></span>

3. <span data-ttu-id="0e1ff-114">를 `sudo mdatp diagnostic create` 실행하여 끝점 로그에 대한 Microsoft Defender를 백업합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-114">Run `sudo mdatp diagnostic create` to back up the Microsoft Defender for Endpoint logs.</span></span> <span data-ttu-id="0e1ff-115">파일은 .zip 보관 파일 안에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-115">The files will be stored inside a .zip archive.</span></span> <span data-ttu-id="0e1ff-116">또한 이 명령은 작업이 성공한 후 백업에 대한 파일 경로를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-116">This command will also print out the file path to the backup after the operation succeeds.</span></span>

   > [!TIP]
   > <span data-ttu-id="0e1ff-117">기본적으로 진단 로그는 에 `/Library/Application Support/Microsoft/Defender/wdavdiag/` 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-117">By default, diagnostic logs are saved to `/Library/Application Support/Microsoft/Defender/wdavdiag/`.</span></span> <span data-ttu-id="0e1ff-118">진단 로그가 저장되는 디렉터리를 변경하려면 아래 명령으로 전달하여 원하는 디렉터리로 `--path [directory]` `[directory]` 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-118">To change the directory where diagnostic logs are saved, pass `--path [directory]` to the below command, replacing `[directory]` with the desired directory.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```
   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. <span data-ttu-id="0e1ff-119">로깅 수준 복원:</span><span class="sxs-lookup"><span data-stu-id="0e1ff-119">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a><span data-ttu-id="0e1ff-120">로깅 설치 문제</span><span class="sxs-lookup"><span data-stu-id="0e1ff-120">Logging installation issues</span></span>

<span data-ttu-id="0e1ff-121">설치 중에 오류가 발생하면 설치 관리자에서 일반적인 오류만 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-121">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="0e1ff-122">자세한 로그는 에 `/Library/Logs/Microsoft/mdatp/install.log` 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-122">The detailed log will be saved to `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="0e1ff-123">설치 중에 문제가 발생하면 이 파일을 보내 원인을 진단하는 데 도움을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-123">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstalling"></a><span data-ttu-id="0e1ff-124">Uninstalling</span><span class="sxs-lookup"><span data-stu-id="0e1ff-124">Uninstalling</span></span>

<span data-ttu-id="0e1ff-125">macOS에서 끝점용 Microsoft Defender를 제거하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-125">There are several ways to uninstall Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="0e1ff-126">JAMF에서는 중앙에서 관리되는 제거를 사용할 수 있는 반면 Microsoft Intune에서는 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-126">Note that while centrally managed uninstall is available on JAMF, it is not yet available for Microsoft Intune.</span></span>

### <a name="interactive-uninstallation"></a><span data-ttu-id="0e1ff-127">대화형 제거</span><span class="sxs-lookup"><span data-stu-id="0e1ff-127">Interactive uninstallation</span></span>

- <span data-ttu-id="0e1ff-128">Open **Finder > Applications**.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-128">Open **Finder > Applications**.</span></span> <span data-ttu-id="0e1ff-129">**Endpoint용 Microsoft Defender를 마우스 오른쪽 단추로 > 휴지통으로 이동을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0e1ff-129">Right click on **Microsoft Defender for Endpoint > Move to Trash**.</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="0e1ff-130">명령줄에서</span><span class="sxs-lookup"><span data-stu-id="0e1ff-130">From the command line</span></span>

- ```sudo rm -rf '/Applications/Microsoft Defender ATP.app'```
- ```sudo rm -rf '/Library/Application Support/Microsoft/Defender/'```

## <a name="configuring-from-the-command-line"></a><span data-ttu-id="0e1ff-131">명령줄에서 구성</span><span class="sxs-lookup"><span data-stu-id="0e1ff-131">Configuring from the command line</span></span>

<span data-ttu-id="0e1ff-132">명령줄에서 제품 설정 제어 및 명령 시 검사 트리거와 같은 중요한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-132">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line:</span></span>

|<span data-ttu-id="0e1ff-133">Group</span><span class="sxs-lookup"><span data-stu-id="0e1ff-133">Group</span></span>        |<span data-ttu-id="0e1ff-134">시나리오</span><span class="sxs-lookup"><span data-stu-id="0e1ff-134">Scenario</span></span>                                   |<span data-ttu-id="0e1ff-135">명령</span><span class="sxs-lookup"><span data-stu-id="0e1ff-135">Command</span></span>                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|<span data-ttu-id="0e1ff-136">구성</span><span class="sxs-lookup"><span data-stu-id="0e1ff-136">Configuration</span></span>|<span data-ttu-id="0e1ff-137">실시간 보호 켜기/끄기</span><span class="sxs-lookup"><span data-stu-id="0e1ff-137">Turn on/off real-time protection</span></span>           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|<span data-ttu-id="0e1ff-138">구성</span><span class="sxs-lookup"><span data-stu-id="0e1ff-138">Configuration</span></span>|<span data-ttu-id="0e1ff-139">클라우드 보호 켜기/끄기</span><span class="sxs-lookup"><span data-stu-id="0e1ff-139">Turn on/off cloud protection</span></span>               |`mdatp config cloud --value [enabled/disabled]`                                   |
|<span data-ttu-id="0e1ff-140">구성</span><span class="sxs-lookup"><span data-stu-id="0e1ff-140">Configuration</span></span>|<span data-ttu-id="0e1ff-141">제품 진단 켜기/끄기</span><span class="sxs-lookup"><span data-stu-id="0e1ff-141">Turn on/off product diagnostics</span></span>            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|<span data-ttu-id="0e1ff-142">구성</span><span class="sxs-lookup"><span data-stu-id="0e1ff-142">Configuration</span></span>|<span data-ttu-id="0e1ff-143">자동 샘플 제출 켜기/끄기</span><span class="sxs-lookup"><span data-stu-id="0e1ff-143">Turn on/off automatic sample submission</span></span>    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|<span data-ttu-id="0e1ff-144">구성</span><span class="sxs-lookup"><span data-stu-id="0e1ff-144">Configuration</span></span>|<span data-ttu-id="0e1ff-145">허용 목록에 위협 이름 추가</span><span class="sxs-lookup"><span data-stu-id="0e1ff-145">Add a threat name to the allowed list</span></span>      |`mdatp threat allowed add --name [threat-name]`                                   |
|<span data-ttu-id="0e1ff-146">구성</span><span class="sxs-lookup"><span data-stu-id="0e1ff-146">Configuration</span></span>|<span data-ttu-id="0e1ff-147">허용된 목록에서 위협 이름 제거</span><span class="sxs-lookup"><span data-stu-id="0e1ff-147">Remove a threat name from the allowed list</span></span> |`mdatp threat allowed remove --name [threat-name]`                                |
|<span data-ttu-id="0e1ff-148">구성</span><span class="sxs-lookup"><span data-stu-id="0e1ff-148">Configuration</span></span>|<span data-ttu-id="0e1ff-149">허용된 모든 위협 이름 나열</span><span class="sxs-lookup"><span data-stu-id="0e1ff-149">List all allowed threat names</span></span>              |`mdatp threat allowed list`                                                       |
|<span data-ttu-id="0e1ff-150">구성</span><span class="sxs-lookup"><span data-stu-id="0e1ff-150">Configuration</span></span>|<span data-ttu-id="0e1ff-151">PUA 보호 켜기</span><span class="sxs-lookup"><span data-stu-id="0e1ff-151">Turn on PUA protection</span></span>                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|<span data-ttu-id="0e1ff-152">구성</span><span class="sxs-lookup"><span data-stu-id="0e1ff-152">Configuration</span></span>|<span data-ttu-id="0e1ff-153">PUA 보호 끄기</span><span class="sxs-lookup"><span data-stu-id="0e1ff-153">Turn off PUA protection</span></span>                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|<span data-ttu-id="0e1ff-154">구성</span><span class="sxs-lookup"><span data-stu-id="0e1ff-154">Configuration</span></span>|<span data-ttu-id="0e1ff-155">PUA 보호에 대한 감사 모드 켜기</span><span class="sxs-lookup"><span data-stu-id="0e1ff-155">Turn on audit mode for PUA protection</span></span>      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|<span data-ttu-id="0e1ff-156">구성</span><span class="sxs-lookup"><span data-stu-id="0e1ff-156">Configuration</span></span>|<span data-ttu-id="0e1ff-157">PassiveMode 켜기/끄기</span><span class="sxs-lookup"><span data-stu-id="0e1ff-157">Turn on/off passiveMode</span></span>                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|<span data-ttu-id="0e1ff-158">진단</span><span class="sxs-lookup"><span data-stu-id="0e1ff-158">Diagnostics</span></span>  |<span data-ttu-id="0e1ff-159">로그 수준 변경</span><span class="sxs-lookup"><span data-stu-id="0e1ff-159">Change the log level</span></span>                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|<span data-ttu-id="0e1ff-160">진단</span><span class="sxs-lookup"><span data-stu-id="0e1ff-160">Diagnostics</span></span>  |<span data-ttu-id="0e1ff-161">진단 로그 생성</span><span class="sxs-lookup"><span data-stu-id="0e1ff-161">Generate diagnostic logs</span></span>                   |`mdatp diagnostic create --path [directory]`                                      |
|<span data-ttu-id="0e1ff-162">상태</span><span class="sxs-lookup"><span data-stu-id="0e1ff-162">Health</span></span>       |<span data-ttu-id="0e1ff-163">제품의 상태 확인</span><span class="sxs-lookup"><span data-stu-id="0e1ff-163">Check the product's health</span></span>                 |`mdatp health`                                                                    |
|<span data-ttu-id="0e1ff-164">상태</span><span class="sxs-lookup"><span data-stu-id="0e1ff-164">Health</span></span>       |<span data-ttu-id="0e1ff-165">spefic 제품 특성 확인</span><span class="sxs-lookup"><span data-stu-id="0e1ff-165">Check for a spefic product attribute</span></span>       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|<span data-ttu-id="0e1ff-166">보호</span><span class="sxs-lookup"><span data-stu-id="0e1ff-166">Protection</span></span>   |<span data-ttu-id="0e1ff-167">경로 검사</span><span class="sxs-lookup"><span data-stu-id="0e1ff-167">Scan a path</span></span>                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|<span data-ttu-id="0e1ff-168">보호</span><span class="sxs-lookup"><span data-stu-id="0e1ff-168">Protection</span></span>   |<span data-ttu-id="0e1ff-169">빠른 검사 실행</span><span class="sxs-lookup"><span data-stu-id="0e1ff-169">Do a quick scan</span></span>                            |`mdatp scan quick`                                                                |
|<span data-ttu-id="0e1ff-170">보호</span><span class="sxs-lookup"><span data-stu-id="0e1ff-170">Protection</span></span>   |<span data-ttu-id="0e1ff-171">전체 검사 실행</span><span class="sxs-lookup"><span data-stu-id="0e1ff-171">Do a full scan</span></span>                             |`mdatp scan full`                                                                 |
|<span data-ttu-id="0e1ff-172">보호</span><span class="sxs-lookup"><span data-stu-id="0e1ff-172">Protection</span></span>   |<span data-ttu-id="0e1ff-173">지속적인 주문형 검사 취소</span><span class="sxs-lookup"><span data-stu-id="0e1ff-173">Cancel an ongoing on-demand scan</span></span>           |`mdatp scan cancel`                                                               |
|<span data-ttu-id="0e1ff-174">보호</span><span class="sxs-lookup"><span data-stu-id="0e1ff-174">Protection</span></span>   |<span data-ttu-id="0e1ff-175">보안 인텔리전스 업데이트 요청</span><span class="sxs-lookup"><span data-stu-id="0e1ff-175">Request a security intelligence update</span></span>     |`mdatp definitions update`                                                        |
|<span data-ttu-id="0e1ff-176">EDR</span><span class="sxs-lookup"><span data-stu-id="0e1ff-176">EDR</span></span>          |<span data-ttu-id="0e1ff-177">디바이스에 그룹 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-177">Add group tag to device.</span></span> <span data-ttu-id="0e1ff-178">EDR 태그는 장치 그룹을 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-178">EDR tags are used for managing device groups.</span></span> <span data-ttu-id="0e1ff-179">자세한 내용은 https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span><span class="sxs-lookup"><span data-stu-id="0e1ff-179">For more information, please visit https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span></span> |`mdatp edr tag set --name GROUP --value [name]` |
|<span data-ttu-id="0e1ff-180">EDR</span><span class="sxs-lookup"><span data-stu-id="0e1ff-180">EDR</span></span>          |<span data-ttu-id="0e1ff-181">장치에서 그룹 태그 제거</span><span class="sxs-lookup"><span data-stu-id="0e1ff-181">Remove group tag from device</span></span>               |`mdatp edr tag remove --tag-name [name]`                                          |
|<span data-ttu-id="0e1ff-182">EDR</span><span class="sxs-lookup"><span data-stu-id="0e1ff-182">EDR</span></span>          |<span data-ttu-id="0e1ff-183">그룹 ID 추가</span><span class="sxs-lookup"><span data-stu-id="0e1ff-183">Add Group ID</span></span>                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a><span data-ttu-id="0e1ff-184">자동 작성을 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="0e1ff-184">How to enable autocompletion</span></span>

<span data-ttu-id="0e1ff-185">bash에서 자동completion을 사용하도록 설정하려면 다음 명령을 실행하고 터미널 세션을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-185">To enable autocompletion in bash, run the following command and restart the Terminal session:</span></span>

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

<span data-ttu-id="0e1ff-186">zsh에서 자동completion을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="0e1ff-186">To enable autocompletion in zsh:</span></span>

- <span data-ttu-id="0e1ff-187">장치에서 자동completion을 사용할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-187">Check whether autocompletion is enabled on your device:</span></span>

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- <span data-ttu-id="0e1ff-188">위의 명령이 출력을 생성하지 않는 경우 다음 명령을 사용하여 자동 작성을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-188">If the preceding command does not produce any output, you can enable autocompletion using the following command:</span></span>

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- <span data-ttu-id="0e1ff-189">MacOS의 끝점용 Microsoft Defender에 대해 자동Completion을 사용하도록 설정하려면 다음 명령을 실행하고 터미널 세션을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-189">Run the following commands to enable autocompletion for Microsoft Defender for Endpoint on macOS and restart the Terminal session:</span></span>

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a><span data-ttu-id="0e1ff-190">클라이언트 Microsoft Defender for Endpoint quarantine directory</span><span class="sxs-lookup"><span data-stu-id="0e1ff-190">Client Microsoft Defender for Endpoint quarantine directory</span></span>

<span data-ttu-id="0e1ff-191">`/Library/Application Support/Microsoft/Defender/quarantine/` 에 의해 검색된 파일이 들어 `mdatp` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contains the files quarantined by `mdatp`.</span></span> <span data-ttu-id="0e1ff-192">파일의 이름은 Threat trackingId의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-192">The files are named after the threat trackingId.</span></span> <span data-ttu-id="0e1ff-193">현재 trackingIds는 와 함께 `mdatp threat list` 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-193">The current trackingIds is shown with `mdatp threat list`.</span></span>

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="0e1ff-194">끝점 포털 정보용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0e1ff-194">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="0e1ff-195">[MacOS용 EDR](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)기능이 끝점용 Microsoft Defender 블로그에 도착했습니다. 끝점용 Microsoft Defender 보안 센터에서 기대할 수 있는 기능에 대한 자세한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1ff-195">[EDR capabilities for macOS have now arrived](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), on the Microsoft Defender for Endpoint blog, provides detailed guidance on what to expect in Microsoft Defender for Endpoint Security Center.</span></span>
