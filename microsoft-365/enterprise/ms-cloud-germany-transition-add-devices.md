---
title: 도이클란드 Microsoft 클라우드에서 마이그레이션하기 위한 추가 장치 정보
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '요약: 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스에 대한 추가 장치 정보입니다.'
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861309"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="1301a-103">도이클란드 Microsoft 클라우드에서 마이그레이션하기 위한 추가 장치 정보</span><span class="sxs-lookup"><span data-stu-id="1301a-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="1301a-104">도이치클랜드 Microsoft 클라우드에 연결된 Azure AD 가입 및 등록된 장치는 9단계 및 10단계 이전으로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="1301a-105">장치 마이그레이션은 장치 유형, 운영 체제 및 AAD 관계에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-105">The migration of a device depends on the devices type, operating system and AAD relation.</span></span> 

## <a name="frequently-asked-questions"></a><span data-ttu-id="1301a-106">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="1301a-106">Frequently asked questions</span></span>

<span data-ttu-id="1301a-107">**조직이 영향을 받는지 어떻게 알 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="1301a-107">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="1301a-108">관리자는 등록된 장치 또는 Azure AD에 가입된 장치가 있는지 `https://portal.microsoftazure.de` 여부를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-108">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered or Azure AD joined devices.</span></span> <span data-ttu-id="1301a-109">조직에서 장치를 등록한 경우 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-109">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="1301a-110">**사용자에게 어떤 영향이 있나요?**</span><span class="sxs-lookup"><span data-stu-id="1301a-110">**What is the impact on my users?**</span></span>

<span data-ttu-id="1301a-111">등록된 장치의 사용자는 마이그레이션 [10단계가](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) 완료되고 도이치란드 Microsoft 클라우드의 끝점을 사용하지 않도록 설정한 후에 더 이상 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-111">Users from a registered device will no longer be able to sign in after [migration phase 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed and the endpoints for Microsoft Cloud Deutschland have been disabled.</span></span>  

<span data-ttu-id="1301a-112">조직이 도이치란드 Microsoft 클라우드에서 연결이 끊어지기 전에 모든 장치가 전 세계 끝점에 등록되어 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-112">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="1301a-113">**사용자가 언제 장치를 다시 등록하나요?**</span><span class="sxs-lookup"><span data-stu-id="1301a-113">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="1301a-114">[9단계가](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) 완료된 후에만 장치를 등록을 등록을 해지하고 다시 등록하는 것은 성공에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-114">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="1301a-115">10단계가 시작되기 전에 다시 등록을 완료해야 합니다. 그렇지 않으면 장치에 대한 액세스 권한이 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-115">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="1301a-116">**마이그레이션 후 장치 상태를 복원하려면 어떻게 해야 합니까?**</span><span class="sxs-lookup"><span data-stu-id="1301a-116">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="1301a-117">Azure AD에 등록된 회사 소유의 Windows 디바이스의 경우 관리자는 원격으로 트리거된 워크플로를 통해 이전 장치 상태의 등록을 등록하지 않는 워크플로를 통해 이러한 디바이스의 마이그레이션을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-117">For company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="1301a-118">Azure AD에 등록된 개인 Windows 장치를 비롯한 다른 모든 장치의 경우 최종 사용자는 이러한 단계를 수동으로 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-118">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="1301a-119">Azure AD에 가입된 장치의 경우 사용자는 등록을 하지 않은 후 장치를 다시 등록하려면 로컬 관리자 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-119">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="1301a-120">아래에서 장치 상태로 복원하는 방법에 대한 자세한 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1301a-120">Please refer to detailed instructions for how to successfully restore device states below.</span></span> 
 
