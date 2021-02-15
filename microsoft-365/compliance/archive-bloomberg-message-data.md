---
title: Bloomberg 메시지 데이터를 보관할 커넥터 설정
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
description: 관리자는 Bloomberg 메시지 전자 메일 도구에서 Microsoft 365로 데이터를 가져오고 보관하는 데이터 커넥터를 설정할 수 있습니다. 이를 통해 Microsoft 365의 타사 데이터 원본에서 데이터를 보관할 수 있으므로 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 조직의 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: f9b082dace9301f5a664078e9028c646ffa28483
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790118"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a>Bloomberg 메시지 데이터를 보관할 커넥터 설정

Microsoft 365 규정 준수 센터의 데이터 커넥터를 사용하여 Bloomberg 메시지 공동 작업 도구에서 재무 서비스 전자 메일 데이터를 [가져오고 보관합니다.](https://www.bloomberg.com/professional/product/collaboration/) 커넥터를 설정하고 구성한 후 커넥터는 매일 한 번씩 조직의 Bloomberg SFTP(Secure FTP) 사이트에 연결하고 Microsoft 365의 사서함으로 전자 메일 항목을 가져올 수 있습니다.

Bloomberg Message 데이터가 사용자 사서함에 저장되고 나면 소송 보존, 콘텐츠 검색, 원본 위치 보관, 감사, 커뮤니케이션 규정 준수 및 Microsoft 365 보존 정책과 같은 Microsoft 365 규정 준수 기능을 Bloomberg 메시지 데이터에 적용할 수 있습니다. 예를 들어 콘텐츠 검색 도구를 사용하여 Bloomberg Message 전자 메일을 검색하거나 Bloomberg Message 데이터가 포함된 사서함을 고급 eDiscovery 사례의 보호자와 연결할 수 있습니다. Bloomberg Message 커넥터를 사용하여 Microsoft 365에서 데이터를 가져오고 보관하면 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.

## <a name="overview-of-archiving-bloomberg-message-data"></a>Bloomberg 메시지 데이터 보관 개요

다음 개요에서는 커넥터를 사용하여 Microsoft 365에서 Bloomberg 메시지 데이터를 보관하는 프로세스에 대해 설명합니다.

![Bloomberg 메시지 가져오기 및 보관 프로세스](../media/BloombergMessageArchiving.png)

1. 조직은 Bloomberg와 함께 Bloomberg SFTP 사이트를 설정합니다. Bloomberg와 함께 전자 메일 메시지를 Bloomberg SFTP 사이트로 복사하도록 Bloomberg 메시지를 구성할 수도 있습니다.

2. 24시간마다 Bloomberg Message의 전자 메일 메시지가 Bloomberg SFTP 사이트에 복사됩니다.

3. Microsoft 365 규정 준수 센터에서 만든 Bloomberg 메시지 커넥터는 매일 Bloomberg SFTP 사이트에 연결하고 이전 24시간의 전자 메일 메시지를 Microsoft 클라우드의 보안 Azure Storage 영역으로 전송합니다.

4. 커넥터는 전자 메일 메시지 항목을 특정 사용자의 사서함으로 가져올 수 있습니다. BloombergMessage라는 새 폴더가 특정 사용자의 사서함에 만들어지며 이 폴더로 항목이 가져오게 됩니다. 

   이 커넥터는 CorporateEmailAddress 속성 값을 사용하여 이 기능을 실행합니다. 모든 전자 메일 메시지에는 전자 메일 메시지의 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다. *CorporateEmailAddress* 속성 값을 사용하는 자동 사용자 매핑 외에도 CSV 매핑 파일을 업로드하여 사용자 지정 매핑을 정의할 수도 있습니다. 이 매핑 파일에는 Bloomberg UUID와 조직의 각 사용자에 대한 해당 Microsoft 365 사서함 주소가 포함되어 있습니다. 자동 사용자 매핑을 사용하도록 설정하고 사용자 지정 매핑을 제공하는 경우 커넥터가 모든 전자 메일 항목에 대해 먼저 사용자 지정 매핑 파일을 살펴 봐야 합니다. 사용자의 Bloomberg UUID에 해당하는 유효한 Microsoft 365 사용자를 찾지 못하면 커넥터가 전자 메일 항목의 *CorporateEmailAddress* 속성을 사용하게 됩니다. 커넥터가 전자 메일 항목의 사용자 지정 매핑 파일 또는 *CorporateEmailAddress* 속성에서 유효한 Microsoft 365 사용자를 찾지 못하면 항목을 가져오지 않습니다.

## <a name="before-you-begin"></a>시작하기 전에

Bloomberg Message 데이터를 보관하는 데 필요한 구현 단계 중 일부는 Microsoft 365 외부에 있으며 준수 센터에서 커넥터를 만들기 전에 완료해야 합니다.

- [Bloomberg Anywhere를 구독합니다.](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA) 이 정보는 Bloomberg Anywhere에 로그인하여 설정 및 구성해야 하는 Bloomberg SFTP 사이트에 액세스할 수 있도록 하는 데 필요합니다.

- Bloomberg SFTP(보안 파일 전송 프로토콜) 사이트를 설치합니다. Bloomberg와 협력하여 SFTP 사이트를 설정하면 Bloomberg Message의 데이터가 매일 SFTP 사이트에 업로드됩니다. 2단계에서 만든 커넥터는 이 SFTP 사이트에 연결하고 전자 메일 데이터를 Microsoft 365 사서함으로 전송합니다. 또한 SFTP는 전송 프로세스 중에 사서함으로 전송되는 Bloomberg Message 데이터를 암호화합니다.

  Bloomberg *SFTP(BB-SFTP라고도 하는)에* 대한 자세한 내용은

  - Bloomberg 지원에서 "SFTP 연결 표준" [문서를 참조합니다.](https://www.bloomberg.com/professional/support/documentation/)

  - [Bloomberg 고객 지원에 문의합니다.](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

   > [!NOTE]
   > 조직에서 Instant Bloomberg 데이터를 보관하는 커넥터를 이미 배포한 경우 다른 SFTP 사이트를 설정할 필요가 없습니다. Bloomberg 메시지 커넥터에 동일한 SFTP 사이트를 사용할 수 있습니다.

- Bloomberg와 함께 SFTP 사이트를 설정한 후 Bloomberg는 Bloomberg 구현 전자 메일 메시지에 응답한 후 몇 가지 정보를 제공합니다. 다음 정보의 복사본을 저장합니다. 이 커넥터를 사용하여 3단계에서 커넥터를 설정할 수 있습니다.

  - 조직의 ID로, Bloomberg SFTP 사이트에 로그인하는 데 사용되는 회사 코드입니다.

  - Bloomberg SFTP 사이트의 암호

  - Bloomberg SFTP 사이트의 URL(예: sftp.bloomberg.com). 또한 Bloomberg는 Bloomberg SFTP 사이트에 해당하는 IP 주소를 제공할 수도 있습니다. 이 주소는 커넥터를 설정하는 데에도 사용할 수 있습니다.

  - Bloomberg SFTP 사이트의 포트 번호

- Bloomberg Message 커넥터는 하루 총 200,000개 항목을 가져올 수 있습니다. SFTP 사이트에 200,000개가 넘는 항목이 있는 경우 해당 항목을 Microsoft 365로 가져오지 않습니다.

- 3단계에서 Bloomberg Message 커넥터를 만들고 1단계에서 공개 키와 IP 주소를 다운로드하는 사용자에게는 Exchange Online에서 사서함 가져오기 내보내기 역할이 할당되어야 합니다. 이는 Microsoft 365 규정 준수 센터의 **데이터** 커넥터 페이지에서 커넥터를 추가하는 데 필요합니다. 기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "Exchange [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하십시오.

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>1단계: SSH 및 PGP 공개 키 얻기

첫 번째 단계는 SSH(보안 셸) 및 PGP(Pretty Good Privacy)에 대한 공개 키의 복사본을 얻는 것입니다. 2단계의 이러한 키를 사용하여 커넥터(3단계에서 만든 커넥터)가 SFTP 사이트에 연결하고 Bloomberg Message 전자 메일 데이터를 Microsoft 365 사서함으로 전송할 수 있도록 Bloomberg SFTP 사이트를 구성합니다. 이 단계에서는 Bloomberg SFTP 사이트를 구성할 때 사용하는 IP 주소도 얻습니다.

1. [](()로 이동하고 왼쪽 https://compliance.microsoft.com\ https://compliance.microsoft.com) nav에서 데이터 커넥터를 클릭합니다. 

2. Bloomberg **메시지** **아래의 데이터** 커넥터 페이지에서 보기를 **클릭합니다.**

3. **Bloomberg 메시지** 제품 설명 페이지에서 커넥터 **추가를 클릭합니다.**

4. 서비스 약관 **페이지에서** 수락을 **클릭합니다.**

5. 1단계에서 **Bloomberg SFTP** 사이트에 대한 자격 증명 추가에서 **SSH** 키 다운로드, **PGP** 키 다운로드 및 **IP** 주소 링크 다운로드를 클릭하여 각 파일의 복사본을 로컬 컴퓨터에 저장합니다. 이러한 파일에는 2단계에서 Bloomberg SFTP 사이트를 구성하는 데 사용되는 다음 항목이 포함되어 있습니다.

   - SSH 공개 키: 이 키는 커넥터가 Bloomberg SFTP 사이트에 연결할 때 보안 원격 로그인을 사용하도록 SSH(보안 셸)를 구성하는 데 사용됩니다.

   - PGP 공개 키: 이 키는 Bloomberg SFTP 사이트에서 Microsoft 365로 전송되는 데이터의 암호화를 구성하는 데 사용됩니다.

   - IP 주소: Bloomberg SFTP 사이트는 3단계에서 만든 Bloomberg 메시지 커넥터에서 사용하는 이 IP 주소의 연결 요청만 수락하도록 구성됩니다.

6. 취소를 **클릭하여** 마법사를 닫습니다. 3단계에서 이 마법사로 돌아와 커넥터를 만들 수 있습니다.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>2단계: Bloomberg SFTP 사이트 구성

> [!NOTE]
> 앞서 설명한 것 처럼 조직에서 Instant Bloomberg 데이터를 보관하기 위해 Bloomberg SFTP 사이트를 이전에 설정한 경우 다른 사이트를 설정할 수 없습니다. 3단계에서 커넥터를 만들 때 동일한 SFTP 사이트를 지정할 수 있습니다.

다음 단계는 1단계에서 획득한 SSH 및 PGP 공개 키와 IP 주소를 사용하여 Bloomberg SFTP 사이트에 대해 SSH 인증 및 PGP 암호화를 구성하는 것입니다. 이렇게 하면 3단계에서 만든 Bloomberg 메시지 커넥터가 Bloomberg SFTP 사이트에 연결하고 Bloomberg Message 데이터를 Microsoft 365로 전송할 수 있습니다. Bloomberg SFTP 사이트를 설정하려면 Bloomberg 고객 지원과 함께 작업해야 합니다. [Bloomberg 고객 지원에 도움을](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) 요청하세요.

> [!IMPORTANT]
> Bloomberg는 1단계에서 다운로드한 세 개의 파일을 전자 메일 메시지에 첨부하고 고객 지원 팀과 함께 작업하여 Bloomberg SFTP 사이트를 설정할 때 해당 파일을 고객 지원 팀에 보내는 것이 좋습니다.

## <a name="step-3-create-a-bloomberg-message-connector"></a>3단계: Bloomberg 메시지 커넥터 만들기

마지막 단계는 Microsoft 365 규정 준수 센터에서 Bloomberg 메시지 커넥터를 만드는 것입니다. 커넥터는 사용자가 제공한 정보를 사용하여 Bloomberg SFTP 사이트에 연결하고 전자 메일 메시지를 Microsoft 365의 해당 사용자 사서함 상자로 전송합니다.

1. Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.

2. Bloomberg **메시지** **아래의 데이터** 커넥터 페이지에서 보기를 **클릭합니다.**

3. **Bloomberg 메시지** 제품 설명 페이지에서 커넥터 **추가를 클릭합니다.**

4. 서비스 약관 **페이지에서** 수락을 **클릭합니다.**

5. **Bloomberg SFTP** 사이트 자격 증명 추가 페이지의 3단계에서 다음 상자에 필요한 정보를 입력하고 다음을 **클릭합니다.**

      - **회사 코드:** Bloomberg SFTP 사이트의 사용자 이름으로 사용되는 조직의 ID입니다.

      - **암호:** 조직의 Bloomberg SFTP 사이트의 암호입니다.

      - **SFTP URL:** Bloomberg SFTP 사이트의 URL(예: sftp.bloomberg.com.

      - **SFTP 포트:** Bloomberg SFTP 사이트의 포트 번호입니다. 커넥터는 이 포트를 사용하여 SFTP 사이트에 연결합니다.

6. 사용자 매핑 **페이지에서** 자동 사용자 매핑을 사용하도록 설정하고 필요한 경우 사용자 지정 사용자 매핑을 제공합니다.

7. 다음을 **클릭하고** 설정을 검토한 다음 커넥터 만들기 준비를 클릭합니다.

8. 데이터 커넥터 **페이지로** 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인하십시오.

## <a name="known-issues"></a>알려진 문제

- Microsoft 365로 가져온 Bloomberg Message 전자 메일의 스레딩은 지원되지 않습니다. 개인에게 전송된 개별 메시지는 가져오지만 스레드 대화에는 표시되지 않습니다. Microsoft는 이후 버전의 Bloomberg Message 데이터 커넥터에서 스레딩을 지원하기 위해 작업 중입니다.
