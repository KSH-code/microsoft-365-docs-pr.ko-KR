---
title: Mac용 Microsoft Defender ATP를 위한 다른 MDM(모바일 장치 관리) 시스템을 사용하여 배포
description: 다른 관리 솔루션에 Mac용 Microsoft Defender ATP를 설치합니다.
keywords: microsoft, defender, atp, mac, 설치, 배포, macos, 카탈로니아, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 58e3b14dcb80db961f01b92f038ce4d32da7e2e8
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689708"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="b79fb-104">macOS의 끝점용 Microsoft Defender에 대해 다른 MDM(모바일 장치 관리) 시스템을 사용하여 배포</span><span class="sxs-lookup"><span data-stu-id="b79fb-104">Deployment with a different Mobile Device Management (MDM) system for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b79fb-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b79fb-105">**Applies to:**</span></span>
- <span data-ttu-id="b79fb-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="b79fb-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="b79fb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b79fb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b79fb-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="b79fb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b79fb-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="b79fb-110">선행 조건 및 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b79fb-110">Prerequisites and system requirements</span></span>

<span data-ttu-id="b79fb-111">시작하기 전에 [MacOS의 주 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md) 페이지에서 현재 소프트웨어 버전에 대한 선행 조건 및 시스템 요구 사항에 대한 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b79fb-111">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="approach"></a><span data-ttu-id="b79fb-112">방법</span><span class="sxs-lookup"><span data-stu-id="b79fb-112">Approach</span></span>

> [!CAUTION]
> <span data-ttu-id="b79fb-113">현재 Microsoft는 MacOS에서 끝점용 Microsoft Defender의 배포 및 관리를 위해 Intune 및 JAMF만 공식적으로 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-113">Currently, Microsoft officially supports only Intune and JAMF for the deployment and management of Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="b79fb-114">Microsoft는 아래 제공된 정보에 대해 표현적 또는 암시적 보증을하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-114">Microsoft makes no warranties, express or implied, with respect to the information provided below.</span></span>

<span data-ttu-id="b79fb-115">조직에서 공식적으로 지원되지 않는 MDM(모바일 장치 관리) 솔루션을 사용하는 경우 macOS에서 끝점용 Microsoft Defender를 배포하거나 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-115">If your organization uses a Mobile Device Management (MDM) solution that is not officially supported, this does not mean you are unable to deploy or run Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="b79fb-116">MacOS의 끝점용 Microsoft Defender는 공급업체별 기능에 의존하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-116">Microsoft Defender for Endpoint on macOS does not depend on any vendor-specific features.</span></span> <span data-ttu-id="b79fb-117">이 기능은 다음 기능을 지원하는 모든 MDM 솔루션에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-117">It can be used with any MDM solution that supports the following features:</span></span>

- <span data-ttu-id="b79fb-118">관리되는 장치에 macOS .pkg를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-118">Deploy a macOS .pkg to managed devices.</span></span>
- <span data-ttu-id="b79fb-119">관리되는 장치에 macOS 시스템 구성 프로필을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-119">Deploy macOS system configuration profiles to managed devices.</span></span>
- <span data-ttu-id="b79fb-120">관리되는 장치에서 임의로 관리자가 구성한 도구/스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-120">Run an arbitrary admin-configured tool/script on managed devices.</span></span>

<span data-ttu-id="b79fb-121">대부분의 최신 MDM 솔루션에는 이러한 기능이 포함되어 있습니다. 그러나 이러한 기능을 다르게 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-121">Most modern MDM solutions include these features, however, they may call them differently.</span></span>

<span data-ttu-id="b79fb-122">그러나 앞의 목록에서 마지막 요구 사항 없이 Defender를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-122">You can deploy Defender without the last requirement from the preceding list, however:</span></span>

- <span data-ttu-id="b79fb-123">중앙 집중식 방식으로 상태를 수집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-123">You will not be able to collect status in a centralized way</span></span>
- <span data-ttu-id="b79fb-124">Defender를 제거하기로 결정한 경우 로컬에서 관리자로 클라이언트 장치에 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-124">If you decide to uninstall Defender, you will need to log on to the client device locally as an administrator</span></span>

## <a name="deployment"></a><span data-ttu-id="b79fb-125">배포</span><span class="sxs-lookup"><span data-stu-id="b79fb-125">Deployment</span></span>

