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
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>도이클란드 Microsoft 클라우드에서 마이그레이션하기 위한 AD FS 마이그레이션 단계

도이클란드 Microsoft 클라우드에서 AD FS(Active Directory Federation Services) 팜을 마이그레이션하려면

1. 다음 단계를 사용하여 FF 트러스트 정보를 포함하여 AD FS 설정을 [백업합니다.](#backup) 백업 **Microsoft 클라우드** Deutschland_Only 이름을 지정하여 도이클란드 Microsoft 클라우드 테넌트 정보만 들이고 있습니다.
2. Microsoft 클라우드 Deutschland_Only 사용하여 복원을 테스트합니다. AD FS 팜은 도이클란드 Microsoft 클라우드로만 계속 작동해야 합니다.
3. **Office 365 서비스에서 AD FS에서 > 트러스트 만들기.**
4. AD  FS 관리 콘솔의 신뢰 대상 트러스트에서 신뢰 대상 트러스트 **추가를 선택합니다.**
5. 신뢰 **파티** **트러스트** 추가 마법사의 시작 페이지에서 다음을 선택합니다.
6. 데이터 원본 **선택 페이지에서** 온라인 또는 로컬 네트워크에서 게시된 의존 관계에 대한 **데이터 가져오기를 선택합니다.** **페더ation 메타데이터 주소(호스트 이름 또는 URL)** 값이 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 으로 설정됩니다. **다음** 을 클릭합니다.
7. 데이터 원본 **선택 페이지에서** 표시 이름을 입력합니다. Microsoft는 **365 Microsoft Office Platform WorldWide를 권장합니다.** **다음** 을 클릭합니다.
8. 지금 **다단계** 인증 구성을 **클릭하고,** 발행 권한 부여 규칙을 선택하고, 트러스트 페이지를 추가할 **준비를 클릭합니다.**
9. 완료 **페이지에서** **닫기를** 클릭합니다.

마법사를 닫는 경우 Office 365 서비스 eSTS에 대한 신뢰 파티 트러스트가 설정됩니다. 그러나 발행 변환 규칙은 설정하지 않습니다.

[AD FS 도움말을 사용하여](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 올바른 발행 변환 규칙을 생성할 수 있습니다. AD FS 도움말을 사용하여 생성된 클레임 규칙은 AD FS 관리 콘솔 또는 PowerShell을 통해 수동으로 추가할 수 있습니다. AD FS 도움말은 실행해야 하는 필요한 PowerShell 스크립트를 생성합니다.  

1. AD  FS에서 클레임 생성 도움말을 실행하고 스크립트 오른쪽  위에 있는 복사 옵션을 사용하여 PowerShell 클레임 변환 스크립트를 복사합니다.
2. 생성된 PowerShell을 다음에 붙여 넣을 수 있습니다.

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  완료된 스크립트를 실행합니다.
4.  두 개의 신뢰 파티 트러스트가 있는지 확인 하나는 전 세계에, 하나는 BF용입니다.
5.  다음 단계를 사용하여 [트러스트 백업.](#backup) **FFAndWorldwide 이름으로 저장합니다.**
6.  백end 마이그레이션을 완료하고 마이그레이션 프로세스 중에 AD FS가 계속 작동하는지 확인해야 합니다.

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS 재해 복구(WID 데이터베이스)

재해 AD FS 신속 복원 도구에서 [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) 팜을 복원하려면 활용해야 합니다. 따라서 도구를 다운로드해야 합니다. 마이그레이션을 시작하기 전에 백업을 만들어 안전하게 저장해야 합니다. 이 예제(TAT 환경)에서는 팜을 백업하기 위해 다음 명령을 실행했습니다.

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>AD FS 팜 백업

1. 주 AD FS 서버에 AD FS 신속 복원 도구를 설치합니다.
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

- [독일 Microsoft 클라우드에서 새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)
- [마이그레이션 중의 고객 환경](ms-cloud-germany-transition-experience.md)

전환을 통해 이동:

- [문장 작업 및 영향 마이그레이션](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경 및](ms-cloud-germany-transition-add-experience.md) [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](https://aka.ms/d365ceoptin)
- [Power BI 마이그레이션 프로그램 정보](https://aka.ms/pbioptin)
- [Microsoft Teams 업그레이드 시작하기](https://aka.ms/SkypeToTeams-Home)
