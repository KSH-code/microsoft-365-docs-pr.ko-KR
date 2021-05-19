---
title: McAfee에서 끝점용 Microsoft Defender로의 준비
description: McAfee에서 끝점용 Microsoft Defender로 마이그레이션하기 위한 준비 1단계입니다.
keywords: migration, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 171c9b4ff02e7f6ddb6918e430af772f44b1777a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538786"
---
# <a name="migrate-from-mcafee---phase-1-prepare-for-your-migration"></a><span data-ttu-id="df77a-104">McAfee에서 마이그레이션 - 1단계: 마이그레이션 준비</span><span class="sxs-lookup"><span data-stu-id="df77a-104">Migrate from McAfee - Phase 1: Prepare for your migration</span></span>

<span data-ttu-id="df77a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="df77a-105">**Applies to:**</span></span>
- [<span data-ttu-id="df77a-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="df77a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="df77a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df77a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

|![1 단계: 준비](images/phase-diagrams/prepare.png)<br/><span data-ttu-id="df77a-109">1 단계: 준비</span><span class="sxs-lookup"><span data-stu-id="df77a-109">Phase 1: Prepare</span></span> |<span data-ttu-id="df77a-110">[![2 단계: 설정](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)</span><span class="sxs-lookup"><span data-stu-id="df77a-110">[![Phase 2: Set up](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)</span></span><br/>[<span data-ttu-id="df77a-111">2 단계: 설정</span><span class="sxs-lookup"><span data-stu-id="df77a-111">Phase 2: Set up</span></span>](mcafee-to-microsoft-defender-setup.md) |<span data-ttu-id="df77a-112">[![3 단계: 온보딩](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)</span><span class="sxs-lookup"><span data-stu-id="df77a-112">[![Phase 3: Onboard](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)</span></span><br/>[<span data-ttu-id="df77a-113">3 단계: 온보딩</span><span class="sxs-lookup"><span data-stu-id="df77a-113">Phase 3: Onboard</span></span>](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
|<span data-ttu-id="df77a-114">*여기 있습니다!*</span><span class="sxs-lookup"><span data-stu-id="df77a-114">*You are here!*</span></span>| | |


<span data-ttu-id="df77a-115">**[McAfee 끝점 보안(McAfee)에서 Endpoint용 Defender로](mcafee-to-microsoft-defender-migration.md#the-migration-process)** 마이그레이션하는 준비 단계에 오신 것을 환영합니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-115">**Welcome to the Prepare phase of [migrating from McAfee Endpoint Security (McAfee) to Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)**.</span></span> 

<span data-ttu-id="df77a-116">이 마이그레이션 단계에는 다음 단계가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-116">This migration phase includes the following steps:</span></span>
1. [<span data-ttu-id="df77a-117">조직 장치에 업데이트 다운로드 및 배포</span><span class="sxs-lookup"><span data-stu-id="df77a-117">Get and deploy updates across your organization's devices</span></span>](#get-and-deploy-updates-across-your-organizations-devices)

2. <span data-ttu-id="df77a-118">[끝점용 Defender를 을(를) 얻습니다.](#get-microsoft-defender-for-endpoint)</span><span class="sxs-lookup"><span data-stu-id="df77a-118">[Get Defender for Endpoint](#get-microsoft-defender-for-endpoint).</span></span>

3. <span data-ttu-id="df77a-119">[에 대한 액세스 권한을 Microsoft Defender 보안 센터.](#grant-access-to-the-microsoft-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="df77a-119">[Grant access to the Microsoft Defender Security Center](#grant-access-to-the-microsoft-defender-security-center).</span></span>

4. <span data-ttu-id="df77a-120">[장치 프록시 및 인터넷 연결 설정을 구성합니다.](#configure-device-proxy-and-internet-connectivity-settings)</span><span class="sxs-lookup"><span data-stu-id="df77a-120">[Configure device proxy and internet connectivity settings](#configure-device-proxy-and-internet-connectivity-settings).</span></span>

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a><span data-ttu-id="df77a-121">조직 장치에 업데이트 다운로드 및 배포</span><span class="sxs-lookup"><span data-stu-id="df77a-121">Get and deploy updates across your organization's devices</span></span>

<span data-ttu-id="df77a-122">조직의 장치 및 끝점을 최신으로 유지하는 것이 가장 좋은 모범 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-122">As a best practice, keep your organization's devices and endpoints up to date.</span></span> <span data-ttu-id="df77a-123">McAfee 끝점 보안(McAfee) 솔루션이 최신 버전이고 조직에 최신 업데이트가 적용된 운영 체제 및 앱도 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-123">Make sure your McAfee Endpoint Security (McAfee) solution is up to date, and that the operating systems and apps your organization is also have the latest updates.</span></span> <span data-ttu-id="df77a-124">이렇게 하면 나중에 Endpoint용 Defender로 마이그레이션할 때 문제를 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-124">Doing this now can help prevent problems later as you migrate to Defender for Endpoint.</span></span>

### <a name="make-sure-your-mcafee-solution-is-up-to-date"></a><span data-ttu-id="df77a-125">McAfee 솔루션이 최신지 확인</span><span class="sxs-lookup"><span data-stu-id="df77a-125">Make sure your McAfee solution is up to date</span></span>

<span data-ttu-id="df77a-126">McAfee를 최신으로 유지하고 조직의 장치에 최신 보안 업데이트가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-126">Keep McAfee up to date, and make sure that your organization's devices have the latest security updates.</span></span> <span data-ttu-id="df77a-127">도움이 필요하신가요?</span><span class="sxs-lookup"><span data-stu-id="df77a-127">Need help?</span></span> <span data-ttu-id="df77a-128">다음은 몇 가지 McAfee 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-128">Here are some McAfee resources:</span></span>

- [<span data-ttu-id="df77a-129">McAfee Enterprise 제품 설명서: Endpoint 보안 작동 방식</span><span class="sxs-lookup"><span data-stu-id="df77a-129">McAfee Enterprise Product Documentation: How Endpoint Security Works</span></span>](https://docs.mcafee.com/bundle/endpoint-security-10.7.x-common-product-guide-windows/page/GUID-1207FF39-D1D2-481F-BBD9-E4079112A8DD.html)

- [<span data-ttu-id="df77a-130">McAfee 기술 문서: Windows 보안 센터에서 실행 시 끝점 보안이 사용하지 않도록 설정되어 있는 경우 간헐적으로 잘못 Windows 10</span><span class="sxs-lookup"><span data-stu-id="df77a-130">McAfee Knowledge Center Technical Article: Windows Security Center intermittently incorrectly reports that Endpoint Security is disabled when running on Windows 10</span></span>](https://kc.mcafee.com/corporate/index?page=content&id=KB91830) 

- [<span data-ttu-id="df77a-131">McAfee 기술 문서: Windows 보안 센터 보고서는 끝점 보안이 실행 중일 때 끝점 보안을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-131">McAfee Knowledge Center Technical Article: Windows Security Center reports Endpoint Security is disabled when Endpoint Security is running</span></span>](https://kc.mcafee.com/corporate/index?page=content&id=KB91428)

- <span data-ttu-id="df77a-132">McAfee 지원 ServicePortal( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) )</span><span class="sxs-lookup"><span data-stu-id="df77a-132">Your McAfee support ServicePortal ([http://mysupport.mcafee.com](http://mysupport.mcafee.com))</span></span>

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a><span data-ttu-id="df77a-133">조직의 장치를 최신으로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-133">Make sure your organization's devices are up to date</span></span>

<span data-ttu-id="df77a-134">조직의 장치를 업데이트하는 데 도움이 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="df77a-134">Need help updating your organization's devices?</span></span> <span data-ttu-id="df77a-135">다음 리소스를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="df77a-135">See the following resources:</span></span>

|<span data-ttu-id="df77a-136">OS</span><span class="sxs-lookup"><span data-stu-id="df77a-136">OS</span></span> | <span data-ttu-id="df77a-137">리소스</span><span class="sxs-lookup"><span data-stu-id="df77a-137">Resource</span></span> |
|:--|:--|
|<span data-ttu-id="df77a-138">Windows</span><span class="sxs-lookup"><span data-stu-id="df77a-138">Windows</span></span> |[<span data-ttu-id="df77a-139">Microsoft 업데이트</span><span class="sxs-lookup"><span data-stu-id="df77a-139">Microsoft Update</span></span>](https://www.update.microsoft.com) |
|<span data-ttu-id="df77a-140">macOS</span><span class="sxs-lookup"><span data-stu-id="df77a-140">macOS</span></span> | [<span data-ttu-id="df77a-141">Mac에서 소프트웨어를 업데이트하는 방법</span><span class="sxs-lookup"><span data-stu-id="df77a-141">How to update the software on your Mac</span></span>](https://support.apple.com/HT201541)|
|<span data-ttu-id="df77a-142">iOS</span><span class="sxs-lookup"><span data-stu-id="df77a-142">iOS</span></span> |[<span data-ttu-id="df77a-143">iPhone, iPad 또는 iPod 터치 업데이트</span><span class="sxs-lookup"><span data-stu-id="df77a-143">Update your iPhone, iPad, or iPod touch</span></span>](https://support.apple.com/HT204204)|
|<span data-ttu-id="df77a-144">Android</span><span class="sxs-lookup"><span data-stu-id="df77a-144">Android</span></span> |[<span data-ttu-id="df77a-145">Android & 업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="df77a-145">Check & update your Android version</span></span>](https://support.google.com/android/answer/7680439) |
|<span data-ttu-id="df77a-146">Linux</span><span class="sxs-lookup"><span data-stu-id="df77a-146">Linux</span></span> | [<span data-ttu-id="df77a-147">Linux 101: 시스템 업데이트</span><span class="sxs-lookup"><span data-stu-id="df77a-147">Linux 101: Updating Your System</span></span>](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a><span data-ttu-id="df77a-148">끝점용 Microsoft Defender 다운로드</span><span class="sxs-lookup"><span data-stu-id="df77a-148">Get Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="df77a-149">조직의 장치를 업데이트한 후 다음 단계는 Endpoint용 Defender를 다운로드하고 라이선스를 할당한 다음 서비스가 프로비전되어 있는지를 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-149">Now that you've updated your organization's devices, the next step is to get Defender for Endpoint, assign licenses, and make sure the service is provisioned.</span></span>

1. <span data-ttu-id="df77a-150">지금 끝점용 Defender를 구입하거나 사용해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-150">Buy or try Defender for Endpoint today.</span></span> <span data-ttu-id="df77a-151">[무료 평가판을 시작하거나 견적을 요청합니다.](https://aka.ms/mdatp)</span><span class="sxs-lookup"><span data-stu-id="df77a-151">[Start a free trial or request a quote](https://aka.ms/mdatp).</span></span> 

2. <span data-ttu-id="df77a-152">라이선스가 올바르게 프로비전되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-152">Verify that your licenses are properly provisioned.</span></span> <span data-ttu-id="df77a-153">[라이선스 상태를 확인 합니다.](production-deployment.md#check-license-state)</span><span class="sxs-lookup"><span data-stu-id="df77a-153">[Check your license state](production-deployment.md#check-license-state).</span></span>

3. <span data-ttu-id="df77a-154">전역 관리자 또는 보안 관리자는 끝점용 Defender의 전용 클라우드 인스턴스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-154">As a global administrator or security administrator, set up your dedicated cloud instance of Defender for Endpoint.</span></span> <span data-ttu-id="df77a-155">[Endpoint 설치: 테넌트 구성에 대한 Defender를 참조합니다.](production-deployment.md#tenant-configuration)</span><span class="sxs-lookup"><span data-stu-id="df77a-155">See [Defender for Endpoint setup: Tenant configuration](production-deployment.md#tenant-configuration).</span></span>

4. <span data-ttu-id="df77a-156">조직의 끝점(예: 장치)이 프록시를 사용하여 인터넷에 액세스하는 경우 Endpoint 설치용 [Defender: 네트워크 구성을 참조합니다.](production-deployment.md#network-configuration)</span><span class="sxs-lookup"><span data-stu-id="df77a-156">If endpoints (such as devices) in your organization use a proxy to access the internet, see [Defender for Endpoint setup: Network configuration](production-deployment.md#network-configuration).</span></span>
 
<span data-ttu-id="df77a-157">이제 Microsoft Defender 보안 센터()를 사용할 보안 관리자 및 보안 운영자에 대한 액세스 권한을 부여할 준비가 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="df77a-157">At this point, you are ready to grant access to your security administrators and security operators who will use the Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)).</span></span> 

> [!NOTE]
> <span data-ttu-id="df77a-158">이 Microsoft Defender 보안 센터 끝점 포털의 Defender라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-158">The Microsoft Defender Security Center is sometimes referred to as the Defender for Endpoint portal.</span></span> 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a><span data-ttu-id="df77a-159">사용자 액세스 권한 Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="df77a-159">Grant access to the Microsoft Defender Security Center</span></span>

<span data-ttu-id="df77a-160">Microsoft Defender 보안 센터 ()는 끝점용 Defender의 기능에 액세스하고 구성하는 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-160">The Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) is where you access and configure features and capabilities of Defender for Endpoint.</span></span> <span data-ttu-id="df77a-161">자세한 내용은 의 [개요를 Microsoft Defender 보안 센터.](use.md)</span><span class="sxs-lookup"><span data-stu-id="df77a-161">To learn more, see [Overview of the Microsoft Defender Security Center](use.md).</span></span>

<span data-ttu-id="df77a-162">기본 사용 Microsoft Defender 보안 센터 RBAC(역할 기반 액세스 제어)를 사용하여 사용 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-162">Permissions to the Microsoft Defender Security Center can be granted by using either basic permissions or role-based access control (RBAC).</span></span> <span data-ttu-id="df77a-163">사용 권한을 보다 세밀하게 제어할 수 있도록 RBAC를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-163">We recommend using RBAC so that you have more granular control over permissions.</span></span>

1. <span data-ttu-id="df77a-164">보안 관리자 및 보안 운영자에 대한 역할 및 사용 권한을 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-164">Plan the roles and permissions for your security administrators and security operators.</span></span> <span data-ttu-id="df77a-165">역할 [기반 액세스 제어를 참조합니다.](prepare-deployment.md#role-based-access-control)</span><span class="sxs-lookup"><span data-stu-id="df77a-165">See [Role-based access control](prepare-deployment.md#role-based-access-control).</span></span>

2. <span data-ttu-id="df77a-166">RBAC를 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-166">Set up and configure RBAC.</span></span> <span data-ttu-id="df77a-167">[Intune을](/mem/intune/fundamentals/what-is-intune) 사용하여 RBAC를 구성하는 것이 좋습니다. 특히 조직에서 Windows 10, macOS, iOS 및 Android 장치의 조합을 사용하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-167">We recommend using [Intune](/mem/intune/fundamentals/what-is-intune) to configure RBAC, especially if your organization is using a combination of Windows 10, macOS, iOS, and Android devices.</span></span> <span data-ttu-id="df77a-168">[Intune을 사용하여 RBAC 설정을 참조합니다.](/mem/intune/fundamentals/role-based-access-control)</span><span class="sxs-lookup"><span data-stu-id="df77a-168">See [setting up RBAC using Intune](/mem/intune/fundamentals/role-based-access-control).</span></span>

    <span data-ttu-id="df77a-169">조직에서 Intune 외의 방법이 필요한 경우 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-169">If your organization requires a method other than Intune, choose one of the following options:</span></span>

    - [<span data-ttu-id="df77a-170">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="df77a-170">Configuration Manager</span></span>](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [<span data-ttu-id="df77a-171">고급 그룹 정책 관리</span><span class="sxs-lookup"><span data-stu-id="df77a-171">Advanced Group Policy Management</span></span>](/microsoft-desktop-optimization-pack/agpm)

    - [<span data-ttu-id="df77a-172">Windows 관리 센터</span><span class="sxs-lookup"><span data-stu-id="df77a-172">Windows Admin Center</span></span>](/windows-server/manage/windows-admin-center/overview)

3. <span data-ttu-id="df77a-173">앱에 대한 액세스 권한을 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="df77a-173">Grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="df77a-174">(도움이 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="df77a-174">(Need help?</span></span> <span data-ttu-id="df77a-175">[RBAC를 사용하여 포털 액세스 관리를 참조합니다.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="df77a-175">See [Manage portal access using RBAC](rbac.md)).</span></span>

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="df77a-176">장치 프록시 및 인터넷 연결 설정 구성</span><span class="sxs-lookup"><span data-stu-id="df77a-176">Configure device proxy and internet connectivity settings</span></span>

<span data-ttu-id="df77a-177">장치와 끝점용 Defender 간의 통신을 사용하도록 설정하려면 프록시 및 인터넷 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-177">To enable communication between your devices and Defender for Endpoint, configure proxy and internet settings.</span></span> <span data-ttu-id="df77a-178">다음 표에는 다양한 운영 체제 및 기능에 대한 프록시 및 인터넷 설정을 구성하는 데 사용할 수 있는 리소스에 대한 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df77a-178">The following table includes links to resources you can use to configure your proxy and internet settings for various operating systems and capabilities:</span></span>

|<span data-ttu-id="df77a-179">기능</span><span class="sxs-lookup"><span data-stu-id="df77a-179">Capabilities</span></span>  | <span data-ttu-id="df77a-180">운영 체제</span><span class="sxs-lookup"><span data-stu-id="df77a-180">Operating System</span></span> | <span data-ttu-id="df77a-181">리소스</span><span class="sxs-lookup"><span data-stu-id="df77a-181">Resources</span></span> |
|--|--|--|
| <span data-ttu-id="df77a-182">[끝점 검색 및](overview-endpoint-detection-response.md) 응답(EDR)</span><span class="sxs-lookup"><span data-stu-id="df77a-182">[Endpoint detection and response](overview-endpoint-detection-response.md) (EDR)</span></span> | [<span data-ttu-id="df77a-183">Windows 10</span><span class="sxs-lookup"><span data-stu-id="df77a-183">Windows 10</span></span>](/windows/release-health/release-information) <p> [<span data-ttu-id="df77a-184">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="df77a-184">Windows Server 2019</span></span>](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[<span data-ttu-id="df77a-185">Windows 서버 1803 이상</span><span class="sxs-lookup"><span data-stu-id="df77a-185">Windows Server 1803 or later</span></span>](/windows-server/get-started/whats-new-in-windows-server-1803)  | [<span data-ttu-id="df77a-186">컴퓨터 프록시 및 인터넷 연결 설정 구성</span><span class="sxs-lookup"><span data-stu-id="df77a-186">Configure machine proxy and internet connectivity settings</span></span>](configure-proxy-internet.md) |
|<span data-ttu-id="df77a-187">EDR</span><span class="sxs-lookup"><span data-stu-id="df77a-187">EDR</span></span> | [<span data-ttu-id="df77a-188">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="df77a-188">Windows Server 2016</span></span>](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[<span data-ttu-id="df77a-189">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="df77a-189">Windows Server 2012 R2</span></span>](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[<span data-ttu-id="df77a-190">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="df77a-190">Windows Server 2008 R2 SP1</span></span>](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[<span data-ttu-id="df77a-191">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="df77a-191">Windows 8.1</span></span>](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[<span data-ttu-id="df77a-192">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="df77a-192">Windows 7 SP1</span></span>](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) | [<span data-ttu-id="df77a-193">프록시 및 인터넷 연결 설정 구성</span><span class="sxs-lookup"><span data-stu-id="df77a-193">Configure proxy and internet connectivity settings</span></span>](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|<span data-ttu-id="df77a-194">EDR</span><span class="sxs-lookup"><span data-stu-id="df77a-194">EDR</span></span>  |<span data-ttu-id="df77a-195">macOS:</span><span class="sxs-lookup"><span data-stu-id="df77a-195">macOS:</span></span> <p><span data-ttu-id="df77a-196">11.3.1(Big Sur)</span><span class="sxs-lookup"><span data-stu-id="df77a-196">11.3.1 (Big Sur)</span></span><p><span data-ttu-id="df77a-197">10.15(카탈로나)</span><span class="sxs-lookup"><span data-stu-id="df77a-197">10.15 (Catalina)</span></span><p><span data-ttu-id="df77a-198">10.14(모잡)</span><span class="sxs-lookup"><span data-stu-id="df77a-198">10.14 (Mojave)</span></span>  | [<span data-ttu-id="df77a-199">MacOS의 끝점용 Defender: 네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="df77a-199">Defender for Endpoint on macOS: Network connections</span></span>](microsoft-defender-endpoint-mac.md#network-connections) |
|[<span data-ttu-id="df77a-200">Windows Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="df77a-200">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md) | [<span data-ttu-id="df77a-201">Windows 10</span><span class="sxs-lookup"><span data-stu-id="df77a-201">Windows 10</span></span>](/windows/release-health/release-information) <p> [<span data-ttu-id="df77a-202">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="df77a-202">Windows Server 2019</span></span>](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[<span data-ttu-id="df77a-203">Windows 서버 1803 이상</span><span class="sxs-lookup"><span data-stu-id="df77a-203">Windows Server 1803 or later</span></span>](/windows-server/get-started/whats-new-in-windows-server-1803) <p>[<span data-ttu-id="df77a-204">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="df77a-204">Windows Server 2016</span></span>](/windows-server/get-started/whats-new-in-windows-server-2016) |[<span data-ttu-id="df77a-205">Microsoft Defender 바이러스 백신 네트워크 연결 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="df77a-205">Configure and validate Microsoft Defender Antivirus network connections</span></span>](configure-network-connections-microsoft-defender-antivirus.md) |
|<span data-ttu-id="df77a-206">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="df77a-206">Antivirus</span></span> |<span data-ttu-id="df77a-207">macOS:</span><span class="sxs-lookup"><span data-stu-id="df77a-207">macOS:</span></span> <p><span data-ttu-id="df77a-208">11.3.1(Big Sur)</span><span class="sxs-lookup"><span data-stu-id="df77a-208">11.3.1 (Big Sur)</span></span><p><span data-ttu-id="df77a-209">10.15(카탈로나)</span><span class="sxs-lookup"><span data-stu-id="df77a-209">10.15 (Catalina)</span></span><p><span data-ttu-id="df77a-210">10.14(모잡)</span><span class="sxs-lookup"><span data-stu-id="df77a-210">10.14 (Mojave)</span></span> |[<span data-ttu-id="df77a-211">MacOS의 끝점용 Defender: 네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="df77a-211">Defender for Endpoint on macOS: Network connections</span></span>](microsoft-defender-endpoint-mac.md#network-connections) |
|<span data-ttu-id="df77a-212">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="df77a-212">Antivirus</span></span> |<span data-ttu-id="df77a-213">Linux:</span><span class="sxs-lookup"><span data-stu-id="df77a-213">Linux:</span></span> <p><span data-ttu-id="df77a-214">RHEL 7.2+</span><span class="sxs-lookup"><span data-stu-id="df77a-214">RHEL 7.2+</span></span><p><span data-ttu-id="df77a-215">CentOS Linux 7.2+</span><span class="sxs-lookup"><span data-stu-id="df77a-215">CentOS Linux 7.2+</span></span><p><span data-ttu-id="df77a-216">Ubuntu 16 LTS 이상</span><span class="sxs-lookup"><span data-stu-id="df77a-216">Ubuntu 16 LTS, or higher LTS</span></span><p><span data-ttu-id="df77a-217">SLES 12+</span><span class="sxs-lookup"><span data-stu-id="df77a-217">SLES 12+</span></span><p><span data-ttu-id="df77a-218">데비안 9+</span><span class="sxs-lookup"><span data-stu-id="df77a-218">Debian 9+</span></span><p><span data-ttu-id="df77a-219">Oracle Linux 7.2</span><span class="sxs-lookup"><span data-stu-id="df77a-219">Oracle Linux 7.2</span></span> |[<span data-ttu-id="df77a-220">Linux의 끝점용 Defender: 네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="df77a-220">Defender for Endpoint on Linux: Network connections</span></span>](microsoft-defender-endpoint-linux.md#network-connections) 

## <a name="next-step"></a><span data-ttu-id="df77a-221">다음 단계</span><span class="sxs-lookup"><span data-stu-id="df77a-221">Next step</span></span>

<span data-ttu-id="df77a-222">**축하합니다!**</span><span class="sxs-lookup"><span data-stu-id="df77a-222">**Congratulations**!</span></span> <span data-ttu-id="df77a-223">[McAfee에서 끝점용 Defender로](mcafee-to-microsoft-defender-migration.md#the-migration-process)마이그레이션하는 준비 단계를 완료했습니다! </span><span class="sxs-lookup"><span data-stu-id="df77a-223">You have completed the **Prepare** phase of [migrating from McAfee to Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)!</span></span>

- <span data-ttu-id="df77a-224">[끝점에 대한 Defender 설정으로 진행합니다.](mcafee-to-microsoft-defender-setup.md)</span><span class="sxs-lookup"><span data-stu-id="df77a-224">[Proceed to set up Defender for Endpoint](mcafee-to-microsoft-defender-setup.md).</span></span>
