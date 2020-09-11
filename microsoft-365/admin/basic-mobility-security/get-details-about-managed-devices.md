---
title: 기본 이동성 및 보안 관리 장치에 대 한 세부 정보 보기
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Windows PowerShell을 사용 하 여 조직의 기본 이동성 및 보안 장치에 대 한 세부 정보를 확인할 수 있습니다.
ms.openlocfilehash: d34263ee215c568834034f2735bb69d9cef9ac6d
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430259"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="d825e-103">기본 이동성 및 보안 관리 장치에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="d825e-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="d825e-104">이 문서에서는 Windows PowerShell을 사용 하 여 기본 이동성 및 보안을 위해 설정한 조직의 장치에 대 한 세부 정보를 가져오는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="d825e-105">여기에는 사용자가 사용할 수 있는 장치 세부 정보에 대 한 분석 과정이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="d825e-106">**자세한 정보**</span><span class="sxs-lookup"><span data-stu-id="d825e-106">**Detail**</span></span>|<span data-ttu-id="d825e-107">**PowerShell에서 조회할 작업**</span><span class="sxs-lookup"><span data-stu-id="d825e-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="d825e-108">장치가 기본 이동성 및 보안에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="d825e-109">자세한 내용은 [기본 이동성 및 보안을 사용 하 여 모바일 장치 등록](enroll-your-mobile-device.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d825e-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="d825e-110"> \*IsManaged*   매개 변수의 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="d825e-111">**True**= 디바이스가 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="d825e-112">**False**= 디바이스가 등록 되지 않음</span><span class="sxs-lookup"><span data-stu-id="d825e-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="d825e-113">장치가 장치 보안 정책을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="d825e-114">자세한 내용은 [장치 보안 정책 만들기](create-device-security-policies.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d825e-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="d825e-115"> \*Iscompliant*   매개 변수의 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="d825e-116">**True**   = 장치가 정책을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="d825e-117">**False**   = 장치가 정책을 준수 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="기본 모바일 및 보안 PowerShell 매개 변수":::

>[!NOTE]
><span data-ttu-id="d825e-119">이 문서의 명령 및 스크립트는 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)에서 관리 되는 모든 장치에 대 한 세부 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d825e-120">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="d825e-120">Before you begin</span></span>

<span data-ttu-id="d825e-121">이 문서에서 설명 하는 명령과 스크립트를 실행 하려면 몇 가지 사항을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="d825e-122">1 단계: Windows PowerShell 용 Azure Active Directory 모듈 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="d825e-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="d825e-123">이러한 단계에 대 한 자세한 내용은 [PowerShell을 사용 하 여 Microsoft 365에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d825e-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="d825e-124"> [IT 전문가 용 Microsoft Online Services 로그인 도우미](https://www.microsoft.com/download/details.aspx?id=41950)로 이동 하 여    *\*Microsoft online services 로그인 도우미에*\*대 한 다운로드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>   

2. <span data-ttu-id="d825e-125">다음 단계에 따라 Windows PowerShell용 Microsoft Azure Active Directory 모듈을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>   

    1. <span data-ttu-id="d825e-126">관리자 수준 PowerShell 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="d825e-127">Install-Module MSOnline 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-127">Run the Install-Module MSOnline command.</span></span>
    
    3. <span data-ttu-id="d825e-128">NuGet 공급자를 설치할지 묻는 메시지가 표시되면 Y를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>   

    4. <span data-ttu-id="d825e-129">PSGallery에서 모듈을 설치할지 묻는 메시지가 표시되면 Y를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>   

    5. <span data-ttu-id="d825e-130">설치 후 PowerShell 명령 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-130">After installation, close the PowerShell command window.</span></span>
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="d825e-131">2 단계: Microsoft 365 구독에 연결</span><span class="sxs-lookup"><span data-stu-id="d825e-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="d825e-132">Windows PowerShell 용 Windows Azure Active Directory 모듈에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="d825e-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="d825e-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="d825e-134">Windows PowerShell 자격 증명 요청 대화 상자에서 Microsoft 365 전역 관리자 계정의 사용자 이름 및 암호를 입력 한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>
    
