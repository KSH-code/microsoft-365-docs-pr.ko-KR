---
title: 역할 기반 액세스 제어에 대한 역할 만들기 및 관리
description: 역할 만들기 및 역할에 할당된 권한을 역할 기반 액세스 제어 구현의 일부로 Microsoft 365 Defender
keywords: 사용자 역할, 역할, rbac 액세스
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1f8ab38d3e224155fc6af311e7dde42410a07823
ms.sourcegitcommit: 4ea16de333421e24b15dd1f164963bc9678653fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "60009592"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a>역할 기반 액세스 제어에 대한 역할 만들기 및 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a>역할 만들기 및 역할 Azure Active Directory 할당

다음 단계에서는 2단계에서 역할을 만드는 방법을 Microsoft 365 Defender. 사용자 그룹에 대해 이미 Azure Active Directory 가정합니다.

1. 보안 [관리자](https://security.microsoft.com/) Microsoft 365 Defender 전역 관리자 역할이 할당된 계정을 사용하여 로그인합니다.

2. 탐색 창에서 **끝점 설정(사용 권한** 아래)를 \>  \>  **선택합니다.**

3. 항목 **추가를 선택합니다.**

4. 역할에 할당할 역할 이름, 설명 및 사용 권한을 입력합니다.

5. **다음을** 선택하여 Azure AD 보안 그룹에 역할을 할당합니다.

6. 필터를 사용하여 이 역할에 추가할 Azure AD 그룹을 선택합니다.

7. **를 저장하고 닫습니다.**

8. 구성 설정을 적용합니다.

> [!IMPORTANT]
> 역할을 만든 후 방금 만든 역할에 할당하여 장치 그룹을 만들고 장치 그룹에 대한 액세스를 제공해야 합니다.

### <a name="permission-options"></a>사용 권한 옵션

- **데이터 보기**
  - **보안 작업** - 포털의 모든 보안 작업 데이터 보기
  - **위협 및 취약성 관리** - 포털에서 위협 및 취약성 관리 데이터 보기

- **활성 수정 작업**
  - **보안 작업** - 대응 조치 수행, 보류 중인 수정 작업 승인 또는 해지, 자동화 및 표시기를 위한 허용/차단 목록 관리
  - **위협 및 취약성 관리 - 예외** 처리 - 새 예외 만들기 및 활성 예외 관리
  - **위협 및 취약성 관리 -** 수정 처리 - 새 수정 요청을 제출하고, 티켓을 만들고, 기존 수정 활동을 관리합니다.

- **경고 조사** - 경고 관리, 자동화된 조사 시작, 검사 실행, 조사 패키지 수집, 장치 태그 관리, PE(이식 가능한 실행 파일) 파일만 다운로드

- **포털 시스템** 설정 관리 - 저장소 설정, SIEM 및 위협 인텔리전스 API 설정 구성(전역적으로 적용), 고급 설정, 자동화된 파일 업로드, 역할 및 장치 그룹

    > [!NOTE]
    > 이 설정은 끝점 관리자용 Microsoft Defender(기본값) 역할에서만 사용할 수 있습니다.

- **보안 센터에서** 보안 설정 관리 - 경고 제거 설정 구성, 자동화에 대한 폴더 제외 관리, 온보드 및 오프보드 장치, 전자 메일 알림 관리, 평가 랩 관리

- **실시간 응답 기능**
  - **기본** 명령:
    - 라이브 응답 세션 시작
    - 원격 장치에서 읽기 전용 라이브 응답 명령 수행(파일 복사 및 실행 제외)
    - 라이브 응답을 통해 원격 장치에서 파일 다운로드
  - **고급** 명령:
    - 파일 페이지에서 PE 및 PE가 아닌 파일 다운로드
    - 업로드 장치에 파일 연결
    - 파일 라이브러리에서 스크립트 보기
    - 파일 라이브러리에서 원격 디바이스에서 스크립트 실행

사용 가능한 명령에 대한 자세한 내용은 Live 응답을 사용하여 [장치 조사를 참조하세요.](live-response.md)

## <a name="edit-roles"></a>역할 편집

1. 보안 관리자 또는 [Microsoft 365 Defender](https://security.microsoft.com/) 할당된 계정을 사용하여 로그인합니다.

2. 탐색 창에서 **끝점 설정(사용 권한** 아래)를 \>  \>  **선택합니다.**

3. 편집할 역할을 선택합니다.

4. **편집** 을 클릭합니다.

5. 역할에 할당된 그룹 또는 세부 정보를 수정합니다.

6. 저장을 **클릭하고 를 닫습니다.**

## <a name="delete-roles"></a>역할 삭제

1. 보안 관리자 또는 [Microsoft 365 Defender](https://security.microsoft.com/) 할당된 계정을 사용하여 로그인합니다.

2. 탐색 창에서 **끝점 설정(사용 권한** 아래)를 \>  \>  **선택합니다.**

3. 삭제할 역할을 선택합니다.

4. 드롭다운 단추를 클릭하고 역할 **삭제 를 선택합니다.**

## <a name="related-topic"></a>관련 항목

- [포털에 액세스하기 위한 사용자 기본 권한](basic-permissions.md)
- [장치 그룹 만들기 및 관리](machine-groups.md)
