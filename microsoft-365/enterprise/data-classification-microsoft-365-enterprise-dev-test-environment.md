---
title: Microsoft 365 기업에 대 한 데이터 분류 테스트 환경
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 만들고 Microsoft 365 기업 테스트 환경에서 문서에 Office 365 레이블을 사용 합니다.
ms.openlocfilehash: 33ac1fa8e26c0037882e6c240cc04ec19e6a6a7b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870333"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 기업에 대 한 데이터 분류 테스트 환경

이 문서의 지침을과 함께 Microsoft 365 기업 테스트 환경에서 Office 365 보존 레이블을 사용 하 여 데이터 분류를 구성 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다

최소 요구 사항을 경량 방식으로 Office 365 레이블을 구성 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.
  
Office 365 레이블 시뮬레이션 된 엔터프라이즈에서 구성 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)에 대 한 지침을 따릅니다.
  
> [!NOTE]
> Office 365 레이블 테스트 하지 않아도 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공는 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다. 

## <a name="phase-2-create-office-365-labels"></a>2단계: Office 365 레이블 만들기

이 단계에서는 다양 한 수준의 SharePoint Online 문서 폴더에 대 한 보존에 대 한 레이블을 만듭니다.
  
1. 필요한 경우 인터넷 브라우저의 개인 인스턴스를 사용 하 고 전역 관리자 계정 사용 하 여 Office 포털에 로그인 합니다. 도움말을 보려면 [Office 365에 로그인 할 위치](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조 하십시오.
    
2. **Microsoft Office 홈** 탭에서 **관리** 타일을 클릭합니다.
    
3. 브라우저의 새 **Office 관리 센터** 탭에서 **관리 센터 > 보안 &amp; 준수**를 클릭합니다.
    
4. 새에서 **홈-보안 &amp; 준수** 탭 클릭 하 여 브라우저의 **분류 > 레이블**합니다. **홈 > 레이블** 창 **보존** 탭을 클릭 합니다.
    
5. **레이블 만들기**를 클릭 합니다.
    
6. **레이블 이름 지정** 창에서 **내부 공용**을 입력하고 **다음**을 클릭합니다.
    
7. **레이블 설정** 창에서 **다음**을 클릭합니다.
    
8. **설정 검토** 창에서 **이 레이블 만들기**, **닫기**를 차례로 클릭합니다.
    
9. 추가 레이블에 5-8단계를 반복합니다.
    
  - 개인
    
  - 중요
    
  - 극비
    
10. **홈 > 레이블 ** 창에서 **레이블 게시**를 클릭합니다.
    
11. **게시할 레이블 선택** 창에서 **게시할 레이블 선택**을 클릭합니다.
    
12. **레이블 선택** 창에서 **추가**를 클릭하고 네 개의 레이블을 모두 선택합니다.
    
13. **완료**를 클릭합니다.
    
14. **게시할 레이블 선택** 창에서 **다음**을 클릭합니다.
    
15. **위치 선택** 창에서 **다음**을 클릭합니다.
    
16. **정책 이름 지정** 창에서 **이름**에 **예제 조직**을 입력하고 **다음**을 클릭합니다.
    
17. **설정 검토** 창에서 **레이블 게시**, **닫기**를 차례로 클릭합니다.

메모를 게시할 수 있는 레이블에 대 한 몇 분정도 걸릴 수 있습니다.

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a>3 단계: Office 365 보존 레이블을 문서에 적용

이 단계에서 SharePoint Online 사이트의 문서 폴더의 파일에 대 한 기본 레이블 동작 찾아 수동으로 레이블 문서를 변경 합니다.

먼저, 민감한 수준 SharePoint Online 팀 사이트를 만듭니다.
  
1. 전역 관리자 계정을 사용 하 여 Office 포털에 로그인 브라우저를 사용 하 여 로컬 컴퓨터에서 하십시오. 도움말을 보려면 [Office 365에 로그인 할 위치](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조 하십시오.
    
2. 타일 목록에서 **SharePoint**를 클릭합니다.
    
3. 브라우저에서 새 **SharePoint** 탭에서 **사이트 만들기를**클릭 합니다.
    
4. **사이트 만들기** 페이지에서 **팀 사이트**를 클릭합니다.
    
5. **팀 사이트 이름** **SensitiveFiles**를 입력 합니다.
    
6. **팀 사이트 설명** **중요 한 파일에 대 한 SharePoint 사이트**를 입력 합니다.
    
7.  **개인 정보 설정**에서 **개인 - 구성원만 이 사이트에 액세스할 수 있음**을 선택하고 **다음**을 클릭합니다.
    
8. **누구를 추가하시겠습니까?** 창에서 **마침**을 클릭합니다.
    
다음으로 중요 한 레이블에 대 한 SensitiveFiles 팀 사이트의 문서 폴더를 구성 합니다.
  
1. 브라우저의 **SensitiveFiles** 탭에서 **문서**를 클릭 합니다.
    
2. 설정 아이콘을 클릭한 다음 **라이브러리 설정**을 클릭합니다.
    
3. **권한 및 관리** 아래에서 **Apply label to items in this library(이 라이브러리의 항목에 레이블 적용)** 을 클릭합니다.
    
4. **레이블 설정 적용**드롭다운 목록 상자에서 **중요 한** 선택 하 고 **저장**을 클릭 합니다.

다음으로 SensitiveFiles 사이트에 새 문서를 작성 하 고 해당 레이블을 변경 합니다.
    
1. 문서 폴더에서 클릭 **새로 만들기 > Word 문서**합니다.
    
2. 다음은 새 문서에 일부 텍스트를 입력 합니다. 텍스트를 저장할 때까지 기다립니다.
    
3. 메뉴 모음에서 **공유 문서**를 클릭 합니다.
    
4. **Document.docx** 파일 이름 옆에 있는 Word 아이콘을 클릭 합니다.
    
5. **속성** 섹션 **적용 보존 레이블**아래에서 오른쪽 창에서 문서 자동으로 적용 하는 **중요 한** 레이블 길었던는 note 합니다.
    
6. **모든 편집**을 클릭 합니다.
    
7. **Document.docx** 창의 **적용 레이블** **매우 기밀** 레이블 선택한 다음 **저장**을 클릭 합니다.

정보 및 프로덕션 환경에서 Office 365 보존 레이블에 대 한 링크에 대 한 **정보 보호** 단계에서 [사용자 환경에 대 한 구성 분류](infoprotect-configure-classification.md) 단계를 참조 하십시오.

## <a name="next-step"></a>다음 단계

추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능 및 기능 테스트 환경에서 살펴봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)

 