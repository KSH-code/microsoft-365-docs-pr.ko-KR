---
title: SSL에서 PostgreSQL 데이터를 보관할 커넥터를 Microsoft 365
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Microsoft 365 규정 준수 센터에서 커넥터를 설정하고 사용하여 PostgreSQL의 Cisco Jabber에서 데이터를 가져오고 보관하는 방법을 Microsoft 365.
ms.openlocfilehash: 06ec56b3b28b28b82554048ec788114a0e5cb389
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842749"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-postgresql-data-preview"></a>PostgreSQL 데이터에 Cisco Jabber를 보관할 커넥터 설정(미리 보기)

Microsoft 365 규정 준수 센터의 Veritas 커넥터를 사용하여 Cisco Jabber 플랫폼에서 조직의 사용자 사서함으로 데이터를 Microsoft 365 보관합니다. Veritas는 타사 데이터 원본에서 항목을 정기적으로 캡처하고 해당 항목을 다른 데이터 원본으로 가져오도록 구성된 [PostgreSQL 커넥터에 Cisco Jabber를](https://www.veritas.com/insights/merge1/jabber) Microsoft 365. 커넥터는 PostgreSQL의 Cisco Jabber에서 메시지, 채팅 및 공유 콘텐츠와 같은 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 사서함의 사용자 사서함으로 Microsoft 365.

PostgreSQL 데이터의 Cisco Jabber가 사용자 사서함에 저장되고 나면 소송 보존, eDiscovery Microsoft 365 보존 정책 및 보존 레이블과 같은 Microsoft 365 준수 기능을 적용할 수 있습니다. PostgreSQL 커넥터의 Cisco Jabber를 사용하여 조직의 데이터를 가져오고 Microsoft 365 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.

## <a name="overview-of-archiving-cisco-jabber-on-postgresql-data"></a>PostgreSQL 데이터에 대한 보관 Cisco Jabber 개요

다음 개요에서는 커넥터를 사용하여 해당 커넥터의 PostgreSQL 데이터에 Cisco Jabber를 보관하는 Microsoft 365.

![PostgreSQL 데이터에 대한 Cisco Jabber용 보관 워크플로](../media/CiscoJabberonPostgreSQLConnectorWorkflow.png)

1. 조직은 PostgreSQL의 Cisco Jabber와 함께 PostgreSQL 사이트에서 Cisco Jabber를 설정하고 구성합니다.

2. 24시간마다 PostgreSQL 항목의 Cisco Jabber가 Veritas Merge1 사이트에 복사됩니다. 또한 이 커넥터는 PostgreSQL 항목의 Cisco Jabber를 전자 메일 메시지 형식으로 변환합니다.

3. Microsoft 365 준수 센터에서 만든 PostgreSQL 커넥터의 Cisco Jabber는 매일 Veritas Merge1 사이트에 연결하고, Microsoft 클라우드의 보안 Azure Storage 위치로 Jabber 콘텐츠를 전송합니다.

4. 커넥터는 3단계에 설명된 자동 사용자 매핑의 *Email* 속성 값을 사용하여 변환된 항목을 특정 사용자의 사서함으로 [가져올 수 있습니다.](#step-3-map-users-and-complete-the-connector-setup) **PostgreSQL의 받은 편지함 폴더에 있는 Cisco Jabber라는** 하위 폴더가 사용자 사서함에 만들어지며 항목이 해당 폴더로 가져오기됩니다. 이 커넥터는 Email 속성 값을 사용하여 이 *기능을* 실행합니다. 모든 Jabber 항목에는 항목의 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

- Microsoft 커넥터에 대한 Merge1 계정을 생성합니다. 이를 위해 [Veritas 고객 지원에 문의합니다.](https://www.veritas.com/content/support/en_US) 1단계에서 커넥터를 만들 때 이 계정에 로그인해야 합니다.

- 1단계에서 PostgreSQL 커넥터에 Cisco Jabber를 만들고 3단계에서 완료하는 사용자는 2단계에서 사서함 가져오기 내보내기 역할에 할당해야 Exchange Online. 이 역할은 준수 센터의  데이터 커넥터 페이지에서 커넥터를 Microsoft 365 필요합니다. 기본적으로 이 역할은 역할 그룹의 역할 그룹에 할당되지 Exchange Online. 사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.

## <a name="step-1-set-up-the-cisco-jabber-on-postgresql-connector"></a>1단계: PostgreSQL 커넥터에서 Cisco Jabber 설정

첫 번째 단계는 Microsoft 365  센터의 데이터 커넥터 페이지에 액세스하고 Jabber 데이터에 대한 커넥터를 만드는 것입니다.

1. 으로 <https://compliance.microsoft.com> 이동한  다음 &gt; **PostgreSQL에서 데이터 커넥터 Cisco Jabber를 클릭합니다.**

2. **PostgreSQL 제품 설명 페이지의 Cisco Jabber에서** 커넥터 **추가를 클릭합니다.**

3. 서비스 **약관 페이지에서** 동의를 **클릭합니다.**

4. 커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**

5. Merge1 계정에 로그인하여 커넥터를 구성합니다.

## <a name="step-2-configure-the-cisco-jabber-on-postgresql-on-the-veritas-merge1-site"></a>2단계: Veritas Merge1 사이트에서 PostgreSQL에서 Cisco Jabber 구성

두 번째 단계는 Veritas Merge1 사이트의 PostgreSQL 커넥터에서 Cisco Jabber를 구성하는 것입니다. PostgreSQL 커넥터에서 Cisco Jabber를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20PostgreSQL%20User%20Guide.pdf)

저장 및 & **마친** 후  준수 센터의 커넥터 마법사에 Microsoft 365 페이지가 표시됩니다.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>3단계: 사용자 매핑 및 커넥터 설정 완료

사용자를 매핑하고 Microsoft 365 준수 센터에서 커넥터 설정을 완료하려면 다음 단계를 수행합니다.

1. **PostgreSQL 사용자의 Cisco Jabber를** 사용자 Microsoft 365 자동 사용자 매핑을 사용하도록 설정하십시오. PostgreSQL 항목의 Cisco Jabber에는 조직의 사용자에 대한 전자 메일 주소를 포함하는 *Email이라는* 속성이 포함됩니다. 커넥터가 이 주소를 Microsoft 365 사용자 사서함으로 항목을 가져올 수 있습니다.

2. **다음을** 클릭하고 설정을 검토한 다음  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.

## <a name="step-4-monitor-the-cisco-jabber-on-postgresql-connector"></a>4단계: PostgreSQL 커넥터에서 Cisco Jabber 모니터링

PostgreSQL 커넥터에서 Cisco Jabber를 만든 후 준수 센터에서 커넥터 상태를 Microsoft 365 있습니다.

1. 으로 <https://compliance.microsoft.com/> 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.

2. 커넥터 **탭을** 클릭한 다음 **PostgreSQL 커넥터에서 Cisco Jabber를** 선택하여 커넥터에 대한 속성과 정보가 포함된 플라이아웃 페이지를 표시합니다.

3. 원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다. 이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.

## <a name="known-issues"></a>알려진 문제

- 현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않지만 나중에 더 큰 항목에 대한 지원을 사용할 수 있습니다.
