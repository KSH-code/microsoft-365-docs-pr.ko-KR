---
title: YouTube 데이터를 보관할 커넥터를 Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: 관리자는 Veritas에서 다른 사용자로 YouTube 데이터를 가져오고 보관할 커넥터를 Microsoft 365. 이 커넥터를 사용하면 타사 데이터 원본의 데이터를 해당 커넥터에 Microsoft 365. 이 데이터를 보관한 후 법적 보존, eDiscovery 및 보존 정책과 같은 규정 준수 기능을 사용하여 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 6205e9a8425b4d9eeea2278a131881045b6e6bac
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60153237"
---
# <a name="set-up-a-connector-to-archive-youtube-data"></a>YouTube 데이터를 보관할 커넥터 설정

조직의 Veritas 커넥터를 사용하여 Microsoft 365 규정 준수 센터 조직의 사용자 사서함으로 데이터를 가져오고 보관할 Microsoft 365 있습니다. Veritas는 타사 데이터 원본에서 항목을 캡처하고 해당 항목을 가져오도록 구성된 커넥터를 Microsoft 365. 커넥터는 채팅, 첨부 파일, 작업, 메모 및 게시물과 같은 콘텐츠를 YouTube에서 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 전자 메일 메시지의 사용자 사서함으로 Microsoft 365.

YouTube 데이터가 사용자 사서함에 저장되고 나면 소송 보존, eDiscovery, 보존 Microsoft 365 레이블과 같은 규정 준수 기능을 적용할 수 있습니다. YouTube 커넥터를 사용하여 조직에서 데이터를 가져오고 Microsoft 365 정부 및 규정 정책을 준수하는 데 도움이 될 수 있습니다.

## <a name="overview-of-archiving-youtube-data"></a>YouTube 데이터 보관 개요

다음 개요에서는 커넥터를 사용하여 YouTube 데이터를 커넥터에 보관하는 Microsoft 365.

![YouTube 데이터에 대한 보관 워크플로입니다.](../media/YouTubeConnectorWorkflow.png)

1. 조직은 YouTube와 함께 YouTube 사이트를 설정하고 구성합니다.

2. 24시간마다 YouTube 항목이 Veritas Merge1 사이트에 복사됩니다. 또한 커넥터는 YouTube 항목을 전자 메일 메시지 형식으로 변환합니다.

3. 조직에서 만드는 YouTube 커넥터는 Microsoft 365 규정 준수 센터 Veritas Merge1 사이트에 매일 연결하고 YouTube 콘텐츠를 Microsoft 클라우드의 안전한 Azure Storage 위치로 전송합니다.

4. 커넥터는 3단계에 설명된 자동 사용자 매핑의 *Email* 속성 값을 사용하여 변환된 항목을 특정 사용자의 사서함으로 [가져올 수 있습니다.](#step-3-map-users-and-complete-the-connector-setup) **YouTube라는** 받은 편지함 폴더의 하위 폴더가 사용자 사서함에 만들어지며 항목이 해당 폴더로 가져오기됩니다. 커넥터는 Email 속성 값을 사용하여 항목을 가져올 사서함을 결정할 *수* 있습니다. 모든 YouTube 항목에는 항목의 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.

## <a name="before-you-set-up-a-connector"></a>커넥터를 설정하기 전에

- Microsoft 커넥터에 대한 Merge1 계정을 생성합니다. 이 계정을 만들하려면 [Veritas 고객 지원에 문의하세요.](https://www.veritas.com/form/requestacall/ms-connectors-contact) 1단계에서 커넥터를 만들 때 이 계정에 로그인해야 합니다.

- YouTube 응용 프로그램을 만들어 YouTube 계정에서 데이터를 페치합니다. 응용 프로그램을 만드는 단계별 지침은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20YouTube%20User%20Guide.pdf)

- 1단계에서 YouTube 커넥터를 만들고 3단계에서 완료하는 사용자는 2단계에서 사서함 가져오기 내보내기 역할에 할당해야 Exchange Online. 이 역할은 서버의 데이터  커넥터 페이지에서 커넥터를 추가하는 Microsoft 365 규정 준수 센터. 기본적으로 이 역할은 역할 그룹의 역할 그룹에 할당되지 Exchange Online. 사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.

## <a name="step-1-set-up-the-youtube-connector"></a>1단계: YouTube 커넥터 설정

첫 번째 단계는 사용자  센터의 데이터 커넥터 페이지에 액세스하고 Microsoft 365 규정 준수 센터 YouTube 데이터에 대한 커넥터를 만드는 것입니다.

1. 으로 <https://compliance.microsoft.com> 이동한 다음 데이터 커넥터   >  **YouTube를 클릭합니다.**

2. **YouTube 제품** 설명 페이지에서 커넥터 **추가를 클릭합니다.**

3. 서비스 **약관 페이지에서** 동의를 **클릭합니다.**

4. 커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**

5. Merge1 계정에 로그인하여 커넥터를 구성합니다.

## <a name="step-2-configure-the-youtube-on-the-veritas-merge1-site"></a>2단계: Veritas Merge1 사이트에서 YouTube 구성

두 번째 단계는 Veritas Merge1 사이트에서 YouTube 커넥터를 구성하는 것입니다. YouTube 커넥터를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20YouTube%20User%20Guide.pdf)

저장 후 & **마친** 후  연결선의 커넥터 마법사에 있는 사용자 매핑 Microsoft 365 규정 준수 센터 표시됩니다.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>3단계: 사용자 매핑 및 커넥터 설정 완료

사용자를 매핑하고 연결기에서 커넥터 설정을 Microsoft 365 규정 준수 센터 다음 단계를 수행합니다.

1. YouTube 사용자를 사용자 Microsoft 365 매핑 **페이지에서** 자동 사용자 매핑을 사용하도록 설정합니다. YouTube 항목에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함됩니다. 커넥터가 이 주소를 Microsoft 365 사용자 사서함으로 항목을 가져올 수 있습니다.

2. **다음을** 클릭하고 설정을 검토한 다음  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.

## <a name="step-4-monitor-the-youtube-connector"></a>4단계: YouTube 커넥터 모니터링

YouTube 커넥터를 만든 후 연결선의 커넥터 상태를 볼 수 Microsoft 365 규정 준수 센터.

1. 으로 <https://compliance.microsoft.com/> 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.

2. 커넥터 **탭을** 클릭한 다음 **YouTube** 커넥터를 선택하여 커넥터에 대한 속성과 정보가 포함된 플라이아웃 페이지를 표시합니다.

3. 원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다. 이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.

## <a name="known-issues"></a>알려진 문제

- 현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다. 더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.
