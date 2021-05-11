---
title: Linux의 끝점용 Microsoft Defender 설치 문제 해결
ms.reviewer: ''
description: Linux의 끝점용 Microsoft Defender 설치 문제 해결
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, linux, 설치
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
ms.openlocfilehash: dc1e8707dc0810c0986698674a64e969792b5fb8
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311235"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="185af-104">Linux의 끝점용 Microsoft Defender 설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="185af-104">Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="185af-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="185af-105">**Applies to:**</span></span>
- [<span data-ttu-id="185af-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="185af-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="185af-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="185af-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="185af-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="185af-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="185af-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a><span data-ttu-id="185af-110">설치가 성공한지 확인</span><span class="sxs-lookup"><span data-stu-id="185af-110">Verify if installation succeeded</span></span>

<span data-ttu-id="185af-111">설치 시 오류가 발생하거나 패키지 관리자가 의미 있는 오류 메시지를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="185af-111">An error in installation may or may not result in a meaningful error message by the package manager.</span></span> <span data-ttu-id="185af-112">설치가 성공적이지 확인하려면 다음을 사용하여 설치 로그를 구하고 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-112">To verify if the installation succeeded, obtain and check the installation logs using:</span></span>

```bash
 sudo journalctl --no-pager | grep 'microsoft-mdatp' > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
```

<span data-ttu-id="185af-113">올바른 설치 날짜와 시간이 있는 이전 명령의 출력은 성공을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="185af-113">An output from the previous command with correct date and time of installation indicates success.</span></span>

<span data-ttu-id="185af-114">또한 [클라이언트 구성을 확인하여](linux-install-manually.md#client-configuration) 제품의 상태와 EICAR 텍스트 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-114">Also check the [Client configuration](linux-install-manually.md#client-configuration) to verify the health of the product and detect the EICAR text file.</span></span>

## <a name="make-sure-you-have-the-correct-package"></a><span data-ttu-id="185af-115">올바른 패키지가 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="185af-115">Make sure you have the correct package</span></span>

<span data-ttu-id="185af-116">설치하는 패키지는 호스트 배포 및 버전과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-116">Please mind that the package you are installing is matching the host distribution and version.</span></span>

| <span data-ttu-id="185af-117">package</span><span class="sxs-lookup"><span data-stu-id="185af-117">package</span></span>                       | <span data-ttu-id="185af-118">distribution</span><span class="sxs-lookup"><span data-stu-id="185af-118">distribution</span></span>                             |
|-------------------------------|------------------------------------------|
| <span data-ttu-id="185af-119">mdatp-rhel8. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="185af-119">mdatp-rhel8.Linux.x86_64.rpm</span></span>  | <span data-ttu-id="185af-120">Oracle, RHEL 및 CentOS 8.x</span><span class="sxs-lookup"><span data-stu-id="185af-120">Oracle, RHEL and CentOS 8.x</span></span>              |
| <span data-ttu-id="185af-121">mdatp-sles12. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="185af-121">mdatp-sles12.Linux.x86_64.rpm</span></span> | <span data-ttu-id="185af-122">SuSE Linux Enterprise Server 12.x</span><span class="sxs-lookup"><span data-stu-id="185af-122">SuSE Linux Enterprise Server 12.x</span></span>        |
| <span data-ttu-id="185af-123">mdatp-sles15. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="185af-123">mdatp-sles15.Linux.x86_64.rpm</span></span> | <span data-ttu-id="185af-124">SuSE Linux Enterprise Server 15.x</span><span class="sxs-lookup"><span data-stu-id="185af-124">SuSE Linux Enterprise Server 15.x</span></span>        |
| <span data-ttu-id="185af-125">mdatp. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="185af-125">mdatp.Linux.x86_64.rpm</span></span>        | <span data-ttu-id="185af-126">Oracle, RHEL 및 CentOS 7.x</span><span class="sxs-lookup"><span data-stu-id="185af-126">Oracle, RHEL and CentOS 7.x</span></span>              |
| <span data-ttu-id="185af-127">mdatp. Linux.x86_64.deb</span><span class="sxs-lookup"><span data-stu-id="185af-127">mdatp.Linux.x86_64.deb</span></span>        | <span data-ttu-id="185af-128">데비안 및 Ubuntu 16.04, 18.04 및 20.04</span><span class="sxs-lookup"><span data-stu-id="185af-128">Debian and Ubuntu 16.04, 18.04 and 20.04</span></span> |

<span data-ttu-id="185af-129">수동 [배포의 경우](linux-install-manually.md)올바른 배포판과 버전이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-129">For [manual deployment](linux-install-manually.md), make sure the correct distro and version had been chosen.</span></span>

## <a name="installation-failed"></a><span data-ttu-id="185af-130">설치 실패</span><span class="sxs-lookup"><span data-stu-id="185af-130">Installation failed</span></span>

<span data-ttu-id="185af-131">mdatp 서비스가 실행 중인지 확인:</span><span class="sxs-lookup"><span data-stu-id="185af-131">Check if the mdatp service is running:</span></span>

```bash
systemctl status mdatp
```

```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a><span data-ttu-id="185af-132">mdatp 서비스가 실행되고 있지 않은 경우 문제 해결 단계</span><span class="sxs-lookup"><span data-stu-id="185af-132">Steps to troubleshoot if mdatp service isn't running</span></span>

1. <span data-ttu-id="185af-133">"mdatp" 사용자가 존재하는지 확인:</span><span class="sxs-lookup"><span data-stu-id="185af-133">Check if "mdatp" user exists:</span></span>

    ```bash
    id "mdatp"
    ```

    <span data-ttu-id="185af-134">출력이 없는 경우 를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-134">If there’s no output, run</span></span>

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. <span data-ttu-id="185af-135">다음을 사용하여 서비스를 사용하도록 설정하고 다시 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="185af-135">Try enabling and restarting the service using:</span></span>

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. <span data-ttu-id="185af-136">이전 명령을 실행할 때 mdatp.service를 찾을 수 없는 경우 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-136">If mdatp.service isn't found upon running the previous command, run:</span></span>

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    <span data-ttu-id="185af-137">여기서 은 Ubuntu 및 데비안 배포를 위한 것이고 `<systemd_path>` `/lib/systemd/system` `/usr/lib/systemd/system` Rhel, CentOS, Oracle 및 SLES용입니다.</span><span class="sxs-lookup"><span data-stu-id="185af-137">where `<systemd_path>` is `/lib/systemd/system` for Ubuntu and Debian distributions and `/usr/lib/systemd/system` for Rhel, CentOS, Oracle and SLES.</span></span>
   <span data-ttu-id="185af-138">그런 다음 2단계를 다시 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-138">Then rerun step 2.</span></span>

4. <span data-ttu-id="185af-139">위의 단계가 작동하지 않는 경우 SELinux가 설치되어 있으며 실행 모드로 설정하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-139">If the above steps don’t work, check if SELinux is installed and in enforcing mode.</span></span> <span data-ttu-id="185af-140">이 경우 이를 사용(가급적) 또는 비활성화 모드로 설정해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="185af-140">If so, try setting it to permissive (preferably) or disabled mode.</span></span> <span data-ttu-id="185af-141">이 매개 변수는 파일에서 매개 변수를 "사용" 또는 "사용 안 하게"로 설정한 다음 다시 부팅하여 `SELINUX` `/etc/selinux/config` 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="185af-141">It can be done by setting the parameter `SELINUX` to "permissive" or "disabled" in `/etc/selinux/config` file, followed by reboot.</span></span> <span data-ttu-id="185af-142">자세한 내용은 selinux의 man-page를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="185af-142">Check the man-page of selinux for more details.</span></span>
<span data-ttu-id="185af-143">이제 2단계를 사용하여 mdatp 서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-143">Now try restarting the mdatp service using step 2.</span></span> <span data-ttu-id="185af-144">보안상의 이유로 구성 변경을 시도한 후 다시 시작한 후 즉시 구성 변경을 되버려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-144">Revert the configuration change immediately though for security reasons after trying it and reboot.</span></span>

5. <span data-ttu-id="185af-145">디렉터리가 기호 링크인 경우 에 `/opt` 대한 바인딩 탑재를 만드십시오. `/opt/microsoft`</span><span class="sxs-lookup"><span data-stu-id="185af-145">If `/opt` directory is a symbolic link, create a bind mount for `/opt/microsoft`.</span></span>

6. <span data-ttu-id="185af-146">데몬에 실행 권한이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="185af-146">Ensure that the daemon has executable permission.</span></span>

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="185af-147">데몬에 실행 권한이 없는 경우 다음을 사용하여 실행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-147">If the daemon doesn't have executable permissions, make it executable using:</span></span>

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="185af-148">2단계를 실행하여 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-148">and retry running step 2.</span></span>

7. <span data-ttu-id="185af-149">wdavdaemon을 포함하는 파일 시스템이 "noexec"로 탑재되어 있지 않은지 확인</span><span class="sxs-lookup"><span data-stu-id="185af-149">Ensure that the file system containing wdavdaemon isn't mounted with "noexec".</span></span>

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a><span data-ttu-id="185af-150">mdatp 서비스가 실행 중이지만 EICAR 텍스트 파일 검색이 작동하지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="185af-150">If mdatp service is running, but EICAR text file detection doesn't work</span></span>

1. <span data-ttu-id="185af-151">다음을 사용하여 파일 시스템 형식을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-151">Check the file system type using:</span></span>

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    <span data-ttu-id="185af-152">액세스 활동에 대해 현재 지원되는 파일 시스템은 여기에 [나열되어 있습니다.](microsoft-defender-endpoint-linux.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="185af-152">Currently supported file systems for on-access activity are listed [here](microsoft-defender-endpoint-linux.md#system-requirements).</span></span> <span data-ttu-id="185af-153">이러한 파일 시스템 외부의 파일은 검색되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="185af-153">Any files outside these file systems won't be scanned.</span></span>

## <a name="command-line-tool-mdatp-isnt-working"></a><span data-ttu-id="185af-154">명령줄 도구 "mdatp"가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="185af-154">Command-line tool “mdatp” isn't working</span></span>

1. <span data-ttu-id="185af-155">명령줄 도구를 실행하면 오류가 `mdatp` `command not found` 발생하면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-155">If running the command-line tool `mdatp` gives an error `command not found`, run the following command:</span></span>

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    <span data-ttu-id="185af-156">다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="185af-156">and try again.</span></span>

    <span data-ttu-id="185af-157">위의 단계 중 도움이 해결하지 못하면 진단 로그를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-157">If none of the above steps help, collect the diagnostic logs:</span></span>

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    <span data-ttu-id="185af-158">로그가 포함된 zip 파일의 경로가 출력으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="185af-158">Path to a zip file that contains the logs will be displayed as an output.</span></span> <span data-ttu-id="185af-159">이러한 로그를 사용하여 고객 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="185af-159">Reach out to our customer support with these logs.</span></span>
