---
title: Microsoft 365에서 FX Connect 데이터를 보관하는 커넥터 설정
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
description: 관리자는 Microsoft 365의 Globanet FX Connect에서 데이터를 가져오고 보관하는 커넥터를 설정할 수 있습니다. 이 커넥터를 사용하면 Microsoft 365의 타사 데이터 원본에서 데이터를 보관할 수 있으므로 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 조직의 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: de358f3aef34754bd7b715f9294aff530fc917ae
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620004"
---
# <a name="set-up-a-connector-to-archive-fx-connect-data"></a>FX Connect 데이터를 보관할 커넥터 설정

Microsoft 365 규정 준수 센터의 Globanet 커넥터를 사용하여 FX Connect 공동 작업 플랫폼에서 Microsoft 365 조직의 사용자 사서함으로 데이터를 가져오고 보관합니다. Globanet은 [FX Connect](https://globanet.com/fx-connect/) 항목을 캡처하고 해당 항목을 Microsoft 365로 가져오도록 구성된 FX Connect 커넥터를 제공합니다. 커넥터는 조직의 FX Connect 계정에서 거래, 메시지 및 기타 세부 정보 등 FX Connect의 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 이러한 항목을 Microsoft 365의 사용자 사서함으로 가져올 수 있습니다.

FX Connect 데이터를 사용자 사서함에 저장한 후 소송 보존, eDiscovery, 보존 정책 및 보존 레이블, 통신 준수와 같은 Microsoft 365 규정 준수 기능을 적용할 수 있습니다. FX Connect 커넥터를 사용하여 Microsoft 365에서 데이터를 가져오고 보관하면 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.

## <a name="overview-of-archiving-fx-connect-data"></a>FX Connect 데이터 보관 개요

다음 개요에서는 커넥터를 사용하여 Microsoft 365에 FX Connect 정보를 보관하는 프로세스에 대해 설명합니다.

![FX Connect 데이터에 대한 보관 워크플로](../media/FXConnectConnectorWorkflow.png)

1. 조직은 FX Connect와 함께 FX Connect 사이트를 설정하고 구성합니다.

2. 24시간마다 FX Connect 계정의 항목이 Globanet Merge1 사이트에 복사됩니다. 또한 커넥터는 FX Connect 항목을 전자 메일 메시지 형식으로 변환합니다.

3. Microsoft 365 규정 준수 센터에서 만든 FX Connect 커넥터는 매일 Globanet Merge1 사이트에 연결하고 FX Connect 항목을 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.

4. 커넥터는 3단계에 설명된 자동 사용자 매핑의 *Email* 속성 값을 사용하여 특정 사용자의 사서함으로 항목을 [가져올 수 있습니다.](#step-3-map-users-and-complete-the-connector-setup) FX **Connect라는** 받은 편지함 폴더의 하위 폴더가 사용자 사서함에 만들어지며 해당 폴더로 항목이 가져오기됩니다. 이 커넥터는 Email 속성 값을 사용하여 이 *기능을* 실행합니다. 모든 FX Connect 항목에는 항목의 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

- Microsoft 커넥터에 대한 Globanet Merge1 계정을 생성합니다.  계정을 만들 경우 [Globanet 고객](https://globanet.com/ms-connectors-contact)지원에 문의하세요. 1단계에서 커넥터를 만들 때 이 계정에 로그인합니다.

- 1단계에서 FX Connect 커넥터를 만들고 3단계에서 완료하는 사용자는 Exchange Online의 사서함 가져오기 내보내기 역할에 할당되어야 합니다. 이 역할은 Microsoft 365 규정 준수 센터의 데이터 커넥터 페이지에서 커넥터를 추가하는 데 필요합니다.  기본적으로 이 역할은 Exchange Online의 역할 그룹에 할당되지 않습니다. Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "Exchange [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서에서 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하십시오.

## <a name="step-1-set-up-the-fx-connect-connector"></a>1단계: FX Connect 커넥터 설정

첫 번째 단계는 Microsoft  365 규정 준수 센터의 데이터 커넥터 페이지에 액세스하고 FX Connect 데이터에 대한 커넥터를 만드는 것입니다.

1. Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click Data **connectors**  >  **FX Connect.**

2. **FX 연결** 제품 설명 페이지에서 커넥터 **추가를 클릭합니다.**

3. 서비스 약관 **페이지에서** 수락을 **클릭합니다.**

4. 커넥터를 식별하는 고유한 이름을 입력하고 다음을 **클릭합니다.**

5. Merge1 계정에 로그인하여 커넥터를 구성합니다.

## <a name="step-2-configure-the-fx-connect-connector-on-the-globanet-merge1-site"></a>2단계: Globanet Merge1 사이트에서 FX Connect 커넥터 구성

두 번째 단계는 Merge1 사이트에서 FX Connect 커넥터를 구성하는 것입니다. FX Connect 커넥터를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors 사용자 가이드를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf)

저장 & **마친** 후 Microsoft  365 준수 센터의 커넥터 마법사에 있는 사용자 매핑 페이지가 표시됩니다.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>3단계: 사용자 매핑 및 커넥터 설정 완료

사용자를 매핑하고 Microsoft 365 규정 준수 센터에서 커넥터 설정을 완료하려면 다음 단계를 수행합니다.

1. Microsoft **365** 사용자에 대한 FX 연결 사용자 매핑 페이지에서 자동 사용자 매핑을 사용하도록 설정합니다. FX Connect 항목에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함됩니다. 커넥터가 이 주소를 Microsoft 365 사용자와 연결하면 항목이 해당 사용자의 사서함으로 가져오기됩니다.

2. 다음을 **클릭하고** 설정을 검토한 다음  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.

## <a name="step-4-monitor-the-fx-connect-connector"></a>4단계: FX Connect 커넥터 모니터링

FX Connect 커넥터를 만든 후 Microsoft 365 규정 준수 센터에서 커넥터 상태를 볼 수 있습니다.

1. Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.

2. 커넥터 **탭을** 클릭한 다음 **FX 연결 커넥터를** 선택하여 플라이아웃 페이지를 표시합니다. 이 페이지에는 커넥터에 대한 속성과 정보가 포함되어 있습니다.

3. 원본이 **있는 커넥터** 상태  아래에서 다운로드 로그 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다. 이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.

## <a name="known-issues"></a>알려진 문제

- 현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다. 더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.
