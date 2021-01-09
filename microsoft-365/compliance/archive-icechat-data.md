---
title: ICE 채팅 데이터를 보관할 커넥터 설정
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
description: 관리자는 ICE 채팅 도구에서 Microsoft 365로 데이터를 가져오고 보관하는 커넥터를 설정할 수 있습니다. 이를 통해 Microsoft 365의 타사 데이터 원본에서 데이터를 보관할 수 있으므로 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 조직의 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 79a18017ce7aa3c646fa6c7230bde4b001ddc4c8
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790172"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a>ICE 채팅 데이터를 보관할 커넥터 설정

Microsoft 365 규정 준수 센터의 기본 커넥터를 사용하여 ICE 채팅 공동 작업 도구에서 재무 서비스 채팅 데이터를 가져오고 보관합니다. 커넥터를 설정하고 구성한 후 커넥터는 매일 한 번씩 조직의 ICE Chat SFTP(Secure FTP) 사이트에 연결하고 채팅 메시지의 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 Microsoft 365의 사서함으로 해당 항목을 가져올 수 있습니다.

ICE 채팅 데이터를 사용자 사서함에 저장한 후 소송 보존, eDiscovery, 보관, 감사, 통신 준수 및 Microsoft 365 보존 정책과 같은 Microsoft 365 규정 준수 기능을 ICE 채팅 데이터에 적용할 수 있습니다. 예를 들어 콘텐츠 검색을 사용하여 ICE 채팅 메시지를 검색하거나 ICE 채팅 데이터가 포함된 사서함을 고급 eDiscovery 사례의 보호자와 연결할 수 있습니다. ICE 채팅 커넥터를 사용하여 Microsoft 365에서 데이터를 가져오고 보관하면 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.

## <a name="overview-of-archiving-ice-chat-data"></a>ICE 채팅 데이터 보관 개요

다음 개요에서는 커넥터를 사용하여 Microsoft 365에서 ICE 채팅 데이터를 보관하는 프로세스에 대해 설명합니다.

![ICE 채팅 보관 워크플로](../media/ICEChatConnectorWorkflow.png)

1. 조직은 ICE 채팅과 함께 ICE Chat SFTP 사이트를 설정합니다. ICE Chat과 함께 채팅 메시지를 ICE Chat SFTP 사이트로 복사하도록 ICE 채팅을 구성할 수도 있습니다.

2. 24시간마다 ICE Chat의 채팅 메시지가 ICE Chat SFTP 사이트에 복사됩니다.

3. Microsoft 365 규정 준수 센터에서 만든 ICE 채팅 커넥터는 매일 ICE Chat SFTP 사이트에 연결하고 지난 24시간의 채팅 메시지를 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다. 또한 커넥터는 채팅 내용을 전자 메일 메시지 형식으로 변환합니다.

4. 커넥터는 채팅 메시지 항목을 특정 사용자의 사서함으로 가져올 수 있습니다. 사용자 사서함에 **ICE Chat이라는** 새 폴더가 만들어지며 채팅 메시지 항목을 해당 폴더로 가져올 수 있습니다. 이 커넥터는 *SenderEmail* 및 *RecipientEmail* 속성 값을 사용하여 실행합니다. 모든 채팅 메시지에는 보낸 사람 및 채팅 메시지의 모든 받는 사람/참가자의 전자 메일 주소로 채워지는 이러한 속성이 포함되어 있습니다.

   *SenderEmail* 및 *RecipientEmail* 속성의 값을 사용하는 자동 사용자 매핑(커넥터가 채팅 메시지를 보낸 사람의 사서함 및 모든 받는 사람의 사서함으로 가져오기)뿐만 아니라 CSV 매핑 파일을 업로드하여 사용자 지정 사용자 매핑을 정의할 수도 있습니다. 이 매핑 파일에는 조직의 모든 사용자에 대한 ICE Chat *ImId* 및 해당 Microsoft 365 사서함 주소가 포함되어 있습니다. 자동 사용자 매핑을 사용하도록 설정하고 사용자 지정 매핑 파일을 제공하는 경우 커넥터가 모든 채팅 항목에 대해 먼저 사용자 지정 매핑 파일을 살펴 봐야 합니다. 사용자의 ICE Chat ImId에 해당하는 유효한 Microsoft 365 사용자 계정을 찾을 수 없는 경우 커넥터는 채팅 항목의 *SenderEmail* 및 *RecipientEmail* 속성을 사용하여 항목을 채팅 참가자의 사서함으로 가져올 수 있습니다. 커넥터가 사용자 지정 매핑 파일 또는 *SenderEmail* 및 *RecipientEmail* 속성에서 유효한 Microsoft 365 사용자를 찾지 못하면 항목을 가져오지 않습니다.

