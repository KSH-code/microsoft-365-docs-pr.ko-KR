---
title: 얼음 채팅 데이터를 보관 하는 커넥터 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 관리자는 아이스크림 채팅 도구에서 Microsoft 365로 데이터를 가져오고 보관 하기 위한 커넥터를 설정할 수 있습니다. 이를 통해 Microsoft 365의 타사 데이터 원본에서 데이터를 보관할 수 있으므로 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용 하 여 조직의 타사 데이터를 관리할 수도 있습니다.
ms.openlocfilehash: c4abcc6b3ba8778616e4a9bf72955a6b6c959cd1
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937355"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data-preview"></a>얼음 채팅 데이터를 보관 하는 커넥터 설정 (미리 보기)

Microsoft 365 준수 센터의 네이티브 커넥터를 사용 하 여 ICE Chat 공동 작업 도구에서 금융 서비스 채팅 데이터를 가져오고 보관 합니다. 커넥터를 설정 하 고 구성한 후에는 조직의 ICE (채팅 보안 FTP) 사이트를 매일 한 번씩 연결 하 고 채팅 메시지의 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 Microsoft 365의 사서함으로 가져옵니다.

사용자 사서함에 ICE 채팅 데이터가 저장 된 후에는 소송 보존, eDiscovery, 보관, 감사, 통신 준수 및 Microsoft 365 고정 정책과 같은 Microsoft 365 준수 기능을 ICE 채팅 데이터에 적용할 수 있습니다. 예를 들어 콘텐츠 검색을 사용 하 여 ICE 채팅 메시지를 검색 하거나, 고급 eDiscovery 사례에서 얼음 채팅 데이터를 포함 하는 사서함을 custodian에 연결할 수 있습니다. 아이스크림 채팅 커넥터를 사용 하 여 Microsoft 365에서 데이터를 가져오고 보관 하면 조직이 정부 및 규정 정책을 준수 하는 데 도움이 될 수 있습니다.

## <a name="overview-of-archiving-ice-chat-data"></a>ICE 채팅 데이터 보관 개요

다음 개요에서는 커넥터를 사용 하 여 Microsoft 365에서 ICE 채팅 데이터를 보관 하는 프로세스에 대해 설명 합니다.

![아이스 채팅 보관 워크플로](../media/ICEChatConnectorWorkflow.png)

1. 조직에서 얼음 채팅을 사용 하 여 아이스 채팅 SFTP 사이트를 설정 합니다. 또한 얼음 채팅을 사용 하 여 온 얼음 채팅을 구성 하 여 얼음 채팅 SFTP 사이트로 채팅 메시지를 복사 합니다.

2. 24 시간 마다 한 번씩 얼음 채팅의 채팅 메시지가 ICE Chat SFTP 사이트로 복사 됩니다.

3. Microsoft 365 준수 센터에서 만드는 아이스크림 채팅 커넥터는 매일 ICE 채팅 SFTP 사이트에 연결 하 고 이전 24 시간에서 Microsoft 클라우드의 안전한 Azure Storage 위치로 채팅 메시지를 전송 합니다. 또한이 커넥터는 채팅 massage의 콘텐츠를 전자 메일 메시지 형식으로 변환 합니다.

4. 커넥터는 채팅 메시지 항목을 특정 사용자의 사서함으로 가져옵니다. 그러면 사용자 사서함에 **ICE chat** 라는 새 폴더가 만들어지고 채팅 메시지 항목을 해당 폴더로 가져오게 됩니다. 커넥터는 *SenderEmail* 및 *RecipientEmail* 속성 값을 사용 하 여 수행 합니다. 모든 채팅 메시지에는 보낸 사람의 전자 메일 주소와 채팅 메시지의 모든 받는 사람/참가자가 채워지는 이러한 속성이 포함 되어 있습니다.

   *SenderEmail* 및 *RecipientEmail* 속성의 값을 사용 하는 자동 사용자 매핑 외에, 즉 커넥터가 보낸 사람의 사서함 및 모든 받는 사람의 사서함으로 채팅 메시지를 가져오지만, CSV 매핑 파일을 업로드 하 여 사용자 지정 user mapping을 정의할 수도 있습니다. 이 매핑 파일에는 조직의 모든 사용자에 대 한 ICE 채팅 *Imid* 와 해당 Microsoft 365 사서함 주소가 포함 되어 있습니다. 자동 사용자 매핑을 사용 하도록 설정 하 고 사용자 지정 매핑 파일을 제공 하는 경우 모든 채팅 항목에 대해 커넥터는 먼저 사용자 지정 매핑 파일을 확인 합니다. 사용자의 아이스크림 채팅 ImId에 해당 하는 유효한 Microsoft 365 사용자 계정을 찾지 못하면 커넥터는 채팅 항목의 *SenderEmail* 및 *RecipientEmail* 속성을 사용 하 여 해당 항목을 채팅 참가자의 사서함으로 가져옵니다. 커넥터가 사용자 지정 매핑 파일 또는 *SenderEmail* 및 *RecipientEmail* 속성에서 유효한 Microsoft 365 사용자를 찾지 못하면 항목을 가져오지 않습니다.

