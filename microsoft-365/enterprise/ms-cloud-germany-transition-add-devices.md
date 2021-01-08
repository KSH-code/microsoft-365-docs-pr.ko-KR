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
description: '요약: 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 이동하는 경우 서비스에 대한 추가 장치 정보입니다.'
ms.openlocfilehash: 151fcac882dc91d96df3ece000c28d1a7abe1d1f
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780299"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="71047-103">도이클란드 Microsoft 클라우드에서 마이그레이션하기 위한 추가 장치 정보</span><span class="sxs-lookup"><span data-stu-id="71047-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="71047-104">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="71047-104">Frequently asked questions</span></span>

<span data-ttu-id="71047-105">**조직이 영향을 받는지 어떻게 알 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="71047-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="71047-106">관리자는 등록된 장치가 있는지 `https://portal.microsoftazure.de` 여부를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="71047-107">조직에서 장치를 등록한 경우 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="71047-108">**사용자에게 어떤 영향이 있나요?**</span><span class="sxs-lookup"><span data-stu-id="71047-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="71047-109">마이그레이션이 [Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 완료 마이그레이션 단계로 들어오면 등록된 장치의 사용자가 더 이상 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="71047-110">조직이 도이클란드 Microsoft 클라우드와의 연결을 끊기 전에 모든 장치가 전 세계 끝점에 등록되어 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="71047-111">**사용자가 언제 장치를 다시 등록하나요?**</span><span class="sxs-lookup"><span data-stu-id="71047-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="71047-112">도이치란드 [Microsoft](ms-cloud-germany-transition.md#how-is-the-migration-organized) 클라우드 마이그레이션 단계가 진행되는 동안 디바이스 등록을 등록을 다시 등록하고 다시 등록하는 것이 성공하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="71047-113">**마이그레이션 후 장치 상태를 복원하려면 어떻게 해야 합니까?**</span><span class="sxs-lookup"><span data-stu-id="71047-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="71047-114">Azure AD에 등록된 하이브리드 Azure AD 가입 및 회사 소유 Windows 디바이스의 경우 관리자는 원격으로 트리거된 워크플로를 통해 이전 장치 상태의 등록을 등록하지 않는 이러한 디바이스의 마이그레이션을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="71047-115">Azure AD에 등록된 개인 Windows 장치를 포함하여 다른 모든 장치의 경우 최종 사용자는 이러한 단계를 수동으로 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="71047-116">Azure AD에 가입된 장치의 경우 사용자는 등록을 등록을 언다가 장치를 다시 등록하려면 로컬 관리자 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="71047-117">Microsoft는 장치 상태를 성공적으로 복원하는 방법에 대한 지침을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="71047-118">**모든 장치가 공용 클라우드에 등록되어 있는 것을 어떻게 알 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="71047-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="71047-119">장치가 공용 클라우드에 등록되어 있는지 확인하려면 Azure AD 포털에서 Excel 스프레드시트로 장치 목록을 내보내고 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="71047-120">그런 다음 도이치란드 [Microsoft](ms-cloud-germany-transition.md#how-is-the-migration-organized) 클라우드와 분리된 마이그레이션 단계 후 _registeredTime_ 열을 사용하여 등록된 장치를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="71047-121">테넌트 마이그레이션 후 장치 등록이 비활성화되어 활성화 또는 비활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="71047-122">Intune이 사용되지 않는 경우 구독에 로그인하고 다음 명령을 실행하여 옵션을 다시 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a><span data-ttu-id="71047-123">하이브리드 Azure AD 조인</span><span class="sxs-lookup"><span data-stu-id="71047-123">Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="71047-124">Windows 다운 수준</span><span class="sxs-lookup"><span data-stu-id="71047-124">Windows down-level</span></span>

<span data-ttu-id="71047-125">_Windows 다운_ 수준 장치는 현재 이전 버전의 Windows(예: Windows 8.1 또는 Windows 7)를 실행하거나 2019 및 2016 이전 버전의 Windows Server를 실행 중인 Windows 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="71047-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="71047-126">이러한 장치가 전에 등록된 경우 등록을 해지하고 해당 장치를 다시 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="71047-127">Windows 다운 수준 장치가 이전에 Azure AD에 가입 했는지 확인하려면 장치에서 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="71047-128">디바이스가 이전에 Azure AD에 가입된 경우 장치에 전역 Azure AD 끝점에 대한 네트워크 연결이 있는 경우 다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="71047-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

<span data-ttu-id="71047-129">영향을 받는 디바이스의 값은 "알 수 없음"인 "장치 상태"입니다.</span><span class="sxs-lookup"><span data-stu-id="71047-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="71047-130">출력이 "디바이스에 가입되지 않은" 또는 "장치 상태" 값이 "괜찮습니다."인 경우 다음 지침을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="71047-131">디바이스가 가입(deviceId, 지문 등)으로 표시하고 "장치 상태" 값이 "알 수 없음"인 장치만 해당 다운 수준 디바이스에서 로그인하는 도메인 사용자 컨텍스트에서 다음 명령을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="71047-132">위의 명령은 Windows 다운 수준 장치에서 도메인 사용자당 한 번만 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71047-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="71047-133">이 명령은 도메인 사용자 로그인 컨텍스트에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="71047-134">사용자가 이후에 로그인할 때 이 명령을 실행하지 않을 수 있도록 충분히 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="71047-135">위의 명령을 실행하면 로그인한 사용자의 로컬 하이브리드 Azure AD 가입 컴퓨터의 가입 상태가 지워지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71047-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="71047-136">또한 컴퓨터가 여전히 테넌트에 하이브리드 Azure AD에 가입하도록 구성된 경우 사용자가 다시 로그인할 때 가입을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="71047-137">Windows Current</span><span class="sxs-lookup"><span data-stu-id="71047-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="71047-138">Unjoin</span><span class="sxs-lookup"><span data-stu-id="71047-138">Unjoin</span></span>

<span data-ttu-id="71047-139">Windows 10 디바이스가 이전에 Azure AD에 가입 했는지 확인하려면 장치에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="71047-140">장치가 하이브리드 Azure AD에 가입된 경우 관리자는 다음 출력을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="71047-141">출력이 "AzureAdJoined : No"이면 다음 지침을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="71047-142">장치가 Azure AD에 가입된 것으로 표시하는 디바이스에 한해 관리자로 다음 명령을 실행하여 디바이스의 가입 상태를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="71047-143">위의 명령은 Windows 장치의 관리 컨텍스트에서 한 번만 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71047-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="71047-144">하이브리드 AD 가입\다시 등록</span><span class="sxs-lookup"><span data-stu-id="71047-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="71047-145">디바이스가 전역 Azure AD 끝점에 대한 네트워크 연결이 있는 한 디바이스가 사용자 또는 관리자 개입 없이 Azure AD에 자동으로 가입됩니다.</span><span class="sxs-lookup"><span data-stu-id="71047-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="azure-ad-join"></a><span data-ttu-id="71047-146">Azure AD 가입</span><span class="sxs-lookup"><span data-stu-id="71047-146">Azure AD Join</span></span>

<span data-ttu-id="71047-147">**중요:** Intune 서비스 보안 주체는 상거래 마이그레이션 후 사용하도록 설정되어 Azure AD 장치 등록의 활성화를 암시합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="71047-148">마이그레이션 전에 Azure AD 장치 등록을 차단한 경우 PowerShell을 사용하여 Intune 서비스 계정을 사용하지 않도록 설정하여 Azure AD 포털에서 Azure AD 장치 등록을 다시 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="71047-149">Azure Active Directory PowerShell for Graph 모듈에서 이 명령을 사용하여 Intune 서비스 계정을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="71047-150">Unjoin</span><span class="sxs-lookup"><span data-stu-id="71047-150">Unjoin</span></span>

<span data-ttu-id="71047-151">Windows 10 디바이스가 이전에 Azure AD에 가입 했는지 여부를 확인하려면 사용자 또는 관리자가 디바이스에서 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="71047-152">디바이스가 Azure AD에 가입된 경우 사용자 또는 관리자는 다음 출력을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="71047-153">출력이 "AzureAdJoined : NO"이면 다음 지침을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="71047-154">사용자: 디바이스가 Azure AD에 가입된 경우 사용자는 설정에서 디바이스 가입을 언가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="71047-155">Azure AD에서 디바이스를 연결하지 전에 디바이스에 로컬 관리자 계정이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="71047-156">디바이스에 다시 로그인하려면 로컬 관리자 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="71047-157">관리자: 조직의 관리자가 Azure AD에 가입된 사용자의 디바이스에 가입을 해지하려는 경우 그룹 정책과 같은 메커니즘을 사용하여 각 장치에서 다음 명령을 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71047-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="71047-158">관리자는 Azure AD에서 디바이스에 연결을 하기 전에 디바이스에 로컬 관리자 계정이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="71047-159">디바이스에 다시 로그인하려면 로컬 관리자 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="71047-160">위의 명령은 Windows 장치의 관리 컨텍스트에서 한 번만 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71047-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="71047-161">Azure AD 가입/다시 등록</span><span class="sxs-lookup"><span data-stu-id="71047-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="71047-162">사용자는 Windows 설정에서 Azure AD에 디바이스를 연결할 수 있습니다. 설정 > 계정 > 또는 학교 액세스 > **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="71047-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="71047-163">Azure AD Registered(회사 소유)</span><span class="sxs-lookup"><span data-stu-id="71047-163">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="71047-164">Windows 10 장치가 Azure AD에 등록되어 있는지 확인하려면 장치에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="71047-165">디바이스가 Azure AD 등록된 경우 다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="71047-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="71047-166">장치에서 기존 Azure AD 등록 계정을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="71047-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="71047-167">장치에서 Azure AD 등록 계정을 제거하려면 여기에서 다운로드할 수 있는 도구인 CleanupWPJ를 [CleanupWPJ.zip. ](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)</span><span class="sxs-lookup"><span data-stu-id="71047-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="71047-168">ZIP 파일을 추출하고 **WPJCleanup.cmd를 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="71047-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="71047-169">이 도구는 디바이스의 Windows 버전에 따라 올바른 실행을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="71047-170">관리자는 그룹 정책과 같은 메커니즘을 사용하여 디바이스에 로그인한 사용자의 컨텍스트에서 디바이스에서 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="71047-171">Azure AD에서 디바이스를 등록하라는 메시지가 웹 계정 관리자를 사용하지 않도록 설정하려면 다음 레지스트리 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="71047-172">위치: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="71047-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="71047-173">형식: DWORD(32비트)</span><span class="sxs-lookup"><span data-stu-id="71047-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="71047-174">이름: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="71047-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="71047-175">값 데이터: 1</span><span class="sxs-lookup"><span data-stu-id="71047-175">Value data: 1</span></span>

<span data-ttu-id="71047-176">이 레지스트리 값이 존재하면 회사 가입이 차단되어 사용자가 디바이스에 가입하라는 메시지가 표시되지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="71047-177">Android</span><span class="sxs-lookup"><span data-stu-id="71047-177">Android</span></span>

<span data-ttu-id="71047-178">Android의 경우 사용자는 디바이스 등록을 등록을 다시 등록하고 다시 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="71047-179">Microsoft Authenticator 앱 또는 회사 포털 앱을 통해 이행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="71047-180">Microsoft Authenticator 앱에서는 사용자가 장치 등록의 **설정 > 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="71047-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="71047-181">이 장치에서 사용자는 디바이스 등록을 등록을 다시 등록하고 다시 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="71047-182">회사 포털에서 사용자는 장치 **탭으로** 이동하여 디바이스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="71047-183">그런 다음 회사 포털을 사용하여 장치를 다시 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="71047-184">또한 사용자는 계정 설정 페이지에서 계정을 제거한 다음 직장 계정을 다시 추가하여 등록을 다시 등록 및 다시 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="71047-185">Microsoft Authenticator 앱을 사용하여 Android에서 디바이스 등록을 등록을 등록하고 다시 등록하려면</span><span class="sxs-lookup"><span data-stu-id="71047-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="71047-186">Microsoft Authenticator 앱을 열고 설정으로 **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="71047-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="71047-187">장치 **등록을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="71047-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="71047-188">등록을 다시 등록하지 **않습니다.**</span><span class="sxs-lookup"><span data-stu-id="71047-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="71047-189">장치 **등록의** 경우 전자 메일 주소를 입력하여 장치를 다시 등록한 다음 등록을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="71047-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="71047-190">Android 설정 페이지에서 Android 장치를 등록을 등록을 등록하고 다시 등록하려면</span><span class="sxs-lookup"><span data-stu-id="71047-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="71047-191">장치 **설정을 열고** 계정으로 **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="71047-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="71047-192">다시 등록할 작업 계정을 선택하고 계정 **제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="71047-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="71047-193">계정이 제거된 후  계정 페이지에서 계정 추가 및 > **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="71047-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="71047-194">Workplace **Join의** 경우 전자 메일 주소를 입력하고 **가입을** 선택하여 장치 등록을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="71047-195">회사 포털에서 Android에서 디바이스 등록을 등록을 등록하고 다시 등록하려면</span><span class="sxs-lookup"><span data-stu-id="71047-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="71047-196">회사 포털을 시작하고 장치 **탭으로** 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="71047-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="71047-197">디바이스를 선택하여 장치 세부 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="71047-198">타원(3개 점) 메뉴에서 장치 제거를 선택하고 대화 상자에서 확인하여 제거를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="71047-199">이제 회사 포털 앱에서 로그아웃됩니다.</span><span class="sxs-lookup"><span data-stu-id="71047-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="71047-200">로그인을 **선택하여** 장치를 다시 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="71047-201">이 워크로드의 마이그레이션 단계 중이나 관리 또는 사용에 미치는 영향에 대한 자세한 내용은 [도이치란드 Microsoft](ms-cloud-germany-transition-azure-ad.md)클라우드에서 마이그레이션하기 위한 추가 Azure AD 정보에서 Azure AD(Azure Active Directory)에 대한 정보를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="71047-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="71047-202">iOS</span><span class="sxs-lookup"><span data-stu-id="71047-202">iOS</span></span>

<span data-ttu-id="71047-203">iOS 장치에서는 사용자가 Microsoft Authenticator에서 캐시된 계정을 수동으로 제거하고, 디바이스의 등록을 등록하지 않은 후 장치의 모든 네이티브 앱에서 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="71047-204">1단계: 있는 경우 Microsoft Authenticator 앱에서 계정 제거</span><span class="sxs-lookup"><span data-stu-id="71047-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="71047-205">Microsoft Authenticator 앱에서 계정을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="71047-206">오른쪽 위 **모서리에** 있는 설정 아이콘을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="71047-207">설정 아이콘이 없는  경우 최신 버전의 Microsoft Authenticator를 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="71047-208">계정 제거 **단추를** 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="71047-209">이 **디바이스의 모든 앱을 탭합니다.**</span><span class="sxs-lookup"><span data-stu-id="71047-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="71047-210">2단계: Microsoft Authenticator 앱에서 디바이스 등록을 등록을 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="71047-211">오른쪽 위 모서리에 있는 메뉴 아이콘을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="71047-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="71047-212">설정을 **탭한** 다음 **장치 등록을 누릅니다.**</span><span class="sxs-lookup"><span data-stu-id="71047-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="71047-213">계정이 표시될 경우 **등록을** 다시 시작하고 대화 상자에서 **계속합니다.**</span><span class="sxs-lookup"><span data-stu-id="71047-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="71047-214">그 이후에는 계정이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="71047-215">3단계: 필요한 경우 개별 앱에서 사인아웃</span><span class="sxs-lookup"><span data-stu-id="71047-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="71047-216">사용자는 Outlook, Teams 및 OneDrive와 같은 개별 앱으로 이동하여 해당 앱에서 계정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71047-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="71047-217">추가 정보</span><span class="sxs-lookup"><span data-stu-id="71047-217">More information</span></span>

<span data-ttu-id="71047-218">시작:</span><span class="sxs-lookup"><span data-stu-id="71047-218">Getting started:</span></span>

- [<span data-ttu-id="71047-219">독일 Microsoft 클라우드에서 새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="71047-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="71047-220">Microsoft Cloud Deutschland 마이그레이션 지원</span><span class="sxs-lookup"><span data-stu-id="71047-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="71047-221">마이그레이션에 대해 옵트인하는 방법</span><span class="sxs-lookup"><span data-stu-id="71047-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="71047-222">마이그레이션 중의 고객 환경</span><span class="sxs-lookup"><span data-stu-id="71047-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="71047-223">전환을 통해 이동:</span><span class="sxs-lookup"><span data-stu-id="71047-223">Moving through the transition:</span></span>

- [<span data-ttu-id="71047-224">문장 작업 및 영향 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="71047-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="71047-225">추가 사전 작업</span><span class="sxs-lookup"><span data-stu-id="71047-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="71047-226">[Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경 및](ms-cloud-germany-transition-add-experience.md) [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.</span><span class="sxs-lookup"><span data-stu-id="71047-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="71047-227">클라우드 앱:</span><span class="sxs-lookup"><span data-stu-id="71047-227">Cloud apps:</span></span>

- [<span data-ttu-id="71047-228">Dynamics 365 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="71047-228">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="71047-229">Power BI 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="71047-229">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="71047-230">Microsoft Teams 업그레이드 시작하기</span><span class="sxs-lookup"><span data-stu-id="71047-230">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
