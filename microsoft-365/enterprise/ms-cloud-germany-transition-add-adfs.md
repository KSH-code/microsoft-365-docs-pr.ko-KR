---
title: Microsoft 클라우드 독일의 마이그레이션에 대 한 AD FS 마이그레이션 단계
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
description: '요약: Microsoft Cloud 독일에서 마이그레이션하는 AD FS (Active Directory Federation Services) 마이그레이션 단계를 설명 합니다.'
ms.openlocfilehash: 175734851c2838eb2e224a9afb57a600d4ed9523
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49554813"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="7c8b6-103">Microsoft 클라우드 독일의 마이그레이션에 대 한 AD FS 마이그레이션 단계</span><span class="sxs-lookup"><span data-stu-id="7c8b6-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="7c8b6-104">Microsoft Cloud 독일에서 AD FS (Active Directory Federation Services) 팜을 마이그레이션하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-104">To migrate your Active Directory Federation Services (AD FS) farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="7c8b6-105">[다음 단계를 수행](#backup)하 여 FF 신뢰 정보를 포함 하는 AD FS 설정을 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-105">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="7c8b6-106">Microsoft **cloud Deutschland_Only** 백업 이름을 지정 하 여 Microsoft cloud 독일 테 넌 트 정보만 포함 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-106">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="7c8b6-107">Microsoft 클라우드 Deutschland_Only 백업을 사용 하 여 복원을 테스트 하 여 AD FS 팜이 Microsoft 클라우드 독일만 계속 작동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-107">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>
3. <span data-ttu-id="7c8b6-108">**AD FS에서 Office 365 서비스를 >** 여 새 신뢰 당사자 트러스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-108">Create a new Relying Party trust from **AD FS >  Office 365 services**.</span></span>
4. <span data-ttu-id="7c8b6-109">AD FS 관리 콘솔의 **신뢰 당사자 트러스트** 에서 **신뢰 당사자 트러스트 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span></span>
5. <span data-ttu-id="7c8b6-110">신뢰 당사자 트러스트 추가 마법사의 **시작** 페이지에서 **다음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-110">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
6. <span data-ttu-id="7c8b6-111">**데이터 원본 선택** 페이지에서 **온라인으로 또는 로컬 네트워크에 게시 된 신뢰 당사자에 대 한 데이터 가져오기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-111">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="7c8b6-112">**페더레이션 메타 데이터 주소 (호스트 이름 또는 URL)** 값이로 설정 됩니다 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="7c8b6-112">The **Federation metadata address (host name or URL)** value is set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="7c8b6-113">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-113">Click **Next**.</span></span>
7. <span data-ttu-id="7c8b6-114">**데이터 원본 선택** 페이지에서 표시 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-114">On the **Select Data Source** page, type the display name.</span></span> <span data-ttu-id="7c8b6-115">Microsoft **Office 365 Id 플랫폼을 전 세계** 에서 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-115">Microsoft recommends **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="7c8b6-116">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-116">Click **Next**.</span></span>
8. <span data-ttu-id="7c8b6-117">**Multi-factor Authentication 구성** 에서 **다음** 을 클릭 하 고 **발급 권한 부여 규칙을 선택한** 다음 신뢰 페이지 **를 추가할 준비** 를 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and **Ready to Add Trust** pages.</span></span>
9. <span data-ttu-id="7c8b6-118">**마침** 페이지에서 **닫기를** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-118">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="7c8b6-119">마법사를 닫으면 Office 365 서비스 eSTS에 대 한 신뢰 당사자 트러스트가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-119">By closing the wizard, the Relying Party Trust to the Office 365 services eSTS is established.</span></span> <span data-ttu-id="7c8b6-120">그러나 발급 변환 규칙은 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-120">However, no Issuance Transform rules are established.</span></span>

