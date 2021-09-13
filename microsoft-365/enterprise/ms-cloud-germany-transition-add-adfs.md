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
ms.openlocfilehash: c8e784c8e582185b4bdebc0cb359cc4c19503d1a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191282"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>도이클란드 Microsoft 클라우드에서 마이그레이션을 위한 AD FS 마이그레이션 단계

2단계가 시작되기 전에 이 구성 변경 사항을 적용해야 합니다.
2단계가 완료되면 구성 변경이 작동하고 을(를) 같은 전역 끝점을 통해 Office 365 수 `https://admin.microsoft.com` 있습니다. 2단계 전에 구성 변경을 구현하는 경우 Office 365 전역 끝점은  아직 작동하지 않지만 새 신뢰 파티 트러스트는 여전히 AD FS(Active Directory Federation Services) 구성의 일부입니다.

AD FS(Active Directory Federation Services)에서 페더전된 인증을 사용하는 고객은 마이그레이션 중의 모든 인증에 사용되는 발급자 URIS를 변경하지 말아야 합니다. 발급자 URIS를 변경하면 도메인의 사용자에 대한 인증 오류가 발생합니다. 발급자 URIS는 AD FS에서 직접 변경하거나 도메인이  관리에서  페더러티로 변환되고 그 반대의 경우도 마찬가지입니다. 마이그레이션된 Azure AD 테넌트에서 페더넌트 도메인을 추가, 제거 또는 변환하지 않는 것이 좋습니다. 발급자 URIS는 마이그레이션이 완전히 완료된 후 변경할 수 있습니다.

도이클란드 Microsoft 클라우드에서 마이그레이션할 AD FS 팜을 준비하기 위해 다음 단계를 수행합니다.

