---
title: Microsoft 365 Enterprise 테스트 환경에 대 한 데이터 분류
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 Microsoft 365 Enterprise 테스트 환경의 문서에 대해 Office 365 보존 레이블을 만들고 사용 합니다.
ms.openlocfilehash: 66e06f9a89b102c131bc29af17c4564fabbab9b4
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072418"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise 테스트 환경에 대 한 데이터 분류

이 문서의 지침을 사용 하 여 Microsoft 365 Enterprise 테스트 환경에서 Office 365 보존 레이블을 사용 하 여 데이터 분류를 구성 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경 구축

최소 요구 사항을 사용 하 여 간단한 방법으로 Office 365 보존 레이블을 구성 하려면 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따르세요.
  
시뮬레이트된 엔터프라이즈에서 Office 365 보존 레이블을 구성 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.
  
> [!NOTE]
> Office 365 보존 레이블 테스트에는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다. 이 기능은 자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다. 

## <a name="phase-2-create-office-365-retention-labels"></a>2 단계: Office 365 보존 레이블 만들기

이 단계에서는 SharePoint Online 문서 폴더에 대 한 여러 보존 수준에 대 한 보존 레이블을 만듭니다.

1. 전역 관리자 계정을 사용하여 [Microsoft 365 규정 준수 포털](https://compliance.microsoft.com)에 로그인합니다.
    
2. 브라우저의 **홈 - Microsoft 365 규정 준수** 탭에서 **분류 > 레이블**을 차례로 클릭합니다.
    
3. **보존 레이블 > 레이블 만들기**를 클릭합니다.
    
4. **레이블 이름 지정** 창에서 **레이블 이름 지정**에 **내부 공용**을 입력하고 **다음**을 클릭합니다.

5. **파일 플랜 설명자** 창에서 **다음**을 클릭합니다.
    
6. 필요에 따라 **레이블 설정** 창에서 **보존**을 **켜기**로 설정하고 **다음**을 클릭합니다.
    
7. **설정 검토** 창에서 **레이블 만들기**를 클릭합니다.
    
8. 아래 이름의 추가 레이블에 대해 3~7단계를 반복합니다.
    
  - 개인
    
  - 중요
    
  - 극비
  
9. **홈 > 레이블 ** 창에서 **레이블 게시**를 클릭합니다.
    
10. **게시할 레이블 선택** 창에서 **게시할 레이블 선택**을 클릭합니다.
    
11. **레이블 선택** 창에서 **추가**를 클릭하고 네 개의 레이블을 모두 선택합니다.
    
12. **완료**를 클릭합니다.
    
13. **게시할 레이블 선택** 창에서 **다음**을 클릭합니다.
    
14. **위치 선택** 창에서 **다음**을 클릭합니다.
    
15. **정책 이름 지정** 창에서 **이름**에 **예제 조직**을 입력하고 **다음**을 클릭합니다.
    
16. **설정 검토** 창에서 **레이블 게시**, **닫기**를 차례로 클릭합니다.
 
보존 레이블을 게시 하는 데 몇 분 정도 걸릴 수 있습니다.

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a>3 단계: 문서에 Office 365 보존 레이블을 적용 합니다.

이 단계에서는 SharePoint Online 사이트의 문서 폴더에 있는 파일에 대 한 기본 보존 레이블 동작을 검색 하 고 문서의 보존 레이블을 수동으로 변경 합니다.

먼저 중요 한 수준의 SharePoint Online 팀 사이트를 만듭니다.
  
1. 로컬 컴퓨터에서 브라우저를 사용하여 전역 관리자 계정으로 [Office 365 포털](https://portal.office.com)에 로그인합니다.
    
2. 타일 목록에서 **SharePoint**를 클릭합니다.
    
3. 브라우저의 새 **SharePoint** 탭에서 **사이트 만들기**를 클릭 합니다.
    
4. **사이트 만들기** 페이지에서 **팀 사이트**를 클릭합니다.
    
5. **팀 사이트 이름**에 **SensitiveFiles**을 입력 합니다.
    
6. **팀 사이트 설명**에서 **중요 한 파일에 대 한 SharePoint 사이트**를 입력 합니다.
    
7.  **개인 정보 설정**에서 **비공개 – 구성원만 이 사이트에 액세스할 수 있습니다.** 를 선택하고 **다음**을 클릭합니다.
    
8. **어떤 사람을 추가하시겠습니까?** 창에서 **마침**을 클릭합니다.
    
그런 다음 SensitiveFiles 팀 사이트의 문서 폴더를 구성 하 여 중요 한 보존 레이블을 지정 합니다.
  
1. 브라우저의 **SensitiveFiles** 탭에서 **문서**를 클릭 합니다.
    
2. 설정 아이콘을 클릭한 다음, **라이브러리 설정**을 클릭합니다.
    
3. **권한 및 관리** 아래에서 **이 라이브러리의 항목에 레이블 적용**을 클릭합니다.
    
4. **설정-레이블 적용**에서 드롭다운 상자에서 **중요** 를 선택 하 고 **저장**을 클릭 합니다.

다음으로, SensitiveFiles 사이트에서 새 문서를 만들고 해당 보존 레이블을 변경 합니다.
    
1. 문서 폴더에서 **새 _GT_ Word 문서**를 클릭 합니다.
    
2. 빈 문서에 텍스트를 입력 합니다. 텍스트가 저장 될 때까지 기다립니다.
    
3. 메뉴 모음에서 **공유 문서**를 클릭 합니다.
    
4. **문서 .docx** 파일 이름 옆에 있는 Word 아이콘을 클릭 합니다.
    
5. 오른쪽 창의 **속성** 섹션에 있는 **보존 레이블 적용**에서 문서에 **중요 한** 레이블이 자동으로 적용 되었는지 확인 합니다.
    
6. **모두 편집**을 클릭 합니다.
    
7. **문서 .docx** 창의 **레이블 적용**에서 **높은 기밀** 레이블을 선택 하 고 **저장**을 클릭 합니다.

프로덕션 환경에서 Office 365 보존 레이블을 배포 하는 방법에 대 한 자세한 내용과 정보는 **정보 보호** 단계에서 작업 [환경의 분류 구성](infoprotect-configure-classification.md) 단계를 참조 하세요.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능에 대해 알아봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)

 