<span data-ttu-id="7c8b6-121">[AD FS 도움말](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 을 사용 하 여 올바른 발급 변환 규칙을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-121">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="7c8b6-122">AD FS 도움말을 사용 하 여 만든 생성 된 클레임 규칙은 AD FS 관리 콘솔 또는 PowerShell을 통해 수동으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-122">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="7c8b6-123">AD FS 도움말에서는 실행 해야 하는 필수 PowerShell 스크립트를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-123">AD FS Help will generate the necessary PowerShell scripts that need to be run.</span></span>  

1. <span data-ttu-id="7c8b6-124">AD FS 도움말에서 **클레임 생성** 을 실행 하 고 스크립트 오른쪽 위 모서리에 있는 **복사** 옵션을 사용 하 여 PowerShell 클레임 변환 스크립트를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-124">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="7c8b6-125">다음에 생성 된 PowerShell을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-125">Paste the generated PowerShell into the following:</span></span>

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  <span data-ttu-id="7c8b6-126">완성 된 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-126">Execute the completed script.</span></span>
4.  <span data-ttu-id="7c8b6-127">두 신뢰 당사자 트러스트가 존재 하는지 확인 합니다. 전 세계 및 BF 용 1 개</span><span class="sxs-lookup"><span data-stu-id="7c8b6-127">Verify that two Relying Party trusts are present; one for worldwide and one for BF.</span></span>
5.  <span data-ttu-id="7c8b6-128">[이러한 단계](#backup)를 사용 하 여 트러스트를 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-128">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="7c8b6-129">이 파일을 **Ffandworldwide** 에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-129">Save it with the name **FFAndWorldwide**.</span></span>
6.  <span data-ttu-id="7c8b6-130">백 엔드 마이그레이션을 완료 하 고 마이그레이션 프로세스 동안 AD FS가 여전히 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-130">Complete your backend migration and verify that AD FS still works during migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="7c8b6-131">AD FS 재해 복구 (WID 데이터베이스)</span><span class="sxs-lookup"><span data-stu-id="7c8b6-131">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="7c8b6-132">재해 Ad FS에서 AD FS 팜을 복원 하려면 [빠른 복원 도구](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) 를 활용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-132">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="7c8b6-133">따라서이 도구를 다운로드 하 고 마이그레이션을 시작 하기 전에 백업을 만들고 안전 하 게 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-133">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="7c8b6-134">이 예제 (환경에서 TAT)에서는 다음 명령을 실행 하 여 팜을 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-134">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="7c8b6-135">AD FS 팜 백업</span><span class="sxs-lookup"><span data-stu-id="7c8b6-135">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="7c8b6-136">기본 AD FS 서버에 AD FS 빠른 복원 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-136">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="7c8b6-137">이 명령을 사용 하 여 PowerShell 세션에서 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-137">Import the module in a PowerShell session with this command.</span></span>

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. <span data-ttu-id="7c8b6-138">백업 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-138">Run the backup command:</span></span>

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. <span data-ttu-id="7c8b6-139">백업을 원하는 대상에 안전 하 게 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-139">Store the backup safely on a desired destination.</span></span> 

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="7c8b6-140">AD FS 팜 복원</span><span class="sxs-lookup"><span data-stu-id="7c8b6-140">Restore an AD FS Farm</span></span>

<span data-ttu-id="7c8b6-141">팜이 완전히 실패 하 고 이전 팜으로 돌아갈 방법이 없는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-141">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="7c8b6-142">이전에 생성 및 저장 된 백업을 새 기본 AD FS 서버로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-142">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="7c8b6-143">다음 `Restore-ADFS` PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-143">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="7c8b6-144">필요한 경우 사전에 AD FS SSL 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-144">If necessary, import the AD FS SSL certificate beforehand.</span></span>

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. <span data-ttu-id="7c8b6-145">새 DNS 레코드 또는 부하 분산 장치를 새 AD FS 서버에 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="7c8b6-145">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="7c8b6-146">추가 정보</span><span class="sxs-lookup"><span data-stu-id="7c8b6-146">More information</span></span>

<span data-ttu-id="7c8b6-147">시작 하기:</span><span class="sxs-lookup"><span data-stu-id="7c8b6-147">Getting started:</span></span>

- [<span data-ttu-id="7c8b6-148">Microsoft Cloud 독일에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7c8b6-148">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="7c8b6-149">Microsoft Cloud Deutschland 마이그레이션 지원</span><span class="sxs-lookup"><span data-stu-id="7c8b6-149">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="7c8b6-150">마이그레이션에 대해 옵트인하는 방법</span><span class="sxs-lookup"><span data-stu-id="7c8b6-150">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="7c8b6-151">마이그레이션 중의 고객 환경</span><span class="sxs-lookup"><span data-stu-id="7c8b6-151">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="7c8b6-152">전환을 통해 이동 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="7c8b6-152">Moving through the transition:</span></span>

- [<span data-ttu-id="7c8b6-153">마이그레이션 단계 작업 및 영향</span><span class="sxs-lookup"><span data-stu-id="7c8b6-153">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="7c8b6-154">추가 사전 작업</span><span class="sxs-lookup"><span data-stu-id="7c8b6-154">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="7c8b6-155">[서비스](ms-cloud-germany-transition-add-general.md), [장치](ms-cloud-germany-transition-add-devices.md), [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS](ms-cloud-germany-transition-add-adfs.md)에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="7c8b6-155">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="7c8b6-156">클라우드 앱:</span><span class="sxs-lookup"><span data-stu-id="7c8b6-156">Cloud apps:</span></span>

- [<span data-ttu-id="7c8b6-157">Dynamics 365 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="7c8b6-157">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="7c8b6-158">Power BI 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="7c8b6-158">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="7c8b6-159">Microsoft Teams 업그레이드 시작하기</span><span class="sxs-lookup"><span data-stu-id="7c8b6-159">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
