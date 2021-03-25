---
title: Linux용 Microsoft Defender ATP
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
ms.openlocfilehash: 84d85b723d4dcbdfc07a074c40241242c57bc390
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185590"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="f2f09-104">Linux용 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f2f09-104">Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f2f09-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f2f09-105">**Applies to:**</span></span>
- [<span data-ttu-id="f2f09-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f2f09-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f2f09-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2f09-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f2f09-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f2f09-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f2f09-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f2f09-110">이 항목에서는 Linux용 끝점용 Microsoft Defender를 설치, 구성, 업데이트 및 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint for Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="f2f09-111">Linux용 Endpoint용 Microsoft Defender와 함께 다른 타사 끝점 보호 제품을 실행하면 성능 문제와 예측할 수 없는 시스템 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint for Linux is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="f2f09-112">Linux용 끝점용 Microsoft Defender를 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="f2f09-112">How to install Microsoft Defender for Endpoint for Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="f2f09-113">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f2f09-113">Prerequisites</span></span>

- <span data-ttu-id="f2f09-114">Microsoft Defender 보안 센터 포털에 액세스</span><span class="sxs-lookup"><span data-stu-id="f2f09-114">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="f2f09-115">시스템 [관리자를](https://systemd.io/) 사용하여 Linux 배포</span><span class="sxs-lookup"><span data-stu-id="f2f09-115">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="f2f09-116">Linux 및 BASH 스크립팅의 초보자 수준 환경</span><span class="sxs-lookup"><span data-stu-id="f2f09-116">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="f2f09-117">디바이스의 관리 권한(수동 배포의 경우)</span><span class="sxs-lookup"><span data-stu-id="f2f09-117">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="f2f09-118">설치 지침</span><span class="sxs-lookup"><span data-stu-id="f2f09-118">Installation instructions</span></span>

<span data-ttu-id="f2f09-119">Linux용 끝점용 Microsoft Defender를 설치하고 구성하는 데 사용할 수 있는 몇 가지 방법 및 배포 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-119">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="f2f09-120">일반적으로 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-120">In general you need to take the following steps:</span></span>

- <span data-ttu-id="f2f09-121">Endpoint용 Microsoft Defender 구독이 있으며 끝점 포털용 [Microsoft Defender에](microsoft-defender-security-center.md)액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-121">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="f2f09-122">다음 배포 방법 중 하나를 사용하여 Linux용 끝점용 Microsoft Defender를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-122">Deploy Microsoft Defender for Endpoint for Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="f2f09-123">명령줄 도구:</span><span class="sxs-lookup"><span data-stu-id="f2f09-123">The command-line tool:</span></span>
    - [<span data-ttu-id="f2f09-124">수동 배포</span><span class="sxs-lookup"><span data-stu-id="f2f09-124">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="f2f09-125">타사 관리 도구:</span><span class="sxs-lookup"><span data-stu-id="f2f09-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="f2f09-126">Puppet 구성 관리 도구를 사용하여 배포</span><span class="sxs-lookup"><span data-stu-id="f2f09-126">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="f2f09-127">Ansible 구성 관리 도구를 사용하여 배포</span><span class="sxs-lookup"><span data-stu-id="f2f09-127">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="f2f09-128">설치 오류가 발생하면 [Linux용 끝점용 Microsoft Defender의](linux-support-install.md)설치 실패 문제 해결을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f2f09-128">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="f2f09-129">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2f09-129">System requirements</span></span>

- <span data-ttu-id="f2f09-130">지원되는 Linux 서버 배포 및 버전:</span><span class="sxs-lookup"><span data-stu-id="f2f09-130">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="f2f09-131">Red Hat Enterprise Linux 7.2 이상</span><span class="sxs-lookup"><span data-stu-id="f2f09-131">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="f2f09-132">CentOS 7.2 이상</span><span class="sxs-lookup"><span data-stu-id="f2f09-132">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="f2f09-133">Ubuntu 16.04 LTS 이상 LTS</span><span class="sxs-lookup"><span data-stu-id="f2f09-133">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="f2f09-134">데비안 9 이상</span><span class="sxs-lookup"><span data-stu-id="f2f09-134">Debian 9 or higher</span></span>
  - <span data-ttu-id="f2f09-135">SUSE Linux Enterprise Server 12 이상</span><span class="sxs-lookup"><span data-stu-id="f2f09-135">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="f2f09-136">Oracle Linux 7.2 이상</span><span class="sxs-lookup"><span data-stu-id="f2f09-136">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="f2f09-137">최소 커널 버전 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="f2f09-137">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="f2f09-138">커널 `fanotify` 옵션을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-138">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="f2f09-139">Linux용 끝점용 Defender를 다른 기반 보안 솔루션과 함께 실행하는 `fanotify` 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-139">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="f2f09-140">운영 체제 중단을 포함하여 예측할 수 없는 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-140">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="f2f09-141">디스크 공간: 1GB</span><span class="sxs-lookup"><span data-stu-id="f2f09-141">Disk space: 1GB</span></span>
- <span data-ttu-id="f2f09-142">이 솔루션은 현재 다음과 같은 파일 시스템 형식에 대한 실시간 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-142">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="f2f09-143">서비스를 사용하도록 설정한 후 네트워크 또는 방화벽에서 해당 서비스 및 끝점 간의 아웃바운드 연결을 허용하도록 구성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-143">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="f2f09-144">감사 프레임워크( `auditd` )를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-144">Audit framework (`auditd`) must be enabled.</span></span>
  >[!NOTE]
  > <span data-ttu-id="f2f09-145">추가된 규칙에 의해 캡처된 시스템 이벤트는 감사 로그에 추가하며 호스트 감사 및 업스트림 컬렉션에 영향을 `audit.logs` 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-145">System events captured by rules added to `audit.logs` will add to audit logs and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="f2f09-146">Linux용 Endopoint용 Microsoft Defender에서 추가한 이벤트는 키로 태그가 `mdatp` 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-146">Events added by Microsoft Defender for Endopoint for Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="f2f09-147">네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="f2f09-147">Network connections</span></span>

<span data-ttu-id="f2f09-148">다음 다운로드 가능한 스프레드시트에는 네트워크에서 연결할 수 있어야 하는 서비스 및 관련 URL이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-148">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="f2f09-149">이러한 URL에 대한 액세스를 거부하는 방화벽 또는 네트워크 필터링 규칙이 없는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-149">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="f2f09-150">있는 경우 해당 규칙에 대해  특별히 허용 규칙을 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-150">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="f2f09-151">**도메인 목록의 스프레드시트**</span><span class="sxs-lookup"><span data-stu-id="f2f09-151">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="f2f09-152">**설명**</span><span class="sxs-lookup"><span data-stu-id="f2f09-152">**Description**</span></span>|
|:-----|:-----|
|![끝점 URL 스프레드시트용 Microsoft Defender의 축소판 이미지](images/mdatp-urls.png)<br/>  | <span data-ttu-id="f2f09-154">서비스 위치, 지리적 위치 및 OS에 대한 특정 DNS 레코드의 스프레드시트입니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-154">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="f2f09-155">여기에서 스프레드시트를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-155">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="f2f09-156">보다 구체적인 URL 목록은 프록시 및 인터넷 연결 설정 [구성을 참조하세요.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="f2f09-156">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="f2f09-157">Endpoint용 Defender는 다음 검색 방법을 사용하여 프록시 서버를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-157">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="f2f09-158">투명한 프록시</span><span class="sxs-lookup"><span data-stu-id="f2f09-158">Transparent proxy</span></span>
- <span data-ttu-id="f2f09-159">수동 정적 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="f2f09-159">Manual static proxy configuration</span></span>

<span data-ttu-id="f2f09-160">프록시 또는 방화벽에서 익명 트래픽을 차단하는 경우 이전에 나열된 URL에서 익명 트래픽이 허용되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="f2f09-160">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="f2f09-161">투명한 proxies의 경우 끝점용 Defender에 대한 추가 구성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-161">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="f2f09-162">정적 프록시의 경우 수동 정적 프록시 [구성의 단계를 따릅니다.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="f2f09-162">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="f2f09-163">PAC, WPAD 및 인증된 proxies는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-163">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="f2f09-164">정적 프록시 또는 투명 프록시만 사용 중이지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-164">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="f2f09-165">보안상의 이유로 SSL 검사 및 가로채기 Proxies도 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-165">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="f2f09-166">SSL 검사 및 프록시 서버에 대한 예외를 구성하여 Linux용 끝점용 Defender의 데이터를 가로채지 않고 관련 URL로 직접 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-166">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="f2f09-167">전역 저장소에 가로채기 인증서를 추가하면 가로채는 것을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-167">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="f2f09-168">문제 해결 단계는 [Linux용 끝점용 Microsoft Defender에 대한 클라우드 연결 문제 해결을 참조하세요.](linux-support-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="f2f09-168">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="f2f09-169">Linux용 끝점용 Microsoft Defender를 업데이트하는 방법</span><span class="sxs-lookup"><span data-stu-id="f2f09-169">How to update Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="f2f09-170">Microsoft는 성능, 보안을 개선하고 새로운 기능을 제공하기 위해 소프트웨어 업데이트를 정기적으로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-170">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="f2f09-171">Linux용 끝점용 Microsoft Defender를 업데이트하기 위해 [Linux용 끝점용 Microsoft Defender 업데이트 배포를 참조하세요.](linux-updates.md)</span><span class="sxs-lookup"><span data-stu-id="f2f09-171">To update Microsoft Defender for Endpoint for Linux, refer to [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="f2f09-172">Linux용 끝점에 대해 Microsoft Defender를 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="f2f09-172">How to configure Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="f2f09-173">엔터프라이즈 환경에서 제품을 구성하는 방법에 대한 지침은 [Linux용 끝점용 Microsoft Defender](linux-preferences.md)기본 설정 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f09-173">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="f2f09-174">리소스</span><span class="sxs-lookup"><span data-stu-id="f2f09-174">Resources</span></span>

- <span data-ttu-id="f2f09-175">로깅, 지우기 또는 기타 항목에 대한 자세한 내용은 Resources 을 [참조하십시오.](linux-resources.md)</span><span class="sxs-lookup"><span data-stu-id="f2f09-175">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
