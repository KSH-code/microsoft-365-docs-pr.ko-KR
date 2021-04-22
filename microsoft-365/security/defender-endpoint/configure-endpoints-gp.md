---
title: 그룹 정책을 통해 끝점용 Microsoft Defender에 Windows 10 장치 온보딩
description: 그룹 정책을 사용하여 Windows 10 장치에 구성 패키지를 배포하여 서비스에 온보드합니다.
keywords: 그룹 정책, 장치 관리를 사용하여 장치 구성, 끝점 장치용 Microsoft Defender 구성, 끝점 장치용 Microsoft Defender 온보딩, 그룹 정책
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: b8f56c8f2ba92073ea7ae9464f199d9c900b932f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933964"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="0144d-104">그룹 정책을 사용하여 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="0144d-104">Onboard Windows 10 devices using Group Policy</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0144d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0144d-105">**Applies to:**</span></span>

- <span data-ttu-id="0144d-106">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="0144d-106">Group Policy</span></span>
- <span data-ttu-id="0144d-107">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="0144d-107">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="0144d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0144d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0144d-109">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="0144d-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0144d-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="0144d-111">GP(그룹 정책) 업데이트를 사용하여 패키지를 배포하려면 Windows Server 2008 R2 이상에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-111">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>
> 
> <span data-ttu-id="0144d-112">Windows Server 2019의 경우 그룹 정책 기본 설정에서 만드는 XML 파일의 NT AUTHORITY\Well-Known-System-Account를 NT AUTHORITY\SYSTEM으로 교체해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-112">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="0144d-113">그룹 정책을 사용하여 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="0144d-113">Onboard devices using Group Policy</span></span>

