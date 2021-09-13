---
title: 엔터프라이즈 테스트 환경에 Microsoft 365 데이터 분류
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom:
- Ent_TLGs
- admindeeplinkMAC
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용하여 엔터프라이즈 테스트 환경용 웹 응용 Microsoft 365 보존 레이블을 만들고 사용할 수 있습니다.
ms.openlocfilehash: a39661da9436473da9e89330ff15d0a43d19db51
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218585"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>엔터프라이즈 테스트 환경에 Microsoft 365 데이터 분류

*이 테스트 랩 가이드는 엔터프라이즈 및 엔터프라이즈용 Microsoft 365 둘 다에 사용할 Office 365 Enterprise 있습니다.*

이 문서에서는 엔터프라이즈 테스트 환경의 사용자 지정 환경에서 보존 레이블을 Microsoft 365 방법을 설명합니다.

테스트 환경에서 데이터를 분류하는 데는 다음 세 단계가 있습니다.
- [1단계: 엔터프라이즈 테스트 Microsoft 365 사용자 환경 구축](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2단계: 보존 레이블 만들기](#phase-2-create-retention-labels)
- [3단계: 문서에 보존 레이블 적용](#phase-3-apply-retention-labels-to-documents)

![Microsoft 클라우드용 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 엔터프라이즈용 테스트 랩 가이드 스택의 Microsoft 365 모든 문서에 대한 시각적 맵을 확인한 다음 엔터프라이즈 테스트 랩 Microsoft 365 스택에 대한 자세한 [설명을 참조하세요.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1단계: 엔터프라이즈 테스트 Microsoft 365 사용자 환경 구축

최소 요구 사항과 함께 경량 방식으로 보존 레이블을 구성하려면 Lightweight [base configuration의 지침을 따릅니다.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
시뮬레이트된 엔터프라이즈에서 보존 레이블을 구성하려는 경우 통과 [인증의 지침을 따릅니다.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> 보존 레이블을 테스트하는 데는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다. 여기에는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스) 포리스트에 대한 디렉터리 동기화가 포함됩니다. 여기서는 옵션으로 제공되어 자동화된 라이선싱 및 그룹 멤버 자격을 테스트하고 일반적인 조직을 나타내는 환경에서 실험해 볼 수 있습니다.

## <a name="phase-2-create-retention-labels"></a>2단계: 보존 레이블 만들기

이 단계에서는 SharePoint Online 문서 폴더의 다양한 보존 수준에 대한 보존 레이블을 생성합니다.

1. 전역 관리자 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">계정으로</a> Microsoft 365 보안 센터에 로그인합니다.
1. 브라우저의 **홈 - Microsoft 365** 보안 탭에서 분류 보존  >  **레이블 을 선택합니다.**
1. **레이블 만들기** 를 선택합니다.
1. 레이블 **이름 지정 창에서** 레이블 이름 **지정에** 내부 공용을 **입력하고** 다음 을 **선택합니다.**
1. 파일 **계획 설명자 창에서** 다음 을 **선택합니다.**
1. 필요한 **경우 레이블 설정** 창에서 **보존을** **으로** 설정하고 다음 을 **선택합니다.**
1. 설정 **검토 창에서** 레이블 **만들기 를 선택합니다.**
1. 아래 이름의 추가 레이블에 대해 3~7단계를 반복합니다.
  - 개인
  - 중요
  - 극비
1. 보존 **레이블 창에서** 레이블 **게시를 선택합니다.**
1. 게시할 레이블 선택 **창에서** 게시할 레이블 **선택을 선택합니다.**
1. 레이블 **선택 창에서** 추가를  선택하고 4개의 레이블을 모두 선택합니다.
1. 추가 **를** 선택한 다음 완료 를 **선택합니다.**
1. 게시할 **레이블 선택 창에서** 다음 을 **선택합니다.**
1. 위치 **선택 창에서** 다음 을 **선택합니다.**
1. 정책 **이름 지정 창에서** 이름에 예제 **조직을** **입력하고** 다음 을 **선택합니다.**
1. 설정 **검토 창에서** 레이블 **게시를 선택합니다.**
 
보존 레이블을 게시하는 데 몇 분 정도 걸릴 수 있습니다.

## <a name="phase-3-apply-retention-labels-to-documents"></a>3단계: 문서에 보존 레이블 적용

이 단계에서는 SharePoint Online 사이트의 문서 폴더에 있는 파일에 대한 기본 보존 레이블 동작을 검색하고 문서의 보존 레이블을 수동으로 변경합니다.

먼저 온라인 팀 SharePoint 중요한 수준으로 만들어야 합니다.
  
1. 브라우저의 개인 인스턴스를 사용하여 전역 관리자 계정을 [Microsoft 365 관리 센터](https://admin.microsoft.com) 로그인합니다.
1. 타일 목록에서 를 **SharePoint.**
1. 브라우저의 **새** SharePoint 탭에서 사이트 **만들기 를 선택합니다.**
1. 사이트 **만들기 페이지에서** 팀 사이트를 **선택합니다.**
1. 팀 **사이트 이름 상자에** **SensitiveFiles 를 입력합니다.**
1. 팀 **사이트 설명 상자에** 중요한 **SharePoint 사이트를 입력합니다.**
1. 개인 **정보 설정 에서** 비공개 - 구성원만 이 사이트에 액세스할 수 **있습니다.를 선택하고** 다음 을 **선택합니다.**
1. In the **Who do you want to add? pane,** select **Finish**.
    
그런 다음 중요한 보존 레이블에 대해 SensitiveFiles 팀 사이트의 문서 폴더를 구성합니다.
  
1. 브라우저의 **SensitiveFiles** 탭에서 문서를 **선택합니다.**
1. 선택 **설정** 선택한 다음 라이브러리 설정 **을 선택합니다.**
1. 사용 **권한 및 관리에서** 이 목록 또는 라이브러리의 항목에 레이블 **적용을 선택합니다.** 이 옵션이 나타나지 않는 경우 보존 레이블이 아직 게시되지 않습니다. 나중에 이 단계를 시도해 보아야 합니다.
1. 레이블 **설정 적용의** 드롭다운  상자에서 중요를 선택한 다음 저장을 **선택합니다.**

그런 다음 SensitiveFiles 사이트에서 새 문서를 만들고 보존 레이블을 변경합니다.
    
1. 문서 폴더에서 새   >  **Word 문서를 선택합니다.**
1. 빈 문서에 텍스트를 입력합니다. 텍스트가 저장될 때까지 기다렸다가
1. 메뉴 표시줄에서 공유 **문서를 선택합니다.**
1. 파일 **Document.docx** 옆에 있는 세로 타원을 선택한 다음 세부 정보 를 **선택합니다.**
1. 오른쪽 창의 속성 **섹션에** 있는 보존 레이블 적용에서 문서에 중요한  보존 레이블이 자동으로 적용되어 있습니다.
1. 모두 **편집을 클릭합니다.**
1. 다음 **Document.docx** 창의 보존 레이블 **적용에서** 높은  기밀 레이블을 선택한 다음 저장을 **선택합니다.**

## <a name="next-step"></a>다음 단계

테스트 환경의 추가 [정보](m365-enterprise-test-lab-guides.md#information-protection) 보호 기능을 살펴보아야 합니다.

## <a name="see-also"></a>참고 항목

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[기업용 Microsoft 365 설명서](/microsoft-365-enterprise/)