---
title: 엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 데이터 분류
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 엔터프라이즈 테스트 환경용 Microsoft 365의 문서에 보존 레이블을 만들고 사용 합니다.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487735"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 데이터 분류

*이 테스트 랩 가이드는 enterprise 및 Office 365 Enterprise 테스트 환경용 Microsoft 365에 모두 사용할 수 있습니다.*

이 문서에서는 엔터프라이즈 테스트 환경용 Microsoft 365의 보존 레이블을 사용 하 여 데이터 분류를 구성 하는 방법을 설명 합니다.

테스트 환경에서 데이터를 분류 하려면 다음 세 단계를 수행 해야 합니다.
- [1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2 단계: 보존 레이블 만들기](#phase-2-create-retention-labels)
- [3 단계: 문서에 보존 레이블 적용](#phase-3-apply-retention-labels-to-documents)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축

최소 요구 사항에 따라 간단한 방법으로 보존 레이블을 구성 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 보존 레이블을 구성 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.
  
> [!NOTE]
> 테스트 보존 레이블에서는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다. 자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트해 볼 수 있도록 여기에서 옵션으로 제공 됩니다.

## <a name="phase-2-create-retention-labels"></a>2 단계: 보존 레이블 만들기

이 단계에서는 SharePoint Online 문서 폴더에 대해 서로 다른 보존 수준에 대 한 보존 레이블을 만듭니다.

1. 전역 관리자 계정을 사용 하 여 [Microsoft 365 보안 센터](https://security.microsoft.com/homepage) 에 로그인 합니다.
1. 브라우저의 **집-Microsoft 365 보안** 탭에서 **분류**  >  **보존 레이블을**선택 합니다.
1. **레이블 만들기**를 선택합니다.
1. **레이블 이름** 지정 창에서 **레이블 이름**에 **내부 공용** 을 입력 하 고 **다음**을 선택 합니다.
1. **파일 계획 설명자** 창에서 **다음**을 선택 합니다.
1. 필요한 경우 **레이블 설정** 창에서 **보존** 을 **On**으로 설정 하 고 **다음**을 선택 합니다.
1. **설정 검토** 창에서 **레이블 만들기**를 선택 합니다.
1. 아래 이름의 추가 레이블에 대해 3~7단계를 반복합니다.
  - 개인
  - 중요
  - 극비
1. **보존 레이블** 창에서 **레이블 게시**를 선택 합니다.
1. **게시할 레이블 선택** 창에서 **게시할 레이블 선택을**선택 합니다.
1. **레이블 선택** 창에서 **추가** 를 선택 하 고 네 개의 레이블을 모두 선택 합니다.
1. **추가**를 선택한 다음 **완료**를 선택 합니다.
1. **게시할 레이블 선택** 창에서 **다음**을 선택 합니다.
1. **위치 선택** 창에서 **다음**을 선택 합니다.
1. **정책 이름** 설정 창에서 **이름**에 **예제 조직을** 입력 하 고 **다음**을 선택 합니다.
1. **설정 검토** 창에서 **레이블 게시**를 선택 합니다.
 
보존 레이블을 게시 하는 데 몇 분 정도 걸릴 수 있습니다.

## <a name="phase-3-apply-retention-labels-to-documents"></a>3 단계: 문서에 보존 레이블 적용

이 단계에서는 SharePoint Online 사이트의 문서 폴더에 있는 파일에 대 한 기본 보존 레이블 동작을 검색 하 고 문서의 보존 레이블을 수동으로 변경 합니다.

먼저 중요 한 수준의 SharePoint Online 팀 사이트를 만듭니다.
  
1. 브라우저의 개인 인스턴스를 사용 하 여 전역 관리자 계정을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.
1. 타일 목록에서 **SharePoint**를 선택 합니다.
1. 브라우저의 새 **SharePoint** 탭에서 **사이트 만들기**를 선택 합니다.
1. **사이트 만들기** 페이지에서 **팀 사이트**를 선택 합니다.
1. **팀 사이트 이름** 상자에 **SensitiveFiles**를 입력 합니다.
1. **팀 사이트 설명** 상자에 **중요 한 파일에 대 한 SharePoint 사이트**를 입력 합니다.
1. **개인 정보 설정**에서 **비공개-구성원만이 사이트에 액세스할 수 있습니다**.를 선택 하 고 **다음**을 선택 합니다.
1. **어떤 사용자를 추가** 하 시겠습니까? 창에서 **마침을**선택 합니다.
    
그런 다음 SensitiveFiles 팀 사이트의 문서 폴더를 구성 하 여 중요 한 보존 레이블을 지정 합니다.
  
1. 브라우저의 **SensitiveFiles** 탭에서 **문서**를 선택 합니다.
1. **설정** 아이콘을 선택한 다음 **라이브러리 설정을**선택 합니다.
1. **사용 권한 및 관리**에서 **이 목록 또는 라이브러리의 항목에 레이블 적용**을 선택 합니다. 이 옵션이 표시 되지 않으면 보존 레이블이 아직 게시 되지 않은 것입니다. 나중에이 단계를 시도 하세요.
1. **설정-레이블 적용**에서 드롭다운 상자에서 **중요** 를 선택 하 고 **저장**을 선택 합니다.

다음으로, SensitiveFiles 사이트에서 새 문서를 만들고 해당 보존 레이블을 변경 합니다.
    
1. 문서 폴더에서 **새**  >  **Word 문서**를 선택 합니다.
1. 빈 문서에 텍스트를 입력 합니다. 텍스트가 저장 될 때까지 기다립니다.
1. 메뉴 모음에서 **공유 문서**를 선택 합니다.
1. **Document.docx** 파일 이름 옆에 있는 세로 줄임표 (...)를 선택 하 고 **세부 정보**를 선택 합니다.
1. 오른쪽 창의 **속성** 섹션에 있는 **보존 레이블 적용**에서 문서에 **중요 한** 보존 레이블이 자동으로 적용 되어 있는지 확인 합니다.
1. **모두 편집**을 클릭 합니다.
1. **Document.docx** 창의 **보존 레이블 적용**에서 **높은 기밀** 레이블을 선택한 다음 **저장**을 선택 합니다.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능에 대해 알아봅니다.

## <a name="see-also"></a>참고 항목

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[엔터프라이즈 설명서에 대 한 Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
