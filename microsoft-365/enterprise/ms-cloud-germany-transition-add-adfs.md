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
ms.openlocfilehash: 852fc8f93158d7b6080f1add5a05e7367539f889
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838416"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="d00bf-103">도이클란드 Microsoft 클라우드에서 마이그레이션을 위한 AD FS 마이그레이션 단계</span><span class="sxs-lookup"><span data-stu-id="d00bf-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="d00bf-104">2단계가 시작되기 전에 이 구성 변경 사항을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-104">This configuration change needs to be applied any time before phase 2 is starting.</span></span>
<span data-ttu-id="d00bf-105">2단계가 완료되면 구성 변경이 작동하고 과 같은 Office 365 전역 끝점을 통해 로그인할 수 `https://portal.office.com` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-105">Once phase 2 is completed the configuration change will work and you are able to sign in via Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="d00bf-106">2단계 전에 구성 변경을 구현하는 경우 Office 365 전역  끝점은 아직 작동하지 않지만 새 신뢰 파티 트러스트는 여전히 AD FS(Active Directory Federation Services) 구성의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="d00bf-107">AD FS(Active Directory Federation Services)에서 페더전된 인증을 사용하는 고객은 마이그레이션 중의 모든 인증에 사용되는 발급자 URIS를 변경하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-107">Customers who use federated authentication with Active Directory Federation Services (AD FS) shouldn't make changes to issuer URIs that are used for all authentications with on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="d00bf-108">발급자 URIS를 변경하면 도메인의 사용자에 대한 인증 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-108">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="d00bf-109">발급자 URIS는 AD FS에서 직접 변경하거나 도메인이  관리에서  페더러티로 변환되고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-109">Issuer URIs can be changed directly in AD FS or when a domain is converted from _managed_ to _federated_ and vice-versa.</span></span> <span data-ttu-id="d00bf-110">마이그레이션된 Azure AD 테넌트에서 페더넌트 도메인을 추가, 제거 또는 변환하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-110">We recommend that you do not add, remove, or convert a federated domain in the Azure AD tenant that has been migrated.</span></span> <span data-ttu-id="d00bf-111">발급자 URIS는 마이그레이션이 완전히 완료된 후 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-111">Issuer URIs can be changed after the migration is fully complete.</span></span>

<span data-ttu-id="d00bf-112">도이클란드 Microsoft 클라우드에서 마이그레이션할 AD FS 팜을 준비하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-112">To prepare your AD FS farm for the migration from Microsoft Cloud Deutschland perform the following steps:</span></span>

