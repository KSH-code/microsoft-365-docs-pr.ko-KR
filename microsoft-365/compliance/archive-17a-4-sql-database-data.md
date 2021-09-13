---
title: 커넥터를 설정하여 SQL 데이터를 Microsoft 365
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
description: DataParser 커넥터를 사용하여 17a-4 SQL 설정하고 사용하여 SQL 데이터를 가져오고 보관하는 Microsoft 365.
ms.openlocfilehash: 21a4c8a8a7d0c1a7e8dbf8cef7f1731e56d456ce
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59193249"
---
# <a name="set-up-a-connector-to-archive-sql-data"></a>데이터 보관을 위한 SQL 설정

17a-4 LLC의 SQL [DataParser를](https://www.17a-4.com/sql-dataparser/) 사용하여 SQL 데이터베이스의 데이터를 Microsoft 365 사서함으로 가져올 수 있습니다. DataParser에는 타사 SQL 원본의 항목을 캡처하고 해당 항목을 가져오도록 구성된 Microsoft 365. 이 SQL DataParser 커넥터는 SQL 데이터를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 전자 메일 메시지의 사용자 사서함으로 Microsoft 365.

사용자 SQL 저장한 후 소송 보존, eDiscovery Microsoft 365 보존 정책 및 보존 레이블, 통신 준수와 같은 Microsoft 365 준수 기능을 적용할 수 있습니다. SQL 커넥터를 사용하여 조직의 데이터 가져오기 및 보관을 Microsoft 365 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.

## <a name="overview-of-archiving-sql-data"></a>보관 데이터 SQL 개요

다음 개요에서는 데이터 커넥터를 사용하여 데이터 커넥터를 사용하여 SQL 데이터를 보관하는 Microsoft 365.

![17a-SQL 데이터를 보관하는 워크플로입니다.](../media/SQLDatabaseDataParserConnectorWorkflow.png)

1. 조직은 17a-4와 함께 작업하여 DataParser를 SQL 구성합니다.

2. 정기적으로 SQL DataParser에서 항목을 수집합니다. 또한 DataParser는 메시지 내용을 전자 메일 메시지 형식으로 변환합니다.

3. SQL 만든 Microsoft 365 규정 준수 센터 DataParser 커넥터는 DataParser에 연결하고 메시지를 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.

4. 사용자 사서함에 SQL **DataParser라는** 받은 편지함 폴더의 하위 폴더가 만들어지며 SQL 폴더로 가져오기됩니다. 커넥터는 Email 속성 값을 사용하여 항목을 가져올 사서함을 결정할 *수* 있습니다. 모든 SQL 항목에는 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.

## <a name="before-you-set-up-a-connector"></a>커넥터를 설정하기 전에

- Microsoft 커넥터에 대한 DataParser 계정을 생성합니다. 이 작업을 위해 [17a-4 LLC에 문의합니다.](https://www.17a-4.com/contact/) 1단계에서 커넥터를 만들 때 이 계정에 로그인해야 합니다.

- 1단계에서 SQL DataParser 커넥터를 만들고 3단계에서 완료하는 사용자는 2단계에서 사서함 가져오기 내보내기 역할에 할당해야 Exchange Online. 이 역할은 서버의 데이터  커넥터 페이지에서 커넥터를 추가하는 Microsoft 365 규정 준수 센터. 기본적으로 이 역할은 역할 그룹의 역할 그룹에 할당되지 Exchange Online. 사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.

## <a name="step-1-set-up-a-sql-dataparser-connector"></a>1단계: DataParser SQL 설정

첫 번째 단계는 서버의 데이터 커넥터 페이지에 액세스하고 Microsoft 365 규정 준수 센터 17a-4 커넥터를 SQL 것입니다.

1. 으로 이동한 다음 <https://compliance.microsoft.com> **DataParser에서**  >  **데이터 SQL 클릭합니다.**

2. **DataParser SQL** 설명 페이지에서 커넥터 **추가를 클릭합니다.**

3. 서비스 **약관 페이지에서** 동의를 **클릭합니다.**

4. 커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**

5. 17a-4 계정에 로그인하고 DataParser 연결 마법사의 SQL 완료합니다.

## <a name="step-2-configure-the-sql-dataparser-connector"></a>2단계: SQL DataParser 커넥터 구성

17a-4 지원에서 데이터 SQL 구성합니다.

## <a name="step-3-map-users"></a>3단계: 사용자 매핑

이 SQL DataParser 커넥터는 데이터를 가져오기 전에 Microsoft 365 전자 메일 주소에 사용자를 Microsoft 365.

## <a name="step-4-monitor-the-sql-dataparser-connector"></a>4단계: 데이터 SQL 모니터링

DataParser SQL 만들면 연결선의 커넥터 상태를 볼 수 Microsoft 365 규정 준수 센터.

1. 으로 <https://compliance.microsoft.com> 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.

2. 커넥터 **탭을** 클릭한 다음 만든 SQL DataParser 커넥터를 선택하여 커넥터에 대한 속성과 정보가 포함된 플라이아웃 페이지를 표시합니다.

3. 원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다. 이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.

## <a name="known-issues"></a>알려진 문제

현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다. 더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.
