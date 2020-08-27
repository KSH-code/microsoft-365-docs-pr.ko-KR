---
title: Bloomberg 메시지 데이터를 보관 하는 커넥터 설정
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
description: 관리자는 데이터 커넥터를 설정 하 여 Bloomberg 메시지 전자 메일 도구에서 Microsoft 365로 데이터를 가져오고 보관 합니다. 이를 통해 Microsoft 365의 타사 데이터 원본에서 데이터를 보관할 수 있으므로 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용 하 여 조직의 타사 데이터를 관리할 수도 있습니다.
ms.openlocfilehash: f9793db545b5298663da7bbfa39a0878854e070d
ms.sourcegitcommit: 195172dd836e8a793e8e0c2db3323b7391bc51ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255865"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data-preview"></a>Bloomberg 메시지 데이터를 보관 하는 커넥터 설정 (미리 보기)

Microsoft 365 준수 센터의 데이터 커넥터를 사용 하 여 [Bloomberg 메시지](https://www.bloomberg.com/professional/product/collaboration/) 공동 작업 도구에서 금융 서비스 전자 메일 데이터를 가져오고 보관 합니다. 커넥터를 설정 하 고 구성한 후에는 매일 조직의 Bloomberg 보안 FTP (SFTP) 사이트에 연결 하 고 Microsoft 365의 사서함으로 전자 메일 항목을 가져옵니다.

Bloomberg 메시지 데이터가 사용자 사서함에 저장 되 면 소송 보존, 콘텐츠 검색, 원본 위치 보관, 감사, 통신 준수 및 Microsoft 365 보존 정책과 같은 Microsoft 365 준수 기능을 Bloomberg 메시지 데이터에 적용할 수 있습니다. 예를 들어 콘텐츠 검색 도구를 사용 하 여 Bloomberg 메시지 전자 메일을 검색 하거나 고급 eDiscovery 사례의 Bloomberg 메시지 데이터를 포함 하는 사서함을 custodian에 연결할 수 있습니다. Bloomberg 메시지 커넥터를 사용 하 여 Microsoft 365에서 데이터를 가져오고 보관 하면 조직이 정부 및 규정 정책을 준수 하는 데 도움이 될 수 있습니다.

## <a name="overview-of-archiving-bloomberg-message-data"></a>Bloomberg 메시지 데이터 보관 개요

다음 개요에서는 커넥터를 사용 하 여 Bloomberg 메시지 데이터를 Microsoft 365에 보관 하는 프로세스에 대해 설명 합니다.

![Bloomberg 메시지 가져오기 및 보관 프로세스](../media/BloombergMessageArchiving.png)

1. 조직에서 Bloomberg를 사용 하 여 Bloomberg SFTP 사이트를 설정 합니다. 또한 Bloomberg을 사용 하 여 Bloomberg 메시지를 구성 하 여 Bloomberg SFTP 사이트에 전자 메일 메시지를 복사 하는 작업을 수행 합니다.

2. 24 시간 마다 한 번씩 Bloomberg 메시지의 전자 메일 메시지는 Bloomberg SFTP 사이트에 복사 됩니다.

3. Microsoft 365 준수 센터에서 만드는 Bloomberg 메시지 커넥터는 매일 Bloomberg SFTP 사이트에 연결 하 고 이전 24 시간에서 Microsoft 클라우드의 안전한 Azure Storage 영역으로 전자 메일 메시지를 전송 합니다.

4. 커넥터는 전자 메일 메시지 항목을 특정 사용자의 사서함으로 가져옵니다. BloombergMessage 이라는 새 폴더가 특정 사용자의 사서함에 만들어지고이 폴더에 항목을 가져오게 됩니다. 

   커넥터는 CorporateEmailAddress 속성 값을 사용 하 여이를 수행 합니다. 모든 전자 메일 메시지에는 전자 메일 메시지의 모든 참석자의 전자 메일 주소로 채워지는이 속성이 포함 되어 있습니다. *CorporateEmailAddress* 속성 값을 사용 하는 자동 사용자 매핑 외에도 CSV 매핑 파일을 업로드 하 여 사용자 지정 매핑을 정의할 수 있습니다. 이 매핑 파일에는 조직의 각 사용자에 대 한 Bloomberg UUID 및 해당 Microsoft 365 사서함 주소가 포함 되어 있습니다. 자동 사용자 매핑을 사용 하도록 설정 하 고 사용자 지정 매핑을 제공 하는 경우 모든 전자 메일 항목에 대해 커넥터가 사용자 지정 매핑 파일을 먼저 확인 합니다. 사용자의 Bloomberg UUID에 해당 하는 유효한 Microsoft 365 사용자를 찾지 못하면 커넥터는 전자 메일 항목의 *CorporateEmailAddress* 속성을 사용 합니다. 커넥터가 사용자 지정 매핑 파일 또는 전자 메일 항목의 *CorporateEmailAddress* 속성에서 유효한 Microsoft 365 사용자를 찾지 못하면 항목을 가져오지 않습니다.

## <a name="before-you-begin"></a>시작하기 전에

Bloomberg 메시지 데이터를 보관 하는 데 필요한 많은 구현 단계는 Microsoft 365 외부에 있으므로, 준수 센터에서 커넥터를 만들기 전에 완료 해야 합니다.

- 조직에서는 Office 365 가져오기 서비스가 조직의 사서함 데이터에 액세스할 수 있도록 허용 해야 합니다. 이 요청에 동의 하려면 [이 페이지로](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)이동 하 여 Office 365 전역 관리자의 자격 증명으로 로그인 한 다음 요청을 수락 합니다. 3 단계에서 Bloomberg 메시지 커넥터를 성공적으로 만들기 전에이 단계를 완료 해야 합니다.

- [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA)를 구독 합니다. 이는 Bloomberg Anywhere에 로그인 하 여 설정 하 고 구성 해야 하는 Bloomberg SFTP 사이트에 액세스할 수 있도록 하는 데 필요 합니다.

- Bloomberg SFTP (보안 파일 전송 프로토콜) 사이트를 설정 합니다. Bloomberg을 사용 하 여 SFTP 사이트를 설정한 후에는 Bloomberg 메시지의 데이터가 매일 SFTP 사이트로 업로드 됩니다. 2 단계에서 만든 커넥터가이 SFTP 사이트에 연결 되 고 전자 메일 데이터를 Microsoft 365 사서함으로 전송 합니다. 또한 SFTP는 전송 프로세스 중에 사서함으로 전송 되는 Bloomberg 메시지 데이터를 암호화 합니다.

  Bloomberg SFTP에 대 한 자세한 내용은 *BB-sftp*라고도 합니다.

  - [Bloomberg 지원](https://www.bloomberg.com/professional/support/documentation/)에서 "SFTP 연결 표준" 문서를 참조 하세요.

  - [Bloomberg 고객 지원](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)에 문의 합니다.

   > [!NOTE]
   > 조직에서 인스턴트 Bloomberg 데이터를 보관 하기 위한 커넥터를 이미 배포한 경우에는 다른 SFTP 사이트를 설정할 필요가 없습니다. Bloomberg 메시지 커넥터에 대해 동일한 SFTP 사이트를 사용할 수 있습니다.

- Bloomberg을 사용 하 여 SFTP 사이트를 설정한 후 Bloomberg에서는 Bloomberg 구현 전자 메일 메시지에 응답 한 후 몇 가지 정보를 제공 합니다. 다음 정보의 복사본을 저장 합니다. 이 도구를 사용 하 여 3 단계에서 커넥터를 설정 합니다.

  - 기업 코드-조직의 ID 이며 Bloomberg SFTP 사이트에 로그인 하는 데 사용 됩니다.

  - Bloomberg SFTP 사이트의 암호

  - Bloomberg SFTP 사이트의 URL (예: sftp.bloomberg.com)입니다. 또한 Bloomberg는 커넥터를 설정 하는 데 사용할 수 있는 Bloomberg SFTP 사이트에 해당 하는 IP 주소를 제공할 수도 있습니다.

  - Bloomberg SFTP 사이트의 포트 번호

- 3 단계에서 Bloomberg 메시지 커넥터를 만들고 1 단계에서 공개 키와 IP 주소를 다운로드 하는 사용자에 게 Exchange Online의 사서함 가져오기 내보내기 역할이 할당 되어야 합니다. 이는 Microsoft 365 준수 센터의 **데이터 커넥터** 페이지에서 커넥터를 추가 하는 데 필요 합니다. 기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당 한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "Exchange Online에서 역할 그룹 관리" 문서의 [역할 그룹 만들기](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 또는 [역할 그룹 수정](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 섹션을 참조 하세요.


## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>1 단계: SSH 및 PGP 공개 키 획득

첫 번째 단계는 SSH (Secure Shell) 용 공개 키와 PGP (매우 좋은 개인 정보)의 복사본을 가져오는 것입니다. 2 단계에서 이러한 키를 사용 하 여 3 단계에서 만든 커넥터에서 SFTP 사이트에 연결 하 고 Bloomberg 메시지 전자 메일 데이터를 Microsoft 365 사서함으로 전송 하도록 Bloomberg SFTP 사이트를 구성 합니다. 또한 Bloomberg SFTP 사이트를 구성할 때 사용 하는이 단계에서 IP 주소를 가져옵니다.

1. []으로 이동 하 https://compliance.microsoft.com\ https://compliance.microsoft.com) 고 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.

2. **데이터 커넥터** 페이지의 **Bloomberg 메시지**에서 **보기**를 클릭 합니다.

3. **Bloomberg 메시지** 제품 설명 페이지에서 **커넥터 추가** 를 클릭 합니다.

4. **서비스 약관** 페이지에서 **수락**을 클릭 합니다.

5. 1 단계 아래에 있는 **BLOOMBERG SFTP에 대 한 자격 증명 추가 사이트** 에서 **SSH 키 다운로드**, **PGP 키**다운로드 및 **IP 주소 링크 다운로드** 를 클릭 하 여 각 파일의 복사본을 로컬 컴퓨터에 저장 합니다. 이러한 파일에는 2 단계에서 Bloomberg SFTP 사이트를 구성 하는 데 사용 되는 다음과 같은 항목이 포함 되어 있습니다.

   - SSH 공개 키:이 키는 커넥터가 Bloomberg SFTP 사이트에 연결 될 때 보안 원격 로그인을 사용 하도록 보안 셸 (SSH)을 구성 하는 데 사용 됩니다.

   - PGP 공개 키:이 키는 Bloomberg SFTP 사이트에서 Microsoft 365로 전송 되는 데이터의 암호화를 구성 하는 데 사용 됩니다.

   - IP 주소: Bloomberg SFTP 사이트는 3 단계에서 만든 Bloomberg 메시지 커넥터에서 사용 하는이 IP 주소 로부터의 연결 요청만 수락 하도록 구성 됩니다.

6. **취소** 를 클릭 하 여 마법사를 닫습니다. 3 단계의이 마법사로 돌아와서 커넥터를 만듭니다.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>2 단계: Bloomberg SFTP 사이트 구성

> [!NOTE]
> 앞에서 설명한 것 처럼 조직에서 이전에 Bloomberg SFTP 사이트를 설정 하 여 인스턴트 Bloomberg 데이터를 보관 하는 경우에는 다른 것을 설정할 필요가 없습니다. 3 단계에서 커넥터를 만들 때 동일한 SFTP 사이트를 지정할 수 있습니다.

다음 단계에서는 1 단계에서 가져온 SSH 및 PGP 공개 키와 IP 주소를 사용 하 여 Bloomberg SFTP 사이트에 대 한 SSH 인증 및 PGP 암호화를 구성 합니다. 이렇게 하면 3 단계에서 만든 Bloomberg 메시지 커넥터가 Bloomberg SFTP 사이트에 연결 하 고 Bloomberg 메시지 데이터를 Microsoft 365로 전송 합니다. Bloomberg SFTP 사이트를 설정 하려면 Bloomberg 고객 지원 서비스를 사용 해야 합니다. 지원 [Bloomberg 고객 지원](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) 에 문의 하세요.

> [!IMPORTANT]
> Bloomberg에서는 1 단계에서 다운로드 한 세 개의 파일을 전자 메일 메시지에 첨부 하 고이를 사용 하 여 Bloomberg SFTP 사이트를 설정 하는 경우 해당 문서를 고객 지원 팀으로 전송 하는 것이 좋습니다.

## <a name="step-3-create-a-bloomberg-message-connector"></a>3 단계: Bloomberg 메시지 커넥터 만들기

마지막 단계는 Microsoft 365 준수 센터에서 Bloomberg 메시지 커넥터를 만드는 것입니다. 커넥터는 제공 하는 정보를 사용 하 여 Bloomberg SFTP 사이트에 연결 하 고 전자 메일 메시지를 Microsoft 365의 해당 사용자 사서함 상자로 전송 합니다.

1. 으로 이동 하 여 [https://compliance.microsoft.com](https://compliance.microsoft.com) 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.

2. **데이터 커넥터** 페이지의 **Bloomberg 메시지**에서 **보기**를 클릭 합니다.

3. **Bloomberg 메시지** 제품 설명 페이지에서 **커넥터 추가** 를 클릭 합니다.

4. **서비스 약관** 페이지에서 **수락**을 클릭 합니다.

5. **BLOOMBERG SFTP 사이트에 대 한 자격 증명 추가** 페이지의 3 단계에서 다음 상자에 필요한 정보를 입력 하 고 **다음**을 클릭 합니다.

      - **회사 코드:** Bloomberg SFTP 사이트의 사용자 이름으로 사용 되는 조직의 ID입니다.

      - **암호:** 조직의 Bloomberg SFTP 사이트에 대 한 암호입니다.

      - **SFTP URL:** Bloomberg SFTP 사이트의 URL (예: sftp.bloomberg.com)입니다.

      - **SFTP 포트:** Bloomberg SFTP 사이트의 포트 번호입니다. 커넥터는이 포트를 사용 하 여 SFTP 사이트에 연결 합니다.

6. **사용자 매핑** 페이지에서 자동 사용자 매핑을 사용 하도록 설정 하 고 필요에 따라 사용자 지정 사용자 매핑을 제공 합니다.

7. **다음**을 클릭 하 고 설정을 검토 한 다음 준비를 클릭 하 여 커넥터를 만듭니다.

8. **데이터 커넥터** 페이지로 이동 하 여 새 커넥터에 대 한 가져오기 프로세스의 진행 상황을 확인 합니다.

## <a name="known-issues"></a>알려진 문제

- Microsoft 365로 가져온 Bloomberg 메시지의 스레딩은 지원 되지 않습니다. 사용자에 게 전송 된 개별 메시지는 가져오지만, 스레드 대화에서는 표시 되지 않습니다. Microsoft는 Bloomberg Message data connector의 이후 버전에서 스레딩을 지원 하기 위해 노력 하 고 있습니다.
