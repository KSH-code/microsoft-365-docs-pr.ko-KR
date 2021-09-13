---
title: Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 사용
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 사용 방법을 배워서 미사용 데이터를 스캔하고 온-프레미스 파일 공유와 온-프레미스 SharePoint 폴더와 문서 라이브러리에 대한 보호 조치를 시행하세요.
ms.openlocfilehash: 3d7c2e30092eee022fc0ed2a7ef6a8be7b82e3f1
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192962"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner"></a>Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 사용하기

DLP 온-프레미스 기능과 해당 기능이 DLP 정책에 나오는 방법에 대한 자세한 내용은 다음 몇 가지 시나리오를 참조하세요.

> [!IMPORTANT]
> 이 DLP 온-프레미스 시나리오는 DLP 정책을 만들고 조정하는 공식 절차가 아닙니다. 일반적으로 DLP 정책을 사용해야 하는 경우 다음 항목을 참조하세요.
>
> - [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)
> - [기본 DLP 정책을 사용하여 시작](get-started-with-the-default-dlp-policy.md)
> - [템플릿에서 DLP 정책 만들기](create-a-dlp-policy-from-a-template.md)
> - [DLP 정책 만들기, 테스트 및 조정](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a>시나리오: DLP 규칙에 일치하는 파일 발견

DLP 온-프레미스 스캐너의 데이터는 다양한 영역에서 나타납니다

#### <a name="activity-explorer"></a>활동 탐색기

 온-프레미스용 Microsoft DLP는 DLP 규칙 일치 항목을 감지하고 이를 [활동 탐색기](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer)에 보고합니다.

#### <a name="microsoft-365-audit-log"></a>Microsoft 365 감사 로그

DLP 규칙 일치 항목은 감사 로그 UI에서 확인할 수 있으며, [규정 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)에서 보거나 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell으로 액세스할 수 있습니다.

#### <a name="aip"></a>AIP

검색 데이터는 csv 형식의 로컬 보고서에서 확인할 수 있으며, 저장 위치는

**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report** 입니다.

 다음 열 레이블을 찾으세요.

- DLP 모드
- DLP 상태
- DLP 메모
- DLP 규칙 이름
- DLP 작업
- 소유자
- 현재 NTFS 사용 권한(SDDL)
- 적용된 NTFS 사용 권한(SDDL)
- NTFS 사용 권한 유형

### <a name="scenario-enforce-dlp-rule"></a>시나리오: DLP 규칙 적용

DLP 규칙을 스캔된 파일에 적용하려면, 적용이 DLP의 AIP와 정책 수준에서의 콘텐츠 스캔 작업이 둘 다 활성화되어 있어야 합니다.

#### <a name="configure-dlp-to-enforce-policy-actions"></a>정책 작업을 적용하기 위한 DLP 구성

1. [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 열고 AIP에서 사용자가 구성한 온-프레미스 위치 리포지토리를 대상으로 하는 DLP 정책을 선택합니다.
2. 정책을 편집합니다.
3. **정책 테스트 또는 켜기** 페이지에서 **지금 정책 켜기** 를 선택합니다.

## <a name="see-also"></a>참고 항목

- [DLP 온-프레미스 스캐너에 대한 자세한 정보](dlp-on-premises-scanner-learn.md)
- [DLP 온-프레미스 스캐너 시작하기](dlp-on-premises-scanner-get-started.md)
- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)
- [DLP 정책 만들기, 테스트 및 조정](create-test-tune-dlp-policy.md)
- [활동 탐색기 시작하기](data-classification-activity-explorer.md)