## <a name="before-you-begin"></a>시작하기 전에

ICE 채팅 데이터를 보관 하는 데 필요한 여러 구현 단계는 Microsoft 365 외부에 있으므로, 준수 센터에서 커넥터를 만들기 전에 완료 해야 합니다.

- 조직에서는 Office 365 가져오기 서비스가 조직의 사서함 데이터에 액세스할 수 있도록 허용 해야 합니다. 이 요청에 동의 하려면 [이 페이지로](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)이동 하 여 Office 365 전역 관리자의 자격 증명으로 로그인 한 다음 요청을 수락 합니다. 3 단계에서 ICE 채팅 커넥터를 성공적으로 만들기 전에이 단계를 완료 해야 합니다.

- 얼음 채팅 비용 외부 규정 준수에 대 한 요금입니다. 조직에서는 아이스크림 채팅 판매 그룹에 문의 하 여 토론 하 고, 온 ICE Chat data services 계약에 서명 하 고,이에 대 한 정보를 수집 합니다 [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) . 이 계약은 얼음 채팅 및 조직 간의 것 이며 Microsoft와 관련이 없습니다. 2 단계에서 ICE 채팅 SFTP 사이트를 설정한 후에는 아이스크림 채팅에서 FTP 자격 증명을 조직에 직접 제공 합니다. 그런 다음 3 단계에서 커넥터를 설정할 때 이러한 자격 증명을 Microsoft에 제공 합니다.

- 3 단계에서 커넥터를 만들기 전에 ICE Chat SFTP 사이트를 설정 해야 합니다. ICE 채팅을 사용 하 여 SFTP 사이트를 설정한 후에는 아이스크림 채팅에서 데이터를 매일 SFTP 사이트로 업로드 합니다. 3 단계에서 만든 커넥터가이 SFTP 사이트에 연결 되 고 채팅 데이터를 Microsoft 365 사서함으로 전송 합니다. 또한 SFTP는 전송 프로세스 중에 사서함으로 전송 되는 ICE 채팅 데이터를 암호화 합니다.