<span data-ttu-id="1301a-121">**모든 장치가 공용 클라우드에 등록되어 있는 것을 어떻게 알 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="1301a-121">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="1301a-122">장치가 공용 클라우드에 등록되어 있는지 확인하려면 Azure AD 포털에서 장치 목록을 내보내고 앱 스프레드시트로 Excel 합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-122">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="1301a-123">그런 다음 도이치랜드 [Microsoft](ms-cloud-germany-transition.md#how-is-the-migration-organized) 클라우드와 별개의 마이그레이션 단계 후 _registeredTime_ 열을 사용하여 등록된 장치를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-123">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="1301a-124">추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="1301a-124">Additional considerations</span></span>
<span data-ttu-id="1301a-125">장치 등록은 테넌트 마이그레이션 후 비활성화되어 활성화하거나 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-125">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> 

<span data-ttu-id="1301a-126">Intune이 사용되지 않는 경우 구독에 로그인하고 다음 명령을 실행하여 옵션을 다시 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-126">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
<span data-ttu-id="1301a-127">**중요:** Intune 서비스 보안 주체는 상거래 마이그레이션 후 활성화됩니다. 이는 Azure AD 장치 등록의 활성화를 암시합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-127">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="1301a-128">마이그레이션 전에 Azure AD 장치 등록을 차단한 경우 Azure AD 포털에서 Azure AD 장치 등록을 다시 사용하지 않도록 설정하려면 PowerShell을 사용하여 Intune 서비스 계정을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-128">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="1301a-129">이 명령을 사용하여 Intune 서비스 주체는 Azure Active Directory PowerShell for Graph 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-129">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a><span data-ttu-id="1301a-130">Azure AD 가입</span><span class="sxs-lookup"><span data-stu-id="1301a-130">Azure AD Join</span></span>
<span data-ttu-id="1301a-131">이는 디바이스에 Windows 10 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-131">This applies to Windows 10 devices.</span></span> 

<span data-ttu-id="1301a-132">디바이스가 Azure AD에 가입된 경우 Azure AD에서 연결을 끊고 다시 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-132">If a device is Azure AD joined, it must be disconnected from Azure AD and be connected again.</span></span> 

