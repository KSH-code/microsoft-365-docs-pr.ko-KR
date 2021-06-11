---
title: Linux에서 끝점용 Microsoft Defender 제외 구성 및 유효성 검사
description: Linux에서 끝점용 Microsoft Defender 제외를 제공하고 유효성을 검사합니다. 파일, 폴더 및 프로세스에 대해 제외를 설정할 수 있습니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, linux, 제외, 검사, 바이러스 백신
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
ms.openlocfilehash: bd506caa041af2585778fb3ecd7a40562463b17e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346417"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="4ea34-105">Linux에서 끝점용 Microsoft Defender 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="4ea34-105">Configure and validate exclusions for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4ea34-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4ea34-106">**Applies to:**</span></span>

- [<span data-ttu-id="4ea34-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4ea34-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4ea34-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ea34-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4ea34-109">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="4ea34-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4ea34-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="4ea34-111">이 문서에서는 요구 시 검사에 적용되는 제외를 정의하는 방법과 실시간 보호 및 모니터링에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ea34-112">이 문서에 설명된 제외는 끝점 감지 및 응답(EDR)을 포함하여 Linux 기능의 다른 Endpoint용 Defender에는 적용되지 EDR.</span><span class="sxs-lookup"><span data-stu-id="4ea34-112">The exclusions described in this article don't apply to other Defender for Endpoint on Linux capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="4ea34-113">이 문서에 설명된 방법을 사용하여 제외하는 파일은 경고 및 기타 EDR 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="4ea34-114">Linux 검사에서 Endpoint용 Defender에서 특정 파일, 폴더, 프로세스 및 프로세스 열기 파일을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint on Linux scans.</span></span>

<span data-ttu-id="4ea34-115">제외는 조직에서 고유하거나 사용자 지정된 파일 또는 소프트웨어에서 잘못된 검색을 방지하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="4ea34-116">Linux의 끝점용 Defender로 인한 성능 문제를 완화하는 데에도 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint on Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="4ea34-117">제외를 정의할 경우 Linux의 끝점에 대한 Defender에서 제공하는 보호가 낮아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-117">Defining exclusions lowers the protection offered by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="4ea34-118">제외 구현과 관련된 위험을 항상 평가해야 합니다. 또한 악의적이지 않다고 확신하는 파일만 제외해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="4ea34-119">지원되는 제외 유형</span><span class="sxs-lookup"><span data-stu-id="4ea34-119">Supported exclusion types</span></span>

<span data-ttu-id="4ea34-120">다음 표에는 Linux의 Endpoint용 Defender에서 지원하는 제외 유형이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-120">The follow table shows the exclusion types supported by Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="4ea34-121">제외</span><span class="sxs-lookup"><span data-stu-id="4ea34-121">Exclusion</span></span> | <span data-ttu-id="4ea34-122">정의</span><span class="sxs-lookup"><span data-stu-id="4ea34-122">Definition</span></span> | <span data-ttu-id="4ea34-123">예제</span><span class="sxs-lookup"><span data-stu-id="4ea34-123">Examples</span></span>
---|---|---
<span data-ttu-id="4ea34-124">파일 확장명</span><span class="sxs-lookup"><span data-stu-id="4ea34-124">File extension</span></span> | <span data-ttu-id="4ea34-125">디바이스의 아무 곳이나 확장명을 사용하여 모든 파일</span><span class="sxs-lookup"><span data-stu-id="4ea34-125">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="4ea34-126">파일</span><span class="sxs-lookup"><span data-stu-id="4ea34-126">File</span></span> | <span data-ttu-id="4ea34-127">전체 경로로 식별된 특정 파일</span><span class="sxs-lookup"><span data-stu-id="4ea34-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="4ea34-128">폴더</span><span class="sxs-lookup"><span data-stu-id="4ea34-128">Folder</span></span> | <span data-ttu-id="4ea34-129">지정된 폴더에 있는 모든 파일(재발성)</span><span class="sxs-lookup"><span data-stu-id="4ea34-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="4ea34-130">프로세스</span><span class="sxs-lookup"><span data-stu-id="4ea34-130">Process</span></span> | <span data-ttu-id="4ea34-131">전체 경로 또는 파일 이름으로 지정된 특정 프로세스 및 이 프로세스에서 연 모든 파일</span><span class="sxs-lookup"><span data-stu-id="4ea34-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="4ea34-132">위의 경로는 기호 링크가 아니라 하드 링크되어야만 성공적으로 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-132">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="4ea34-133">를 실행하여 경로가 기호 링크인지 확인할 수 `file <path-name>` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-133">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="4ea34-134">파일, 폴더 및 프로세스 제외는 다음 와일드카드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-134">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="4ea34-135">와일드카드</span><span class="sxs-lookup"><span data-stu-id="4ea34-135">Wildcard</span></span> | <span data-ttu-id="4ea34-136">설명</span><span class="sxs-lookup"><span data-stu-id="4ea34-136">Description</span></span> | <span data-ttu-id="4ea34-137">예제</span><span class="sxs-lookup"><span data-stu-id="4ea34-137">Example</span></span> | <span data-ttu-id="4ea34-138">일치</span><span class="sxs-lookup"><span data-stu-id="4ea34-138">Matches</span></span> | <span data-ttu-id="4ea34-139">일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-139">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="4ea34-140">none을 포함한 모든 문자와 일치합니다(경로 내에서 이 와일드카드를 사용하는 경우 폴더 하나만 대체).</span><span class="sxs-lookup"><span data-stu-id="4ea34-140">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="4ea34-141">?</span><span class="sxs-lookup"><span data-stu-id="4ea34-141">?</span></span> | <span data-ttu-id="4ea34-142">단일 문자와 일치</span><span class="sxs-lookup"><span data-stu-id="4ea34-142">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="4ea34-143">제외 목록을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="4ea34-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="4ea34-144">관리 콘솔에서</span><span class="sxs-lookup"><span data-stu-id="4ea34-144">From the management console</span></span>

<span data-ttu-id="4ea34-145">Puppet, Ansible 또는 다른 관리 콘솔에서 제외를 구성하는 방법에 대한 자세한 내용은 [Linux에서 끝점용 Defender에](linux-preferences.md)대한 기본 설정 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ea34-145">For more information on how to configure exclusions from Puppet, Ansible, or another management console, see [Set preferences for Defender for Endpoint on Linux](linux-preferences.md).</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="4ea34-146">명령줄에서</span><span class="sxs-lookup"><span data-stu-id="4ea34-146">From the command line</span></span>

<span data-ttu-id="4ea34-147">다음 명령을 실행하여 제외를 관리하는 데 사용할 수 있는 스위치를 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-147">Run the following command to see the available switches for managing exclusions:</span></span>

```bash
mdatp exclusion
```

> [!TIP]
> <span data-ttu-id="4ea34-148">와일드카드로 제외를 구성할 때 매개 변수를 따옴표로 묶어 글로브링을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-148">When configuring exclusions with wildcards, enclose the parameter in double-quotes to prevent globbing.</span></span>

<span data-ttu-id="4ea34-149">예제:</span><span class="sxs-lookup"><span data-stu-id="4ea34-149">Examples:</span></span>

- <span data-ttu-id="4ea34-150">파일 확장명에 대한 제외를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-150">Add an exclusion for a file extension:</span></span>

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- <span data-ttu-id="4ea34-151">파일에 대한 제외를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-151">Add an exclusion for a file:</span></span>

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- <span data-ttu-id="4ea34-152">폴더에 대한 제외를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-152">Add an exclusion for a folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="4ea34-153">와일드카드가 있는 폴더에 대한 제외를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-153">Add an exclusion for a folder with a wildcard in it:</span></span>

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > <span data-ttu-id="4ea34-154">이 경우 */var/ 아래의* 한 수준만 경로가 제외되지만 더 깊이 중첩된 폴더는 제외됩니다. 예를 들어 */var/this-subfolder/but-not-this-subfolder입니다.*</span><span class="sxs-lookup"><span data-stu-id="4ea34-154">This will only exclude paths one level below */var/*, but not folders which are more deeply nested; for example, */var/this-subfolder/but-not-this-subfolder*.</span></span>
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > <span data-ttu-id="4ea34-155">그러면 부모가 */var/ 인 모든 경로가 제외됩니다.* 예: */var/this-subfolder/and-this-subfolder-as-well*.</span><span class="sxs-lookup"><span data-stu-id="4ea34-155">This will exclude all paths whose parent is */var/*; for example, */var/this-subfolder/and-this-subfolder-as-well*.</span></span>

    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="4ea34-156">프로세스에 대한 제외를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-156">Add an exclusion for a process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="4ea34-157">EICAR 테스트 파일을 사용하여 제외 목록 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="4ea34-157">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="4ea34-158">테스트 파일을 다운로드하는 데 사용하여 제외 목록이 작동하고 있는지 확인할 `curl` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-158">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="4ea34-159">다음 Bash 코드 코드에서는 제외 규칙을 준수하는 파일로 `test.txt` 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-159">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="4ea34-160">예를 들어 확장을 제외한 `.testing` 경우 를 로 `test.txt` 바) `test.testing` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-160">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="4ea34-161">경로를 테스트하는 경우 해당 경로 내에서 명령을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-161">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="4ea34-162">Linux의 끝점용 Defender가 맬웨어를 보고하면 규칙이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-162">If Defender for Endpoint on Linux reports malware, then the rule is not working.</span></span> <span data-ttu-id="4ea34-163">맬웨어에 대한 보고서가 없는 경우 다운로드한 파일이 있는 경우 제외가 작동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-163">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="4ea34-164">파일을 열어 [EICAR](http://2016.eicar.org/86-0-Intended-use.html)테스트 파일 웹 사이트에 설명된 내용과 동일한지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-164">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="4ea34-165">인터넷에 액세스할 수 없는 경우 자체 EICAR 테스트 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-165">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="4ea34-166">다음 Bash 명령을 사용하여 새 텍스트 파일에 EICAR 문자열을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-166">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="4ea34-167">또한 문자열을 빈 텍스트 파일에 복사하여 파일 이름이나 제외하려는 폴더에 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-167">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="4ea34-168">위협 허용</span><span class="sxs-lookup"><span data-stu-id="4ea34-168">Allow threats</span></span>

<span data-ttu-id="4ea34-169">특정 콘텐츠를 검사하지 못하도록 제외하는 것 외에도 일부 위협 클래스(위협 이름로 식별)를 검색하지 못하도록 제품을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-169">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="4ea34-170">이 기능을 사용할 때는 장치가 보호되지 않은 것으로 남을 수 있는 경우 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-170">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="4ea34-171">허용 목록에 위협 이름을 추가하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-171">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="4ea34-172">장치의 검색과 관련된 위협 이름은 다음 명령을 사용하여 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-172">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="4ea34-173">예를 들어 허용 목록에 추가(EICAR 검색과 연결된 위협 이름)를 추가하기 위해 `EICAR-Test-File (not a virus)` 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea34-173">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
