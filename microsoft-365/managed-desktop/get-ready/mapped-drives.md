---
title: Microsoft Managed Desktop의 매핑된 드라이브 준비
description: 사용자가 매핑된 드라이브의 데이터에 액세스할 수 있도록 하는 중요한 단계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d272c08287dd6198d4c33b4d1df3ff8662eda12781d676b75c93189d08409de7
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53819094"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 매핑된 드라이브 준비

대부분의 엔터프라이즈 환경에는 매핑된 드라이브에 대한 레거시 요구 사항이 있습니다. 이러한 요구 사항은 사용자 또는 팀이 파일을 공유하고 저장할 수 있도록 허용하거나, 또는 사내 응용 프로그램용입니다. Microsoft는 매핑된 드라이브와 함께 매핑된 드라이브를 사용하지 Microsoft Managed Desktop. 대신 다음과 같이 파일 액세스 솔루션을 최신화하는 것이 좋습니다.
  
- 개별 사용자가 사용하는 매핑된 드라이브를 마이그레이션하여 비즈니스용 OneDrive. 
- 팀에서 파일을 공유하는 데 사용하는 매핑된 드라이브를 온라인 SharePoint 마이그레이션합니다. 
- 해당 요구 사항을 제거하기 위해 사내 파일 공유를 사용하는 응용 프로그램을 최신화하거나 대체합니다.
  
이러한 서비스를 현대화하면 사용자 환경을 가장 잘 사용할 수 Microsoft Managed Desktop. Microsoft FastTrack 서비스는 Microsoft 클라우드 서비스를 사용하여 환경을 현대화하는 데 도움을 줍니다. 적합한 서비스 및 계획에서 FastTrack 서비스를 [](/fasttrack/m365-eligible-services-and-plans) 사용할 자격이 있는지 확인한 다음 직접 연락하여 서비스 준비를 Microsoft Managed Desktop. FastTrack 비즈니스용 OneDrive 또는 SharePoint 마이그레이션에 대한 배경 내용은 [데이터 마이그레이션을 참조하세요.](/fasttrack/o365-data-migration)

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>드라이브의 매핑된 Microsoft Managed Desktop
 
일부 사용 사례에 대해 매핑된 드라이브를 제거하거나 교체할 수 없는 경우 Microsoft Managed Desktop 관리 포털에서 지원 요청을 제출하여 Microsoft Managed Desktop 합니다.
    
이러한 요청의 경우 지원 요청에 다음 세부 정보를 제공해야 합니다. 

- Microsoft Managed Desktop 위해 매핑해야 하는 파일 공유 위치에 대한 모든 UNC 경로 
- 이러한 파일 공유 위치에 액세스해야 하는 사용자 그룹 
- 할당해야 하는 특정 드라이브 문자(필요한 경우)

예를 들어 다음과 같은 가치를 제공해야 합니다.

| 드라이브 문자 | UNC 경로 | 사용자 그룹 |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

사용자 및 그룹이 파일 공유 위치에 액세스하기 위한 올바른 권한을 가지고 유지 관리하고, 액세스 가능한 상태로 유지 관리하고, 사내 파일 서비스에 계속 액세스할 수 있도록 하는 것은 전적으로 사용자의 책임입니다. 또한 이러한 파일 공유에 대한 요구 사항을 최대한 빨리 제거해야 합니다.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>매핑된 드라이브를 배포할 수 Microsoft Managed Desktop
 
매핑된 드라이브를 피할 수 없는지와 서비스 요청을 제출하기 전에 요구 사항을 신중하게 검토해야 합니다. 그런 다음 다음 단계를 수행합니다.

1. 서비스 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) "문제 해결 + 지원"을 선택한 다음 Microsoft Managed Desktop 섹션에서 "서비스 요청"을 검색합니다.  
2. "매핑된 드라이브 배포"라는 지원 요청을 제출하고 필요한 모든 파일 공유 세부 정보를 제공합니다.  
3. Microsoft Managed Desktop IT 운영은 요청이 완료되면 지원 요청 업데이트를 사용하여 이를 권고합니다. 처음에 이 구성은 테스트 배포 그룹의 장치에만 배포됩니다.  
4. IT 작업에서 배포한 구성이 예상한 Microsoft Managed Desktop 테스트하고 확인해야 합니다. 테스트를 완료한 후 동일한 지원 요청의 세부 정보에서 Microsoft Managed Desktop IT 작업에게 알릴 수 있습니다.  
5. Microsoft Managed Desktop IT 운영 팀은 구성을 다른 배포 그룹에 배포합니다. 

## <a name="steps-to-get-ready"></a>준비 단계

1. 에 대한 [선행 Microsoft Managed Desktop.](prerequisites.md)
2. [준비 평가 도구를 사용합니다.](readiness-assessment-tool.md)
3. [게스트 계정에 대한 필수 구성 요소](guest-accounts.md)
4. [Microsoft Managed Desktop의 네트워크 구성](network.md)
5. [Microsoft Managed Desktop 인증서 및 네트워크 프로필 준비](certs-wifi-lan.md)
6. [Microsoft Managed Desktop의 온-프레미스 리소스 액세스 준비](authentication.md)
7. [Microsoft Managed Desktop의 앱](apps.md)
8. [매핑된 드라이브에서 Microsoft Managed Desktop](mapped-drives.md) 준비(이 문서)
9. [Microsoft Managed Desktop의 인쇄 리소스 준비](printing.md)