1. <span data-ttu-id="d00bf-113">다음 단계를 사용하여 기존 Microsoft 클라우드 도이클라일랜드 신뢰권자 트러스트 등 AD FS 설정을 [백업합니다.](#backup)</span><span class="sxs-lookup"><span data-stu-id="d00bf-113">Back up your AD FS settings, including the existing Microsoft Cloud Deutschland Relying Party trust, with [these steps](#backup).</span></span> <span data-ttu-id="d00bf-114">백업 **이름을 MicrosoftCloudDeutschlandOnly로** 지정하여 도이치랜드 Microsoft 클라우드 테넌트 정보만 으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-114">Name the backup **MicrosoftCloudDeutschlandOnly** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d00bf-115">백업에는 도이치란드 Microsoft 클라우드용 기존 Office 365 신뢰 파티 트러스트뿐 아니라 해당 AD FS 팜에 있는 다른 모든 신뢰 파티 트러스트도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-115">The backup will not only contain the existing Office 365 Relying Party Trust for Microsoft Cloud Deutschland, but also all other Relying Party Trusts present on the respective AD FS farm.</span></span>

2. <span data-ttu-id="d00bf-116">MicrosoftCloudDeutschlandOnly 백업을 사용하여 복원을 테스트하고 AD FS 팜은 계속해서 Microsoft 클라우드 도이클란드로 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-116">Test the restore using the MicrosoftCloudDeutschlandOnly backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="d00bf-117">AD FS 백업을 완료하고 테스트한 후 다음 단계를 수행하여 ADFS 구성에 새 신뢰자 트러스트가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-117">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="d00bf-118">AD FS 관리 콘솔을 니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-118">Open the AD FS management console.</span></span>

2. <span data-ttu-id="d00bf-119">ADFS 관리 콘솔의 왼쪽 창에서 신뢰 파티 트러스트 **메뉴로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-119">In the left pane of the ADFS management console navigate to the **Relying Party Trusts** menu.</span></span>

3. <span data-ttu-id="d00bf-120">오른쪽 창에서 신뢰하는 파티 **트러스트 추가...를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d00bf-120">In the right pane, select **Add Relying Party Trust...**</span></span>

4. <span data-ttu-id="d00bf-121">신뢰 **파티 트러스트** **추가** 마법사의 시작 페이지에서 시작을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-121">Select **Start** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>

5. <span data-ttu-id="d00bf-122">데이터 **원본 선택 페이지에서** 온라인 또는 로컬 네트워크에서 게시된 의존 관계에 대한 데이터 **가져오기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d00bf-122">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="d00bf-123">**페더ation 메타데이터 주소(호스트 이름** 또는 URL) 값을 로 설정해야 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-123">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="d00bf-124">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-124">Click **Next**.</span></span>

6. <span data-ttu-id="d00bf-125">표시 이름 **지정 페이지에서** **365 Identity Platform WorldWide와 같은 표시 Microsoft Office 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="d00bf-125">On the **Specify Display Name** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="d00bf-126">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-126">Click **Next**.</span></span>

7. <span data-ttu-id="d00bf-127">ADFS를 사용하는 Windows Server 2012 지금 다단계 인증 구성 마법사 페이지에서 인증 요구 사항에 따라 적절한 선택을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-127">If you are using ADFS in Windows Server 2012, on the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="d00bf-128">기본값을 사용하는 경우 지금 이 신뢰 파티 트러스트에 대해 다단계 인증 설정을 구성하지 않습니다.를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d00bf-128">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="d00bf-129">원하는 경우 나중에 이 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-129">You can change this setting later if you want to.</span></span>

8. <span data-ttu-id="d00bf-130">AD FS 2012의 경우: **Choose Issuance Authorization Rules에서** 모든 사용자가 이 트러디드 파티에 액세스할 수 있도록 허용을 선택한 후 다음을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="d00bf-130">For AD FS 2012: On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected and click **Next**.</span></span>

8. <span data-ttu-id="d00bf-131">AD FS 2016 및 AD FS 2019: 액세스 제어 정책 선택 페이지에서 적절한 액세스 제어 정책을 선택하고 다음 을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="d00bf-131">For AD FS 2016 and AD FS 2019: On the **Choose Access Control Policy** page, select the appropriate access control policy and click **Next**.</span></span> <span data-ttu-id="d00bf-132">선택하지 않은 경우 신뢰 파티 트러스트가 **작동하지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-132">If none is chosen, the Relying Party Trust will **NOT** work.</span></span>

9. <span data-ttu-id="d00bf-133">**트러스트** 추가 **준비** 완료 페이지에서 다음을 클릭하여 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-133">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>

10. <span data-ttu-id="d00bf-134">마친 **페이지에서** **닫기 를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-134">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="d00bf-135">마법사를 닫아 Office 365 전역 서비스에 대한 신뢰 파티 트러스트가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-135">By closing the wizard, the Relying Party Trust with the Office 365 Global service is established.</span></span> <span data-ttu-id="d00bf-136">그러나 아직 구성되지 않은 Issuance Transform 규칙은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-136">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="d00bf-137">[AD FS 도움말을 사용하여](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 올바른 발행 변환 규칙을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-137">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="d00bf-138">AD FS 도움말을 사용하여 생성된 클레임 규칙은 AD FS 관리 콘솔을 통해 또는 PowerShell을 사용하여 수동으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-138">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="d00bf-139">AD FS 도움말은 실행해야 하는 필수 PowerShell 스크립트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-139">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

> [!NOTE]
> <span data-ttu-id="d00bf-140">[AD FS 도움말은](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 제품과 함께 배송되는 표준 발행 변환 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-140">[AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) will generate the standard issuance transform rules that ship with the product.</span></span> <span data-ttu-id="d00bf-141">그러나 사용자 지정 발급 변환 규칙이 Microsoft 클라우드 도이치랜드 신뢰도 트러스트에 있는 경우(예: 사용자 지정 발급자 URIS, 비표준 변경 불가능한 ID 또는 기타 사용자 지정) AD FS 도움말에서 생성하는 규칙은 Microsoft 클라우드 신뢰자 트러스트에 대해 현재 있는 사용자 지정 논리에 맞는 방식으로 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-141">However, if custom issuance transform rules are in place in the Microsoft Cloud Deutschland Relying Party Trust (for example, custom issuer URIs, non-standard immutable IDs, or any other customizations), the rules generated by AD FS help must be modified in a way that they fit the custom logic currently in place for the Microsoft Cloud Deutschland relying party trust.</span></span> <span data-ttu-id="d00bf-142">이러한 사용자 지정이 [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)도움말을 통해 생성된 규칙에 통합되지 않은 경우 Microsoft Office  **365 Identity Platform WorldWide에** 대한 인증은 페더러티 ID에 대해 작동하지 않을 가능성이 습니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-142">If these customizations are not integrated in the rules generated via [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator), authentication to **Microsoft Office 365 Identity Platform WorldWide** will most likely **not** work for your federated identities.</span></span>

1. <span data-ttu-id="d00bf-143">AD  FS 도움말에서 클레임 생성 도움말을 [실행하고](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 스크립트 오른쪽 위 모서리에 있는 복사 옵션을 사용하여 PowerShell 스크립트를 복사합니다. </span><span class="sxs-lookup"><span data-stu-id="d00bf-143">Run **Generate Claims** on [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) and copy the PowerShell script using the **Copy** option on the right upper corner of the script.</span></span>

2. <span data-ttu-id="d00bf-144">AD FS 팜에서 PowerShell 스크립트를 실행하여 전역 신뢰 파티 트러스트 생성 방법에 대한 [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 도움말에 설명된 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-144">Follow the steps outlined at [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) on how to run the PowerShell script in your AD FS farm to generate the global Relying Party Trust.</span></span>

3. <span data-ttu-id="d00bf-145">두 개의 Relying PartyTtrusts가 있는지 확인 도이치클란드 Microsoft 클라우드 및 Office 365 전역 서비스용 1개</span><span class="sxs-lookup"><span data-stu-id="d00bf-145">Verify that two Relying PartyTtrusts are present; one for Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span> <span data-ttu-id="d00bf-146">검사에 다음 명령을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-146">The following command can be leveraged for the check.</span></span> <span data-ttu-id="d00bf-147">행 2개와 각 이름 및 식별자를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-147">It should return two rows and the respective names and identifiers.</span></span>

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. <span data-ttu-id="d00bf-148">다음 단계를 사용하여 신뢰 파티 트러스트 모두를 포함하여 전체 마이그레이션 구성을 [백업합니다.](#backup)</span><span class="sxs-lookup"><span data-stu-id="d00bf-148">Backup your full migration configuration, including both Relying Party trusts, using [these steps](#backup).</span></span> <span data-ttu-id="d00bf-149">**MicrosoftCloudDeutschlandAndWorldwide 이름으로 저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="d00bf-149">Save it with the name **MicrosoftCloudDeutschlandAndWorldwide**.</span></span>

5. <span data-ttu-id="d00bf-150">테넌트가 마이그레이션 중일 때 지원되는 다양한 마이그레이션 단계에서 AD FS 인증이 도이클란드 Microsoft 클라우드 및 Microsoft Global 클라우드와 함께 작동하고 있는지 정기적으로 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-150">While your tenant is in migration, regularly verify that AD FS authentication is working with Microsoft Cloud Deutschland and Microsoft Global cloud in the various supported migration steps.</span></span>


## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="d00bf-151">AD FS 재해 복구(WID 데이터베이스)</span><span class="sxs-lookup"><span data-stu-id="d00bf-151">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="d00bf-152">재해 AD FS 신속 복원 도구에서 [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) 팜을 복원하려면 활용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-152">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="d00bf-153">따라서 도구를 다운로드하고 마이그레이션을 시작하기 전에 백업을 만들어 안전하게 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-153">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="d00bf-154">이 예제에서는 WID 데이터베이스에서 실행되는 팜을 백업하기 위해 다음 명령을 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-154">In this example, the following commands have been run to back up a farm running on a WID database:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="d00bf-155">AD FS 팜 백업</span><span class="sxs-lookup"><span data-stu-id="d00bf-155">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="d00bf-156">기본 AD FS 서버에 AD FS 신속 복원 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-156">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>

2. <span data-ttu-id="d00bf-157">이 명령을 사용하여 PowerShell 세션에서 모듈을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-157">Import the module in a PowerShell session with this command.</span></span>

   ```powershell
   Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
   ```

3. <span data-ttu-id="d00bf-158">백업 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-158">Run the backup command:</span></span>

   ```powershell
   Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
   ```

4. <span data-ttu-id="d00bf-159">백업을 원하는 대상에 안전하게 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-159">Store the backup safely on a desired destination.</span></span>


### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="d00bf-160">AD FS 팜 복원</span><span class="sxs-lookup"><span data-stu-id="d00bf-160">Restore an AD FS Farm</span></span>

<span data-ttu-id="d00bf-161">팜이 완전히 실패하여 이전 팜으로 돌아올 방법이 없는 경우 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-161">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="d00bf-162">이전에 생성된 백업 및 저장된 백업을 새 주 AD FS 서버로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="d00bf-162">Move the previously generated and stored backup to the new primary AD FS server.</span></span>

2. <span data-ttu-id="d00bf-163">다음 `Restore-ADFS` PowerShell 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-163">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="d00bf-164">필요한 경우 AD FS SSL 인증서를 먼저 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-164">If necessary, import the AD FS SSL certificate beforehand.</span></span>

   ```powershell
   Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
   ```

3. <span data-ttu-id="d00bf-165">새 DNS 레코드 또는 부하 잔액을 새 AD FS 서버를 지점으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d00bf-165">Point your new DNS records or load balancer to the new AD FS servers.</span></span>


## <a name="more-information"></a><span data-ttu-id="d00bf-166">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d00bf-166">More information</span></span>

<span data-ttu-id="d00bf-167">시작:</span><span class="sxs-lookup"><span data-stu-id="d00bf-167">Getting started:</span></span>

- [<span data-ttu-id="d00bf-168">독일 Microsoft 클라우드에서 새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="d00bf-168">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="d00bf-169">Microsoft Cloud Deutschland 마이그레이션 지원</span><span class="sxs-lookup"><span data-stu-id="d00bf-169">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="d00bf-170">마이그레이션에 대해 옵트인하는 방법</span><span class="sxs-lookup"><span data-stu-id="d00bf-170">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="d00bf-171">마이그레이션 중의 고객 환경</span><span class="sxs-lookup"><span data-stu-id="d00bf-171">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="d00bf-172">전환을 통해 이동:</span><span class="sxs-lookup"><span data-stu-id="d00bf-172">Moving through the transition:</span></span>

- [<span data-ttu-id="d00bf-173">문장 작업 및 영향 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="d00bf-173">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="d00bf-174">추가 사전 작업</span><span class="sxs-lookup"><span data-stu-id="d00bf-174">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="d00bf-175">[Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.</span><span class="sxs-lookup"><span data-stu-id="d00bf-175">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="d00bf-176">클라우드 앱:</span><span class="sxs-lookup"><span data-stu-id="d00bf-176">Cloud apps:</span></span>

- [<span data-ttu-id="d00bf-177">Dynamics 365 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="d00bf-177">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="d00bf-178">Power BI 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="d00bf-178">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="d00bf-179">Microsoft Teams 업그레이드 시작하기</span><span class="sxs-lookup"><span data-stu-id="d00bf-179">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
