---
title: 도이클란드 Microsoft 클라우드에서 마이그레이션하기 위한 AD FS 마이그레이션 단계
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
description: '요약: 도이클란드 Microsoft 클라우드에서 마이그레이션하기 위한 AD FS(Active Directory Federation Services) 마이그레이션 단계입니다.'
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688668"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="e21bf-103">도이클란드 Microsoft 클라우드에서 마이그레이션하기 위한 AD FS 마이그레이션 단계</span><span class="sxs-lookup"><span data-stu-id="e21bf-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="e21bf-104">도이클란드 Microsoft 클라우드에서 AD FS(Active Directory Federation Services) 팜을 마이그레이션하려면</span><span class="sxs-lookup"><span data-stu-id="e21bf-104">To migrate your Active Directory Federation Services (AD FS) farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="e21bf-105">다음 단계를 사용하여 FF 트러스트 정보를 포함하여 AD FS 설정을 [백업합니다.](#backup)</span><span class="sxs-lookup"><span data-stu-id="e21bf-105">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="e21bf-106">백업 **Microsoft 클라우드** Deutschland_Only 이름을 지정하여 도이클란드 Microsoft 클라우드 테넌트 정보만 들이고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-106">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="e21bf-107">Microsoft 클라우드 Deutschland_Only 사용하여 복원을 테스트합니다. AD FS 팜은 도이클란드 Microsoft 클라우드로만 계속 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-107">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>
3. <span data-ttu-id="e21bf-108">**Office 365 서비스에서 AD FS에서 > 트러스트 만들기.**</span><span class="sxs-lookup"><span data-stu-id="e21bf-108">Create a new Relying Party trust from **AD FS >  Office 365 services**.</span></span>
4. <span data-ttu-id="e21bf-109">AD  FS 관리 콘솔의 신뢰 대상 트러스트에서 신뢰 대상 트러스트 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e21bf-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span></span>
5. <span data-ttu-id="e21bf-110">신뢰 **파티** **트러스트** 추가 마법사의 시작 페이지에서 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-110">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
6. <span data-ttu-id="e21bf-111">데이터 원본 **선택 페이지에서** 온라인 또는 로컬 네트워크에서 게시된 의존 관계에 대한 **데이터 가져오기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e21bf-111">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="e21bf-112">**페더ation 메타데이터 주소(호스트 이름 또는 URL)** 값이 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-112">The **Federation metadata address (host name or URL)** value is set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="e21bf-113">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-113">Click **Next**.</span></span>
7. <span data-ttu-id="e21bf-114">데이터 원본 **선택 페이지에서** 표시 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-114">On the **Select Data Source** page, type the display name.</span></span> <span data-ttu-id="e21bf-115">Microsoft는 **365 Microsoft Office Platform WorldWide를 권장합니다.**</span><span class="sxs-lookup"><span data-stu-id="e21bf-115">Microsoft recommends **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="e21bf-116">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-116">Click **Next**.</span></span>
8. <span data-ttu-id="e21bf-117">지금 **다단계** 인증 구성을 **클릭하고,** 발행 권한 부여 규칙을 선택하고, 트러스트 페이지를 추가할 **준비를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e21bf-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and **Ready to Add Trust** pages.</span></span>
9. <span data-ttu-id="e21bf-118">완료 **페이지에서** **닫기를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-118">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="e21bf-119">마법사를 닫는 경우 Office 365 서비스 eSTS에 대한 신뢰 파티 트러스트가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-119">By closing the wizard, the Relying Party Trust to the Office 365 services eSTS is established.</span></span> <span data-ttu-id="e21bf-120">그러나 발행 변환 규칙은 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-120">However, no Issuance Transform rules are established.</span></span>

<span data-ttu-id="e21bf-121">[AD FS 도움말을 사용하여](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 올바른 발행 변환 규칙을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-121">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="e21bf-122">AD FS 도움말을 사용하여 생성된 클레임 규칙은 AD FS 관리 콘솔 또는 PowerShell을 통해 수동으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-122">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="e21bf-123">AD FS 도움말은 실행해야 하는 필요한 PowerShell 스크립트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-123">AD FS Help will generate the necessary PowerShell scripts that need to be run.</span></span>  

1. <span data-ttu-id="e21bf-124">AD  FS에서 클레임 생성 도움말을 실행하고 스크립트 오른쪽  위에 있는 복사 옵션을 사용하여 PowerShell 클레임 변환 스크립트를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-124">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="e21bf-125">생성된 PowerShell을 다음에 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-125">Paste the generated PowerShell into the following:</span></span>

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  <span data-ttu-id="e21bf-126">완료된 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-126">Execute the completed script.</span></span>
4.  <span data-ttu-id="e21bf-127">두 개의 신뢰 파티 트러스트가 있는지 확인 하나는 전 세계에, 하나는 BF용입니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-127">Verify that two Relying Party trusts are present; one for worldwide and one for BF.</span></span>
5.  <span data-ttu-id="e21bf-128">다음 단계를 사용하여 [트러스트 백업.](#backup)</span><span class="sxs-lookup"><span data-stu-id="e21bf-128">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="e21bf-129">**FFAndWorldwide 이름으로 저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="e21bf-129">Save it with the name **FFAndWorldwide**.</span></span>
6.  <span data-ttu-id="e21bf-130">백end 마이그레이션을 완료하고 마이그레이션 프로세스 중에 AD FS가 계속 작동하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-130">Complete your backend migration and verify that AD FS still works during migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="e21bf-131">AD FS 재해 복구(WID 데이터베이스)</span><span class="sxs-lookup"><span data-stu-id="e21bf-131">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="e21bf-132">재해 AD FS 신속 복원 도구에서 [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) 팜을 복원하려면 활용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-132">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="e21bf-133">따라서 도구를 다운로드해야 합니다. 마이그레이션을 시작하기 전에 백업을 만들어 안전하게 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-133">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="e21bf-134">이 예제(TAT 환경)에서는 팜을 백업하기 위해 다음 명령을 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-134">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="e21bf-135">AD FS 팜 백업</span><span class="sxs-lookup"><span data-stu-id="e21bf-135">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="e21bf-136">주 AD FS 서버에 AD FS 신속 복원 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-136">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="e21bf-137">이 명령을 사용하여 PowerShell 세션에서 모듈을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-137">Import the module in a PowerShell session with this command.</span></span>

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. <span data-ttu-id="e21bf-138">백업 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-138">Run the backup command:</span></span>

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. <span data-ttu-id="e21bf-139">백업을 원하는 대상에 안전하게 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-139">Store the backup safely on a desired destination.</span></span> 

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="e21bf-140">AD FS 팜 복원</span><span class="sxs-lookup"><span data-stu-id="e21bf-140">Restore an AD FS Farm</span></span>

<span data-ttu-id="e21bf-141">팜이 완전히 실패하여 이전 팜으로 돌아올 방법이 없는 경우 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-141">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="e21bf-142">이전에 생성된 백업 및 저장된 백업을 새 주 AD FS 서버로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="e21bf-142">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="e21bf-143">다음 `Restore-ADFS` PowerShell 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-143">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="e21bf-144">필요한 경우 AD FS SSL 인증서를 먼저 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-144">If necessary, import the AD FS SSL certificate beforehand.</span></span>

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. <span data-ttu-id="e21bf-145">새 DNS 레코드 또는 부하 잔액을 새 AD FS 서버를 지점으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e21bf-145">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="e21bf-146">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e21bf-146">More information</span></span>

<span data-ttu-id="e21bf-147">시작:</span><span class="sxs-lookup"><span data-stu-id="e21bf-147">Getting started:</span></span>

- [<span data-ttu-id="e21bf-148">독일 Microsoft 클라우드에서 새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="e21bf-148">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="e21bf-149">Microsoft Cloud Deutschland 마이그레이션 지원</span><span class="sxs-lookup"><span data-stu-id="e21bf-149">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="e21bf-150">마이그레이션에 대해 옵트인하는 방법</span><span class="sxs-lookup"><span data-stu-id="e21bf-150">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="e21bf-151">마이그레이션 중의 고객 환경</span><span class="sxs-lookup"><span data-stu-id="e21bf-151">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="e21bf-152">전환을 통해 이동:</span><span class="sxs-lookup"><span data-stu-id="e21bf-152">Moving through the transition:</span></span>

- [<span data-ttu-id="e21bf-153">문장 작업 및 영향 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="e21bf-153">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="e21bf-154">추가 사전 작업</span><span class="sxs-lookup"><span data-stu-id="e21bf-154">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="e21bf-155">[Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경 및](ms-cloud-germany-transition-add-experience.md) [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.</span><span class="sxs-lookup"><span data-stu-id="e21bf-155">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="e21bf-156">클라우드 앱:</span><span class="sxs-lookup"><span data-stu-id="e21bf-156">Cloud apps:</span></span>

- [<span data-ttu-id="e21bf-157">Dynamics 365 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="e21bf-157">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="e21bf-158">Power BI 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="e21bf-158">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="e21bf-159">Microsoft Teams 업그레이드 시작하기</span><span class="sxs-lookup"><span data-stu-id="e21bf-159">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
