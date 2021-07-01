---
title: 기본 모바일 및 보안 관리 장치에 대한 세부 정보 확인
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
description: 조직의 Windows PowerShell 모바일 및 보안 장치에 대한 세부 정보를 얻습니다.
ms.openlocfilehash: 2edee1b08f137d3e4f977b4d6800c1b0fc0e0473
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228174"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="4edb2-103">기본 모바일 및 보안 관리 장치에 대한 세부 정보 확인</span><span class="sxs-lookup"><span data-stu-id="4edb2-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="4edb2-104">이 문서에서는 기본 이동성 및 Windows PowerShell 설정한 조직의 장치에 대한 세부 정보를 얻을 수 있는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="4edb2-105">다음은 사용할 수 있는 장치 세부 정보의 분석입니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="4edb2-106">**자세한 정보**</span><span class="sxs-lookup"><span data-stu-id="4edb2-106">**Detail**</span></span>|<span data-ttu-id="4edb2-107">**PowerShell에서 찾아야 할 것**</span><span class="sxs-lookup"><span data-stu-id="4edb2-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="4edb2-108">장치가 기본 모바일 및 보안에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="4edb2-109">자세한 내용은 기본 모바일 및 보안을 사용하여 모바일 장치 [등록을 참조하세요.](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="4edb2-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="4edb2-110"> \*isManaged* 매개   변수의 값은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="4edb2-111">**True**= 장치가 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="4edb2-112">**False**= 장치가 등록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="4edb2-113">장치가 장치 보안 정책을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="4edb2-114">자세한 내용은 장치 보안 [정책 만들기를 참조하세요.](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4edb2-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="4edb2-115"> \*isCompliant* 매개 변수의   값은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="4edb2-116">**True**   = 장치가 정책을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="4edb2-117">**False**   = 장치가 정책을 준수하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="기본 Mobility and Security PowerShell 매개 변수":::

> [!NOTE]
> <span data-ttu-id="4edb2-119">이 문서의 명령 및 스크립트는 또한 에서 관리하는 모든 장치에 대한 세부 [Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="4edb2-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4edb2-120">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="4edb2-120">Before you begin</span></span>

<span data-ttu-id="4edb2-121">이 문서에 설명된 명령 및 스크립트를 실행하려면 몇 가지를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="4edb2-122">1단계: Azure Active Directory 모듈 다운로드 및 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4edb2-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="4edb2-123">이러한 단계에 대한 자세한 내용은 [PowerShell을 사용하여 커넥트 Microsoft 365 참조하세요.](/office365/enterprise/powershell/connect-to-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="4edb2-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="4edb2-124">IT 전문가용 Microsoft Online Services Sign-In 도우미 [RTWl로](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)이동하고 로그인 도우미에 Microsoft Online Services    **다운로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4edb2-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="4edb2-125">다음 단계에 따라 Windows PowerShell용 Microsoft Azure Active Directory 모듈을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="4edb2-126">관리자 수준 PowerShell 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-126">Open an administrator-level PowerShell command prompt.</span></span>

    2. <span data-ttu-id="4edb2-127">`Install-Module MSOnline` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-127">Run the `Install-Module MSOnline` command.</span></span>

    3. <span data-ttu-id="4edb2-128">NuGet 공급자를 설치할지 묻는 메시지가 표시되면 Y를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="4edb2-129">PSGallery에서 모듈을 설치할지 묻는 메시지가 표시되면 Y를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="4edb2-130">설치 후 PowerShell 명령 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="4edb2-131">2단계: 커넥트 구독에 Microsoft 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="4edb2-132">다음 Windows Azure Active Directory 모듈에서 Windows PowerShell 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="4edb2-133">자격 증명 Windows PowerShell 대화 상자에 전역 관리자 계정의 사용자 이름과 암호를 Microsoft 365 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4edb2-133">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="4edb2-134">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-134">Run the following command.</span></span>

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="4edb2-135">3단계: PowerShell 스크립트를 실행할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="4edb2-135">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

> [!NOTE]
> <span data-ttu-id="4edb2-136">PowerShell 스크립트를 실행하기로 이미 설정한 경우 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-136">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="4edb2-137">Get-MsolUserDeviceComplianceStatus.ps1 실행하려면 PowerShell 스크립트 실행을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-137">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="4edb2-138">데스크톱에서 Windows **를** 선택하고 시작을 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4edb2-138">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="4edb2-139">사용자 Windows PowerShell 마우스 오른쪽 단추로 클릭한 다음 관리자 권한으로 실행 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4edb2-139">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="4edb2-140">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-140">Run the following command.</span></span>

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. <span data-ttu-id="4edb2-141">메시지가 표시될 때 Y를 입력한 다음 Enter를 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-141">When prompted, type Y and then press Enter.</span></span>

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a><span data-ttu-id="4edb2-142">Get-MsolDevice cmdlet을 실행하여 조직의 모든 장치에 대한 세부 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-142">Run the Get-MsolDevice cmdlet to display details for all devices in your organization</span></span>

1. <span data-ttu-id="4edb2-143">Windows PowerShell용 Microsoft Azure Active Directory 모듈을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-143">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="4edb2-144">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-144">Run the following command.</span></span>

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

<span data-ttu-id="4edb2-145">자세한 예제는  [Get-MsolDevice 를 참조합니다.](https://go.microsoft.com/fwlink/?linkid=2157939)</span><span class="sxs-lookup"><span data-stu-id="4edb2-145">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="4edb2-146">스크립트를 실행하여 장치 세부 정보 확인</span><span class="sxs-lookup"><span data-stu-id="4edb2-146">Run a script to get device details</span></span>

<span data-ttu-id="4edb2-147">먼저 스크립트를 컴퓨터에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-147">First, save the script to your computer.</span></span>

1. <span data-ttu-id="4edb2-148">다음 텍스트를 복사하여 텍스트에 메모장.</span><span class="sxs-lookup"><span data-stu-id="4edb2-148">Copy and paste the following text into Notepad.</span></span>

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. <span data-ttu-id="4edb2-149">파일 확장명 Windows PowerShell 사용하여 스크립트 파일로 .ps1. 예를 들어 Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="4edb2-149">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="4edb2-150">스크립트를 실행하여 단일 사용자 계정에 대한 장치 정보 얻기</span><span class="sxs-lookup"><span data-stu-id="4edb2-150">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="4edb2-151">Windows PowerShell용 Microsoft Azure Active Directory 모듈을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-151">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="4edb2-152">스크립트를 저장한 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-152">Go to the folder where you saved the script.</span></span> <span data-ttu-id="4edb2-153">예를 들어 C:\PS-Scripts에 저장한 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-153">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="4edb2-154">다음 명령을 실행하여 장치 세부 정보를 확인할 사용자를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-154">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="4edb2-155">이 예제에서는 자세한 정보를 bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="4edb2-155">This example gets details for bar@example.com.</span></span>

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. <span data-ttu-id="4edb2-156">다음 명령을 실행하여 스크립트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-156">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="4edb2-157">정보는 사용자 데스크톱으로 Windows CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-157">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="4edb2-158">추가 매개 변수를 사용하여 CSV의 파일 이름과 경로를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-158">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="4edb2-159">스크립트를 실행하여 사용자 그룹에 대한 장치 정보 얻기</span><span class="sxs-lookup"><span data-stu-id="4edb2-159">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="4edb2-160">Windows PowerShell용 Microsoft Azure Active Directory 모듈을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-160">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="4edb2-161">스크립트를 저장한 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-161">Go to the folder where you saved the script.</span></span> <span data-ttu-id="4edb2-162">예를 들어 C:\PS-Scripts에 저장한 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-162">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="4edb2-163">다음 명령을 실행하여 장치 세부 정보를 확인할 그룹을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-163">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="4edb2-164">이 예에서는 FinanceStaff 그룹의 사용자에 대한 세부 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-164">This example gets details for users in the FinanceStaff group.</span></span>

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. <span data-ttu-id="4edb2-165">다음 명령을 실행하여 스크립트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-165">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="4edb2-166">정보는 사용자 데스크톱으로 Windows CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-166">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="4edb2-167">추가 매개 변수를 사용하여 CSV의 파일 이름과 경로를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edb2-167">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4edb2-168">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4edb2-168">Related topics</span></span>

[<span data-ttu-id="4edb2-169">Microsoft 커넥트 사용 중지</span><span class="sxs-lookup"><span data-stu-id="4edb2-169">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="4edb2-170">기본 모바일 및 보안 개요</span><span class="sxs-lookup"><span data-stu-id="4edb2-170">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="4edb2-171">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="4edb2-171">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)