<span data-ttu-id="0144d-114">[![다양한 배포 경로를 보여 주며 PDF 이미지](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0144d-114">[![Image of the PDF showing the various deployment paths](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span></span>

<span data-ttu-id="0144d-115">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) 또는 [Visio를](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) 확인하여 끝점용 Defender 배포에서 다양한 경로를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 



1. <span data-ttu-id="0144d-116">서비스 온보더링 마법사에서 다운로드한 GP 구성 패키지 *.zip* 파일(WindowsDefenderATPOnboardingPackage.zip)을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="0144d-117">Microsoft Defender 보안 센터에서 패키지를 [다운로드할 수 있습니다.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="0144d-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>
 
    1. <span data-ttu-id="0144d-118">탐색 창에서 설정   >  **온보드 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0144d-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="0144d-119">운영 체제로 Windows 10을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-119">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="0144d-120">배포 **방법 필드에서** 그룹 정책 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0144d-120">In the **Deployment method** field, select **Group policy**.</span></span>
    
    1. <span data-ttu-id="0144d-121">패키지 **다운로드를 클릭하고** .zip 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-121">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="0144d-122">.zip 파일의 내용을 장치에서 액세스할 수 있는 공유 읽기 전용 위치에 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-122">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="0144d-123">*OptionalParamsPolicy라는* 폴더와 *WindowsDefenderATPOnboardingScript.cmd* 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-123">You should have a folder called *OptionalParamsPolicy* and the file *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="0144d-124">GPMC(그룹 정책 관리 콘솔)를 열고 구성할 GPO(그룹 정책 개체)를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.** [](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)</span><span class="sxs-lookup"><span data-stu-id="0144d-124">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="0144d-125">그룹 정책 **관리 편집기에서** 컴퓨터 **구성,** **기본** 설정, 제어판 **설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="0144d-125">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="0144d-126">예약된 **작업 을** 마우스 오른쪽 단추로 클릭하고 새로 고침을 클릭한 다음 직접 실행 **작업(Windows 7 이상)을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0144d-126">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

6. <span data-ttu-id="0144d-127">작업 **창이** 열리면 일반 **탭으로** 이동됩니다. 보안 **옵션에서** **사용자** 또는 그룹 변경을 클릭하고 SYSTEM을 입력한 다음 이름 **확인을** 클릭한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0144d-127">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="0144d-128">작업이 실행될 사용자 계정으로 NT AUTHORITY\SYSTEM이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-128">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

7. <span data-ttu-id="0144d-129">사용자가 **로그온되어** 있는지 여부에 따라  실행을 선택하고 가장 높은 권한으로 실행 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-129">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

8. <span data-ttu-id="0144d-130">작업 **탭으로 이동하여** 새로 **고치기...를 클릭합니다.** 작업 **필드에서 프로그램** **시작이 선택되어 있도록** 합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-130">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="0144d-131">공유 *WindowsDefenderATPOnboardingScript.cmd* 파일의 파일 이름과 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-131">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

9. <span data-ttu-id="0144d-132">확인을 **클릭하고** 열려 있는 GPMC 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-132">Click **OK** and close any open GPMC windows.</span></span>

>[!TIP]
> <span data-ttu-id="0144d-133">장치를 온보드한 후 검색 테스트를 실행하여 장치가 서비스에 제대로 온보드되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-133">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="0144d-134">자세한 내용은 새로 온보딩된 Endpoint 디바이스용 Defender에서 검색 테스트 [실행을 참조하세요.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="0144d-134">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>

## <a name="additional-defender-for-endpoint-configuration-settings"></a><span data-ttu-id="0144d-135">끝점 구성 설정에 대한 추가 Defender</span><span class="sxs-lookup"><span data-stu-id="0144d-135">Additional Defender for Endpoint configuration settings</span></span>
<span data-ttu-id="0144d-136">각 디바이스에 대해 Microsoft Defender 보안 센터를 통해 요청이 있을 때 장치에서 샘플을 수집하여 심층 분석을 위해 파일을 제출할 수 있는지 여부를 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-136">For each device, you can state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="0144d-137">GP(그룹 정책)를 사용하여 심층 분석 기능에 사용되는 샘플 공유 설정과 같은 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-137">You can use Group Policy (GP) to configure settings, such as settings for the sample sharing used in the deep analysis feature.</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="0144d-138">샘플 수집 설정 구성</span><span class="sxs-lookup"><span data-stu-id="0144d-138">Configure sample collection settings</span></span>
1.  <span data-ttu-id="0144d-139">GP 관리 장치에서 구성 패키지에서 다음 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-139">On your GP management device, copy the following files from the configuration package:</span></span>

    - <span data-ttu-id="0144d-140">_AtpConfiguration.admx를_ _C: \\ Windows \\ PolicyDefinitions에 복사_</span><span class="sxs-lookup"><span data-stu-id="0144d-140">Copy _AtpConfiguration.admx_ into _C:\\Windows\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="0144d-141">_AtpConfiguration.adml을_ _C: \\ Windows \\ PolicyDefinitions \\ en-US에 복사_</span><span class="sxs-lookup"><span data-stu-id="0144d-141">Copy _AtpConfiguration.adml_ into _C:\\Windows\\PolicyDefinitions\\en-US_</span></span>

    <span data-ttu-id="0144d-142">그룹 정책 관리 템플릿에 대한 중앙 저장소를 사용하는 경우 [구성](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)패키지에서 다음 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-142">If you are using a [Central Store for Group Policy Administrative Templates](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra), copy the following files from the configuration package:</span></span>
    
    - <span data-ttu-id="0144d-143">_AtpConfiguration.admx를_ _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ 정책 \\ 정책데 정의에 복사_</span><span class="sxs-lookup"><span data-stu-id="0144d-143">Copy _AtpConfiguration.admx_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="0144d-144">_AtpConfiguration.adml을_ _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ 정책 \\ 정책데 정의itions \\ en-US에 복사_</span><span class="sxs-lookup"><span data-stu-id="0144d-144">Copy _AtpConfiguration.adml_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions\\en-US_</span></span>

2.  <span data-ttu-id="0144d-145">그룹 정책 [관리 콘솔을 열고](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)구성할 GPO를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0144d-145">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), right-click the GPO you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="0144d-146">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="0144d-146">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="0144d-147">**정책,** 관리 **템플릿을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0144d-147">Click **Policies**, then **Administrative templates**.</span></span>

5.  <span data-ttu-id="0144d-148">**Windows 구성 요소를 클릭한** 다음 **ATP Windows Defender 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0144d-148">Click **Windows components** and then **Windows Defender ATP**.</span></span>

6.  <span data-ttu-id="0144d-149">장치에서 샘플 공유를 사용하도록 설정하거나 사용하지 않도록 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="0144d-149">Choose to enable or disable sample sharing from your devices.</span></span>

>[!NOTE]
> <span data-ttu-id="0144d-150">값을 설정하지 않은 경우 기본값은 샘플 컬렉션을 사용하도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-150">If you don't set a value, the default value is to enable sample collection.</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="0144d-151">기타 권장 구성 설정</span><span class="sxs-lookup"><span data-stu-id="0144d-151">Other recommended configuration settings</span></span>

### <a name="update-endpoint-protection-configuration"></a><span data-ttu-id="0144d-152">끝점 보호 구성 업데이트</span><span class="sxs-lookup"><span data-stu-id="0144d-152">Update endpoint protection configuration</span></span>

<span data-ttu-id="0144d-153">온보딩 스크립트를 구성한 후 동일한 그룹 정책을 계속 편집하여 끝점 보호 구성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-153">After configuring the onboarding script, continue editing the same group policy to add endpoint protection configurations.</span></span> <span data-ttu-id="0144d-154">Windows 10 또는 Server 2019를 실행하는 시스템에서 그룹 정책을 편집하여 필요한 모든 Microsoft Defender 바이러스 백신 기능을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-154">Perform group policy edits from a system running Windows 10 or Server 2019 to ensure you have all of the required Microsoft Defender Antivirus capabilities.</span></span> <span data-ttu-id="0144d-155">그룹 정책 개체를 닫았다가 다시 열고 Defender ATP 구성 설정을 등록해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-155">You may need to close and reopen the group policy object to register the Defender ATP configuration settings.</span></span>

<span data-ttu-id="0144d-156">모든 정책은 에 `Computer Configuration\Policies\Administrative Templates` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-156">All policies are located under `Computer Configuration\Policies\Administrative Templates`.</span></span>

<span data-ttu-id="0144d-157">**정책 위치:** \Windows 구성 요소\Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="0144d-157">**Policy location:** \Windows Components\Windows Defender ATP</span></span>

<span data-ttu-id="0144d-158">정책</span><span class="sxs-lookup"><span data-stu-id="0144d-158">Policy</span></span> | <span data-ttu-id="0144d-159">설정</span><span class="sxs-lookup"><span data-stu-id="0144d-159">Setting</span></span> 
:---|:---
<span data-ttu-id="0144d-160">샘플 컬렉션 사용\사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="0144d-160">Enable\Disable Sample collection</span></span>|   <span data-ttu-id="0144d-161">사용 - "컴퓨터의 샘플 수집 사용" 확인</span><span class="sxs-lookup"><span data-stu-id="0144d-161">Enabled - "Enable sample collection on machines" checked</span></span>

<br/>

<span data-ttu-id="0144d-162">**정책 위치:**  \Windows 구성 요소\Windows Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="0144d-162">**Policy location:**  \Windows Components\Windows Defender Antivirus</span></span>

<span data-ttu-id="0144d-163">정책</span><span class="sxs-lookup"><span data-stu-id="0144d-163">Policy</span></span> | <span data-ttu-id="0144d-164">설정</span><span class="sxs-lookup"><span data-stu-id="0144d-164">Setting</span></span> 
:---|:---
<span data-ttu-id="0144d-165">잠재적으로 원치 않는 응용 프로그램에 대한 검색 구성</span><span class="sxs-lookup"><span data-stu-id="0144d-165">Configure detection for potentially unwanted applications</span></span> | <span data-ttu-id="0144d-166">사용, 차단</span><span class="sxs-lookup"><span data-stu-id="0144d-166">Enabled, Block</span></span>

<br/>

<span data-ttu-id="0144d-167">**정책 위치:** \Windows 구성 요소\Windows Defender 바이러스 백신\MAPS</span><span class="sxs-lookup"><span data-stu-id="0144d-167">**Policy location:** \Windows Components\Windows Defender Antivirus\MAPS</span></span>

<span data-ttu-id="0144d-168">정책</span><span class="sxs-lookup"><span data-stu-id="0144d-168">Policy</span></span> | <span data-ttu-id="0144d-169">설정</span><span class="sxs-lookup"><span data-stu-id="0144d-169">Setting</span></span> 
:---|:---
<span data-ttu-id="0144d-170">Microsoft MAPS에 가입</span><span class="sxs-lookup"><span data-stu-id="0144d-170">Join Microsoft MAPS</span></span> | <span data-ttu-id="0144d-171">사용, 고급 지도</span><span class="sxs-lookup"><span data-stu-id="0144d-171">Enabled, Advanced MAPS</span></span>
<span data-ttu-id="0144d-172">추가 분석이 필요한 경우 파일 샘플 보내기</span><span class="sxs-lookup"><span data-stu-id="0144d-172">Send file samples when further analysis is required</span></span> | <span data-ttu-id="0144d-173">사용, 안전한 샘플 보내기</span><span class="sxs-lookup"><span data-stu-id="0144d-173">Enabled, Send safe samples</span></span>

<br/>

<span data-ttu-id="0144d-174">**정책 위치:** \Windows 구성 요소\Windows Defender 바이러스 백신\실시간 보호</span><span class="sxs-lookup"><span data-stu-id="0144d-174">**Policy location:** \Windows Components\Windows Defender Antivirus\Real-time Protection</span></span>

<span data-ttu-id="0144d-175">정책</span><span class="sxs-lookup"><span data-stu-id="0144d-175">Policy</span></span> | <span data-ttu-id="0144d-176">설정</span><span class="sxs-lookup"><span data-stu-id="0144d-176">Setting</span></span> 
:---|:---
<span data-ttu-id="0144d-177">실시간 보호 끄기</span><span class="sxs-lookup"><span data-stu-id="0144d-177">Turn off real-time protection</span></span>|<span data-ttu-id="0144d-178">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0144d-178">Disabled</span></span>
<span data-ttu-id="0144d-179">동작 모니터링 켜기</span><span class="sxs-lookup"><span data-stu-id="0144d-179">Turn on behavior monitoring</span></span>|<span data-ttu-id="0144d-180">사용</span><span class="sxs-lookup"><span data-stu-id="0144d-180">Enabled</span></span>
<span data-ttu-id="0144d-181">다운로드한 모든 파일 및 첨부 파일 검색</span><span class="sxs-lookup"><span data-stu-id="0144d-181">Scan all downloaded files and attachments</span></span>|<span data-ttu-id="0144d-182">사용</span><span class="sxs-lookup"><span data-stu-id="0144d-182">Enabled</span></span>
<span data-ttu-id="0144d-183">컴퓨터에서 파일 및 프로그램 활동 모니터링</span><span class="sxs-lookup"><span data-stu-id="0144d-183">Monitor file and program activity on your computer</span></span>|<span data-ttu-id="0144d-184">사용</span><span class="sxs-lookup"><span data-stu-id="0144d-184">Enabled</span></span>

<br/>

<span data-ttu-id="0144d-185">**정책 위치:**  \Windows 구성 요소\Windows Defender 바이러스 백신\검사</span><span class="sxs-lookup"><span data-stu-id="0144d-185">**Policy location:**  \Windows Components\Windows Defender Antivirus\Scan</span></span>

<span data-ttu-id="0144d-186">이러한 설정은 끝점의 주기적인 검색을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-186">These settings configure periodic scans of the endpoint.</span></span> <span data-ttu-id="0144d-187">매주 빠른 검사, 성능 허용을 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-187">We recommend performing a weekly quick scan, performance permitting.</span></span>

<span data-ttu-id="0144d-188">정책</span><span class="sxs-lookup"><span data-stu-id="0144d-188">Policy</span></span> | <span data-ttu-id="0144d-189">설정</span><span class="sxs-lookup"><span data-stu-id="0144d-189">Setting</span></span> 
:---|:---
<span data-ttu-id="0144d-190">예약된 검사를 실행하기 전에 최신 바이러스 및 스파이웨어 보안 인텔리전스 확인</span><span class="sxs-lookup"><span data-stu-id="0144d-190">Check for the latest virus and spyware security intelligence before running a scheduled scan</span></span> |<span data-ttu-id="0144d-191">사용</span><span class="sxs-lookup"><span data-stu-id="0144d-191">Enabled</span></span>


<br/>

<span data-ttu-id="0144d-192">**정책 위치:** \Windows 구성 요소\Windows Defender 바이러스 백신\Windows Defender Exploit Guard\공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="0144d-192">**Policy location:** \Windows Components\Windows Defender Antivirus\Windows Defender Exploit Guard\Attack Surface Reduction</span></span>

<span data-ttu-id="0144d-193">공격 표면 감소 규칙 사용자 지정에서 공격 표면 감소 GUID의 현재 [목록을 얻습니다.](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="0144d-193">Get the current list of attack surface reduction GUIDs from [Customize attack surface reduction rules](customize-attack-surface-reduction.md)</span></span>

1. <span data-ttu-id="0144d-194">공격 표면 **축소 구성 정책을 열** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-194">Open the **Configure Attack Surface Reduction** policy.</span></span>

1. <span data-ttu-id="0144d-195">**사용하도록 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-195">Select **Enabled**.</span></span>

1. <span data-ttu-id="0144d-196">표시 **단추를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-196">Select the **Show** button.</span></span>

1. <span data-ttu-id="0144d-197">값 이름 필드에 **값이** 2인 각 GUID를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-197">Add each GUID in the **Value Name** field with a Value of 2.</span></span>

   <span data-ttu-id="0144d-198">그러면 각 감사에 대해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-198">This will set each up for audit only.</span></span>

   ![공격 표면 축소 구성 이미지](images/asr-guid.png)



<span data-ttu-id="0144d-200">정책</span><span class="sxs-lookup"><span data-stu-id="0144d-200">Policy</span></span> | <span data-ttu-id="0144d-201">설정</span><span class="sxs-lookup"><span data-stu-id="0144d-201">Setting</span></span> 
:---|:---
<span data-ttu-id="0144d-202">제어된 폴더 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="0144d-202">Configure Controlled folder access</span></span>| <span data-ttu-id="0144d-203">사용, 감사 모드</span><span class="sxs-lookup"><span data-stu-id="0144d-203">Enabled, Audit Mode</span></span>



## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="0144d-204">그룹 정책을 사용하여 디바이스 오프보드</span><span class="sxs-lookup"><span data-stu-id="0144d-204">Offboard devices using Group Policy</span></span>
<span data-ttu-id="0144d-205">보안상의 이유로, 오프보드 장치에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-205">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="0144d-206">장치에 전송된 만료된 오프보더 패키지는 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-206">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="0144d-207">오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-207">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="0144d-208">온보드 및 오프보더 정책을 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-208">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="0144d-209">Microsoft Defender 보안 센터에서 오프보딩 [패키지를 다운로드합니다.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="0144d-209">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="0144d-210">탐색 창에서 설정 **오프보링**  >  **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0144d-210">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="0144d-211">운영 체제로 Windows 10을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-211">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="0144d-212">배포 **방법 필드에서** 그룹 정책 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0144d-212">In the **Deployment method** field, select **Group policy**.</span></span>

    1. <span data-ttu-id="0144d-213">패키지 **다운로드를 클릭하고** .zip 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-213">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="0144d-214">.zip 파일의 내용을 장치에서 액세스할 수 있는 공유 읽기 전용 위치에 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-214">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="0144d-215">이름이 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd 입니다.*</span><span class="sxs-lookup"><span data-stu-id="0144d-215">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="0144d-216">GPMC(그룹 정책 관리 콘솔)를 열고 구성할 GPO(그룹 정책 개체)를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.** [](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)</span><span class="sxs-lookup"><span data-stu-id="0144d-216">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="0144d-217">그룹 정책 **관리 편집기에서** 컴퓨터 **구성,** 기본 설정, 제어판 **설정으로 이동합니다.** </span><span class="sxs-lookup"><span data-stu-id="0144d-217">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="0144d-218">예약된 **작업 을 마우스 오른쪽** 단추로 클릭하고 새로 고를 **클릭한** 다음 직접 실행 **작업을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0144d-218">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

6. <span data-ttu-id="0144d-219">작업 **창이** 열리면 일반 **탭으로** 이동됩니다. 보안 옵션 에서 로컬 시스템 사용자 계정(BUILTIN\SYSTEM)을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0144d-219">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

7. <span data-ttu-id="0144d-220">사용자가 **로그온되어** 있는지 여부에 따라 실행을 선택하고 가장 높은 권한으로 실행 **확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-220">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

8. <span data-ttu-id="0144d-221">작업 **탭으로** 이동하여 새로 **고치기... 를 클릭합니다.** 작업 **필드에서 프로그램** **시작이 선택되어 있도록** 합니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-221">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="0144d-222">공유 파일 이름과 위치를 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd 파일입니다.*</span><span class="sxs-lookup"><span data-stu-id="0144d-222">Enter the file name and location of the shared  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

9. <span data-ttu-id="0144d-223">확인을 **클릭하고** 열려 있는 GPMC 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-223">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0144d-224">오프보더링을 통해 디바이스가 포털에 센서 데이터 전송을 중지하지만, 디바이스에서 전송한 모든 경고에 대한 참조를 포함하여 장치의 데이터는 최대 6개월 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-224">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="0144d-225">장치 구성 모니터링</span><span class="sxs-lookup"><span data-stu-id="0144d-225">Monitor device configuration</span></span>
<span data-ttu-id="0144d-226">그룹 정책을 사용하는 경우 디바이스에서 정책 배포를 모니터링할 수 있는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-226">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="0144d-227">모니터링은 포털에서 직접 수행하거나 다른 배포 도구를 사용하여 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-227">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="0144d-228">포털을 사용하여 장치 모니터링</span><span class="sxs-lookup"><span data-stu-id="0144d-228">Monitor devices using the portal</span></span>
1. <span data-ttu-id="0144d-229">Microsoft [Defender 보안 센터로 이동](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="0144d-229">Go to [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span>
2. <span data-ttu-id="0144d-230">장치 **목록을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0144d-230">Click **Devices list**.</span></span>
3. <span data-ttu-id="0144d-231">장치가 나타나는지 확인</span><span class="sxs-lookup"><span data-stu-id="0144d-231">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="0144d-232">디바이스 목록 에 장치가 표시될 때 며칠이 **걸릴 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="0144d-232">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="0144d-233">여기에는 정책이 장치에 배포되는 데 걸리는 시간, 사용자가 로그온하는 데 걸리는 시간 및 끝점에서 보고를 시작하는 데 걸리는 시간이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0144d-233">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="0144d-234">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0144d-234">Related topics</span></span>
- [<span data-ttu-id="0144d-235">Microsoft Endpoint Configuration Manager를 사용하여 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="0144d-235">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="0144d-236">모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="0144d-236">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="0144d-237">로컬 스크립트를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="0144d-237">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="0144d-238">비영구 VDI(가상 데스크톱 인프라) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="0144d-238">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="0144d-239">새로 온보딩된 끝점 디바이스용 Microsoft Defender에서 검색 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="0144d-239">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](run-detection-test.md)
- [<span data-ttu-id="0144d-240">끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결</span><span class="sxs-lookup"><span data-stu-id="0144d-240">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