## <a name="before-you-begin"></a>시작하기 전에

ICE 채팅 데이터를 보관하는 데 필요한 구현 단계 중 일부는 Microsoft 365 외부에 있으며 준수 센터에서 커넥터를 만들기 전에 완료해야 합니다.

- ICE 채팅은 고객에게 외부 규정 준수에 대한 요금을 부과합니다. 조직은 ICE 채팅 영업 그룹에 연락하여 논의하고, 이 계약을 통해 얻을 수 있는 ICE 채팅 데이터 서비스 계약에 서명해야 [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) 합니다. 이 계약은 ICE 채팅과 조직 간에 있으며 Microsoft와 관련이 없습니다. 2단계에서 ICE Chat SFTP 사이트를 설정한 후 ICE Chat은 FTP 자격 증명을 조직에 직접 제공합니다. 그런 다음 3단계에서 커넥터를 설정할 때 해당 자격 증명을 Microsoft에 제공할 수 있습니다.

- 3단계에서 커넥터를 만들기 전에 ICE Chat SFTP 사이트를 설정해야 합니다. ICE Chat을 사용하여 SFTP 사이트를 설정한 후 ICE 채팅의 데이터는 매일 SFTP 사이트에 업로드됩니다. 3단계에서 만든 커넥터는 이 SFTP 사이트에 연결하고 채팅 데이터를 Microsoft 365 사서함으로 전송합니다. 또한 SFTP는 전송 프로세스 중에 사서함으로 전송되는 ICE 채팅 데이터를 암호화합니다.

- ICE 채팅 커넥터는 하루 총 200,000개 항목을 가져올 수 있습니다. SFTP 사이트에 200,000개가 넘는 항목이 있는 경우 해당 항목을 Microsoft 365로 가져오지 않습니다.

- 3단계에서 ICE 채팅 커넥터를 만들고 1단계에서 공개 키와 IP 주소를 다운로드하는 관리자에게는 Exchange Online에서 사서함 가져오기 내보내기 역할이 할당되어야 합니다. 이 역할은 Microsoft 365 규정 준수 센터의 데이터 커넥터 페이지에서 커넥터를 추가하는 데 필요합니다.  기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "Exchange [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하십시오.

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>1단계: SSH 및 PGP 공개 키 얻기

첫 번째 단계는 SSH(보안 셸) 및 PGP(Pretty Good Privacy)에 대한 공개 키의 복사본을 얻는 것입니다. 2단계의 이러한 키를 사용하여 커넥터(3단계에서 만든 커넥터)가 SFTP 사이트에 연결하고 ICE 채팅 데이터를 Microsoft 365 사서함으로 전송할 수 있도록 ICE Chat SFTP 사이트를 구성합니다. 이 단계에서는 ICE Chat SFTP 사이트를 구성할 때 사용하는 IP 주소도 얻게 됩니다.

1. Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.

2. ICE **채팅 아래의 데이터** 커넥터 **페이지에서** 보기를 **클릭합니다.**

3. ICE **채팅 페이지에서** 커넥터 **추가를 클릭합니다.**

4. 서비스 약관 **페이지에서** 수락을 **클릭합니다.**

5. 1단계 아래의 **ICE Chat SFTP** 사이트 자격 증명 추가 페이지에서 **SSH** 키 다운로드, **PGP** 키 다운로드 및 **IP** 주소 링크 다운로드를 클릭하여 각 파일의 복사본을 로컬 컴퓨터에 저장합니다. 이러한 파일에는 2단계에서 ICE Chat SFTP 사이트를 구성하는 데 사용되는 다음 항목이 포함되어 있습니다.

   - SSH 공개 키: 이 키는 커넥터가 ICE Chat SFTP 사이트에 연결할 때 보안 원격 로그인을 사용하도록 보안 SSH를 구성하는 데 사용됩니다.

   - PGP 공개 키: 이 키는 ICE Chat SFTP 사이트에서 Microsoft 365로 전송되는 데이터의 암호화를 구성하는 데 사용됩니다.

   - IP 주소: ICE Chat SFTP 사이트는 3단계에서 만든 ICE 채팅 커넥터에서 사용하는 이 IP 주소의 연결 요청만 수락하도록 구성됩니다.

