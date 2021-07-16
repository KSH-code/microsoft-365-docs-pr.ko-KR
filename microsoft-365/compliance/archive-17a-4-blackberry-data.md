---
title: 커넥터를 설정하여 BlackBerry 데이터를 보관할 Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 17a-4 BlackBerry DataParser 커넥터를 설정하고 사용하여 17a-4에서 BlackBerry 데이터를 가져오고 보관하는 Microsoft 365.
ms.openlocfilehash: 565b51c4575324bfe1c80299adf82d391a8d14e1
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454556"
---
# <a name="set-up-a-connector-to-archive-blackberry-data"></a>BlackBerry 데이터를 보관할 커넥터 설정

17a-4 LLC의 [BlackBerry DataParser를](https://www.17a-4.com/BlackBerry-dataparser/) 사용하여 BlackBerry 엔터프라이즈 데이터를 가져오고 조직의 사용자 사서함에 Microsoft 365 보관합니다. DataParser에는 타사 데이터 원본의 항목을 캡처하고 해당 항목을 다른 데이터 원본으로 가져오도록 구성된 BlackBerry 커넥터가 Microsoft 365. BlackBerry DataParser 커넥터는 BlackBerry 데이터를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 전자 메일 메시지의 사용자 사서함으로 Microsoft 365.

BlackBerry 데이터를 사용자 사서함에 저장한 후 소송 보존, Microsoft 365, 보존 정책 및 보존 레이블, 통신 규정 준수와 같은 Microsoft 365 준수 기능을 적용할 수 있습니다. BlackBerry 커넥터를 사용하여 조직의 데이터를 가져오고 Microsoft 365 정부 및 규정 정책을 준수하는 데 도움이 될 수 있습니다.

## <a name="overview-of-archiving-blackberry-data"></a>BlackBerry 데이터 보관 개요

다음 개요에서는 데이터 커넥터를 사용하여 BlackBerry 데이터를 데이터 원본에 보관하는 Microsoft 365.

![17a-4의 BlackBerry 데이터에 대한 보관 워크플로](../media/BlackBerryDataParserConnectorWorkflow.png)

1. 조직은 17a-4와 함께 BlackBerry DataParser를 설정하고 구성합니다.

2. BlackBerry 항목은 정기적으로 DataParser에 의해 수집됩니다. 또한 DataParser는 메시지 내용을 전자 메일 메시지 형식으로 변환합니다.

3. 조직에서 만든 BlackBerry DataParser 커넥터는 Microsoft 365 규정 준수 센터 연결하고 메시지를 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.

4. 받은 편지함 **폴더의 BlackBerry DataParser라는** 하위 폴더가 사용자 사서함에 만들어지며 BlackBerry 항목을 해당 폴더로 가져오게 됩니다. 커넥터는 Email 속성 값을 사용하여 항목을 가져올 사서함을 결정할 *수* 있습니다. 모든 BlackBerry 항목에는 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.

## <a name="before-you-set-up-a-connector"></a>커넥터를 설정하기 전에

- Microsoft 커넥터에 대한 DataParser 계정을 생성합니다. 이 작업을 위해 [17a-4 LLC에 문의합니다.](https://www.17a-4.com/contact/) 1단계에서 커넥터를 만들 때 이 계정에 로그인해야 합니다.

- 1단계에서 BlackBerry DataParser 커넥터를 만들고 3단계에서 완료하는 사용자는 2단계에서 사서함 가져오기 내보내기 역할에 할당해야 Exchange Online. 이 역할은 서버의 데이터  커넥터 페이지에서 커넥터를 추가하는 Microsoft 365 규정 준수 센터. 기본적으로 이 역할은 역할 그룹의 역할 그룹에 할당되지 Exchange Online. 사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.

## <a name="step-1-set-up-a-blackberry-dataparser-connector"></a>1단계: BlackBerry DataParser 커넥터 설정

첫 번째 단계는 서버의 데이터 커넥터 페이지에 액세스하고 Microsoft 365 규정 준수 센터 BlackBerry 데이터에 대한 17a-4 커넥터를 만드는 것입니다.

1. 으로 <https://compliance.microsoft.com> 이동한 다음 **데이터** 커넥터  >  **BlackBerry DataParser 를 클릭합니다.**

2. **BlackBerry DataParser** 제품 설명 페이지에서 커넥터 **추가를 클릭합니다.**

3. 서비스 **약관 페이지에서** 동의를 **클릭합니다.**

4. 커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**

5. 17a-4 계정에 로그인하고 BlackBerry DataParser 연결 마법사의 단계를 완료합니다.

## <a name="step-2-configure-the-blackberry-dataparser-connector"></a>2단계: BlackBerry DataParser 커넥터 구성

17a-4 지원에서 BlackBerry DataParser 커넥터를 구성합니다.

## <a name="step-3-map-users"></a>3단계: 사용자 매핑

BlackBerry DataParser 커넥터는 데이터를 전자 메일로 가져오기 전에 Microsoft 365 전자 메일 주소에 자동으로 Microsoft 365.

## <a name="step-4-monitor-the-blackberry-dataparser-connector"></a>4단계: BlackBerry DataParser 커넥터 모니터링

BlackBerry DataParser 커넥터를 만든 후 연결선의 커넥터 상태를 볼 수 Microsoft 365 규정 준수 센터.

1. 으로 <https://compliance.microsoft.com> 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.

2. 커넥터 **탭을** 클릭한 다음 만든 BlackBerry DataParser 커넥터를 선택하여 커넥터에 대한 속성과 정보가 포함된 플라이아웃 페이지를 표시합니다.

3. 원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다. 이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.

## <a name="known-issues"></a>알려진 문제

현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다. 더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.