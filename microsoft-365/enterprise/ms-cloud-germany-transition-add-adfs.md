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
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft 클라우드 독일의 마이그레이션에 대 한 AD FS 마이그레이션 단계

Microsoft Cloud 독일에서 AD FS (Active Directory Federation Services) 팜을 마이그레이션하려면 다음을 수행 합니다.

1. [다음 단계를 수행](#backup)하 여 FF 신뢰 정보를 포함 하는 AD FS 설정을 백업 합니다. Microsoft **cloud Deutschland_Only** 백업 이름을 지정 하 여 Microsoft cloud 독일 테 넌 트 정보만 포함 하도록 합니다.
2. Microsoft 클라우드 Deutschland_Only 백업을 사용 하 여 복원을 테스트 하 여 AD FS 팜이 Microsoft 클라우드 독일만 계속 작동 해야 합니다.
3. **AD FS에서 Office 365 서비스를 >** 여 새 신뢰 당사자 트러스트를 만듭니다.
4. AD FS 관리 콘솔의 **신뢰 당사자 트러스트** 에서 **신뢰 당사자 트러스트 추가** 를 선택 합니다.
5. 신뢰 당사자 트러스트 추가 마법사의 **시작** 페이지에서 **다음** 을 선택 합니다.
6. **데이터 원본 선택** 페이지에서 **온라인으로 또는 로컬 네트워크에 게시 된 신뢰 당사자에 대 한 데이터 가져오기를** 선택 합니다. **페더레이션 메타 데이터 주소 (호스트 이름 또는 URL)** 값이로 설정 됩니다 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . **다음** 을 클릭합니다.
7. **데이터 원본 선택** 페이지에서 표시 이름을 입력 합니다. Microsoft **Office 365 Id 플랫폼을 전 세계** 에서 권장 합니다. **다음** 을 클릭합니다.
8. **Multi-factor Authentication 구성** 에서 **다음** 을 클릭 하 고 **발급 권한 부여 규칙을 선택한** 다음 신뢰 페이지 **를 추가할 준비** 를 합니다.
9. **마침** 페이지에서 **닫기를** 클릭 합니다.

마법사를 닫으면 Office 365 서비스 eSTS에 대 한 신뢰 당사자 트러스트가 설정 됩니다. 그러나 발급 변환 규칙은 설정 되지 않습니다.

[AD FS 도움말](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 을 사용 하 여 올바른 발급 변환 규칙을 생성할 수 있습니다. AD FS 도움말을 사용 하 여 만든 생성 된 클레임 규칙은 AD FS 관리 콘솔 또는 PowerShell을 통해 수동으로 추가할 수 있습니다. AD FS 도움말에서는 실행 해야 하는 필수 PowerShell 스크립트를 생성 합니다.  

1. AD FS 도움말에서 **클레임 생성** 을 실행 하 고 스크립트 오른쪽 위 모서리에 있는 **복사** 옵션을 사용 하 여 PowerShell 클레임 변환 스크립트를 복사 합니다.
2. 다음에 생성 된 PowerShell을 붙여 넣습니다.

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  완성 된 스크립트를 실행 합니다.
4.  두 신뢰 당사자 트러스트가 존재 하는지 확인 합니다. 전 세계 및 BF 용 1 개
5.  [이러한 단계](#backup)를 사용 하 여 트러스트를 백업 합니다. 이 파일을 **Ffandworldwide** 에 저장 합니다.
6.  백 엔드 마이그레이션을 완료 하 고 마이그레이션 프로세스 동안 AD FS가 여전히 작동 하는지 확인 합니다.

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS 재해 복구 (WID 데이터베이스)

재해 Ad FS에서 AD FS 팜을 복원 하려면 [빠른 복원 도구](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) 를 활용 해야 합니다. 따라서이 도구를 다운로드 하 고 마이그레이션을 시작 하기 전에 백업을 만들고 안전 하 게 저장 해야 합니다. 이 예제 (환경에서 TAT)에서는 다음 명령을 실행 하 여 팜을 백업 합니다.

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>AD FS 팜 백업

1. 기본 AD FS 서버에 AD FS 빠른 복원 도구를 설치 합니다.
2. 이 명령을 사용 하 여 PowerShell 세션에서 모듈을 가져옵니다.

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. 백업 명령을 실행 합니다.

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. 백업을 원하는 대상에 안전 하 게 저장 합니다. 

### <a name="restore-an-ad-fs-farm"></a>AD FS 팜 복원

팜이 완전히 실패 하 고 이전 팜으로 돌아갈 방법이 없는 경우 다음을 수행 합니다. 

1. 이전에 생성 및 저장 된 백업을 새 기본 AD FS 서버로 이동 합니다.
2. 다음 `Restore-ADFS` PowerShell 명령을 실행 합니다. 필요한 경우 사전에 AD FS SSL 인증서를 가져옵니다.

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. 새 DNS 레코드 또는 부하 분산 장치를 새 AD FS 서버에 가리킵니다.

## <a name="more-information"></a>추가 정보

시작 하기:

- [Microsoft Cloud 독일에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)
- [마이그레이션 중의 고객 환경](ms-cloud-germany-transition-experience.md)

전환을 통해 이동 하는 경우:

- [마이그레이션 단계 작업 및 영향](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [서비스](ms-cloud-germany-transition-add-general.md), [장치](ms-cloud-germany-transition-add-devices.md), [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS](ms-cloud-germany-transition-add-adfs.md)에 대 한 추가 정보

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](https://aka.ms/d365ceoptin)
- [Power BI 마이그레이션 프로그램 정보](https://aka.ms/pbioptin)
- [Microsoft Teams 업그레이드 시작하기](https://aka.ms/SkypeToTeams-Home)