- 3 단계 및 1 단계에서 공개 키와 IP 주소를 다운로드 하는 관리자에 게 Exchange Online의 사서함 가져오기 내보내기 역할이 할당 되어야 합니다. 이 역할은 Microsoft 365 준수 센터의 **데이터 커넥터** 페이지에 커넥터를 추가 하는 데 필요 합니다. 기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당 한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "Exchange Online에서 역할 그룹 관리" 문서의 [역할 그룹 만들기](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 또는 [역할 그룹 수정](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 섹션을 참조 하세요.

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>1 단계: SSH 및 PGP 공개 키 획득

첫 번째 단계는 SSH (Secure Shell) 용 공개 키와 PGP (매우 좋은 개인 정보)의 복사본을 가져오는 것입니다. 2 단계에서 이러한 키를 사용 하 여 3 단계에서 만든 커넥터에서 SFTP 사이트에 연결 하 고 아이스크림 채팅 데이터를 Microsoft 365 사서함으로 전송 하도록 ICE Chat SFTP 사이트를 구성 합니다. 또한이 단계에서 ICE Chat SFTP 사이트를 구성할 때 사용 하는 IP 주소도 얻을 수 있습니다.

1. 으로 이동 하 여 [https://compliance.microsoft.com](https://compliance.microsoft.com) 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.

2. **데이터 연결선 (미리 보기)** 페이지의 **ICE Chat**에서 **보기**를 클릭 합니다.

3. **ICE 채팅** 페이지에서 **커넥터 추가**를 클릭 합니다.

4. **서비스 약관** 페이지에서 **수락**을 클릭 합니다.

5. 1 단계 아래에 있는 **ICE CHAT SFTP 사이트의 자격 증명 추가** 페이지에서 **다운로드 SSH 키**, **PGP 키 다운로드**및 **IP 주소 링크 다운로드** 를 클릭 하 여 각 파일의 복사본을 로컬 컴퓨터에 저장 합니다. 이러한 파일에는 2 단계에서 ICE Chat SFTP 사이트를 구성 하는 데 사용 되는 다음 항목이 포함 되어 있습니다.

   - SSH 공개 키:이 키는 커넥터가 ICE Chat SFTP 사이트에 연결할 때 보안 원격 로그인을 사용 하도록 보안 SSH를 구성 하는 데 사용 됩니다.

   - PGP 공개 키:이 키는 ICE Chat SFTP 사이트에서 Microsoft 365로 전송 되는 데이터의 암호화를 구성 하는 데 사용 됩니다.

   - IP 주소: ICE Chat SFTP 사이트는 3 단계에서 만든 ICE 채팅 커넥터에서 사용 하는이 IP 주소 로부터의 연결 요청만 수락 하도록 구성 됩니다.

6. **취소** 를 클릭 하 여 마법사를 닫습니다. 3 단계의이 마법사로 돌아와서 커넥터를 만듭니다.

## <a name="step-2-configure-the-ice-chat-sftp-site"></a>2 단계: ICE Chat SFTP 사이트 구성

다음 단계에서는 1 단계에서 가져온 SSH 및 PGP 공개 키와 IP 주소를 사용 하 여 아이스크림 채팅 SFTP 사이트에 대 한 SSH 인증 및 PGP 암호화를 구성 합니다. 이렇게 하면 3 단계에서 만든 얼음 채팅 커넥터가 ICE chat SFTP 사이트에 연결 하 고, ICE 채팅 데이터를 Microsoft 365로 전송 합니다. Ice 채팅 SFTP 사이트를 설정 하려면 ICE Chat customer 지원 서비스를 사용 해야 합니다.

## <a name="step-3-create-an-ice-chat-connector"></a>3 단계: ICE 채팅 커넥터 만들기

마지막 단계는 Microsoft 365 준수 센터에서 ICE 채팅 커넥터를 만드는 것입니다. 커넥터는 사용자가 제공 하는 정보를 사용 하 여 ICE Chat SFTP 사이트에 연결 하 고 채팅 메시지를 Microsoft 365의 해당 사서함 상자로 전송 합니다.

1. 으로 이동 하 여 [https://compliance.microsoft.com](https://compliance.microsoft.com) 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.

2. **데이터 커넥터** 페이지의 **ICE Chat**에서 **보기**를 클릭 합니다.

3. **ICE 채팅** 페이지에서 **커넥터 추가**를 클릭 합니다.

4. **서비스 약관** 페이지에서 **수락**을 클릭 합니다.

5. **ICE CHAT SFTP 사이트에 대 한 자격 증명 추가** 페이지의 3 단계에서 다음 상자에 필요한 정보를 입력 한 다음 **연결 유효성 검사**를 클릭 합니다.

   - **회사 코드:** ICE Chat SFTP 사이트의 사용자 이름으로 사용 되는 조직의 ID입니다.

   - **암호:** ICE Chat SFTP 사이트의 암호입니다.

   - **SFTP URL:** ICE Chat SFTP 사이트의 URL (예: sftp.theice.com)입니다.

   - **SFTP 포트:** ICE Chat SFTP 사이트의 포트 번호입니다. 커넥터는이 포트를 사용 하 여 SFTP 사이트에 연결 합니다.

6. 연결을 확인 한 후에 **다음**을 클릭 합니다.

7. **Microsoft 365 사용자에 게 외부 사용자** 매핑 페이지에서 자동 사용자 매핑을 사용 하도록 설정 하 고 필요에 따라 사용자 지정 사용자 매핑을 제공 합니다. 이 페이지에서는 사용자 매핑 CSV 파일의 복사본을 다운로드할 수 있습니다. 파일에 사용자 매핑을 추가한 다음 업로드할 수 있습니다.

   > [!NOTE]
   > 앞에서 설명한 것 처럼 사용자 지정 매핑 파일 CSV 파일에는 각 사용자에 대 한 ICE 채팅 imid와 해당 Microsoft 365 사서함 주소가 포함 되어 있습니다. 자동 사용자 매핑을 사용 하도록 설정 하 고 사용자 지정 매핑을 제공 하는 경우 모든 채팅 항목에 대해 커넥터는 먼저 사용자 지정 매핑 파일을 확인 합니다. 사용자의 아이스크림 채팅 imid에 해당 하는 유효한 Microsoft 365 사용자를 찾지 못하면 커넥터는 채팅 항목의 *SenderEmail* 및 *RecipientEmail* 속성에 지정 된 사용자의 사서함으로 항목을 가져옵니다. 커넥터가 자동 또는 사용자 지정 사용자 매핑으로 유효한 Microsoft 365 사용자를 찾지 못하면 항목을 가져오지 않습니다.

8. **다음**을 클릭 하 고 설정을 검토 한 다음 **마침을** 클릭 하 여 커넥터를 만듭니다.

9. **데이터 커넥터** 페이지로 이동 하 여 새 커넥터에 대 한 가져오기 프로세스의 진행 상황을 확인 합니다.