<span data-ttu-id="1301a-133">[![Azure AD 장치 Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1301a-133">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="1301a-134">사용자가 디바이스의 관리자인 Windows 10 Azure AD에서 디바이스 등록을 등록을 해지하고 다시 가입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-134">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again.</span></span> <span data-ttu-id="1301a-135">관리자 권한이 없는 사용자는 이 컴퓨터의 로컬 관리자 계정 자격 증명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-135">If he has no administrator privileges, the user needs credentials of a local administrator account on this machine.</span></span> 


<span data-ttu-id="1301a-136">관리자는 다음 구성 경로에 따라 디바이스에서 로컬 관리자 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-136">An Administrator can create an local administrator account on the device following this configuration path:</span></span>

<span data-ttu-id="1301a-137">*설정 > 계정 > Microsoft > 없는 사용자 > > 자격 증명을 사용할 수 없음*</span><span class="sxs-lookup"><span data-stu-id="1301a-137">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="1301a-138">1단계: 디바이스가 Azure ID에 가입된지 확인</span><span class="sxs-lookup"><span data-stu-id="1301a-138">Step 1: Determine if the device is Azure ID joined</span></span>
1.  <span data-ttu-id="1301a-139">사용자 전자 메일 및 암호로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-139">Sign In with users E-mail and password.</span></span>
2.  <span data-ttu-id="1301a-140">Go to 설정 > Accounts > Access Work or School.</span><span class="sxs-lookup"><span data-stu-id="1301a-140">Go to Settings > Accounts > Access Work Or School.</span></span> 
3.  <span data-ttu-id="1301a-141">에 연결된 사용자 **목록에서 사용자를 찾아야 합니다. 의 Azure AD.**</span><span class="sxs-lookup"><span data-stu-id="1301a-141">Look for a user in the list with **connected to … ‘s Azure AD**.</span></span> 
4.  <span data-ttu-id="1301a-142">연결된 사용자가 있는 경우 2단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-142">If a connected user exists, proceed with Step 2.</span></span> <span data-ttu-id="1301a-143">그렇지 않은 경우 추가 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-143">If not, no further action is required.</span></span>
### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="1301a-144">2단계: Azure AD에서 장치 연결 끊기</span><span class="sxs-lookup"><span data-stu-id="1301a-144">Step 2: Disconnect the device from Azure AD</span></span>
1.  <span data-ttu-id="1301a-145">연결된 **직장** 또는 학교 계정에서 연결 끊기를 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-145">Tap **Disconnect** on the connected work or School Account.</span></span> 
2.  <span data-ttu-id="1301a-146">연결이 끊어진 것을 두 번 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-146">Confirm the disconnect twice.</span></span> 
3.  <span data-ttu-id="1301a-147">로컬 관리자 사용자 이름과 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-147">Enter the local administrator username and password.</span></span> <span data-ttu-id="1301a-148">디바이스의 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-148">The device is disconnected.</span></span>
4.  <span data-ttu-id="1301a-149">장치를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-149">Restart the device.</span></span>
### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="1301a-150">3단계: 디바이스를 Azure AD에 연결</span><span class="sxs-lookup"><span data-stu-id="1301a-150">Step 3: Join the device to Azure AD</span></span>
1.  <span data-ttu-id="1301a-151">사용자가 로컬 관리자의 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-151">the user signs in with the credentials of the local administrator</span></span>
2.  <span data-ttu-id="1301a-152">다음으로 **설정** **계정으로** 이동한 다음 직장 **또는 학교에 액세스**</span><span class="sxs-lookup"><span data-stu-id="1301a-152">Go to **Settings** then **Accounts** then **Access Work Or School**</span></span>
3.  <span data-ttu-id="1301a-153">탭 **커넥트**</span><span class="sxs-lookup"><span data-stu-id="1301a-153">Tap **Connect**</span></span>
4.  <span data-ttu-id="1301a-154">**중요:** **Azure AD에 가입을 탭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1301a-154">**IMPORTANT**: Tap **Join to Azure AD**</span></span>
5.  <span data-ttu-id="1301a-155">사용자의 전자 메일 주소와 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-155">Enter the e-mail address and password of the user.</span></span> <span data-ttu-id="1301a-156">디바이스가 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-156">The device is connected</span></span>
6.  <span data-ttu-id="1301a-157">장치 다시 시작</span><span class="sxs-lookup"><span data-stu-id="1301a-157">Restart the device</span></span> 
7.  <span data-ttu-id="1301a-158">전자 메일 주소 및 암호로 서명</span><span class="sxs-lookup"><span data-stu-id="1301a-158">sign with your e-mail address and password</span></span>

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="1301a-159">Azure AD 등록(회사 소유)</span><span class="sxs-lookup"><span data-stu-id="1301a-159">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="1301a-160">장치 Windows 10 Azure AD가 등록되어 있는지 확인하려면 장치에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-160">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="1301a-161">디바이스가 Azure AD 등록된 경우 다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-161">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="1301a-162">장치에서 기존 Azure AD 등록 계정을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="1301a-162">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="1301a-163">장치에서 Azure AD 등록 계정을 제거하려면 여기에서 다운로드할 수 있는 도구인 CleanupWPJ를 [CleanupWPJ.zip. ](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)</span><span class="sxs-lookup"><span data-stu-id="1301a-163">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="1301a-164">ZIP 파일을 추출하고 **WPJCleanup.cmd를 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="1301a-164">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="1301a-165">이 도구는 디바이스의 버전에 따라 올바른 실행 Windows 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-165">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="1301a-166">관리자는 그룹 정책과 같은 메커니즘을 사용하여 디바이스에 로그인한 사용자의 컨텍스트에서 디바이스에서 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-166">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="1301a-167">Azure AD에서 디바이스를 등록하라는 웹 계정 관리자 프롬프트를 사용하지 않도록 설정하려면 다음 레지스트리 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-167">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="1301a-168">위치: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="1301a-168">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="1301a-169">형식: DWORD(32비트)</span><span class="sxs-lookup"><span data-stu-id="1301a-169">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="1301a-170">이름: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="1301a-170">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="1301a-171">값 데이터: 1</span><span class="sxs-lookup"><span data-stu-id="1301a-171">Value data: 1</span></span>

<span data-ttu-id="1301a-172">이 레지스트리 값이 있는 경우 작업 공간 조인을 차단하고 사용자에게 디바이스에 가입하라는 메시지가 표시되지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-172">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="1301a-173">Android</span><span class="sxs-lookup"><span data-stu-id="1301a-173">Android</span></span>

<span data-ttu-id="1301a-174">Android의 경우 사용자는 장치를 등록을 하지 않은 후 다시 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-174">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="1301a-175">이 완료는 앱 앱 또는 Microsoft Authenticator 앱을 통해 회사 포털 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-175">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="1301a-176">Microsoft Authenticator 앱에서 사용자는 장치 **등록으로 설정 > 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="1301a-176">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="1301a-177">이 경우 사용자는 디바이스 등록을 등록을 다시 등록하고 다시 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-177">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="1301a-178">사용자가 회사 포털 탭으로 **이동하여** 디바이스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-178">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="1301a-179">그런 다음 디바이스를 사용하여 장치를 다시 회사 포털.</span><span class="sxs-lookup"><span data-stu-id="1301a-179">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="1301a-180">또한 사용자는 계정 설정 페이지에서 계정을 제거한 다음 직장 계정을 다시 추가하여 등록을 다시 등록 및 다시 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-180">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="1301a-181">앱 앱을 사용하여 Android에서 디바이스 등록을 등록을 Microsoft Authenticator:</span><span class="sxs-lookup"><span data-stu-id="1301a-181">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="1301a-182">앱 Microsoft Authenticator 열고 으로 **설정.**</span><span class="sxs-lookup"><span data-stu-id="1301a-182">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="1301a-183">장치 **등록 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1301a-183">Select **Device registration**.</span></span>
3.  <span data-ttu-id="1301a-184">등록을 다시 등록하지 않습니다.를 선택하여 디바이스 **등록을 등록을 하세요.**</span><span class="sxs-lookup"><span data-stu-id="1301a-184">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="1301a-185">장치 **등록의** 경우 전자 메일 주소를 입력하여 장치를 다시 등록한 다음 등록을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1301a-185">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="1301a-186">Android 장치 등록을 등록을 해지하고 Android 디바이스를 다시 등록하려면 설정:</span><span class="sxs-lookup"><span data-stu-id="1301a-186">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="1301a-187">장치 **설정** 열고 계정으로 **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="1301a-187">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="1301a-188">다시 등록할 직장 계정을 선택하고 계정 제거 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1301a-188">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="1301a-189">계정이 제거된 후  계정 페이지에서 계정 추가 계정 > **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1301a-189">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="1301a-190">Workplace **Join의** 경우 전자 메일 주소를 입력하고 **가입을** 선택하여 장치 등록을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-190">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="1301a-191">Android에서 디바이스 등록을 해지하고 디바이스를 다시 등록하려면 다음을 회사 포털.</span><span class="sxs-lookup"><span data-stu-id="1301a-191">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="1301a-192">시작 회사 포털 및 장치 **탭으로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-192">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="1301a-193">장치를 선택하여 장치 세부 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-193">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="1301a-194">타원(세 점) 메뉴에서 장치 제거를 선택하고 대화 상자에서 확인하여 제거를 완료합니다. </span><span class="sxs-lookup"><span data-stu-id="1301a-194">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="1301a-195">이제 앱에 로그아웃해야 회사 포털 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-195">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="1301a-196">로그인을 **선택하여** 장치를 다시 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-196">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="1301a-197">이 작업의 마이그레이션 단계 중에 필요한 작업 또는 관리 또는 사용에 미치는 영향에 대한 자세한 내용은 도이치랜드에서 마이그레이션을 위한 추가 Azure AD 정보의 Azure Active Directory(Azure AD)에 대한 정보를 [검토하세요.](ms-cloud-germany-transition-azure-ad.md)</span><span class="sxs-lookup"><span data-stu-id="1301a-197">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="1301a-198">iOS</span><span class="sxs-lookup"><span data-stu-id="1301a-198">iOS</span></span>

<span data-ttu-id="1301a-199">iOS 장치에서는 캐시된 계정을 장치에서 수동으로 제거하고, Microsoft Authenticator 등록을 해지하고, 장치의 모든 네이티브 앱에서 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-199">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="1301a-200">1단계: 있는 경우 앱의 Microsoft Authenticator 제거</span><span class="sxs-lookup"><span data-stu-id="1301a-200">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="1301a-201">앱 앱의 계정을 Microsoft Authenticator 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-201">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="1301a-202">오른쪽 **설정** 아이콘을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-202">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="1301a-203">if you don't see the **설정,** you might not using the latest version of Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="1301a-203">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="1301a-204">계정 **제거 단추를** 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-204">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="1301a-205">이 **디바이스의 모든 앱을 탭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1301a-205">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="1301a-206">2단계: Microsoft Authenticator 앱에서 디바이스 등록을 Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="1301a-206">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="1301a-207">오른쪽 위 모서리에서 메뉴 아이콘을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-207">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="1301a-208">를 **설정** 다음 **장치 등록 을 탭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1301a-208">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="1301a-209">계정이 표시될 경우 **등록을** 하지 않은 장치 및 대화 상자에서 **계속을** 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-209">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="1301a-210">그 이후에는 계정이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-210">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="1301a-211">3단계: 필요한 경우 개별 앱에서 서명</span><span class="sxs-lookup"><span data-stu-id="1301a-211">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="1301a-212">사용자는 앱, 앱 Outlook, Teams 및 OneDrive 앱으로 이동하고 해당 앱에서 계정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1301a-212">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="1301a-213">추가 정보</span><span class="sxs-lookup"><span data-stu-id="1301a-213">More information</span></span>

<span data-ttu-id="1301a-214">시작:</span><span class="sxs-lookup"><span data-stu-id="1301a-214">Getting started:</span></span>

- [<span data-ttu-id="1301a-215">독일 Microsoft 클라우드에서 새 독일 Office 365 서비스로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="1301a-215">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="1301a-216">Microsoft Cloud Deutschland 마이그레이션 지원</span><span class="sxs-lookup"><span data-stu-id="1301a-216">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="1301a-217">마이그레이션에 대해 옵트인하는 방법</span><span class="sxs-lookup"><span data-stu-id="1301a-217">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="1301a-218">마이그레이션 중의 고객 환경</span><span class="sxs-lookup"><span data-stu-id="1301a-218">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="1301a-219">전환을 통해 이동:</span><span class="sxs-lookup"><span data-stu-id="1301a-219">Moving through the transition:</span></span>

- [<span data-ttu-id="1301a-220">문장 작업 및 영향 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="1301a-220">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="1301a-221">추가 사전 작업</span><span class="sxs-lookup"><span data-stu-id="1301a-221">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="1301a-222">[Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.</span><span class="sxs-lookup"><span data-stu-id="1301a-222">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="1301a-223">클라우드 앱:</span><span class="sxs-lookup"><span data-stu-id="1301a-223">Cloud apps:</span></span>

- [<span data-ttu-id="1301a-224">Dynamics 365 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="1301a-224">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="1301a-225">Power BI 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="1301a-225">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="1301a-226">Microsoft Teams 업그레이드 시작하기</span><span class="sxs-lookup"><span data-stu-id="1301a-226">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)