---
title: Facebook에서 Workplace 데이터를 보관할 커넥터를 Microsoft 365
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
description: 관리자는 Veritas의 Merge1 사이트에 보관된 Facebook의 Workplace에서 데이터를 가져오고 보관할 커넥터를 설정하여 데이터를 다른 사용자로 Microsoft 365. 커넥터를 설정하려면 Veritas와 함께 작업해야 합니다. 이 커넥터를 사용하면 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 조직의 타사 데이터를 관리할 수 있도록 Microsoft 365 타사 데이터 원본의 데이터를 보관할 수 있습니다.
ms.openlocfilehash: 0d2db469186469759226f59775a30bac78fe8daa
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60179442"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a>Facebook 데이터에서 Workplace를 보관하는 커넥터 설정

조직의 Veritas 커넥터를 Microsoft 365 규정 준수 센터 Facebook에서 사용자 사서함으로 데이터를 가져오고 보관할 Microsoft 365 있습니다. Veritas는 타사 데이터 원본에서 항목을 캡처하고(정기적으로) 해당 항목을 가져오도록 구성된 [Facebook](https://globanet.com/workplace/) 커넥터에서 Workplace를 Microsoft 365. 커넥터는 채팅, 첨부 파일, 게시물 및 비디오와 같은 콘텐츠를 Workplace에서 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 전자 메일의 사용자 사서함으로 Microsoft 365.

Workplace 데이터가 사용자 사서함에 저장되고 나면 소송 보존, eDiscovery Microsoft 365 보존 정책 및 보존 레이블, 통신 규정 준수와 같은 Microsoft 365 준수 기능을 적용할 수 있습니다. Facebook 커넥터에서 Workplace를 사용하여 조직의 데이터를 가져오고 Microsoft 365 정책을 준수하는 데 도움이 될 수 있습니다.

## <a name="overview-of-archiving-workplace-from-facebook-data"></a>Facebook 데이터에서 작업 공간 보관 개요

다음 개요에서는 커넥터를 사용하여 작업 공간 데이터를 커넥터에 보관하는 Microsoft 365.

![Facebook 데이터에서 Workplace용 보관 워크플로](../media/WorkplaceConnectorWorkflow.png)

1. 조직은 Facebook의 Workplace와 함께 작업하여 Workplace 사이트를 설정하고 구성합니다.

2. 24시간마다 Workplace의 항목이 Veritas Merge1 사이트에 복사됩니다. 또한 커넥터는 이러한 항목의 내용을 전자 메일 메시지 형식으로 변환합니다.

3. 조직에서 만든 Facebook 커넥터에서 Microsoft 365 규정 준수 센터 매일 Veritas Merge1에 연결하고 Workplace 항목을 Microsoft 클라우드의 안전한 Azure Storage 위치로 전송합니다.

4. 커넥터는 3단계에 설명된 자동 사용자 매핑의 *Email* 속성 값을 사용하여 변환된 항목을 특정 사용자의 사서함으로 가져올 수 있습니다. Facebook의 받은 편지함 폴더에 **Workplace라는** 하위 폴더가 만들어지며 Workplace 항목을 해당 폴더로 가져오게 됩니다. 이 커넥터는 Email 속성 값을 사용하여 이 *기능을* 실행합니다. 모든 Workplace 항목에는 모든 채팅 또는 사후 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

- Microsoft 커넥터에 대한 Veritas Merge1 계정을 생성합니다. 이 계정을 만들하려면 [Veritas 고객 지원에 문의하세요.](https://globanet.com/ms-connectors-contact) 1단계에서 커넥터를 만들 때 이 계정에 로그인합니다.

- 에서 사용자 지정 통합을 만들어 규정 준수 및 https://my.workplace.com/work/admin/apps/ eDiscovery 목적으로 API를 통해 Workplace에서 데이터를 검색합니다.

   통합을 만들 때 Workplace 플랫폼은 인증에 사용되는 토큰을 생성하는 데 사용되는 고유한 자격 증명 집합을 생성합니다. 이러한 토큰은 2단계의 Facebook 커넥터 구성 마법사에서 Workplace에서 사용됩니다. 응용 프로그램을 만드는 방법에 대한 단계별 지침은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)

- 1단계에서 Facebook 커넥터에서 Workplace를 만들고 3단계에서 완료하는 사용자는 2단계에서 사서함 가져오기 내보내기 역할에 할당해야 Exchange Online. 이 역할은 서버의 데이터  커넥터 페이지에서 커넥터를 추가하는 Microsoft 365 규정 준수 센터. 기본적으로 이 역할은 역할 그룹의 역할 그룹에 할당되지 Exchange Online. 사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a>1단계: Facebook 커넥터에서 Workplace 설정

첫 번째 단계는 작업  공간의 데이터 커넥터 페이지에 액세스하고 Microsoft 365 규정 준수 센터 대한 커넥터를 만드는 것입니다.

1. 으로 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 이동한 다음 **Facebook에서 데이터** 커넥터  >  **Workplace를 클릭합니다.**

2. Facebook **제품 설명 페이지에서** 커넥터 **추가를 클릭합니다.**

3. 서비스 **약관 페이지에서** 동의를 **클릭합니다.**

4. 커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**

5. Merge1 계정에 로그인하여 커넥터를 구성합니다.

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-veritas-merge1-site"></a>2단계: Veritas Merge1 사이트에서 Facebook 커넥터에서 작업 공간 구성

두 번째 단계는 Merge1 사이트에서 Facebook 커넥터에서 Workplace를 구성하는 것입니다. Facebook 커넥터에서 Workplace를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)

Save & **Finish를** 클릭하면 연결선의 커넥터 마법사에 있는 사용자 매핑 Microsoft 365 규정 준수 센터 표시됩니다. 

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>3단계: 사용자 매핑 및 커넥터 설정 완료

사용자를 매핑하고 연결기에서 커넥터 설정을 Microsoft 365 규정 준수 센터 다음 단계를 수행합니다.

1. 외부 사용자를 **사용자 Microsoft 365** 매핑 페이지에서 자동 사용자 매핑을 사용하도록 설정합니다. Workplace 항목에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함됩니다. 커넥터가 이 주소를 Microsoft 365 사용자 사서함으로 항목을 가져올 수 있습니다.

2. **다음을** 클릭하고 설정을 검토한 다음  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a>4단계: Facebook 커넥터에서 작업 공간 모니터링

Facebook 커넥터에서 Workplace를 만든 후 Facebook 커넥터의 커넥터 상태를 볼 수 Microsoft 365 규정 준수 센터.

1. 으로 [https://compliance.microsoft.com](https://compliance.microsoft.com) 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.

2. 커넥터 **탭을** 클릭한 다음 Facebook 커넥터에서 **Workplace를** 선택하여 플라이아웃 페이지를 표시합니다. 이 페이지에는 커넥터에 대한 속성과 정보가 포함되어 있습니다.

3. 원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다. 이 로그에는 Microsoft 클라우드로 가져온 데이터에 대한 정보가 포함되어 있습니다.

## <a name="known-issues"></a>알려진 문제

- 현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다. 더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.