1. 다음 단계를 사용하여 기존 Microsoft 클라우드 도이클라일랜드 신뢰권자 트러스트 등 AD FS 설정을 [백업합니다.](#backup) 백업 **이름을 MicrosoftCloudDeutschlandOnly로** 지정하여 도이치랜드 Microsoft 클라우드 테넌트 정보만 으로 지정합니다.

   > [!NOTE]
   > 백업에는 도이치란드 Microsoft 클라우드에 대한 Office 365 신뢰 파티 트러스트뿐 아니라 해당 AD FS 팜에 있는 다른 모든 신뢰 파티 트러스트도 포함되어 있습니다.

2. MicrosoftCloudDeutschlandOnly 백업을 사용하여 복원을 테스트하고 AD FS 팜은 계속해서 Microsoft 클라우드 도이클란드로 작동해야 합니다.

AD FS 백업을 완료하고 테스트한 후 다음 단계를 수행하여 ADFS 구성에 새 신뢰자 트러스트가 추가됩니다.

1. AD FS관리 콘솔을 엽니다.

2. ADFS 관리 콘솔의 왼쪽 창에서 신뢰 파티 트러스트 **메뉴로** 이동합니다.

3. 오른쪽 창에서 신뢰하는 파티 **트러스트 추가...를 선택합니다.**

4. 신뢰 **파티 트러스트** **추가** 마법사의 시작 페이지에서 시작을 선택합니다.

5. 데이터 **원본 선택 페이지에서** 온라인 또는 로컬 네트워크에서 게시된 의존 관계에 대한 데이터 **가져오기 를 선택합니다.** **페더ation 메타데이터 주소(호스트 이름** 또는 URL) 값을 로 설정해야 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 합니다. **다음** 을 클릭합니다.

6. 표시 이름 **지정 페이지에서** ID **플랫폼 WorldWide와 Microsoft Office 365 표시 이름을 입력합니다.** **다음** 을 클릭합니다.

7. ADFS를 사용하는 Windows Server 2012 지금 다단계 인증 구성 마법사 페이지에서 인증 요구 사항에 따라 적절한 선택을 선택합니다. 기본값을 사용하는 경우 지금 이 신뢰 파티 트러스트에 대해 다단계 인증 설정을 구성하지 않습니다.를 **선택합니다.** 원하는 경우 나중에 이 설정을 변경할 수 있습니다.

8. AD FS 2012의 경우: **Choose Issuance Authorization Rules에서** 모든 사용자가 이 트러디드 파티에 액세스할 수 있도록 허용을 선택한 후 다음을 **클릭합니다.** 

9. AD FS 2016 및 AD FS 2019: 액세스 제어 정책 선택 페이지에서 적절한 액세스 제어 정책을 선택하고 다음 을 **클릭합니다.**  선택하지 않은 경우 신뢰 파티 트러스트가 **작동하지** 않습니다.

10. **트러스트** 추가 **준비** 완료 페이지에서 다음을 클릭하여 마법사를 완료합니다.

11. 마친 **페이지에서** **닫기 를** 클릭합니다.

마법사를 닫아 전역 서비스를 Office 365 신뢰하는 트러스트가 설정됩니다. 그러나 아직 구성되지 않은 Issuance Transform 규칙은 없습니다.

[AD FS 도움말을 사용하여](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 올바른 발행 변환 규칙을 생성할 수 있습니다. AD FS 도움말을 사용하여 생성된 클레임 규칙은 AD FS 관리 콘솔을 통해 또는 PowerShell을 사용하여 수동으로 추가할 수 있습니다. AD FS 도움말은 실행해야 하는 필수 PowerShell 스크립트를 생성합니다.  

> [!NOTE]
> [AD FS 도움말은](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 제품과 함께 배송되는 표준 발행 변환 규칙을 생성합니다. 그러나 사용자 지정 발급 변환 규칙이 Microsoft 클라우드 도이치랜드 신뢰도 트러스트에 있는 경우(예: 사용자 지정 발급자 URIS, 비표준 변경 불가능한 ID 또는 기타 사용자 지정) AD FS 도움말에서 생성하는 규칙은 Microsoft 클라우드 신뢰자 트러스트에 대해 현재 있는 사용자 지정 논리에 맞는 방식으로 수정해야 합니다. 이러한 사용자 지정이 [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)도움말을 통해 생성된 규칙에 통합되지 않은 경우 ID  **Microsoft Office 365 WorldWide에** 대한 인증은 페더러티 ID에 대해 작동하지 않을 가능성이 습니다.

1. AD  FS 도움말에서 클레임 생성 도움말을 [실행하고](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 스크립트 오른쪽 위 모서리에 있는 복사 옵션을 사용하여 PowerShell 스크립트를 복사합니다. 

2. AD FS 팜에서 PowerShell 스크립트를 실행하여 전역 신뢰 파티 트러스트 생성 방법에 대한 [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 도움말에 설명된 단계를 따릅니다. 스크립트를 실행하기 전에 생성된 스크립트의 다음 코드 줄을 아래 설명과 같이 바꾸십시오.

   ```powershell
   # AD FS Help generated value
   $claims = Get-AdfsRelyingPartyTrust -Identifier $(Get-RpIdentifier) | Select-Object IssuanceTransformRules;
   # replace with
   $claims = Get-AdfsRelyingPartyTrust -Identifier urn:federation:MicrosoftOnline | Select-Object IssuanceTransformRules;

   # AD FS Help generated value
   Set-AdfsRelyingPartyTrust -TargetIdentifier $(Get-RpIdentifier) -IssuanceTransformRules $RuleSet.ClaimRulesString;
   # replace with
   Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:MicrosoftOnline -IssuanceTransformRules $RuleSet.ClaimRulesString;
   ```

3. 두 개의 Relying PartyTtrusts가 있는지 확인 도이치클란드 Microsoft 클라우드에 대해 하나, Office 365 글로벌 서비스용입니다. 검사에 다음 명령을 활용할 수 있습니다. 행 2개와 각 이름 및 식별자를 반환해야 합니다.

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. 다음 단계를 사용하여 신뢰 파티 트러스트 모두를 포함하여 전체 마이그레이션 구성을 [백업합니다.](#backup) **MicrosoftCloudDeutschlandAndWorldwide 이름으로 저장합니다.**

5. 테넌트가 마이그레이션 중일 때 지원되는 다양한 마이그레이션 단계에서 AD FS 인증이 도이클란드 Microsoft 클라우드 및 Microsoft Global 클라우드와 함께 작동하고 있는지 정기적으로 확인해야 합니다.

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS 재해 복구(WID 데이터베이스)

재해 AD FS 신속 복원 도구에서 [AD FS](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) 팜을 복원하려면 활용해야 합니다. 따라서 도구를 다운로드하고 마이그레이션을 시작하기 전에 백업을 만들어 안전하게 저장해야 합니다. 이 예제에서는 WID 데이터베이스에서 실행되는 팜을 백업하기 위해 다음 명령을 실행했습니다.

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>AD FS 팜 백업

1. 기본 AD FS 서버에 AD FS 신속 복원 도구를 설치합니다.

2. 이 명령을 사용하여 PowerShell 세션에서 모듈을 가져올 수 있습니다.

   ```powershell
   Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
   ```

3. 백업 명령을 실행합니다.

   ```powershell
   Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
   ```

4. 백업을 원하는 대상에 안전하게 저장합니다.

### <a name="restore-an-ad-fs-farm"></a>AD FS 팜 복원

팜이 완전히 실패하여 이전 팜으로 돌아올 방법이 없는 경우 다음을 합니다. 

1. 이전에 생성된 백업 및 저장된 백업을 새 주 AD FS 서버로 이동하십시오.

2. 다음 `Restore-ADFS` PowerShell 명령을 실행합니다. 필요한 경우 AD FS SSL 인증서를 먼저 가져와야 합니다.

   ```powershell
   Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
   ```

3. 새 DNS 레코드 또는 부하 잔액을 새 AD FS 서버를 지점으로 합니다.

## <a name="more-information"></a>추가 정보

시작:

- [독일 Microsoft 클라우드에서 새 독일 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)
- [마이그레이션 중의 고객 환경](ms-cloud-germany-transition-experience.md)

전환을 통해 이동:

- [문장 작업 및 영향 마이그레이션](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 마이그레이션 프로그램 정보](/power-bi/admin/service-admin-migrate-data-germany)
- [Microsoft Teams 업그레이드 시작하기](/microsoftteams/upgrade-start-here)
