---
title: Microsoft 365에서 MS 365에 Cisco Jabber를 SQL 커넥터 설정
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
description: 관리자는 Microsoft 365의 Globanet에서 Cisco Jabber 데이터를 가져오고 보관하는 커넥터를 설정할 수 있습니다. 이 커넥터를 사용하면 Microsoft 365에서 타사 데이터 원본의 데이터를 보관할 수 있습니다. 이 데이터를 보관한 후 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 준수 기능을 사용하여 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 2790a29cdfa090372976d78de2e5cc5e5c5ce12e
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620044"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data"></a>Cisco Jabber 데이터를 보관할 커넥터 설정

Microsoft 365 규정 준수 센터의 Globanet 커넥터를 사용하여 Cisco Jabber 플랫폼에서 Microsoft 365 조직의 사용자 사서함으로 데이터를 가져오고 보관합니다. Globanet은 Jabber의 MS SQL 데이터베이스에서 항목을 캡처한 다음 1:1 채팅 메시지 및 그룹 채팅과 같은 항목을 Microsoft 365로 가져오도록 구성된 [Cisco Jabber](https://globanet.com/jabber/) 커넥터를 제공합니다. 커넥터는 Cisco Jabber의 MS SQL Database에서 데이터를 검색하고 처리한 다음 사용자의 Cisco Jabber 계정에서 전자 메일 메시지 형식으로 콘텐츠를 변환한 다음 해당 항목을 Microsoft 365의 사용자 사서함으로 가져올 수 있습니다.

Cisco Jabber 데이터가 사용자 사서함에 저장되고 나면 소송 보존, eDiscovery, 보존 정책 및 보존 레이블, 통신 준수와 같은 Microsoft 365 규정 준수 기능을 적용할 수 있습니다. Cisco Jabber 커넥터를 사용하여 Microsoft 365에서 데이터를 가져오고 보관하면 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.

## <a name="overview-of-archiving-cisco-jabber-data"></a>Cisco Jabber 데이터 보관 개요

다음 개요에서는 커넥터를 사용하여 Microsoft 365에서 Cisco Jabber 데이터를 보관하는 프로세스에 대해 설명합니다.

![Cisco Jabber 데이터에 대한 보관 워크플로](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. 조직은 Cisco와 함께 MS SQL 데이터베이스에서 Cisco Jabber를 설정하고 구성합니다.

2. 24시간마다 Cisco Jabber 항목이 MS SQL 데이터베이스에서 Globanet Merge1 사이트로 복사됩니다. 또한 커넥터는 채팅 메시지의 내용을 전자 메일 메시지 형식으로 변환합니다.

3. Microsoft 365 규정 준수 센터에서 만든 Cisco Jabber 커넥터는 매일 Globanet Merge1 사이트에 연결하여 항목을 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.

4. 커넥터가 [3단계에서](#step-3-map-users-and-complete-the-connector-setup)설명한 *Email* 속성 값을 사용하여 항목을 특정 사용자의 사서함으로 가져오는 자동 사용자 매핑입니다. MS SQL **Cisco Jabber라는** 받은 편지함 폴더의 하위 폴더가 사용자 사서함에 만들어지며 메시지 항목은 해당 폴더로 가져와야 합니다. 커넥터는 Email 속성 값을 사용하여 항목을 가져올 사서함을 결정할 *수* 있습니다. 모든 Cisco Jabber 항목에는 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

- Microsoft 커넥터에 대한 Globanet Merge1 계정을 만드시다. 이 계정을 만들하려면 [Globanet 고객 지원에 문의하세요.](https://globanet.com/ms-connectors-contact/) 1단계에서 커넥터를 만들 때 이 계정에 로그인합니다.

- 1단계에서 커넥터를 만들기 SQL Jabber 항목을 검색할 MS SQL 데이터베이스를 설치합니다. 2단계에서 Cisco Jabber 커넥터를 구성할 때 MS SQL 데이터베이스에 대한 연결 설정을 지정합니다. 자세한 내용은 Merge1 타사 커넥터 [사용자 가이드를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)

- 1단계에서 Cisco Jabber 커넥터를 만들고 3단계에서 완료하는 사용자는 Exchange Online의 사서함 가져오기 내보내기 역할에 할당되어야 합니다. 이 역할은 Microsoft 365 규정 준수 센터의 데이터 커넥터 페이지에서 커넥터를 추가하는 데 필요합니다.  기본적으로 이 역할은 Exchange Online의 역할 그룹에 할당되지 않습니다. Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "Exchange [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서에서 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하십시오.

## <a name="step-1-set-up-the-cisco-jabber-connector"></a>1단계: Cisco Jabber 커넥터 설정

첫 번째 단계는 Microsoft 365 규정 준수 센터에서 **데이터** 커넥터에 액세스하고 MS 365 데이터에서 Cisco Jabber에 SQL 것입니다.

1. GO to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click Data **connectors**  >  **Cisco Jabber on MS SQL.**

2. MS SQL 설명 페이지의 **Cisco Jabber에서** 커넥터 추가를 **클릭합니다.**

3. 서비스 약관 **페이지에서** 수락을 **클릭합니다.**

4. 커넥터를 식별하는 고유한 이름을 입력하고 다음을 **클릭합니다.**

5. Merge1 계정에 로그인하여 커넥터를 구성합니다.

## <a name="step-2-configure-the-cisco-jabber-connector-on-the-globanet-merge1-site"></a>2단계: Globanet Merge1 사이트에서 Cisco Jabber 커넥터 구성

두 번째 단계는 Globanet Merge1 사이트에서 MS SQL 커넥터에서 Cisco Jabber를 구성하는 것입니다. MS SQL 커넥터에서 Cisco Jabber를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors 사용자 가이드를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)

저장 **&** 마친 후 Microsoft  365 준수 센터의 커넥터 마법사에 있는 사용자 매핑 페이지가 표시됩니다.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>3단계: 사용자 매핑 및 커넥터 설정 완료

사용자를 매핑하고 Microsoft 365 규정 준수 센터에서 설정된 커넥터를 완료하기 위해 다음 단계를 수행합니다.

1. MS **365** 사용자에 대한 MS SQL 사용자 매핑 페이지에서 자동 사용자 매핑을 사용하도록 설정하세요. MS SQL 항목의 Cisco Jabber에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함되어 있습니다. 커넥터가 이 주소를 Microsoft 365 사용자와 연결하면 항목이 해당 사용자의 사서함으로 가져오기됩니다.

2. 다음을 **클릭하고** 설정을 검토하고  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>4단계: Cisco Jabber 커넥터 모니터링

MS SQL 커넥터에서 Cisco Jabber를 만든 후 Microsoft 365 규정 준수 센터에서 커넥터 상태를 볼 수 있습니다.

1. Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.

2. 커넥터 **탭을** 클릭한 다음 MS SQL 커넥터에서 **Cisco Jabber를** 선택하여 플라이아웃 페이지를 표시합니다. 이 페이지에는 커넥터에 대한 속성과 정보가 포함되어 있습니다.

3. 원본이 **있는 커넥터** 상태  아래에서 다운로드 로그 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다. 이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.

## <a name="known-issues"></a>알려진 문제

- 현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다. 더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.
