---
title: Microsoft Cloud 독일의 마이그레이션에 대 한 추가 장치 정보
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
description: '요약: Microsoft cloud 전라남도 (Microsoft 클라우드 독일)에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 이동할 때의 추가 장치 정보입니다.'
ms.openlocfilehash: da05a3c2eb6a8d579c53d403a1ef575c389eda12
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551956"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="8740e-103">Microsoft Cloud 독일의 마이그레이션에 대 한 추가 장치 정보</span><span class="sxs-lookup"><span data-stu-id="8740e-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="8740e-104">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="8740e-104">Frequently asked questions</span></span>

<span data-ttu-id="8740e-105">**조직이 영향을 받는지 어떻게 확인할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="8740e-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="8740e-106">관리자는 등록 된 장치가 있는지 확인 해야 합니다 `https://portal.microsoftazure.de` .</span><span class="sxs-lookup"><span data-stu-id="8740e-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="8740e-107">조직에서 장치를 등록 한 경우 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="8740e-108">**사용자에 게 미치는 영향은 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="8740e-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="8740e-109">등록 된 장치의 사용자는 마이그레이션이 [AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 마이그레이션 단계로 들어간 후 더 이상 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="8740e-110">조직이 Microsoft 클라우드 독일의 연결을 끊기 전에 모든 장치가 전 세계 끝점에 등록 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="8740e-111">**사용자가 자신의 장치를 다시 등록 해야 하는 경우**</span><span class="sxs-lookup"><span data-stu-id="8740e-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="8740e-112">[Microsoft Cloud 독일](ms-cloud-germany-transition.md#how-is-the-migration-organized) 마이그레이션 단계가 진행 되는 동안에만 장치를 등록 취소 하 고 다시 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="8740e-113">**마이그레이션 후 장치 상태를 복원 하려면 어떻게 해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="8740e-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="8740e-114">Azure AD에 등록 된 하이브리드 Azure AD-조인 및 회사 소유 Windows 장치의 경우 관리자는 이전 장치 상태의 등록을 취소 하는 원격으로 트리거된 워크플로를 통해 이러한 장치 마이그레이션을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="8740e-115">Azure AD에 등록 되어 있는 개인 Windows 장치를 비롯 한 다른 모든 장치에서는 최종 사용자가 다음 단계를 수동으로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="8740e-116">Azure AD-결합 된 장치의 경우 사용자의 등록을 취소 하 고 다시 등록 하려면 로컬 관리자 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="8740e-117">Microsoft는 장치 상태를 성공적으로 복원 하는 방법에 대 한 지침을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="8740e-118">**모든 내 장치가 공용 클라우드에 등록 되어 있는지 어떻게 알 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="8740e-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="8740e-119">장치가 공용 클라우드에 등록 되어 있는지 여부를 확인 하려면 Azure AD 포털에서 Excel 스프레드시트로 장치 목록을 내보내고 다운로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="8740e-120">그런 다음 [Microsoft 클라우드 독일](ms-cloud-germany-transition.md#how-is-the-migration-organized) 마이그레이션 단계와는 별개의 _registeredTime_ 열을 사용 하 여 등록 된 장치를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="8740e-121">장치 등록은 테 넌 트가 마이그레이션 후 비활성화 되며 사용 하거나 사용 하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="8740e-122">Intune을 사용 하지 않는 경우 구독에 로그인 하 고이 명령을 실행 하 여 옵션을 다시 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a><span data-ttu-id="8740e-123">Windows 하이브리드 Azure AD 조인</span><span class="sxs-lookup"><span data-stu-id="8740e-123">Windows Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="8740e-124">Windows 하위 수준</span><span class="sxs-lookup"><span data-stu-id="8740e-124">Windows down-level</span></span>

<span data-ttu-id="8740e-125">_Windows 하위 수준 장치_ 는 현재 이전 버전의 windows를 실행 하는 windows 장치 (예: windows 8.1 또는 windows 7) 이거나 windows Server 버전을 2019 및 2016 보다 이전의 상태로 실행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="8740e-126">이러한 장치를 이전에 등록 한 경우 해당 장치를 등록 취소 하 고 다시 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="8740e-127">이전에 Windows 하위 수준 장치가 Azure AD에 연결 되었는지 여부를 확인 하려면 장치에서 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="8740e-128">장치가 이전에 Azure AD에 가입 된 경우 및 장치에 글로벌 Azure AD 끝점에 대 한 네트워크 연결이 있으면 다음 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

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

<span data-ttu-id="8740e-129">영향을 받는 장치에는 "장치 상태" 값이 "알 수 없음"으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="8740e-130">출력이 "장치 가입 되지 않음" 또는 "장치 상태" 값이 "정상" 인 경우 다음 지침을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="8740e-131">장치가 가입 되어 있고 (deviceId, 손도장 등) 해당 "장치 상태" 값이 "알 수 없음" 인 것을 표시 하는 장치에 대해서만 관리자가 해당 하위 수준 장치에 로그인 한 도메인 사용자 로그인 컨텍스트에서 다음 명령을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="8740e-132">이전 명령은 Windows 하위 수준 장치에서 도메인 사용자 로그인 당 한 번만 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="8740e-133">이 명령은 도메인 사용자 로그인의 컨텍스트에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="8740e-134">사용자가 다음에 로그인 할 때이 명령을 실행 하지 않으려면 충분히 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="8740e-135">위의 명령이 실행 되 면 로그인 한 사용자에 대해 로컬 하이브리드 Azure AD에 연결 된 컴퓨터의 참가 상태를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="8740e-136">또한 컴퓨터가 테 넌 트에 연결 된 하이브리드 Azure AD로 계속 구성 되어 있으면 사용자가 다시 로그인 할 때 가입을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="8740e-137">Windows 현재</span><span class="sxs-lookup"><span data-stu-id="8740e-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="8740e-138">않도록</span><span class="sxs-lookup"><span data-stu-id="8740e-138">Unjoin</span></span>

<span data-ttu-id="8740e-139">이전에 Windows 10 장치가 Azure AD에 연결 되었는지 확인 하려면 장치에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="8740e-140">장치가 하이브리드 Azure AD에 연결 된 경우 관리자는 다음과 같은 출력을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="8740e-141">출력이 "AzureAdJoined: No" 이면 다음 지침을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="8740e-142">장치가 Azure AD에 가입 되어 있음을 보여주는 장치에만 다음 명령을 관리자 권한으로 실행 하 여 장치에 대 한 가입 상태를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="8740e-143">위의 명령은 Windows 장치에서 관리 컨텍스트에서 한 번만 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="8740e-144">하이브리드 AD Join\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="8740e-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="8740e-145">장치가 글로벌 Azure AD 끝점에 대 한 네트워크 연결을 사용 하는 경우 사용자 또는 관리자 간섭 없이 디바이스가 자동으로 Azure AD에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="windows-azure-ad-join"></a><span data-ttu-id="8740e-146">Windows Azure AD 조인</span><span class="sxs-lookup"><span data-stu-id="8740e-146">Windows Azure AD Join</span></span>

### <a name="unjoin"></a><span data-ttu-id="8740e-147">않도록</span><span class="sxs-lookup"><span data-stu-id="8740e-147">Unjoin</span></span>

<span data-ttu-id="8740e-148">이전에 Windows 10 장치를 Azure AD에 조인한 적이 있는지 확인 하려면 사용자 또는 관리자가 장치에서 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-148">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="8740e-149">디바이스가 Azure AD에 가입 되어 있으면 사용자 또는 관리자에 게 다음과 같은 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-149">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="8740e-150">출력이 "AzureAdJoined: NO" 이면 다음 지침을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-150">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="8740e-151">사용자: 디바이스가 Azure AD에 가입 된 경우 사용자는 설정에서 디바이스의 가입을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-151">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="8740e-152">장치를 Azure AD에서 unjoining 전에 해당 장치에 로컬 관리자 계정이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-152">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="8740e-153">장치에 다시 로그인 하려면 로컬 관리자 계정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-153">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="8740e-154">관리자: 조직의 관리자가 가입 된 사용자의 장치를 그룹 정책 등의 메커니즘을 사용 하 여 연결 하는 방법으로 해당 디바이스를 구독 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-154">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="8740e-155">관리자가 Azure AD에서 장치를 unjoining 전에 장치에 로컬 관리자 계정이 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-155">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="8740e-156">장치에 다시 로그인 하려면 로컬 관리자 계정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-156">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="8740e-157">위의 명령은 Windows 장치에서 관리 컨텍스트에서 한 번만 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-157">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="8740e-158">Azure AD Join/재등록</span><span class="sxs-lookup"><span data-stu-id="8740e-158">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="8740e-159">사용자는 Windows 설정에서 Azure AD에 연결할 수 있음: **설정 > 계정 > 액세스 하 여 회사 또는 학교 > 연결** 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-159">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="windows-azure-ad-registered-company-owned"></a><span data-ttu-id="8740e-160">Windows Azure AD 등록 (회사 소유)</span><span class="sxs-lookup"><span data-stu-id="8740e-160">Windows Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="8740e-161">Windows 10 장치가 등록 되어 있는지 여부를 확인 하려면 장치에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-161">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="8740e-162">디바이스가 Azure AD에 등록 되어 있으면 다음과 같은 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-162">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="8740e-163">장치에서 기존 Azure AD 등록 계정을 제거 하려면:</span><span class="sxs-lookup"><span data-stu-id="8740e-163">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="8740e-164">장치에서 Azure AD-등록 된 계정을 제거 하려면 [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)에서 다운로드할 수 있는 도구인 CleanupWPJ를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-164">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="8740e-165">ZIP 파일을 추출 하 고 **WPJCleanup를 실행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8740e-165">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="8740e-166">이 도구는 장치의 Windows 버전에 따라 올바른 실행 파일을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-166">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="8740e-167">관리자는 그룹 정책 같은 메커니즘을 사용 하 여 장치에서 로그인 한 모든 사용자의 컨텍스트에서이 명령을 장치에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-167">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="8740e-168">Azure AD에 장치를 등록 하도록 웹 계정 관리자 프롬프트를 사용 하지 않도록 설정 하려면 다음 레지스트리 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-168">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="8740e-169">위치: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="8740e-169">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="8740e-170">유형: DWORD (32 비트)</span><span class="sxs-lookup"><span data-stu-id="8740e-170">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="8740e-171">이름: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="8740e-171">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="8740e-172">값 데이터: 1</span><span class="sxs-lookup"><span data-stu-id="8740e-172">Value data: 1</span></span>

<span data-ttu-id="8740e-173">이 레지스트리 값이 있으면 작업 영역 조인이 차단 되 고 사용자가 장치에 연결 하 라는 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-173">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="8740e-174">Android</span><span class="sxs-lookup"><span data-stu-id="8740e-174">Android</span></span>

<span data-ttu-id="8740e-175">Android의 경우 사용자는 해당 디바이스의 등록을 취소 하 고 다시 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-175">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="8740e-176">Microsoft Authenticator 앱 또는 회사 포털 앱을 통해이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-176">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="8740e-177">사용자는 Microsoft 인증자 앱에서 **설정 > 장치 등록** 으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-177">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="8740e-178">사용자가 자신의 장치를 등록 취소 하 고 다시 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-178">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="8740e-179">회사 포털에서 사용자가 **장치** 탭으로 이동 하 여 장치를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-179">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="8740e-180">그런 다음 회사 포털을 사용 하 여 장치를 다시 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-180">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="8740e-181">또한 사용자는 계정 설정 페이지에서 계정을 제거한 다음 다시 추가 하는 방법으로 작업을 등록 취소 하 고 재등록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-181">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="8740e-182">Microsoft Authenticator 앱을 사용 하 여 Android에서 장치를 등록 취소 하 고 다시 등록 하려면:</span><span class="sxs-lookup"><span data-stu-id="8740e-182">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="8740e-183">Microsoft Authenticator 앱을 열고 **설정** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-183">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="8740e-184">**장치 등록** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-184">Select **Device registration**.</span></span>
3.  <span data-ttu-id="8740e-185">**등록 취소** 를 선택 하 여 장치를 등록 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-185">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="8740e-186">**장치 등록** 의 경우 전자 메일 주소를 입력 하 여 장치를 다시 등록 한 다음 **레지스터** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-186">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="8740e-187">Android 설정 페이지를 사용 하 여 Android 장치를 등록 취소 하 고 다시 등록 하려면:</span><span class="sxs-lookup"><span data-stu-id="8740e-187">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="8740e-188">**장치 설정을** 열고 **계정** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-188">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="8740e-189">다시 등록할 작업 계정을 선택 하 고 **계정 제거** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-189">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="8740e-190">계정을 제거한 후 계정 페이지에서 **계정 > 작업 계정 추가** 를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8740e-190">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="8740e-191">**회사 조인의** 경우 사용자의 전자 메일 주소를 입력 하 고 **참가** 를 선택 하 여 장치 등록을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-191">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="8740e-192">회사 포털에서 Android의 장치 등록을 취소 하 고 다시 등록 하려면:</span><span class="sxs-lookup"><span data-stu-id="8740e-192">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="8740e-193">회사 포털을 시작 하 고 **장치** 탭으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-193">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="8740e-194">장치를 선택 하 여 장치 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-194">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="8740e-195">줄임표 (점 3 개) 메뉴에서 **장치 제거** 를 선택 하 고 대화 상자에서 확인 하 여 제거를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-195">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="8740e-196">이제 회사 포털 앱에서 로그 아웃 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-196">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="8740e-197">**로그인** 을 선택 하 여 장치를 다시 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-197">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="8740e-198">이 작업의 마이그레이션 단계 중에 필요한 작업 또는 관리 또는 사용 현황에 대 한 영향에 대 한 자세한 내용은 [Microsoft Cloud 독일의 마이그레이션에 대 한 추가 일반 정보](ms-cloud-germany-transition-add-general.md#azure-active-directory)에서 Azure Active Directory에 대 한 정보를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8740e-198">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory in [Additional general information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-add-general.md#azure-active-directory).</span></span>

## <a name="ios"></a><span data-ttu-id="8740e-199">iOS</span><span class="sxs-lookup"><span data-stu-id="8740e-199">iOS</span></span>

<span data-ttu-id="8740e-200">IOS 장치에서는 사용자가 Microsoft 인증자에서 캐시 된 계정을 수동으로 제거 하 고, 장치를 등록 취소 하 고, 장치의 기본 앱에서 로그 아웃 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-200">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="8740e-201">1 단계: (있는 경우) Microsoft Authenticator 앱에서 계정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-201">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="8740e-202">Microsoft Authenticator 앱에서 계정을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-202">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="8740e-203">오른쪽 위 모서리에 있는 **설정** 아이콘을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-203">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="8740e-204">**설정** 아이콘이 표시 되지 않으면 최신 버전의 Microsoft 인증자를 사용 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-204">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="8740e-205">**계정 제거** 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-205">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="8740e-206">**이 장치의 모든 앱을** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-206">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="8740e-207">2 단계: Microsoft Authenticator 앱에서 장치 등록 취소</span><span class="sxs-lookup"><span data-stu-id="8740e-207">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="8740e-208">오른쪽 위 모서리에 있는 메뉴 아이콘을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-208">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="8740e-209">**설정** 및 **장치 등록** 을 차례로 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-209">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="8740e-210">계정이 표시 되 면 **장치 등록 해제** 를 탭 하 고 대화 상자에서 **계속** 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-210">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="8740e-211">그 후에 계정이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-211">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="8740e-212">3 단계: 필요한 경우 개별 앱에서 로그 아웃</span><span class="sxs-lookup"><span data-stu-id="8740e-212">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="8740e-213">사용자는 Outlook, 팀 및 OneDrive와 같은 개별 앱으로 이동 하 여 해당 앱에서 계정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740e-213">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="8740e-214">추가 정보</span><span class="sxs-lookup"><span data-stu-id="8740e-214">More information</span></span>

<span data-ttu-id="8740e-215">시작 하기:</span><span class="sxs-lookup"><span data-stu-id="8740e-215">Getting started:</span></span>

- [<span data-ttu-id="8740e-216">Microsoft Cloud 독일에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="8740e-216">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="8740e-217">Microsoft Cloud Deutschland 마이그레이션 지원</span><span class="sxs-lookup"><span data-stu-id="8740e-217">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="8740e-218">마이그레이션에 대해 옵트인하는 방법</span><span class="sxs-lookup"><span data-stu-id="8740e-218">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="8740e-219">마이그레이션 중의 고객 환경</span><span class="sxs-lookup"><span data-stu-id="8740e-219">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="8740e-220">전환을 통해 이동 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="8740e-220">Moving through the transition:</span></span>

- [<span data-ttu-id="8740e-221">마이그레이션 단계 작업 및 영향</span><span class="sxs-lookup"><span data-stu-id="8740e-221">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="8740e-222">추가 사전 작업</span><span class="sxs-lookup"><span data-stu-id="8740e-222">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="8740e-223">[서비스](ms-cloud-germany-transition-add-general.md), [장치](ms-cloud-germany-transition-add-devices.md), [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS](ms-cloud-germany-transition-add-adfs.md)에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="8740e-223">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="8740e-224">클라우드 앱:</span><span class="sxs-lookup"><span data-stu-id="8740e-224">Cloud apps:</span></span>

- [<span data-ttu-id="8740e-225">Dynamics 365 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="8740e-225">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="8740e-226">Power BI 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="8740e-226">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="8740e-227">Microsoft Teams 업그레이드 시작하기</span><span class="sxs-lookup"><span data-stu-id="8740e-227">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
