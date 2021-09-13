---
title: 개인 정보 관리에서 사용자 권한 설정 및 역할 할당(미리 보기)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: 개인 정보 관리 권한을 설정하고 사용자를 역할 그룹에 할당하는 방법을 배워야 합니다.
ms.openlocfilehash: 6caf786a99e08c2f5c6abfd4c2dbabc438151d06
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216595"
---
# <a name="set-user-permissions-and-assign-roles-in-privacy-management-preview"></a>개인 정보 관리에서 사용자 권한 설정 및 역할 할당(미리 보기)

조직의 구성원에게 개인 정보 관리를 사용할 수 있는 권한을 부여하려면 조직의 해당 역할 그룹에 Microsoft 365 규정 준수 센터. 개인 정보 관리와 관련한 역할은 개인 정보 보호 정책에 Azure Active Directory.

## <a name="sign-in-and-set-permissions"></a>로그인 및 사용 권한 설정

1. 이동하여 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/) **탐색에서** 사용 권한을 선택합니다.  
2. 준수 센터 **드롭다운에서** 역할을 **선택합니다.** 역할 그룹의 전체 목록이 표시됩니다.
3. 하나 이상의 사용자를 추가할 역할 그룹을 찾고 그룹 이름 왼쪽에 있는 확인란을 선택합니다. 개인 정보 관리 역할 목록은 아래를 참조하세요.  
4. 해당 그룹의 플라이아웃 창에서  구성원 헤더에서 **편집을** 선택합니다.  
5. 구성원 **선택 을 선택합니다.** 다른 플라이아웃 창이 나타납니다.
6. **+ 추가를 선택하여** 그룹에 추가할 사용자를 하나 이상 선택합니다.  
7. 추가할 이름 옆의 확인란을 선택한 다음 아래쪽의 추가 단추를 선택합니다.   
8. 사용자 할당을 완료했면 **완료,** **저장,** 닫기 를 **선택합니다.**

## <a name="role-groups-and-roles"></a>역할 그룹 및 역할

수행해야 하는 작업과 적절한 파일 액세스 수준에 따라 구성원을 역할 그룹에 할당해야 합니다. 각 역할 그룹에는 하나 이상의 역할이 포함됩니다. 이러한 역할은 특정 개인 정보 관리 작업 또는 해당 그룹의 구성원에 대해 사용 또는 제한되는 주요 기능과 관련이 있을 수 있습니다.  

필요한 경우 역할 그룹을 사용자 정의할 수 있습니다. 실수로 액세스가 손실되는 것을 방지하기 위해 사용자 지정하고자 하는 기존 역할 그룹의 복사본을 만들고, 복사본에 식별 가능한 이름을 지정하고, 새 그룹에 대한 변경 내용을 만들고 확인하며, 사용자에게 적절한 권한을 할당하는 것이 좋습니다.

## <a name="privacy-management-role-group"></a>개인 정보 관리 역할 그룹

이 그룹에는 단일 그룹에 있는 모든 개인 정보 관리 권한 역할이 포함되어 있습니다. 이 역할 그룹은 개인 정보 관리 솔루션 내에서 동일한 개인이 모든 업무를 수행할 수 있는 조직에 적합할 수 있습니다. 이 역할 그룹의 구성원 자격을 제공하면 해당 계정에 개인 정보 관리 솔루션의 모든 기능에 대한 모든 권한이 부여됩니다.

역할에는 다음이 포함됩니다.

- 사례 관리  
- 데이터 분류 콘텐츠 뷰어  
- 데이터 분류 목록 뷰어  
- 개인 정보 관리 관리자  
- 개인 정보 관리 분석  
- 개인 정보 관리 조사  
- 개인 정보 관리 영구 기여  
- 개인 정보 관리 임시 기여  
- 개인 정보 관리 뷰어  
- 주체 권한 요청 관리자  
- View-Only 사례

## <a name="privacy-management-administrators-role-group"></a>개인 정보 관리 관리자 역할 그룹

이 역할 그룹의 구성원은 개인 정보 관리 정책, 주체 권한 요청, 개인 정보 관리 권한 및 개인 정보 관리 설정 만들기, 읽기, 업데이트 및 삭제를 비롯한 개인 정보 관리 기능에 대한 광범위한 액세스를 제공합니다.

역할에는 다음이 포함됩니다.

- 사례 관리  
- 개인 정보 관리 관리자  
- View-Only 사례

## <a name="privacy-management-analysts-role-group"></a>개인 정보 관리 분석가 역할 그룹

이 역할 그룹의 구성원은 개인 정보 관리 사례 분석가 역할을 합니다. 정책 일치를 조사하고, 파일 메타데이터를 보고, 수정 작업을 수행할 수 있습니다. 이 그룹은 콘텐츠 탐색기를 통해 전체 파일에 액세스할 수 없습니다.

역할에는 다음이 포함됩니다.

- 사례 관리  
- 데이터 분류 목록 뷰어  
- 개인 정보 관리 분석  
- View-Only 사례

### <a name="privacy-management-investigators-role-group"></a>개인 정보 관리 조사자 역할 그룹

이 그룹의 구성원은 개인 정보 관리 데이터 조사자 역할을 합니다. 정책 일치를 조사하고, 연결된 파일 콘텐츠를 보고, 수정 작업을 수행할 수 있습니다. 이 그룹은 콘텐츠 탐색기를 통해 파일에 액세스할 수 있습니다.

역할에는 다음이 포함됩니다.

- 사례 관리  
- 데이터 분류 콘텐츠 뷰어  
- 데이터 분류 목록 뷰어  
- 개인 정보 관리 조사  
- View-Only 사례

## <a name="privacy-management-viewer-role-group"></a>개인 정보 관리 뷰어 역할 그룹

이 그룹의 구성원은 개인 정보 관리에서 개요, 데이터 프로필 및 주체 요청 보고서와 같은 분석 정보를 볼 수 있습니다.

역할에는 다음이 포함됩니다.

- 개인 정보 관리 뷰어

## <a name="subject-rights-request-administrators-role-group"></a>주체 권한 요청 관리자 역할 그룹

이 그룹의 구성원은 주체 권한 요청을 관리하고 만들 수 있는 모든 권한이 있습니다.

역할에는 다음이 포함됩니다.

- 주체 권한 요청 관리자

## <a name="privacy-management-contributors-role-group"></a>개인 정보 관리 참가자 역할 그룹

이 그룹의 구성원은 주체 권한 요청에 대한 참가자 액세스 권한이 있습니다.  

역할에는 다음이 포함됩니다.

- 개인 정보 관리 임시 기여  
- 개인 정보 관리 영구 기여
