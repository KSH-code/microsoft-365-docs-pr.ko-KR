---
title: Microsoft 365에서 XSLT/XML 데이터를 보관 하는 커넥터 설정
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
description: 관리자는 Microsoft 365에서 Globanet 로부터 XSLT/XML 데이터를 가져오고 보관 하기 위한 커넥터를 설정할 수 있습니다. 이 커넥터를 사용 하면 Microsoft 365의 타사 데이터 원본에서 데이터를 보관할 수 있으므로 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 통해 조직의 타사 데이터를 관리 하는 데 도움이 됩니다.
ms.openlocfilehash: 3cc41ace1be3f0131458f885b66e7b5645b8eb2c
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816750"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a>XSLT/XML 데이터를 보관 하는 커넥터 설정

Microsoft 365 준수 센터의 Globanet 커넥터를 사용 하 여 Microsoft 365 조직의 사용자 사서함으로 웹 페이지 원본의 데이터를 가져오고 보관 합니다. Globanet에서는 XSLT [/XML 커넥터](https://globanet.com/xslt-xml) 를 사용 하 여 XML 파일을 Microsoft 365로 가져올 수 있는 다른 파일 형식 (예: HTML 또는 텍스트)으로 변환 하는 방법으로 (확장 가능한 스타일 시트 언어 변환)에서 만든 파일을 빠르게 개발할 수 있습니다. 커넥터는 항목의 콘텐츠를 XSLT/XML 원본에서 전자 메일 메시지 형식으로 변환한 다음 변환 된 항목을 Microsoft 365 사서함으로 가져옵니다.

XSLT/XML 데이터가 사용자 사서함에 저장 되 면 소송 보존, eDiscovery, 보존 정책 및 보존 레이블과 같은 Microsoft 365 준수 기능을 적용할 수 있습니다. XSLT/XML 커넥터를 사용 하 여 Microsoft 365에서 데이터를 가져오고 보관 하면 조직이 정부 및 규정 정책을 준수 하는 데 도움이 될 수 있습니다.

## <a name="overview-of-archiving-xsltxml-data"></a>XSLT/XML 데이터 보관 개요

다음 개요에서는 커넥터를 사용 하 여 Microsoft 365에서 XSLT/XML 원본 데이터를 보관 하는 프로세스에 대해 설명 합니다.

![XSLT/XML 데이터에 대 한 보관 워크플로](../media/XSLT-XMLConnectorWorkflow.png)

1. 조직이 XSLT/xml 원본을 사용 하 여 XSLT/XML 사이트를 설정 및 구성 하는 작업을 수행할 수 있습니다.

2. 24 시간 마다 한 번씩 XSLT/XML 원본의 채팅 메시지는 Globanet Merge1 site에 복사 됩니다. 또한이 커넥터는 콘텐츠를 전자 메일 메시지 형식으로 변환 합니다.

3. Microsoft 365 준수 센터에서 만든 XSLT/XML 커넥터는 매일 Globanet Merge1 site에 연결 하 고 메시지를 Microsoft 클라우드의 안전한 Azure Storage 위치로 전송 합니다.

4. 커넥터는 3 단계에서 설명한 대로 자동 사용자 매핑의 *Email* 속성 값을 사용 하 여 변환 된 메시지 항목을 특정 사용자의 사서함으로 가져옵니다. **XSLT/XML** 이라는 받은 편지함 폴더의 새 하위 폴더가 사용자 사서함에 만들어지고 메시지 항목을 해당 폴더로 가져오게 됩니다. 커넥터는 *Email* 속성 값을 사용 하 여이를 수행 합니다. 모든 메시지에는 메시지의 모든 참가자의 전자 메일 주소로 채워지는이 속성이 포함 되어 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

- Microsoft 커넥터에 대 한 Globanet Merge1 계정을 만듭니다. 이 계정을 만들려면 [Globanet 고객 지원](https://globanet.com/contact-us/)에 문의 하세요. 1 단계에서 커넥터를 만들 때이 계정에 로그인 합니다.

- 1 단계에서 XSLT/XML 커넥터를 만든 후 3 단계에서 완료 한 사용자는 Exchange Online의 사서함 가져오기 내보내기 역할에 할당 해야 합니다. 이 역할은 Microsoft 365 준수 센터의 **데이터 커넥터** 페이지에 커넥터를 추가 하는 데 필요 합니다. 기본적으로이 역할은 Exchange Online의 역할 그룹에 할당 되지 않습니다. Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당 한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "Exchange Online에서 역할 그룹 관리" 문서의 [역할 그룹 만들기](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 또는 [역할 그룹 수정](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 섹션을 참조 하세요.

## <a name="step-1-set-up-an-xsltxml-connector"></a>1 단계: XSLT/XML 커넥터 설정

첫 번째 단계는 Microsoft 365 준수 센터의 **데이터 커넥터** 에 액세스 하 고 XSLT/XML 데이터에 대 한 커넥터를 만드는 것입니다.

1. 로 이동한 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 후 **데이터 커넥터**  >  **XSLT/XML** 을 클릭 합니다.

2. **XSLT/XML** 제품 설명 페이지에서 **새 커넥터 추가** 를 클릭 합니다.

3. **서비스 약관** 페이지에서 **수락** 을 클릭 합니다.

4. 커넥터를 식별 하는 고유한 이름을 입력 한 후 **다음** 을 클릭 합니다.

5. Merge1 계정에 로그인 하 여 커넥터를 구성 합니다.

## <a name="step-2-configure-an-xsltxml-connector"></a>2 단계: XSLT/XML 커넥터 구성

두 번째 단계는 Merge1 사이트에서 XSLT/XML 커넥터를 구성 하는 것입니다. Globanet Merge1 사이트에서 XSLT/XML 커넥터를 구성 하는 방법에 대 한 자세한 내용은 [Merge1 타사 커넥터 사용자 가이드](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)를 참조 하십시오.

**마침 & 저장** 을 클릭 하면 Microsoft 365 준수 센터의 커넥터 마법사에 있는 **사용자 매핑** 페이지가 표시 됩니다.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>3 단계: 사용자 매핑 및 커넥터 설정 완료

1. 사용자를 매핑하고 Microsoft 365 준수 센터에서 커넥터 설정을 완료 하려면 다음 단계를 수행 합니다.

2. **XSLT/XML 사용자를 Microsoft 365 사용자에** 게 매핑 페이지에서 자동 사용자 매핑을 사용 하도록 설정 합니다. XSLT/XML 항목에는 조직의 사용자에 대 한 전자 메일 주소를 포함 하는 *email* 이라는 속성이 포함 되어 있습니다. 커넥터가이 주소를 Microsoft 365 사용자와 연결할 수 있으면 해당 사용자의 사서함으로 항목을 가져옵니다.

3. **관리자 동의** 페이지에서 **동의를 제공** 합니다 .를 클릭 합니다. Microsoft 사이트로 리디렉션됩니다. **수락** 을 클릭 하 여 동의를 제공 합니다.

   조직에서는 Office 365 가져오기 서비스가 조직의 사서함 데이터에 액세스할 수 있도록 허용 해야 합니다. 관리자의 동의를 제공 하려면 Microsoft 365 전역 관리자의 자격 증명을 사용 하 여 로그인 한 다음 승인 요청을 수락 해야 합니다. 전역 관리자로 로그인 하지 않은 경우 [이 페이지로](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) 이동 하 여 전역 관리자 자격 증명을 사용 하 여 로그인 하 고 요청을 수락할 수 있습니다.

4. **다음** 을 클릭 하 고 설정을 검토 한 다음 **데이터 커넥터** 페이지로 이동 하 여 새 커넥터에 대 한 가져오기 프로세스의 진행 상황을 확인 합니다.

## <a name="step-4-monitor-the-xsltxml-connector"></a>4 단계: XSLT/XML 커넥터 모니터링

XSLT/XML 커넥터를 만든 후에는 Microsoft 365 준수 센터에서 커넥터 상태를 볼 수 있습니다.

1. 으로 이동 하 여 [https://compliance.microsoft.com](https://compliance.microsoft.com) 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.

2. **커넥터** 탭을 클릭 한 다음 **XSLT/XML** 커넥터를 선택 하 여 플라이 아웃 페이지를 표시 합니다. 이 페이지에는 커넥터에 대 한 속성 및 정보가 포함 되어 있습니다.

3. **커넥터 상태 (원본 포함** )에서 **로그 다운로드** 링크를 클릭 하 여 커넥터의 상태 로그를 열거나 저장 합니다. 이 로그는 Microsoft 클라우드로 가져온 데이터를 포함 합니다.

## <a name="known-issues"></a>알려진 문제

- 현재로 서는 10mb 보다 큰 첨부 파일 또는 항목을 가져올 수 없습니다. 더 큰 항목에 대 한 지원은 나중에 제공 될 예정입니다.
