---
title: Microsoft Endpoint Configuration Manager를 사용하여 온보딩
description: 다음을 사용하여 끝점용 Microsoft Defender에 온보딩하는 Microsoft Endpoint Configuration Manager
keywords: 온보딩, 구성, 배포, 배포, 끝점 구성 관리자, Endpoint용 Microsoft Defender, 컬렉션 만들기, 끝점 감지 응답, 차세대 보호, 공격 표면 감소, Microsoft 끝점 구성 관리자
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: eab23ddeb9011e80cf2835b8d38b2d3fad4b7089
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843509"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="68a85-104">Microsoft Endpoint Configuration Manager를 사용하여 온보딩</span><span class="sxs-lookup"><span data-stu-id="68a85-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="68a85-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="68a85-105">**Applies to:**</span></span>
- [<span data-ttu-id="68a85-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="68a85-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="68a85-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68a85-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="68a85-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="68a85-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="68a85-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="68a85-110">이 문서는 배포 가이드의 일부로, 온보더링 방법의 예로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="68a85-111">계획 [항목에서는](deployment-strategy.md) 디바이스를 서비스에 온보드하는 여러 가지 방법이 제공되었습니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="68a85-112">이 항목에서는 공동 관리 아키텍처에 대해 다산합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="68a85-113">![클라우드 기본 아키텍처의 이미지 ](images/co-management-architecture.png)
 *환경 아키텍처 다이어그램*</span><span class="sxs-lookup"><span data-stu-id="68a85-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="68a85-114">Endpoint용 Defender는 다양한 끝점 및 도구의 온보딩을 지원하기는 하지만 이 문서에서는 이를 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="68a85-115">지원되는 다른 배포 도구 및 방법을 사용하는 일반적인 온보드에 대한 자세한 내용은 [Onboarding overview 를 참조하세요.](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="68a85-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="68a85-116">이 항목에서는 사용자에게 다음을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-116">This topic guides users in:</span></span>
- <span data-ttu-id="68a85-117">1단계: Windows 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="68a85-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="68a85-118">2단계: 끝점 기능에 대한 Defender 구성</span><span class="sxs-lookup"><span data-stu-id="68a85-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="68a85-119">이 온보더링 지침은 다음 기본 단계를 안내합니다. 이 가이드를 사용할 때 Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="68a85-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="68a85-120">**컬렉션에서 컬렉션 Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="68a85-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="68a85-121">**Microsoft Defender를 사용하여 끝점 기능을 Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="68a85-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="68a85-122">이 Windows 배포에서는 모든 디바이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="68a85-123">1단계: Windows 사용하여 Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="68a85-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="68a85-124">컬렉션 만들기</span><span class="sxs-lookup"><span data-stu-id="68a85-124">Collection creation</span></span>
<span data-ttu-id="68a85-125">장치를 Windows 10 온보 Microsoft Endpoint Configuration Manager 배포는 기존 컬렉션을 대상으로 지정하거나 테스트하기 위해 새 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="68a85-126">그룹 정책 또는 수동 방법과 같은 도구를 사용하여 온보더링하면 시스템에 에이전트가 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="68a85-127">Microsoft Endpoint Configuration Manager 콘솔 내에서 온보더링 프로세스는 콘솔 내의 규정 준수 설정의 일부로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="68a85-128">이 필수 구성을 받는 모든 시스템은 Configuration Manager 클라이언트가 관리 지점에서 이 정책을 계속 받는 한 해당 구성을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="68a85-129">다음 단계에 따라 온보더를 사용하여 끝점을 Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="68a85-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="68a85-130">Microsoft Endpoint Configuration Manager 콘솔에서 자산 및 준수 **\> 개요 장치 \> 컬렉션으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![Microsoft Endpoint Configuration Manager 마법사의 이미지1](images/configmgr-device-collections.png)

2. <span data-ttu-id="68a85-132">장치 **컬렉션을 마우스 오른쪽 단추로 클릭하고** **장치 컬렉션 만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![Microsoft Endpoint Configuration Manager 마법사의 이미지2](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="68a85-134">이름 **및** **제한 컬렉션을 제공한** 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager 마법사의 이미지3](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="68a85-136">규칙 **추가를** 선택하고 쿼리 **규칙 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![Microsoft Endpoint Configuration Manager 마법사4의 이미지](images/configmgr-query-rule.png)

5.  <span data-ttu-id="68a85-138">직접 **구성원 마법사에서** **다음을 클릭하고** 쿼리 문 **편집 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![Microsoft Endpoint Configuration Manager 마법사5의 이미지](images/configmgr-direct-membership.png)

6. <span data-ttu-id="68a85-140">조건을 **선택한** 다음 별 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-140">Select **Criteria** and then choose the star icon.</span></span>

     ![Microsoft Endpoint Configuration Manager 마법사6의 이미지](images/configmgr-criteria.png)

7. <span data-ttu-id="68a85-142">기준 유형을 **단순** 값으로 유지  , 운영 체제 **-** 빌드 번호, 연산자가 14393보다 크거나 같고 값 **14393으로** 선택한 후 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![Microsoft Endpoint Configuration Manager 이미지7](images/configmgr-simple-value.png)

8. <span data-ttu-id="68a85-144">다음을 **선택하고** **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-144">Select **Next** and **Close**.</span></span>

    ![Microsoft Endpoint Configuration Manager 마법사의 이미지8](images/configmgr-membership-rules.png)

9. <span data-ttu-id="68a85-146">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-146">Select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager Microsoft Endpoint Configuration Manager 이미지](images/configmgr-confirm.png)


<span data-ttu-id="68a85-148">이 작업을 완료한 후 이제 환경의 모든 Windows 10 장치 컬렉션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="68a85-149">2단계: 끝점용 Microsoft Defender 기능 구성</span><span class="sxs-lookup"><span data-stu-id="68a85-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="68a85-150">이 섹션에서는 Microsoft Endpoint Configuration Manager 디바이스에서 다음 기능을 Windows 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="68a85-151">**엔드포인트 검색 및 대응**</span><span class="sxs-lookup"><span data-stu-id="68a85-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="68a85-152">**차세대 보호**</span><span class="sxs-lookup"><span data-stu-id="68a85-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="68a85-153">**공격 표면 감소**</span><span class="sxs-lookup"><span data-stu-id="68a85-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="68a85-154">엔드포인트 감지 및 응답</span><span class="sxs-lookup"><span data-stu-id="68a85-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="68a85-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="68a85-155">Windows 10</span></span>
<span data-ttu-id="68a85-156">정책 내에서 Microsoft Defender 보안 센터 '.onboarding' 정책을 다운로드하여 System Center Configuration Manager 정책을 Windows 10 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="68a85-157">Microsoft Defender 보안 센터 포털에서 설정 [를 선택한 다음 온보더링을 선택합니다.](https://securitycenter.windows.com/preferences2/onboarding)</span><span class="sxs-lookup"><span data-stu-id="68a85-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="68a85-158">배포 방법에서 지원되는 버전의 **Microsoft Endpoint Configuration Manager.**</span><span class="sxs-lookup"><span data-stu-id="68a85-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![끝점 온보딩 마법사용 Microsoft Defender의 이미지10](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="68a85-160">패키지 **다운로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-160">Select **Download package**.</span></span>

    ![끝점 온보딩 마법사용 Microsoft Defender의 이미지11](images/mdatp-download-package.png)

4. <span data-ttu-id="68a85-162">접근성 있는 위치에 패키지를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="68a85-163">다음 Microsoft Endpoint Configuration Manager: 자산 및 준수 정책 개요 > **정책 > Endpoint Protection > Microsoft Defender ATP 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="68a85-164">정책 Microsoft Defender ATP 마우스 오른쪽 **단추로 클릭하고** **정책 Microsoft Defender ATP 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![Microsoft Endpoint Configuration Manager wizard12의 이미지](images/configmgr-create-policy.png)

7. <span data-ttu-id="68a85-166">이름과 설명을 입력하고 **온보더링이** 선택되어 있는지 확인한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager wizard13의 이미지](images/configmgr-policy-name.png)


8. <span data-ttu-id="68a85-168">**찾아보기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-168">Click **Browse**.</span></span>

9. <span data-ttu-id="68a85-169">위의 4단계에서 다운로드한 파일의 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="68a85-170">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-170">Click **Next**.</span></span>
11. <span data-ttu-id="68a85-171">적절한 **샘플(없음** 또는 모든 파일 형식)으로 **에이전트를 구성합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![구성 설정의 이미지1](images/configmgr-config-settings.png)

12. <span data-ttu-id="68a85-173">적절한 원격 분석(**Normal** 또는 **Expedited)을** 선택하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![구성 설정의 이미지2](images/configmgr-telemetry.png)

14. <span data-ttu-id="68a85-175">구성을 확인한 후 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-175">Verify the configuration, then click **Next**.</span></span>

     ![구성 설정의 이미지3](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="68a85-177">**마법사가** 완료되면 닫기 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="68a85-178">Microsoft Endpoint Configuration Manager 콘솔에서 방금 만든 끝점용 Defender 정책을 마우스 오른쪽 단추로 클릭하고 배포를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![구성 설정의 이미지4](images/configmgr-deploy.png)

17. <span data-ttu-id="68a85-180">오른쪽 패널에서 이전에 만든 컬렉션을 선택하고 확인 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![구성 설정의 이미지5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="68a85-182">이전 버전의 Windows 클라이언트(Windows 7 및 Windows 8.1)</span><span class="sxs-lookup"><span data-stu-id="68a85-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="68a85-183">이전 버전의 작업 영역의 온보딩에 필요한 끝점 작업 영역 ID 및 작업 영역 키에 대한 Defender를 식별하려면 Windows.</span><span class="sxs-lookup"><span data-stu-id="68a85-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="68a85-184">Microsoft Defender 보안 센터 포털에서 온보 설정 > **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="68a85-185">운영 체제에서 Windows **7 SP1 및 8.1 을 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="68a85-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="68a85-186">작업 영역 **ID 및** 작업 영역 키를 **복사하여** 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="68a85-187">프로세스의 후반부에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-187">They will be used later in the process.</span></span>

    ![온보더링 이미지](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="68a85-189">MMA(Microsoft Monitoring Agent 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="68a85-190">MMA는 현재(2019년 1월 현재) 다음 운영 체제에서 Windows 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="68a85-191">서버 SKUS: Windows Server 2008 SP1 이상</span><span class="sxs-lookup"><span data-stu-id="68a85-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="68a85-192">클라이언트 SKUS: Windows 7 SP1 이상</span><span class="sxs-lookup"><span data-stu-id="68a85-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="68a85-193">MMA 에이전트는 디바이스에 Windows 합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="68a85-194">에이전트를 설치하려면 일부 시스템에서 MMA를 사용하여 데이터를 수집하기 위해 고객 환경 및 진단 원격 분석용 업데이트를 다운로드해야 합니다. [](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span><span class="sxs-lookup"><span data-stu-id="68a85-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="68a85-195">이러한 시스템 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="68a85-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="68a85-196">Windows 8.1</span></span>

    -   <span data-ttu-id="68a85-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="68a85-197">Windows 7</span></span>

    -   <span data-ttu-id="68a85-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="68a85-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="68a85-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="68a85-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="68a85-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="68a85-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="68a85-201">특히, Windows SP1의 경우 다음 패치를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="68a85-202">[KB4074598 설치](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="68a85-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="68a85-203">4..NET Framework 이상 또는 KB3154518 중 하나를 [](https://www.microsoft.com/download/details.aspx?id=30653) 
         [설치합니다.](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="68a85-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="68a85-204">동일한 시스템에 두 가지를 모두 설치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="68a85-205">프록시를 사용하여 인터넷에 연결하는 경우 프록시 설정 구성 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68a85-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="68a85-206">완료되면 1시간 이내에 포털에 온보드 엔드포인트가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="68a85-207">차세대 보호</span><span class="sxs-lookup"><span data-stu-id="68a85-207">Next generation protection</span></span> 
<span data-ttu-id="68a85-208">Microsoft Defender 바이러스 백신은 데스크톱, 휴대용 컴퓨터 및 서버에 대한 차세대 보호를 제공하는 기본 제공 맬웨어 방지 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="68a85-209">Microsoft Endpoint Configuration Manager 콘솔에서 자산 및 준수 개요 Endpoint Protection 맬웨어 방지 정책 만들기 **를 선택 합니다.** **\> \> \>**</span><span class="sxs-lookup"><span data-stu-id="68a85-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![맬웨어 방지 정책 이미지](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="68a85-211">예약된 **검사,** 검사 **설정,** 기본 **작업,** 실시간 **보호,** 제외 **설정,** **고급,** **위협** 다시 지정, **클라우드 보호** 서비스 **및** 보안 인텔리전스 업데이트를 선택하고 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![차세대 보호 창의 이미지1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="68a85-213">특정 산업이나 일부 엔터프라이즈 고객은 바이러스 백신 구성 방법에 대한 특정 요구가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="68a85-214">빠른 검사와 전체 검사 및 사용자 지정 검사</span><span class="sxs-lookup"><span data-stu-id="68a85-214">Quick scan versus full scan and custom scan</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="68a85-215">자세한 내용은 구성 프레임워크 Windows 보안 [참조](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="68a85-215">For more details, see [Windows Security configuration framework](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![차세대 보호 창의 이미지2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![차세대 보호 창의 이미지3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![차세대 보호 창의 이미지4](images/a28afc02c1940d5220b233640364970c.png)

    ![차세대 보호 창의 이미지5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![차세대 보호 창의 이미지6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![차세대 보호 창의 이미지7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![차세대 보호 창의 이미지8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![차세대 보호 창 9의 이미지](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="68a85-224">새로 만든 맬웨어 방지 정책을 마우스 오른쪽 단추로 클릭하고 배포를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![차세대 보호 창의 이미지10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="68a85-226">새 맬웨어 방지 정책을 Windows 10 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![차세대 보호 창의 이미지11](images/configmgr-select-collection.png)

<span data-ttu-id="68a85-228">이 작업을 완료한 후 이제 작업을 성공적으로 구성했습니다Windows Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="68a85-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="68a85-229">공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="68a85-229">Attack surface reduction</span></span>
<span data-ttu-id="68a85-230">Endpoint용 Defender의 공격 표면 감소 기조에는 Exploit Guard에서 사용할 수 있는 기능 집합이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="68a85-231">ASR(공격 표면 축소) 규칙, 제어된 폴더 액세스, 네트워크 보호 및 Exploit Protection</span><span class="sxs-lookup"><span data-stu-id="68a85-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="68a85-232">이러한 모든 기능은 감사 모드와 차단 모드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="68a85-233">감사 모드에서는 최종 사용자에게 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="68a85-234">추가 원격 분석만 수집하고 원격 분석에서 사용할 수 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="68a85-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="68a85-235">배포의 목표는 단계별 보안 컨트롤을 차단 모드로 이동하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="68a85-236">감사 모드에서 ASR 규칙을 설정하는 경우:</span><span class="sxs-lookup"><span data-stu-id="68a85-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="68a85-237">Microsoft Endpoint Configuration Manager 콘솔에서 Exploit Guard를 사용하여 자산 및 준수 Endpoint Protection **\> Windows Defender \> \> 탐색하고** Exploit Guard 정책 **만들기 를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="68a85-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![Microsoft Endpoint Configuration Manager console0의 이미지](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="68a85-239">공격 **표면 감소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="68a85-240">규칙을 **감사로 설정하고** 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-240">Set rules to **Audit** and click **Next**.</span></span>


    ![콘솔 Microsoft Endpoint Configuration Manager 이미지1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="68a85-242">다음 을 클릭하여 새 Exploit Guard 정책을 **확인 합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![콘솔 Microsoft Endpoint Configuration Manager 이미지2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="68a85-244">정책을 만든 후 닫기 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-244">Once the policy is created click **Close**.</span></span>

    ![콘솔 Microsoft Endpoint Configuration Manager 이미지3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![콘솔 Microsoft Endpoint Manager 이미지1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="68a85-247">새로 만든 정책을 마우스 오른쪽 단추로 클릭하고 배포 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![콘솔 Microsoft Endpoint Configuration Manager 이미지](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="68a85-249">새로 만든 Windows 10 정책을 대상으로 지정하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![콘솔 Microsoft Endpoint Configuration Manager 이미지](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="68a85-251">이 작업을 완료한 후 감사 모드에서 ASR 규칙을 성공적으로 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="68a85-252">다음은 ASR 규칙이 끝점에 올바르게 적용되는지 확인하기 위한 추가 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="68a85-253">(이 경우 몇 분 정도 걸릴 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="68a85-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="68a85-254">웹 브라우저에서 로 <https://securitycenter.windows.com> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="68a85-255">왼쪽 **메뉴에서** 구성 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="68a85-256">공격 **표면 관리 패널에서** 공격 표면 관리로 이동을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![공격 표면 관리 이미지](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="68a85-258">공격 **표면** 감소 규칙 보고서에서 구성 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="68a85-259">각 디바이스에서 ASR 규칙 구성 개요 및 ASR 규칙 상태를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![공격 표면 감소 규칙 보고서의 스크린샷1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="68a85-261">각 장치를 클릭하면 ASR 규칙의 구성 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-261">Click each device shows configuration details of ASR rules.</span></span>

    ![공격 표면 감소 규칙 보고서의 스크린샷2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="68a85-263">자세한 [내용은 ASR 규칙 배포 및](/microsoft-365/security/defender-endpoint/configure-machines-asr)   검색 최적화를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-263">See [Optimize ASR rule deployment and detections](/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="68a85-264">감사 모드에서 네트워크 보호 규칙을 설정:</span><span class="sxs-lookup"><span data-stu-id="68a85-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="68a85-265">Microsoft Endpoint Configuration Manager 콘솔에서 Exploit Guard를 사용하여 자산 및 준수 Endpoint Protection **\> Windows Defender \> \> 탐색하고** Exploit Guard 정책 **만들기 를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="68a85-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Configuration Manager1의 System Center 스크린샷](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="68a85-267">네트워크 **보호 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="68a85-268">설정을 감사로 **설정하고** 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![Confirugatiom Manager2의 System Center 스크린샷](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="68a85-270">다음 을 클릭하여 새 Exploit Guard 정책을 **확인 합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![스크린샷 Exploit GUard 정책1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="68a85-272">정책이 만들어지면 닫기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-272">Once the policy is created click on **Close**.</span></span>

    ![스크린샷 Exploit GUard 정책2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="68a85-274">새로 만든 정책을 마우스 오른쪽 단추로 클릭하고 배포 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![스크린샷 Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="68a85-276">새로 만든 Windows 10 정책을 선택하고 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![스크린샷 Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="68a85-278">이 작업을 완료한 후 감사 모드에서 네트워크 보호를 성공적으로 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="68a85-279">감사 모드에서 제어된 폴더 액세스 규칙을 설정하는 경우:</span><span class="sxs-lookup"><span data-stu-id="68a85-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="68a85-280">Microsoft Endpoint Configuration Manager 콘솔에서 Exploit Guard를 사용하여 자산 및 준수 Endpoint Protection **\> Windows Defender \> \> 탐색하고** Exploit Guard 정책 **만들기 를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="68a85-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Microsoft Endpoint Configuration Manager3의 스크린샷](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="68a85-282">제어된 **폴더 액세스 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="68a85-283">구성을 **감사로 설정하고** 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager4의 스크린샷](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="68a85-285">다음 을 클릭하여 새 Exploit Guard 정책을 **확인 합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager5의 스크린샷](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="68a85-287">정책이 만들어지면 닫기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-287">Once the policy is created click on **Close**.</span></span>

    ![Microsoft Endpoint Configuration Manager6의 스크린샷](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="68a85-289">새로 만든 정책을 마우스 오른쪽 단추로 클릭하고 배포 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Microsoft Endpoint Configuration Manager7의 스크린샷](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="68a85-291">새로 만든 Windows 10 정책을 대상으로 지정하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68a85-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Microsoft Endpoint Configuration Manager8의 스크린샷](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="68a85-293">이제 감사 모드에서 제어된 폴더 액세스를 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="68a85-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="68a85-294">관련 항목</span><span class="sxs-lookup"><span data-stu-id="68a85-294">Related topic</span></span>
- [<span data-ttu-id="68a85-295">Microsoft Endpoint Manager를 사용하여 온보딩</span><span class="sxs-lookup"><span data-stu-id="68a85-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