3. <span data-ttu-id="d825e-135">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-135">Run the following command.</span></span>
    
    <span data-ttu-id="d825e-136">Connect-msolservice-자격 증명 $UserCredential</span><span class="sxs-lookup"><span data-stu-id="d825e-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="d825e-137">3 단계: PowerShell 스크립트를 실행할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="d825e-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="d825e-138">PowerShell 스크립트를 실행 하도록 이미 설정 되어 있는 경우에는이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="d825e-139">Get-MsolUserDeviceComplianceStatus.ps1 스크립트를 실행 하려면 PowerShell 스크립트를 실행 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="d825e-140">Windows 바탕 화면에서 **시작**을 선택 하 고 windows PowerShell을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="d825e-141">Windows PowerShell을 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="d825e-142">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-142">Run the following command.</span></span>
    
    <span data-ttu-id="d825e-143">ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="d825e-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="d825e-144">메시지가 표시 되 면 Y를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-144">When prompted, type Y and then press Enter.</span></span>
    
<span data-ttu-id="d825e-145">**MsolDevice cmdlet을 실행 하 여 조직의 모든 장치에 대 한 세부 정보를 표시 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d825e-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="d825e-146">Windows PowerShell용 Microsoft Azure Active Directory 모듈을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="d825e-147">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-147">Run the following command.</span></span>
    
    <span data-ttu-id="d825e-148">MsolDevice-All-ReturnRegisteredOwners | 여기에서-개체 {$ _. RegisteredOwners-gt 0}</span><span class="sxs-lookup"><span data-stu-id="d825e-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="d825e-149">자세한 예는  [MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d825e-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="d825e-150">스크립트를 실행 하 여 장치 세부 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="d825e-150">Run a script to get device details</span></span>

<span data-ttu-id="d825e-151">먼저, 스크립트를 컴퓨터에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="d825e-152">다음 텍스트를 복사 하 여 메모장에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="d825e-153">a</span><span class="sxs-lookup"><span data-stu-id="d825e-153">param (</span></span>
    

3.  <span data-ttu-id="d825e-154">[PSObject []] $users = @ (),</span><span class="sxs-lookup"><span data-stu-id="d825e-154">[PSObject[]]$users = @(),</span></span>
    

4.  <span data-ttu-id="d825e-155">[스위치] $export</span><span class="sxs-lookup"><span data-stu-id="d825e-155">[Switch]$export,</span></span>
    

5.  <span data-ttu-id="d825e-156">[String] $exportFileName = "UserDeviceComplianceStatus_" + (Get-Date-Format "yyMMdd_HHMMss") + ".csv",</span><span class="sxs-lookup"><span data-stu-id="d825e-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>
    

6.  <span data-ttu-id="d825e-157">[String] $exportPath = [Environment]:: GetFolderPath ("Desktop")</span><span class="sxs-lookup"><span data-stu-id="d825e-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>
    

7.  <span data-ttu-id="d825e-158">)</span><span class="sxs-lookup"><span data-stu-id="d825e-158">)</span></span>
    

9.  <span data-ttu-id="d825e-159">[System.object] $script: schema = @ {</span><span class="sxs-lookup"><span data-stu-id="d825e-159">[System.Collections.IDictionary]$script:schema = @{</span></span>
    

11.  <span data-ttu-id="d825e-160">DeviceId = ' '</span><span class="sxs-lookup"><span data-stu-id="d825e-160">DeviceId = ''</span></span>
    

12.  <span data-ttu-id="d825e-161">DeviceOSType = ' '</span><span class="sxs-lookup"><span data-stu-id="d825e-161">DeviceOSType = ''</span></span>
    

13.  <span data-ttu-id="d825e-162">DeviceOSVersion = ' '</span><span class="sxs-lookup"><span data-stu-id="d825e-162">DeviceOSVersion = ''</span></span>
    

14.  <span data-ttu-id="d825e-163">DeviceTrustLevel = ' '</span><span class="sxs-lookup"><span data-stu-id="d825e-163">DeviceTrustLevel = ''</span></span>
    

15.  <span data-ttu-id="d825e-164">DisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="d825e-164">DisplayName = ''</span></span>
    

16.  <span data-ttu-id="d825e-165">IsCompliant = ' '</span><span class="sxs-lookup"><span data-stu-id="d825e-165">IsCompliant = ''</span></span>
    

17.  <span data-ttu-id="d825e-166">IsManaged = ' '</span><span class="sxs-lookup"><span data-stu-id="d825e-166">IsManaged = ''</span></span>
    

18.  <span data-ttu-id="d825e-167">ApproximateLastLogonTimestamp = ' '</span><span class="sxs-lookup"><span data-stu-id="d825e-167">ApproximateLastLogonTimestamp = ''</span></span>
    

19.  <span data-ttu-id="d825e-168">DeviceObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="d825e-168">DeviceObjectId = ''</span></span>
    

20.  <span data-ttu-id="d825e-169">RegisteredOwnerUpn = ' '</span><span class="sxs-lookup"><span data-stu-id="d825e-169">RegisteredOwnerUpn = ''</span></span>
    

21.  <span data-ttu-id="d825e-170">RegisteredOwnerObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="d825e-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="d825e-171">RegisteredOwnerDisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="d825e-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="d825e-172">}</span><span class="sxs-lookup"><span data-stu-id="d825e-172">}</span></span>
    

