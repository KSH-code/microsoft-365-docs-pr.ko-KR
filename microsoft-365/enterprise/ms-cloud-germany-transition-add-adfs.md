---
title: 도이클란드 Microsoft 클라우드에서 마이그레이션을 위한 AD FS 마이그레이션 단계
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
description: '요약: 도이치란드 Microsoft 클라우드에서 마이그레이션하기 위한 AD FS(Active Directory Federation Services) 마이그레이션 단계입니다.'
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727470"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="a401a-103">도이클란드 Microsoft 클라우드에서 마이그레이션을 위한 AD FS 마이그레이션 단계</span><span class="sxs-lookup"><span data-stu-id="a401a-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="a401a-104">4단계가 시작되기 전에 이 구성 변경을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-104">This configuration change can be applied at any time before phase 4 is starting.</span></span>
<span data-ttu-id="a401a-105">2단계가 완료되면 구성 변경이 작동하고 과 같은 Office 365 전역 끝점에 로그인할 수 `https://portal.office.com` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-105">Once phase 2 is completed the configuration change will work and you are able to sign in to Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="a401a-106">2단계 전에 구성 변경을 구현하는 경우 Office 365 전역  끝점은 아직 작동하지 않지만 새 신뢰 파티 트러스트는 여전히 AD FS(Active Directory Federation Services) 구성의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="a401a-107">도이클란드 Microsoft 클라우드에서 AD FS 팜을 마이그레이션하려면</span><span class="sxs-lookup"><span data-stu-id="a401a-107">To migrate your AD FS farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="a401a-108">다음 단계를 사용하여 FF 트러스트 정보를 포함하여 AD FS 설정을 [백업합니다.](#backup)</span><span class="sxs-lookup"><span data-stu-id="a401a-108">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="a401a-109">백업 **이름을 Microsoft Deutschland_Only** Microsoft 클라우드 테넌트 정보만 으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-109">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="a401a-110">Microsoft 클라우드 Deutschland_Only 사용하여 복원을 테스트합니다. AD FS 팜은 도이클란드 Microsoft 클라우드로만 계속 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-110">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="a401a-111">AD FS 백업을 완료하고 테스트한 후 다음 단계를 수행하여 ADFS 구성에 새 신뢰자 트러스트가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-111">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="a401a-112">AD FS 관리 콘솔 열기</span><span class="sxs-lookup"><span data-stu-id="a401a-112">Open the AD FS management console</span></span>
2. <span data-ttu-id="a401a-113">ADFS 관리 콘솔의 왼쪽 창에서 **ADFS,** 트러스트 관계, 신뢰하는 파티 트러스트를 **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="a401a-113">In the left pane of the ADFS management console, expand **ADFS**, then **Trust Relationships**, then **Relying Party Trusts**</span></span>
3. <span data-ttu-id="a401a-114">오른쪽 창에서 신뢰하는 파티 **트러스트 추가...를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a401a-114">In the right pane, select **Add Relying Party Trust...**</span></span>
4. <span data-ttu-id="a401a-115">신뢰 **파티** 트러스트 **추가** 마법사의 시작 페이지에서 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-115">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
5. <span data-ttu-id="a401a-116">데이터 **원본 선택 페이지에서** 온라인 또는 로컬 네트워크에서 게시된 의존 관계에 대한 데이터 **가져오기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a401a-116">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="a401a-117">**페더ation 메타데이터 주소(호스트 이름** 또는 URL) 값을 로 설정해야 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-117">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="a401a-118">그리고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-118">Then, click **Next**.</span></span>
6. <span data-ttu-id="a401a-119">데이터 **원본 선택 페이지에서** **365 Identity Platform WorldWide와 Microsoft Office 표시 이름을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="a401a-119">On the **Select Data Source** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="a401a-120">그리고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-120">Then, click **Next**.</span></span>
7. <span data-ttu-id="a401a-121">마법사 페이지 지금 다단계 인증 **구성?** 에서 인증 요구 사항에 따라 적절한 선택을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-121">On the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="a401a-122">기본값을 사용하는 경우 지금 이 신뢰 파티 트러스트에 대해 다단계 인증 설정을 구성하지 않습니다.를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a401a-122">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="a401a-123">원하는 경우 나중에 이 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-123">You can change this setting later if you want to.</span></span>
8. <span data-ttu-id="a401a-124">Choose **Issuance Authorization Rules 에서** **모든** 사용자가 이 수의신인에게 액세스 허용을 선택한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a401a-124">On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected click **Next**</span></span>
9. <span data-ttu-id="a401a-125">**트러스트** 추가 **준비** 완료 페이지에서 다음을 클릭하여 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-125">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>
10. <span data-ttu-id="a401a-126">마친 **페이지에서** **닫기 를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-126">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="a401a-127">마법사를 닫아 Office 365 전역 서비스와의 신뢰 파티 트러스트가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-127">By closing the wizard, the Relying Party Trust with the Office 365 Global services is established.</span></span> <span data-ttu-id="a401a-128">그러나 아직 구성되지 않은 Issuance Transform 규칙은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-128">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="a401a-129">[AD FS 도움말을 사용하여](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 올바른 발행 변환 규칙을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-129">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="a401a-130">AD FS 도움말을 사용하여 생성된 클레임 규칙은 AD FS 관리 콘솔을 통해 또는 PowerShell을 사용하여 수동으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-130">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="a401a-131">AD FS 도움말은 실행해야 하는 필수 PowerShell 스크립트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-131">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. <span data-ttu-id="a401a-132">AD  FS에서 클레임 생성 도움말을 실행하고 스크립트의  오른쪽 위 모서리에 있는 복사 옵션을 사용하여 PowerShell 클레임 변환 스크립트를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-132">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="a401a-133">기본 설정 텍스트 편집기를 열고 PowerShell 스크립트를 새 텍스트 창에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-133">Open your preferred text editor and paste the PowerShell script into a new text window.</span></span>
3. <span data-ttu-id="a401a-134">2단계에서 붙여 넣은 스크립트의 끝에 다음 PowerShell 줄 추가</span><span class="sxs-lookup"><span data-stu-id="a401a-134">Add the following PowerShell lines to the end of the pasted script from step 2</span></span>
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. <span data-ttu-id="a401a-135">안전하며 PowerShell 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-135">Safe and execute the PowerShell script.</span></span>
5. <span data-ttu-id="a401a-136">두 개의 신뢰 파티 트러스트가 있는지 확인 도이치클란드 Microsoft 클라우드와 Office 365 전역 서비스용 1개</span><span class="sxs-lookup"><span data-stu-id="a401a-136">Verify that two Relying Party trusts are present; one for the Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span>
6. <span data-ttu-id="a401a-137">다음 단계를 사용하여 [트러스트 백업](#backup).</span><span class="sxs-lookup"><span data-stu-id="a401a-137">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="a401a-138">이름을 **FFAndWorldwide로 저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="a401a-138">Save it with the name **FFAndWorldwide**.</span></span>
7. <span data-ttu-id="a401a-139">백end 마이그레이션을 완료하고 마이그레이션 프로세스 중에 AD FS가 계속 작동하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-139">Complete your backend migration and verify that AD FS still works during the migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="a401a-140">AD FS 재해 복구(WID 데이터베이스)</span><span class="sxs-lookup"><span data-stu-id="a401a-140">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="a401a-141">재해 AD FS 신속 복원 도구에서 [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) 팜을 복원하려면 활용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-141">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="a401a-142">따라서 도구를 다운로드하고 마이그레이션을 시작하기 전에 백업을 만들어 안전하게 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-142">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="a401a-143">이 예(TAT 환경)에서는 팜을 백업하기 위해 다음 명령을 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-143">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="a401a-144">AD FS 팜 백업</span><span class="sxs-lookup"><span data-stu-id="a401a-144">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="a401a-145">기본 AD FS 서버에 AD FS 신속 복원 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-145">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="a401a-146">이 명령을 사용하여 PowerShell 세션에서 모듈을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-146">Import the module in a PowerShell session with this command.</span></span>
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. <span data-ttu-id="a401a-147">백업 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-147">Run the backup command:</span></span>
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. <span data-ttu-id="a401a-148">백업을 원하는 대상에 안전하게 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-148">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="a401a-149">AD FS 팜 복원</span><span class="sxs-lookup"><span data-stu-id="a401a-149">Restore an AD FS Farm</span></span>

<span data-ttu-id="a401a-150">팜이 완전히 실패하여 이전 팜으로 돌아올 방법이 없는 경우 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-150">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="a401a-151">이전에 생성된 백업 및 저장된 백업을 새 주 AD FS 서버로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="a401a-151">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="a401a-152">다음 `Restore-ADFS` PowerShell 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-152">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="a401a-153">필요한 경우 AD FS SSL 인증서를 먼저 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-153">If necessary, import the AD FS SSL certificate beforehand.</span></span>

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. <span data-ttu-id="a401a-154">새 DNS 레코드 또는 부하 잔액을 새 AD FS 서버를 지점으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a401a-154">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="a401a-155">추가 정보</span><span class="sxs-lookup"><span data-stu-id="a401a-155">More information</span></span>

<span data-ttu-id="a401a-156">시작:</span><span class="sxs-lookup"><span data-stu-id="a401a-156">Getting started:</span></span>

- [<span data-ttu-id="a401a-157">독일 Microsoft 클라우드에서 새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="a401a-157">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="a401a-158">Microsoft Cloud Deutschland 마이그레이션 지원</span><span class="sxs-lookup"><span data-stu-id="a401a-158">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="a401a-159">마이그레이션에 대해 옵트인하는 방법</span><span class="sxs-lookup"><span data-stu-id="a401a-159">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="a401a-160">마이그레이션 중의 고객 환경</span><span class="sxs-lookup"><span data-stu-id="a401a-160">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="a401a-161">전환을 통해 이동:</span><span class="sxs-lookup"><span data-stu-id="a401a-161">Moving through the transition:</span></span>

- [<span data-ttu-id="a401a-162">문장 작업 및 영향 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="a401a-162">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="a401a-163">추가 사전 작업</span><span class="sxs-lookup"><span data-stu-id="a401a-163">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="a401a-164">[Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.</span><span class="sxs-lookup"><span data-stu-id="a401a-164">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="a401a-165">클라우드 앱:</span><span class="sxs-lookup"><span data-stu-id="a401a-165">Cloud apps:</span></span>

- [<span data-ttu-id="a401a-166">Dynamics 365 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="a401a-166">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="a401a-167">Power BI 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="a401a-167">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="a401a-168">Microsoft Teams 업그레이드 시작하기</span><span class="sxs-lookup"><span data-stu-id="a401a-168">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
