---
title: Mac의 끝점용 Microsoft Defender
ms.reviewer: ''
description: Mac에서 끝점용 Microsoft Defender를 설치, 구성, 업데이트 및 사용하는 방법을 학습합니다.
keywords: microsoft, defender, Endpoint용 Microsoft Defender, mac, 설치, 배포, 제거, intune, jamf, macos, big sur, catalina, mojave, mac용 mde
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
ms.openlocfilehash: 365fed8b5f7c7fc617ea068e324da541f7f1b187
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301779"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="3b46b-104">Mac의 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3b46b-104">Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3b46b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3b46b-105">**Applies to:**</span></span>
- [<span data-ttu-id="3b46b-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3b46b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3b46b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b46b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3b46b-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3b46b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3b46b-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="3b46b-110">이 항목에서는 Mac에서 끝점용 Defender를 설치, 구성, 업데이트 및 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Mac.</span></span>

> [!CAUTION]
> <span data-ttu-id="3b46b-111">Mac에서 끝점용 Microsoft Defender와 함께 다른 타사 끝점 보호 제품을 실행하면 성능 문제와 예측할 수 없는 부작용이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Mac is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="3b46b-112">사용자 환경에서 비 Microsoft 끝점 보호가 절대적인 요구 사항이면 수동 모드에서 실행될 바이러스 백신 기능을 구성한 후에도 Mac용 끝점용 Defender를 EDR 기능을 안전하게 활용할 [수 있습니다.](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="3b46b-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Mac EDR functionality after configuring the antivirus functionality to run in [Passive mode](mac-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="whats-new-in-the-latest-release"></a><span data-ttu-id="3b46b-113">최신 릴리스의 새로운 소식</span><span class="sxs-lookup"><span data-stu-id="3b46b-113">What’s new in the latest release</span></span>

[<span data-ttu-id="3b46b-114">엔드포인트용 Microsoft Defender의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="3b46b-114">What's new in Microsoft Defender for Endpoint</span></span>](whats-new-in-microsoft-defender-atp.md)

[<span data-ttu-id="3b46b-115">Mac의 끝점용 Microsoft Defender의 새로운</span><span class="sxs-lookup"><span data-stu-id="3b46b-115">What's new in Microsoft Defender for Endpoint on Mac</span></span>](mac-whatsnew.md)

> [!TIP]
> <span data-ttu-id="3b46b-116">공유하고자 하는 피드백이 있는 경우 장치의 Mac에서 끝점용 Microsoft Defender를 열고 피드백 보내기 도움말로 를 확인하여  >  **제출합니다.**</span><span class="sxs-lookup"><span data-stu-id="3b46b-116">If you have any feedback that you would like to share, submit it by opening Microsoft Defender for Endpoint on Mac on your device and navigating to **Help** > **Send feedback**.</span></span>

<span data-ttu-id="3b46b-117">미리 보기 기능(예: Mac 장치에 대한 끝점 감지 및 응답)을 비롯한 최신 기능을 얻기 위해 끝점용 Microsoft Defender를 실행하는 macOS 장치를 "Insider" 장치로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-117">To get the latest features, including preview capabilities (such as endpoint detection and response for your Mac devices), configure your macOS device running Microsoft Defender for Endpoint to be an "Insider" device.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="3b46b-118">Mac에 끝점용 Microsoft Defender를 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="3b46b-118">How to install Microsoft Defender for Endpoint on Mac</span></span>

### <a name="prerequisites"></a><span data-ttu-id="3b46b-119">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="3b46b-119">Prerequisites</span></span>

- <span data-ttu-id="3b46b-120">끝점용 Defender 구독 및 Microsoft Defender 보안 센터 포털 액세스</span><span class="sxs-lookup"><span data-stu-id="3b46b-120">A Defender for Endpoint subscription and access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="3b46b-121">macOS 및 BASH 스크립팅의 초보자 수준 환경</span><span class="sxs-lookup"><span data-stu-id="3b46b-121">Beginner-level experience in macOS and BASH scripting</span></span>
- <span data-ttu-id="3b46b-122">디바이스의 관리 권한(수동 배포의 경우)</span><span class="sxs-lookup"><span data-stu-id="3b46b-122">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="3b46b-123">설치 지침</span><span class="sxs-lookup"><span data-stu-id="3b46b-123">Installation instructions</span></span>

<span data-ttu-id="3b46b-124">Mac에서 끝점용 Defender를 설치하고 구성하는 데 사용할 수 있는 몇 가지 방법 및 배포 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-124">There are several methods and deployment tools that you can use to install and configure Defender for Endpoint on Mac.</span></span>

- <span data-ttu-id="3b46b-125">타사 관리 도구:</span><span class="sxs-lookup"><span data-stu-id="3b46b-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="3b46b-126">Microsoft Intune 기반 배포</span><span class="sxs-lookup"><span data-stu-id="3b46b-126">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md)
    - [<span data-ttu-id="3b46b-127">JAMF 기반 배포</span><span class="sxs-lookup"><span data-stu-id="3b46b-127">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
    - [<span data-ttu-id="3b46b-128">기타 MDM 제품</span><span class="sxs-lookup"><span data-stu-id="3b46b-128">Other MDM products</span></span>](mac-install-with-other-mdm.md)

- <span data-ttu-id="3b46b-129">명령줄 도구:</span><span class="sxs-lookup"><span data-stu-id="3b46b-129">Command-line tool:</span></span>
    - [<span data-ttu-id="3b46b-130">수동 배포</span><span class="sxs-lookup"><span data-stu-id="3b46b-130">Manual deployment</span></span>](mac-install-manually.md)

### <a name="system-requirements"></a><span data-ttu-id="3b46b-131">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b46b-131">System requirements</span></span>

<span data-ttu-id="3b46b-132">macOS의 가장 최근 주요 릴리스 3개가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-132">The three most recent major releases of macOS are supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b46b-133">macOS 11(Big Sur)에서는 끝점용 Microsoft Defender에 추가 구성 프로필이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-133">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="3b46b-134">이전 버전의 macOS에서 업그레이드하는 기존 고객인 경우 MacOS 카탈로리나 및 최신 [버전의 macOS용](mac-sysext-policies.md)새 구성 프로필에 나열된 추가 구성 프로필을 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-134">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [New configuration profiles for macOS Catalina and newer versions of macOS](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b46b-135">MacOS 10.13(High Sierra)에 대한 지원은 2021년 2월 15일부터 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-135">Support for macOS 10.13 (High Sierra) has been discontinued as of February 15th, 2021.</span></span>

- <span data-ttu-id="3b46b-136">11(빅 수르), 10.15(카탈리나), 10.14(모자베)</span><span class="sxs-lookup"><span data-stu-id="3b46b-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)</span></span>
- <span data-ttu-id="3b46b-137">디스크 공간: 1GB</span><span class="sxs-lookup"><span data-stu-id="3b46b-137">Disk space: 1GB</span></span>

<span data-ttu-id="3b46b-138">MacOS의 베타 버전은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-138">Beta versions of macOS are not supported.</span></span>

<span data-ttu-id="3b46b-139">M1 프로세서가 있는 macOS 장치는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-139">macOS devices with M1 processors are not supported.</span></span>

<span data-ttu-id="3b46b-140">서비스를 사용하도록 설정한 후 네트워크 또는 방화벽에서 해당 서비스 및 끝점 간의 아웃바운드 연결을 허용하도록 구성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-140">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="3b46b-141">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b46b-141">Licensing requirements</span></span>

<span data-ttu-id="3b46b-142">Mac의 끝점용 Microsoft Defender에는 다음 Microsoft 볼륨 라이선싱 제품 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-142">Microsoft Defender for Endpoint on Mac requires one of the following Microsoft Volume Licensing offers:</span></span>

- <span data-ttu-id="3b46b-143">Microsoft 365 E5(M365 E5)</span><span class="sxs-lookup"><span data-stu-id="3b46b-143">Microsoft 365 E5 (M365 E5)</span></span>
- <span data-ttu-id="3b46b-144">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="3b46b-144">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="3b46b-145">Microsoft 365 A5(M365 A5)</span><span class="sxs-lookup"><span data-stu-id="3b46b-145">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="3b46b-146">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="3b46b-146">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="3b46b-147">끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3b46b-147">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="3b46b-148">적격 라이선스 사용자는 최대 5개의 동시 장치에서 끝점용 Microsoft Defender를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-148">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="3b46b-149">Microsoft Defender for Endpoint는 CSP(Microsoft Defender for Endpoint)에서 클라우드 솔루션 공급자 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-149">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span> <span data-ttu-id="3b46b-150">CSP를 통해 구매한 경우 나열된 Microsoft 볼륨 라이선스 제품은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-150">When purchased via a CSP, it does not require Microsoft Volume Licensing offers listed.</span></span>

### <a name="network-connections"></a><span data-ttu-id="3b46b-151">네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="3b46b-151">Network connections</span></span>

<span data-ttu-id="3b46b-152">다음 다운로드 가능한 스프레드시트에는 네트워크에서 연결할 수 있어야 하는 서비스 및 관련 URL이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-152">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="3b46b-153">이러한 URL에 대한 액세스를 거부하는 방화벽 또는 네트워크 필터링 규칙이 없는지 또는 해당 URL에 대한 허용 규칙을 만들어야 할 수도 있습니다. </span><span class="sxs-lookup"><span data-stu-id="3b46b-153">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>



|<span data-ttu-id="3b46b-154">**도메인 목록의 스프레드시트**</span><span class="sxs-lookup"><span data-stu-id="3b46b-154">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="3b46b-155">**설명**</span><span class="sxs-lookup"><span data-stu-id="3b46b-155">**Description**</span></span>|
|:-----|:-----|
|![끝점 URL 스프레드시트용 Microsoft Defender의 축소판 이미지](images/mdatp-urls.png)<br/>  | <span data-ttu-id="3b46b-157">서비스 위치, 지리적 위치 및 OS에 대한 특정 DNS 레코드의 스프레드시트입니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-157">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br><span data-ttu-id="3b46b-158">여기에서 스프레드시트를 [다운로드합니다.mdatp-urls.xlsx. ](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)</span><span class="sxs-lookup"><span data-stu-id="3b46b-158">Download the spreadsheet here: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span></span>

<span data-ttu-id="3b46b-159">끝점용 Microsoft Defender는 다음 검색 방법을 사용하여 프록시 서버를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-159">Microsoft Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="3b46b-160">PAC(프록시 자동 구성)</span><span class="sxs-lookup"><span data-stu-id="3b46b-160">Proxy autoconfig (PAC)</span></span>
- <span data-ttu-id="3b46b-161">WPAD(웹 프록시 자동 검색 프로토콜)</span><span class="sxs-lookup"><span data-stu-id="3b46b-161">Web Proxy Autodiscovery Protocol (WPAD)</span></span>
- <span data-ttu-id="3b46b-162">수동 정적 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="3b46b-162">Manual static proxy configuration</span></span>

<span data-ttu-id="3b46b-163">프록시 또는 방화벽에서 익명 트래픽을 차단하는 경우 이전에 나열된 URL에서 익명 트래픽이 허용되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="3b46b-163">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="3b46b-164">인증된 proxies는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-164">Authenticated proxies are not supported.</span></span> <span data-ttu-id="3b46b-165">PAC, WPAD 또는 정적 프록시만 사용 중이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-165">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span>
>
> <span data-ttu-id="3b46b-166">보안상의 이유로 SSL 검사 및 가로채기 Proxies도 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-166">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="3b46b-167">MacOS용 끝점용 Microsoft Defender의 데이터를 가로채지 않고 관련 URL로 직접 전달하도록 SSL 검사 및 프록시 서버에 대한 예외를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-167">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="3b46b-168">전역 저장소에 가로채기 인증서를 추가하면 가로채는 것을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-168">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="3b46b-169">연결이 차단되지 않는지 테스트하기 위해 브라우저에서 [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) 열립니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-169">To test that a connection is not blocked, open [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) and [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) in a browser.</span></span>

<span data-ttu-id="3b46b-170">명령줄을 원하는 경우 터미널에서 다음 명령을 실행하여 연결을 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-170">If you prefer the command line, you can also check the connection by running the following command in Terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="3b46b-171">이 명령의 출력은 다음과 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-171">The output from this command should be similar to the following:</span></span>

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> <span data-ttu-id="3b46b-172">클라이언트 장치에서 SIP(시스템 무결성 [보호)를](https://support.apple.com/en-us/HT204899) 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-172">We recommend that you keep [System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) enabled on client devices.</span></span> <span data-ttu-id="3b46b-173">SIP는 OS에 대한 낮은 수준의 변조를 방지하는 기본 제공 macOS 보안 기능으로, 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-173">SIP is a built-in macOS security feature that prevents low-level tampering with the OS, and is enabled by default.</span></span>

<span data-ttu-id="3b46b-174">Endpoint용 Microsoft Defender가 설치되면 터미널에서 다음 명령을 실행하여 연결의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-174">Once Microsoft Defender for Endpoint is installed, connectivity can be validated by running the following command in Terminal:</span></span>
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="3b46b-175">Mac에서 끝점용 Microsoft Defender를 업데이트하는 방법</span><span class="sxs-lookup"><span data-stu-id="3b46b-175">How to update Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="3b46b-176">Microsoft는 성능, 보안을 개선하고 새로운 기능을 제공하기 위해 소프트웨어 업데이트를 정기적으로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-176">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="3b46b-177">Mac에서 끝점용 Microsoft Defender를 업데이트하기 위해 MAU(Microsoft 자동 업데이트)라는 프로그램이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-177">To update Microsoft Defender for Endpoint on Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="3b46b-178">자세한 내용은 Mac에서 [끝점용 Microsoft Defender 업데이트 배포를 참조하세요.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="3b46b-178">To learn more, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="3b46b-179">Mac에서 끝점용 Microsoft Defender를 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="3b46b-179">How to configure Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="3b46b-180">엔터프라이즈 환경에서 제품을 구성하는 방법에 대한 지침은 [Mac의 끝점용 Microsoft Defender](mac-preferences.md)기본 설정에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-180">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Mac](mac-preferences.md).</span></span>

## <a name="macos-kernel-and-system-extensions"></a><span data-ttu-id="3b46b-181">macOS 커널 및 시스템 확장</span><span class="sxs-lookup"><span data-stu-id="3b46b-181">macOS kernel and system extensions</span></span>

<span data-ttu-id="3b46b-182">MacOS의 진화에 맞춰 커널 확장 대신 시스템 확장을 활용하는 Mac에서 끝점용 Microsoft Defender 업데이트를 준비하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46b-182">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint on Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="3b46b-183">관련 세부 정보는 [Mac의 끝점용 Microsoft Defender의 새로운 내용을 참조합니다.](mac-whatsnew.md)</span><span class="sxs-lookup"><span data-stu-id="3b46b-183">For relevant details, see [What's new in Microsoft Defender for Endpoint on Mac](mac-whatsnew.md).</span></span>

## <a name="resources"></a><span data-ttu-id="3b46b-184">리소스</span><span class="sxs-lookup"><span data-stu-id="3b46b-184">Resources</span></span>

- <span data-ttu-id="3b46b-185">로깅, 지우기 또는 기타 항목에 대한 자세한 내용은 [Mac의 끝점용 Microsoft Defender 리소스를 참조하세요.](mac-resources.md)</span><span class="sxs-lookup"><span data-stu-id="3b46b-185">For more information about logging, uninstalling, or other topics, see [Resources for Microsoft Defender for Endpoint on Mac](mac-resources.md).</span></span>

- <span data-ttu-id="3b46b-186">[Mac의 끝점용 Microsoft Defender에 대한 개인 정보 .](mac-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="3b46b-186">[Privacy for Microsoft Defender for Endpoint on Mac](mac-privacy.md).</span></span>