25.  <span data-ttu-id="d825e-173">함수 createResultObject</span><span class="sxs-lookup"><span data-stu-id="d825e-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="d825e-174">{</span><span class="sxs-lookup"><span data-stu-id="d825e-174">{</span></span>
    

28.  <span data-ttu-id="d825e-175">[PSObject] $resultObject = 새 개체-TypeName PSObject-속성 $script: schema</span><span class="sxs-lookup"><span data-stu-id="d825e-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="d825e-176">반환 $resultObject</span><span class="sxs-lookup"><span data-stu-id="d825e-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="d825e-177">}</span><span class="sxs-lookup"><span data-stu-id="d825e-177">}</span></span>
    

33.  <span data-ttu-id="d825e-178">If ($users Count-eq 0)</span><span class="sxs-lookup"><span data-stu-id="d825e-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="d825e-179">{</span><span class="sxs-lookup"><span data-stu-id="d825e-179">{</span></span>
    

35.  <span data-ttu-id="d825e-180">$users = Get-msoluser</span><span class="sxs-lookup"><span data-stu-id="d825e-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="d825e-181">}</span><span class="sxs-lookup"><span data-stu-id="d825e-181">}</span></span>
    

38.  <span data-ttu-id="d825e-182">[PSObject []] $result = foreach ($users의 $u)</span><span class="sxs-lookup"><span data-stu-id="d825e-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="d825e-183">{</span><span class="sxs-lookup"><span data-stu-id="d825e-183">{</span></span>
    

41.  <span data-ttu-id="d825e-184">[PSObject] $devices = msoldevice-RegisteredOwnerUpn $u. UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="d825e-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="d825e-185">foreach ($devices의 $d)</span><span class="sxs-lookup"><span data-stu-id="d825e-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="d825e-186">{</span><span class="sxs-lookup"><span data-stu-id="d825e-186">{</span></span>
    

44.  <span data-ttu-id="d825e-187">[PSObject] $deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="d825e-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="d825e-188">$deviceResult. DeviceId = $d. DeviceId</span><span class="sxs-lookup"><span data-stu-id="d825e-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="d825e-189">$deviceResult DeviceOSType = $d DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="d825e-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="d825e-190">$deviceResult DeviceOSVersion = $d DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="d825e-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="d825e-191">$deviceResult DeviceTrustLevel = $d DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="d825e-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="d825e-192">$deviceResult DisplayName = $d. DisplayName</span><span class="sxs-lookup"><span data-stu-id="d825e-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="d825e-193">$deviceResult. IsCompliant = $d GraphDeviceObject. IsCompliant</span><span class="sxs-lookup"><span data-stu-id="d825e-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="d825e-194">$deviceResult IsManaged = $d. GraphDeviceObject</span><span class="sxs-lookup"><span data-stu-id="d825e-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="d825e-195">$deviceResult DeviceObjectId = $d. ObjectId</span><span class="sxs-lookup"><span data-stu-id="d825e-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="d825e-196">$deviceResult RegisteredOwnerUpn = $u UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="d825e-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="d825e-197">$deviceResult RegisteredOwnerObjectId = $u. ObjectId</span><span class="sxs-lookup"><span data-stu-id="d825e-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="d825e-198">$deviceResult RegisteredOwnerDisplayName = $u. DisplayName</span><span class="sxs-lookup"><span data-stu-id="d825e-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="d825e-199">$deviceResult ApproximateLastLogonTimestamp = $d ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="d825e-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="d825e-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="d825e-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="d825e-201">}</span><span class="sxs-lookup"><span data-stu-id="d825e-201">}</span></span>
    

61.  <span data-ttu-id="d825e-202">}</span><span class="sxs-lookup"><span data-stu-id="d825e-202">}</span></span>
    