<span data-ttu-id="b79fb-126">대부분의 MDM 솔루션은 비슷한 용어를 사용하여 macOS 장치를 관리하는 데 동일한 모델을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-126">Most MDM solutions use the same model for managing macOS devices, with similar terminology.</span></span> <span data-ttu-id="b79fb-127">[JAMF 기반 배포를](mac-install-with-jamf.md) 템플릿으로 사용</span><span class="sxs-lookup"><span data-stu-id="b79fb-127">Use [JAMF-based deployment](mac-install-with-jamf.md) as a template.</span></span>

### <a name="package"></a><span data-ttu-id="b79fb-128">패키지</span><span class="sxs-lookup"><span data-stu-id="b79fb-128">Package</span></span>

<span data-ttu-id="b79fb-129">Microsoft Defender [](mac-install-with-jamf.md)보안 센터에서 다운로드한 설치 패키지(wdav.pkg)를 통해 필수 응용 프로그램 패키지의 [배포를 구성합니다.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="b79fb-129">Configure deployment of a [required application package](mac-install-with-jamf.md), with the installation package (wdav.pkg) downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>

<span data-ttu-id="b79fb-130">엔터프라이즈에 패키지를 배포하기 위해 MDM 솔루션과 관련된 지침을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="b79fb-130">In order to deploy the package to your enterprise, use the instructions associated with your MDM solution.</span></span>

### <a name="license-settings"></a><span data-ttu-id="b79fb-131">라이선스 설정</span><span class="sxs-lookup"><span data-stu-id="b79fb-131">License settings</span></span>

<span data-ttu-id="b79fb-132">시스템 [구성 프로필을 설정합니다.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="b79fb-132">Set up [a system configuration profile](mac-install-with-jamf.md).</span></span> <span data-ttu-id="b79fb-133">MacOS의 끝점용 Microsoft Defender는 macOS의 일부가 아니기에 MDM 솔루션에서 "사용자 지정 설정 프로필"처럼 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-133">Your MDM solution may call it something like "Custom Settings Profile", as Microsoft Defender for Endpoint on macOS is not part of macOS.</span></span>

<span data-ttu-id="b79fb-134">Microsoft Defender 보안 센터에서 다운로드한 등록 패키지에서 추출할 수 있는 속성 목록 jamf/WindowsDefenderATPOnboarding.plist를 [사용하세요.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="b79fb-134">Use the property list, jamf/WindowsDefenderATPOnboarding.plist, which can be extracted from an onboarding package downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>
<span data-ttu-id="b79fb-135">시스템에서 임의의 속성 목록을 XML 형식으로 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-135">Your system may support an arbitrary property list in XML format.</span></span> <span data-ttu-id="b79fb-136">jamf/WindowsDefenderATPOnboarding.plist 파일을 현재 있는 것으로 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-136">You can upload the jamf/WindowsDefenderATPOnboarding.plist file as-is in that case.</span></span>
<span data-ttu-id="b79fb-137">또는 먼저 속성 목록을 다른 형식으로 변환해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-137">Alternatively, it may require you to convert the property list to a different format first.</span></span>

<span data-ttu-id="b79fb-138">일반적으로 사용자 지정 프로필에는 ID, 이름 또는 도메인 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-138">Typically, your custom profile has an ID, name, or domain attribute.</span></span> <span data-ttu-id="b79fb-139">이 값은 정확히 "com.microsoft.wdav.atp"를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-139">You must use exactly "com.microsoft.wdav.atp" for this value.</span></span>
<span data-ttu-id="b79fb-140">MDM은 이 파일을 사용하여 클라이언트 장치의 **/Library/Managed Preferences/com.microsoft.wdav.atp.plist에** 설정 파일을 배포하고 Defender는 이 파일을 사용하여 온보딩 정보를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-140">MDM uses it to deploy the settings file to **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** on a client device, and Defender uses this file for loading the onboarding information.</span></span>

### <a name="kernel-extension-policy"></a><span data-ttu-id="b79fb-141">커널 확장 정책</span><span class="sxs-lookup"><span data-stu-id="b79fb-141">Kernel extension policy</span></span>

<span data-ttu-id="b79fb-142">KEXT 또는 커널 확장 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-142">Set up a KEXT or kernel extension policy.</span></span> <span data-ttu-id="b79fb-143">팀 식별자 **UBF8T346G9를** 사용하여 Microsoft에서 제공하는 커널 확장을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-143">Use team identifier **UBF8T346G9** to allow kernel extensions provided by Microsoft.</span></span>

> [!CAUTION]
> <span data-ttu-id="b79fb-144">작업 환경이 Apple 실리콘(M1) 장치로 구성된 경우 이러한 컴퓨터는 KEXT 정책을 사용하여 구성 프로필을 수신하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-144">If your environment consists of Apple Silicon (M1) devices, these machines should not receive configuration profiles with KEXT policies.</span></span>
> <span data-ttu-id="b79fb-145">Apple은 이러한 컴퓨터의 KEXT를 지원하지 않습니다. 이러한 프로필의 배포는 M1 컴퓨터에서 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-145">Apple does not support KEXT on these machines, deployment of such profile would fail on M1 machines.</span></span>

### <a name="system-extension-policy"></a><span data-ttu-id="b79fb-146">시스템 확장 정책</span><span class="sxs-lookup"><span data-stu-id="b79fb-146">System extension policy</span></span>

<span data-ttu-id="b79fb-147">시스템 확장 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-147">Set up a system extension policy.</span></span> <span data-ttu-id="b79fb-148">팀 식별자 **UBF8T346G9를** 사용하여 다음 번들 식별자를 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-148">Use team identifier **UBF8T346G9** and approve the following bundle identifiers:</span></span>

- <span data-ttu-id="b79fb-149">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="b79fb-149">com.microsoft.wdav.epsext</span></span>
- <span data-ttu-id="b79fb-150">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="b79fb-150">com.microsoft.wdav.netext</span></span>

### <a name="full-disk-access-policy"></a><span data-ttu-id="b79fb-151">전체 디스크 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="b79fb-151">Full disk access policy</span></span>

<span data-ttu-id="b79fb-152">다음 구성 요소에 대한 전체 디스크 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-152">Grant Full Disk Access to the following components:</span></span>

- <span data-ttu-id="b79fb-153">끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b79fb-153">Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="b79fb-154">식별자: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="b79fb-154">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="b79fb-155">식별자 유형: 번들 ID</span><span class="sxs-lookup"><span data-stu-id="b79fb-155">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="b79fb-156">코드 요구 사항: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="b79fb-156">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

- <span data-ttu-id="b79fb-157">끝점 보안 확장용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b79fb-157">Microsoft Defender for Endpoint Security Extension</span></span>
    - <span data-ttu-id="b79fb-158">식별자: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="b79fb-158">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="b79fb-159">식별자 유형: 번들 ID</span><span class="sxs-lookup"><span data-stu-id="b79fb-159">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="b79fb-160">코드 요구 사항: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="b79fb-160">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

### <a name="network-extension-policy"></a><span data-ttu-id="b79fb-161">네트워크 확장 정책</span><span class="sxs-lookup"><span data-stu-id="b79fb-161">Network extension policy</span></span>

<span data-ttu-id="b79fb-162">끝점 감지 및 응답 기능의 일부로 macOS의 끝점용 Microsoft Defender는 소켓 트래픽을 검사하고 이 정보를 Microsoft Defender 보안 센터 포털에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-162">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="b79fb-163">다음 정책은 네트워크 확장에서 이 기능을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-163">The following policy allows the network extension to perform this functionality.</span></span>

- <span data-ttu-id="b79fb-164">필터 유형: 플러그 인</span><span class="sxs-lookup"><span data-stu-id="b79fb-164">Filter type: Plugin</span></span>
- <span data-ttu-id="b79fb-165">플러그 인 번들 식별자: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="b79fb-165">Plugin bundle identifier: `com.microsoft.wdav`</span></span>
- <span data-ttu-id="b79fb-166">필터 데이터 공급자 번들 식별자: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="b79fb-166">Filter data provider bundle identifier: `com.microsoft.wdav.netext`</span></span>
- <span data-ttu-id="b79fb-167">데이터 공급자가 지정한 요구 사항을 필터링합니다. `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="b79fb-167">Filter data provider designated requirement: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
- <span data-ttu-id="b79fb-168">필터 소켓: `true`</span><span class="sxs-lookup"><span data-stu-id="b79fb-168">Filter sockets: `true`</span></span>

## <a name="check-installation-status"></a><span data-ttu-id="b79fb-169">설치 상태 확인</span><span class="sxs-lookup"><span data-stu-id="b79fb-169">Check installation status</span></span>

<span data-ttu-id="b79fb-170">클라이언트 [장치에서 끝점용 Microsoft Defender를](mac-install-with-jamf.md) 실행하여 온보딩 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b79fb-170">Run [Microsoft Defender for Endpoint](mac-install-with-jamf.md) on a client device to check the onboarding status.</span></span>