6. 취소를 **클릭하여** 마법사를 닫습니다. 3단계에서 이 마법사로 돌아와 커넥터를 만들 수 있습니다.

## <a name="step-2-configure-the-ice-chat-sftp-site"></a>2단계: ICE Chat SFTP 사이트 구성

다음 단계는 1단계에서 획득한 SSH 및 PGP 공개 키와 IP 주소를 사용하여 ICE Chat SFTP 사이트에 대해 SSH 인증 및 PGP 암호화를 구성하는 것입니다. 이렇게 하면 3단계에서 만든 ICE 채팅 커넥터가 ICE Chat SFTP 사이트에 연결하고 ICE 채팅 데이터를 Microsoft 365로 전송할 수 있습니다. ICE Chat SFTP 사이트를 설정하려면 ICE 채팅 고객 지원과 함께 작업해야 합니다.

## <a name="step-3-create-an-ice-chat-connector"></a>3단계: ICE 채팅 커넥터 만들기

마지막 단계는 Microsoft 365 규정 준수 센터에서 ICE 채팅 커넥터를 만드는 것입니다. 커넥터는 사용자가 제공한 정보를 사용하여 ICE Chat SFTP 사이트에 연결하고 채팅 메시지를 Microsoft 365의 해당 사용자 사서함 상자로 전송합니다.

1. Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.

2. ICE **채팅 아래의 데이터** 커넥터 **페이지에서** 보기를 **클릭합니다.**

3. ICE **채팅 페이지에서** 커넥터 **추가를 클릭합니다.**

4. 서비스 약관 **페이지에서** 수락을 **클릭합니다.**

5. ICE **Chat SFTP** 사이트 자격 증명 추가 페이지의 3단계에서 다음 상자에 필요한 정보를 입력한 다음 연결 유효성 검사를 **클릭합니다.**

   - **회사 코드:** 조직의 ID로, ICE Chat SFTP 사이트의 사용자 이름으로 사용됩니다.

   - **암호:** ICE Chat SFTP 사이트의 암호입니다.

   - **SFTP URL:** ICE Chat SFTP 사이트의 URL(예: sftp.theice.com.

   - **SFTP 포트:** ICE Chat SFTP 사이트의 포트 번호입니다. 커넥터는 이 포트를 사용하여 SFTP 사이트에 연결합니다.

6. 연결의 유효성을 검사한 후 다음을 **클릭합니다.**

7. 외부 사용자를 **Microsoft 365** 사용자에 매핑 페이지에서 자동 사용자 매핑을 사용하도록 설정하고 필요한 경우 사용자 지정 사용자 매핑을 제공합니다. 이 페이지에서 사용자 매핑 CSV 파일의 복사본을 다운로드할 수 있습니다. 파일에 사용자 매핑을 추가한 다음 업로드할 수 있습니다.

   > [!NOTE]
   > 앞서 설명한 것 처럼 사용자 지정 매핑 파일 CSV 파일에는 각 사용자에 대한 ICE Chat imid 및 해당 Microsoft 365 사서함 주소가 포함되어 있습니다. 자동 사용자 매핑을 사용하도록 설정하고 사용자 지정 매핑을 제공하는 경우 모든 채팅 항목에 대해 커넥터가 먼저 사용자 지정 매핑 파일을 살펴 니다. 사용자의 ICE Chat imid에 해당하는 유효한 Microsoft 365 사용자를 찾지 못하면 커넥터는 채팅 항목의 *SenderEmail* 및 *RecipientEmail* 속성에 지정된 사용자의 사서함으로 항목을 가져올 수 있습니다. 커넥터가 자동 또는 사용자 지정 사용자 매핑을 통해 유효한 Microsoft 365 사용자를 찾지 못하면 항목을 가져오지 않습니다.

8. 다음을 **클릭하고** 설정을 검토한 다음 **마친을** 클릭하여 커넥터를 생성합니다.

9. 데이터 커넥터  페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인하십시오.