63.  <span data-ttu-id="d825e-203">If ($export)</span><span class="sxs-lookup"><span data-stu-id="d825e-203">If ($export)</span></span>
    

64.  <span data-ttu-id="d825e-204">{</span><span class="sxs-lookup"><span data-stu-id="d825e-204">{</span></span>
    

65.  <span data-ttu-id="d825e-205">$result | Export-.Csv 경로 ($exportPath + " \" + $exportFileName)-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="d825e-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="d825e-206">}</span><span class="sxs-lookup"><span data-stu-id="d825e-206">}</span></span>
    

67.  <span data-ttu-id="d825e-207">알리게</span><span class="sxs-lookup"><span data-stu-id="d825e-207">Else</span></span>
    

68.  <span data-ttu-id="d825e-208">{</span><span class="sxs-lookup"><span data-stu-id="d825e-208">{</span></span>
    

69.  <span data-ttu-id="d825e-209">$result</span><span class="sxs-lookup"><span data-stu-id="d825e-209">$result</span></span>
    

70.  <span data-ttu-id="d825e-210">}</span><span class="sxs-lookup"><span data-stu-id="d825e-210">}</span></span>
    

71.  <span data-ttu-id="d825e-211">파일 확장명. ps1;을 사용 하 여 Windows PowerShell 스크립트 파일로 저장 합니다. 예를 Get-MsolUserDeviceComplianceStatus.ps1 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="d825e-212">스크립트를 실행 하 여 단일 사용자 계정에 대 한 장치 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="d825e-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="d825e-213">Windows PowerShell용 Microsoft Azure Active Directory 모듈을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="d825e-214">스크립트를 저장 한 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="d825e-215">예를 들어 C:\PS-Scripts에 저장 한 경우 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="d825e-216">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="d825e-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="d825e-217">다음 명령을 실행 하 여 장치 세부 정보를 가져올 사용자를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="d825e-218">이 예에서는 bar@example.com에 대 한 세부 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="d825e-219">$u = Get-msoluser-UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="d825e-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="d825e-220">다음 명령을 실행 하 여 스크립트를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="d825e-221">.\Get-MsolUserDeviceComplianceStatus.ps1-사용자 $u-내보내기</span><span class="sxs-lookup"><span data-stu-id="d825e-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="d825e-222">정보는 Windows 데스크톱에 CSV 파일로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="d825e-223">추가 매개 변수를 사용 하 여 CSV의 파일 이름과 경로를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="d825e-224">스크립트를 실행 하 여 사용자 그룹에 대 한 장치 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="d825e-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="d825e-225">Windows PowerShell용 Microsoft Azure Active Directory 모듈을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="d825e-226">스크립트를 저장 한 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="d825e-227">예를 들어 C:\PS-Scripts에 저장 한 경우 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="d825e-228">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="d825e-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="d825e-229">다음 명령을 실행 하 여 장치 세부 정보를 가져올 그룹을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="d825e-230">이 예에서는 FinanceStaff 그룹의 사용자에 대 한 세부 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="d825e-231">$u = MsolGroupMember-SearchString "FinanceStaff" | % {Get-Get-msoluser-ObjectId $ _를 사용 합니다. Id</span><span class="sxs-lookup"><span data-stu-id="d825e-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="d825e-232">다음 명령을 실행 하 여 스크립트를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-232">Run the following command to initiate the script.</span></span>   

    <span data-ttu-id="d825e-233">.\Get-MsolUserDeviceComplianceStatus.ps1-사용자 $u-내보내기</span><span class="sxs-lookup"><span data-stu-id="d825e-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="d825e-234">정보는 Windows 데스크톱에 CSV 파일로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="d825e-235">추가 매개 변수를 사용 하 여 CSV의 파일 이름과 경로를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d825e-236">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d825e-236">Related topics</span></span>

[<span data-ttu-id="d825e-237">Microsoft Connect가 만료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d825e-237">Microsoft Connect Has Been Retired</span></span>](https://docs.microsoft.com/collaborate/connect-redirect)

[<span data-ttu-id="d825e-238">기본 이동성 및 보안 개요</span><span class="sxs-lookup"><span data-stu-id="d825e-238">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="d825e-239">MsolDevice</span><span class="sxs-lookup"><span data-stu-id="d825e-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=841721)