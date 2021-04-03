---
title: 엔드포인트용 Microsoft Defender(Linux)
ms.reviewer: ''
description: Linux용 Microsoft Defender ATP를 설치하고 사용하는 방법에 대해 설명
keywords: microsoft, defender, atp, linux, 설치, 배포, 제거, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: cc2f5be700395f6d88c05481d74501f4d9d92b76
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500671"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="73654-104">엔드포인트용 Microsoft Defender(Linux)</span><span class="sxs-lookup"><span data-stu-id="73654-104">Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="73654-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="73654-105">**Applies to:**</span></span>
- [<span data-ttu-id="73654-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="73654-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="73654-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73654-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="73654-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="73654-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="73654-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="73654-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="73654-110">이 항목에서는 Linux용 끝점용 Microsoft Defender를 설치, 구성, 업데이트 및 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73654-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint for Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="73654-111">Linux용 Endpoint용 Microsoft Defender와 함께 다른 타사 끝점 보호 제품을 실행하면 성능 문제와 예측할 수 없는 부작용이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73654-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint for Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="73654-112">사용자 환경에서 Microsoft가 아닌 엔드포인트 보호가 절대적인 요구 사항이면 수동 모드에서 실행될 바이러스 백신 기능을 구성한 후에도 Linux EDR 기능에 대한 Endpoint용 Defender를 안전하게 활용할 [수 있습니다.](linux-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="73654-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint for Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="73654-113">Linux용 끝점용 Microsoft Defender를 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="73654-113">How to install Microsoft Defender for Endpoint for Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="73654-114">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="73654-114">Prerequisites</span></span>

- <span data-ttu-id="73654-115">Microsoft Defender 보안 센터 포털에 액세스</span><span class="sxs-lookup"><span data-stu-id="73654-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="73654-116">시스템 [관리자를](https://systemd.io/) 사용하여 Linux 배포</span><span class="sxs-lookup"><span data-stu-id="73654-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="73654-117">Linux 및 BASH 스크립팅의 초보자 수준 환경</span><span class="sxs-lookup"><span data-stu-id="73654-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="73654-118">디바이스의 관리 권한(수동 배포의 경우)</span><span class="sxs-lookup"><span data-stu-id="73654-118">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="73654-119">설치 지침</span><span class="sxs-lookup"><span data-stu-id="73654-119">Installation instructions</span></span>

<span data-ttu-id="73654-120">Linux용 끝점용 Microsoft Defender를 설치하고 구성하는 데 사용할 수 있는 몇 가지 방법 및 배포 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73654-120">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="73654-121">일반적으로 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73654-121">In general you need to take the following steps:</span></span>

- <span data-ttu-id="73654-122">Endpoint용 Microsoft Defender 구독이 있으며 끝점 포털용 [Microsoft Defender에](microsoft-defender-security-center.md)액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="73654-122">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="73654-123">다음 배포 방법 중 하나를 사용하여 Linux용 끝점용 Microsoft Defender를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="73654-123">Deploy Microsoft Defender for Endpoint for Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="73654-124">명령줄 도구:</span><span class="sxs-lookup"><span data-stu-id="73654-124">The command-line tool:</span></span>
    - [<span data-ttu-id="73654-125">수동 배포</span><span class="sxs-lookup"><span data-stu-id="73654-125">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="73654-126">타사 관리 도구:</span><span class="sxs-lookup"><span data-stu-id="73654-126">Third-party management tools:</span></span>
    - [<span data-ttu-id="73654-127">Puppet 구성 관리 도구를 사용하여 배포</span><span class="sxs-lookup"><span data-stu-id="73654-127">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="73654-128">Ansible 구성 관리 도구를 사용하여 배포</span><span class="sxs-lookup"><span data-stu-id="73654-128">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="73654-129">설치 오류가 발생하면 [Linux용 끝점용 Microsoft Defender의](linux-support-install.md)설치 실패 문제 해결을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73654-129">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="73654-130">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="73654-130">System requirements</span></span>

- <span data-ttu-id="73654-131">지원되는 Linux 서버 배포 및 버전:</span><span class="sxs-lookup"><span data-stu-id="73654-131">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="73654-132">Red Hat Enterprise Linux 7.2 이상</span><span class="sxs-lookup"><span data-stu-id="73654-132">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="73654-133">CentOS 7.2 이상</span><span class="sxs-lookup"><span data-stu-id="73654-133">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="73654-134">Ubuntu 16.04 LTS 이상 LTS</span><span class="sxs-lookup"><span data-stu-id="73654-134">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="73654-135">데비안 9 이상</span><span class="sxs-lookup"><span data-stu-id="73654-135">Debian 9 or higher</span></span>
  - <span data-ttu-id="73654-136">SUSE Linux Enterprise Server 12 이상</span><span class="sxs-lookup"><span data-stu-id="73654-136">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="73654-137">Oracle Linux 7.2 이상</span><span class="sxs-lookup"><span data-stu-id="73654-137">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="73654-138">최소 커널 버전 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="73654-138">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="73654-139">커널 `fanotify` 옵션을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73654-139">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="73654-140">Linux용 끝점용 Defender를 다른 기반 보안 솔루션과 함께 실행하는 `fanotify` 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73654-140">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="73654-141">운영 체제 중단을 포함하여 예측할 수 없는 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73654-141">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="73654-142">디스크 공간: 1GB</span><span class="sxs-lookup"><span data-stu-id="73654-142">Disk space: 1GB</span></span>
- <span data-ttu-id="73654-143">/opt/microsoft/mdatp/sbin/wdavdaemon에는 실행 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="73654-143">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="73654-144">자세한 내용은 [Linux용 Microsoft Defender ATP](/microsoft-365/security/defender-endpoint/linux-support-install)설치 문제 해결에서 "디먼에 실행 권한이 있도록 확인"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73654-144">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender ATP for Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>
- <span data-ttu-id="73654-145">메모리: 1GB</span><span class="sxs-lookup"><span data-stu-id="73654-145">Memory: 1GB</span></span>
    > [!NOTE]
    > <span data-ttu-id="73654-146">/var에 디스크 공간이 있는지 확인하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="73654-146">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="73654-147">이 솔루션은 현재 다음과 같은 파일 시스템 형식에 대한 실시간 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="73654-147">The solution currently provides real-time protection for the following file system types:</span></span>

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

<span data-ttu-id="73654-148">서비스를 사용하도록 설정한 후 네트워크 또는 방화벽에서 해당 서비스 및 끝점 간의 아웃바운드 연결을 허용하도록 구성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73654-148">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="73654-149">감사 프레임워크( `auditd` )를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73654-149">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="73654-150">추가된 규칙에 의해 캡처된 시스템 이벤트는 (s)에 추가될 것이고 호스트 감사 및 업스트림 컬렉션에 영향을 `/etc/audit/rules.d/` `audit.log` 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73654-150">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="73654-151">Linux용 끝점용 Microsoft Defender에서 추가한 이벤트는 키로 태그가 `mdatp` 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="73654-151">Events added by Microsoft Defender for Endpoint for Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="73654-152">네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="73654-152">Network connections</span></span>

<span data-ttu-id="73654-153">다음 다운로드 가능한 스프레드시트에는 네트워크에서 연결할 수 있어야 하는 서비스 및 관련 URL이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="73654-153">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="73654-154">이러한 URL에 대한 액세스를 거부하는 방화벽 또는 네트워크 필터링 규칙이 없는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73654-154">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="73654-155">있는 경우 해당 규칙에 대해  특별히 허용 규칙을 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73654-155">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="73654-156">**도메인 목록의 스프레드시트**</span><span class="sxs-lookup"><span data-stu-id="73654-156">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="73654-157">**설명**</span><span class="sxs-lookup"><span data-stu-id="73654-157">**Description**</span></span>|
|:-----|:-----|
|![끝점 URL 스프레드시트용 Microsoft Defender의 축소판 이미지](images/mdatp-urls.png)<br/>  | <span data-ttu-id="73654-159">서비스 위치, 지리적 위치 및 OS에 대한 특정 DNS 레코드의 스프레드시트입니다.</span><span class="sxs-lookup"><span data-stu-id="73654-159">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="73654-160">여기에서 스프레드시트를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="73654-160">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="73654-161">보다 구체적인 URL 목록은 프록시 및 인터넷 연결 설정 [구성을 참조하세요.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="73654-161">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="73654-162">Endpoint용 Defender는 다음 검색 방법을 사용하여 프록시 서버를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73654-162">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="73654-163">투명한 프록시</span><span class="sxs-lookup"><span data-stu-id="73654-163">Transparent proxy</span></span>
- <span data-ttu-id="73654-164">수동 정적 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="73654-164">Manual static proxy configuration</span></span>

<span data-ttu-id="73654-165">프록시 또는 방화벽에서 익명 트래픽을 차단하는 경우 이전에 나열된 URL에서 익명 트래픽이 허용되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="73654-165">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="73654-166">투명한 proxies의 경우 끝점용 Defender에 대한 추가 구성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73654-166">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="73654-167">정적 프록시의 경우 수동 정적 프록시 [구성의 단계를 따릅니다.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="73654-167">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="73654-168">PAC, WPAD 및 인증된 proxies는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73654-168">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="73654-169">정적 프록시 또는 투명 프록시만 사용 중이지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="73654-169">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="73654-170">보안상의 이유로 SSL 검사 및 가로채기 Proxies도 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73654-170">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="73654-171">SSL 검사 및 프록시 서버에 대한 예외를 구성하여 Linux용 끝점용 Defender의 데이터를 가로채지 않고 관련 URL로 직접 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="73654-171">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="73654-172">전역 저장소에 가로채기 인증서를 추가하면 가로채는 것을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73654-172">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="73654-173">문제 해결 단계는 [Linux용 끝점용 Microsoft Defender에 대한 클라우드 연결 문제 해결을 참조하세요.](linux-support-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="73654-173">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="73654-174">Linux용 끝점용 Microsoft Defender를 업데이트하는 방법</span><span class="sxs-lookup"><span data-stu-id="73654-174">How to update Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="73654-175">Microsoft는 성능, 보안을 개선하고 새로운 기능을 제공하기 위해 소프트웨어 업데이트를 정기적으로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="73654-175">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="73654-176">Linux용 끝점용 Microsoft Defender를 업데이트하기 위해 [Linux용 끝점용 Microsoft Defender 업데이트 배포를 참조하세요.](linux-updates.md)</span><span class="sxs-lookup"><span data-stu-id="73654-176">To update Microsoft Defender for Endpoint for Linux, refer to [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="73654-177">Linux용 끝점에 대해 Microsoft Defender를 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="73654-177">How to configure Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="73654-178">엔터프라이즈 환경에서 제품을 구성하는 방법에 대한 지침은 [Linux용 끝점용 Microsoft Defender](linux-preferences.md)기본 설정 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73654-178">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="73654-179">리소스</span><span class="sxs-lookup"><span data-stu-id="73654-179">Resources</span></span>

- <span data-ttu-id="73654-180">로깅, 지우기 또는 기타 항목에 대한 자세한 내용은 Resources 을 [참조하십시오.](linux-resources.md)</span><span class="sxs-lookup"><span data-stu-id="73654-180">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
