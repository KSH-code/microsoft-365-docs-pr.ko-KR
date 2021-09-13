---
title: Instant Bloomberg 데이터를 보관할 커넥터 설정
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
description: 관리자가 데이터 커넥터를 설정하고 사용하여 Instant Bloomberg 채팅 도구에서 데이터 원본으로 데이터를 가져오고 보관하는 Microsoft 365.
ms.openlocfilehash: 98c9cd9077a8c2e11f8d51db983cbfbd0620c6f3
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59188300"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data"></a>Instant Bloomberg 데이터를 보관할 커넥터 설정

인스턴트 블룸버그 공동 작업 Microsoft 365 규정 준수 센터 금융 서비스 채팅 데이터를 가져오고 보관할 수 있는 기본 [커넥터를](https://www.bloomberg.com/professional/product/collaboration/) 사용합니다. 커넥터를 설정하고 구성한 후 커넥터는 매일 조직의 Bloomberg SFTP(Secure FTP 사이트)에 연결하고 채팅 메시지의 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 조직의 사서함으로 Microsoft 365.

Instant Bloomberg 데이터가 사용자 사서함에 저장되고 나면 소송 보존, Microsoft 365 검색, In-Place 보관, 감사, 통신 준수 및 Microsoft 365 보존 정책과 같은 Microsoft 365 준수 기능을 Instant Bloomberg 데이터에 적용할 수 있습니다. 예를 들어 콘텐츠 검색을 사용하여 Instant Bloomberg 채팅 메시지를 검색하거나 Instant Bloomberg 데이터가 포함된 사서함을 특정 사례의 보위원과 Advanced eDiscovery 있습니다. Instant Bloomberg 커넥터를 사용하여 조직의 데이터를 가져오고 보관하는 Microsoft 365 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.

## <a name="overview-of-archiving-instant-bloomberg-data"></a>Instant Bloomberg 데이터 보관 개요

다음 개요에서는 커넥터를 사용하여 Instant Bloomberg 채팅 데이터를 커넥터에 보관하는 Microsoft 365. 

![Instant Bloomberg import and archive process.](../media/InstantBloombergDataArchiving.png)

1. 조직은 Bloomberg와 함께 Bloomberg SFTP 사이트를 설정합니다. Bloomberg와 함께 채팅 메시지를 Bloomberg SFTP 사이트로 복사하도록 Instant Bloomberg를 구성할 수도 있습니다.

2. 24시간마다 Instant Bloomberg의 채팅 메시지가 Bloomberg SFTP 사이트에 복사됩니다.

3. Microsoft 365 규정 준수 센터 만든 Instant Bloomberg 커넥터는 매일 Bloomberg SFTP 사이트에 연결하고 지난 24시간 동안의 채팅 메시지를 Microsoft 클라우드의 보안 Azure Storage 영역으로 전송합니다. 또한 커넥터는 채팅 내용을 전자 메일 메시지 형식으로 변환합니다.

4. 커넥터는 채팅 메시지 항목을 특정 사용자의 사서함으로 가져올 수 있습니다. InstantBloomberg라는 새 폴더가 특정 사용자의 사서함에 만들어지며 항목이 해당 폴더로 가져오기됩니다. 이 커넥터는 *CorporateEmailAddress* 속성 값을 사용하여 이 기능을 실행합니다. 모든 채팅 메시지에는 채팅 메시지의 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다. *CorporateEmailAddress* 속성 값을 사용하는 자동 사용자 매핑 외에도 CSV 매핑 파일을 업로드하여 사용자 지정 매핑을 정의할 수도 있습니다. 이 매핑 파일에는 Bloomberg UUID 및 각 사용자에 대한 Microsoft 365 사서함 주소가 포함되어야 합니다. 자동 사용자 매핑을 사용하도록 설정하고 사용자 지정 매핑을 제공하는 경우 커넥터가 모든 채팅 항목에 대해 먼저 사용자 지정 매핑 파일을 봐야 합니다. 사용자의 Bloomberg UUID에 해당하는 유효한 Microsoft 365 사용자가 없는 경우 커넥터는 채팅 항목의 *CorporateEmailAddress* 속성을 사용됩니다. 커넥터가 사용자 지정 매핑 파일 또는 채팅 항목의 *CorporateEmailAddress* 속성에서 유효한 Microsoft 365 사용자를 찾지 못하면 항목을 가져오지 않습니다.

## <a name="before-you-set-up-a-connector"></a>커넥터를 설정하기 전에

Instant Bloomberg 데이터를 보관하는 데 필요한 일부 구현 단계는 Microsoft 365 외부에 있으며 준수 센터에서 커넥터를 만들기 전에 완료해야 합니다.

- Instant Bloomberg 커넥터를 설정하기 위해 PGP(Pretty Good Privacy) 및 SSH(보안 셸)에 키와 키 암호가 필요합니다. 이러한 키는 Bloomberg SFTP 사이트를 구성하는 데 사용하며, 커넥터가 Bloomberg SFTP 사이트에 연결하여 데이터를 가져오는 데 Microsoft 365. PGP 키는 Bloomberg SFTP 사이트에서 전송된 데이터 암호화를 구성하는 데 Microsoft 365. SSH 키는 커넥터가 Bloomberg SFTP 사이트에 연결할 때 보안 원격 로그인을 사용하도록 보안 셸을 구성하는 데 사용됩니다.

  커넥터를 설정할 때 Microsoft에서 제공하는 공개 키와 키 암호 또는 개인 키와 암호(passphrases)를 사용할 수 있습니다. Microsoft에서 제공하는 공개 키를 사용하는 것이 좋습니다. 그러나 조직에서 개인 키를 사용하여 Bloomberg SFTP 사이트를 이미 구성한 경우 동일한 개인 키를 사용하여 커넥터를 만들 수 있습니다.

- [Bloomberg Anywhere 구독](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). 이 정보는 Bloomberg Anywhere에 로그인하여 설정 및 구성해야 하는 Bloomberg SFTP 사이트에 액세스할 수 있도록 하는 데 필요합니다.

- Bloomberg SFTP(보안 파일 전송 프로토콜) 사이트를 설치합니다. Bloomberg와 협력하여 SFTP 사이트를 설정한 후 Instant Bloomberg의 데이터는 매일 SFTP 사이트에 업로드됩니다. 2단계에서 만든 커넥터는 이 SFTP 사이트에 연결하고 채팅 데이터를 Microsoft 365 전송합니다. 또한 SFTP는 전송 프로세스 중에 사서함으로 전송되는 Instant Bloomberg 채팅 데이터를 암호화합니다.

  Bloomberg *SFTP(BB-SFTP라고도 불리는)에 대한 자세한 내용은 BB-SFTP를 참조하십시오.*

  - Bloomberg 지원에서 "SFTP 연결 표준" [문서를 참조합니다.](https://www.bloomberg.com/professional/support/documentation/)

  - [Bloomberg 고객 지원에 문의합니다.](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

  Bloomberg와 함께 SFTP 사이트를 설정한 후 Bloomberg는 Bloomberg 구현 전자 메일 메시지에 응답한 후 몇 가지 정보를 제공합니다. 다음 정보의 복사본을 저장합니다. 이 커넥터를 사용하여 3단계에서 커넥터를 설정할 수 있습니다.

  - 조직의 ID로 Bloomberg SFTP 사이트에 로그인하는 데 사용되는 회사 코드입니다.

  - Bloomberg SFTP 사이트의 암호

  - Bloomberg SFTP 사이트의 URL(예: sftp.bloomberg.com)

  - Bloomberg SFTP 사이트의 포트 번호

- Instant Bloomberg 커넥터는 하루 총 200,000개 항목을 가져올 수 있습니다. SFTP 사이트에 200,000개가 넘는 항목이 있는 경우 해당 항목을 가져오지 Microsoft 365.

- 3단계에서 Instant Bloomberg 커넥터를 만들고 1단계에서 공개 키 및 IP 주소를 다운로드하는 사용자에게는 3단계에서 사서함 가져오기 내보내기 역할이 할당되어야 Exchange Online. 이 연결은 서버의 데이터  커넥터 페이지에서 커넥터를 추가하는 Microsoft 365 규정 준수 센터. 기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. 사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.

## <a name="set-up-a-connector-using-public-keys"></a>공개 키를 사용하여 커넥터 설정

이 섹션의 단계에서는 PGP(Pretty Good Privacy) 및 SSH(보안 셸)에 대한 공개 키를 사용하여 Instant Bloomberg 커넥터를 설정하는 방법을 설명합니다.

### <a name="step-1-obtain-pgp-and-ssh-and-public-keys"></a>1단계: PGP 및 SSH 및 공개 키 얻기

첫 번째 단계는 PGP(Pretty Good Privacy) 및 SSH(보안 셸)에 대한 공개 키의 복사본을 얻는 것입니다. 2단계에서 이러한 키를 사용하여 Bloomberg SFTP 사이트를 구성하여 커넥터(3단계에서 만든 커넥터)가 SFTP 사이트에 연결하고 Instant Bloomberg 채팅 데이터를 Microsoft 365 사서함에 전송합니다. 이 단계에서는 Bloomberg SFTP 사이트를 구성할 때 사용하는 IP 주소도 얻게 됩니다.

1. 으로 <https://compliance.microsoft.com> 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.

2. Instant  **Bloomberg의** 데이터 커넥터 페이지에서 보기를 **클릭합니다.**

3. Instant **Bloomberg** 제품 설명 페이지에서 커넥터 **추가를 클릭합니다.**

4. 서비스 **약관 페이지에서** 동의를 **클릭합니다.**

5. 콘텐츠 **원본에 대한** 자격 증명 추가 페이지에서 Microsoft에서 제공하는 PGP 및 SSH 공개 키를 **사용하려는 경우를 클릭합니다.**

   ![공개 키를 사용하는 옵션을 선택합니다.](../media/InstantBloombergPublicKeysOption.png)

6. 1단계에서 **SSH** 키 다운로드, **PGP** 키 다운로드 및 **IP** 주소 링크 다운로드를 클릭하여 각 파일의 복사본을 로컬 컴퓨터에 저장합니다.

   ![공개 키 및 IP 주소를 다운로드하는 링크입니다.](../media/InstantBloombergPublicKeyDownloadLinks.png)

   이러한 파일에는 2단계에서 Bloomberg SFTP 사이트를 구성하는 데 사용되는 다음 항목이 포함되어 있습니다.

   - PGP 공개 키: 이 키는 Bloomberg SFTP 사이트에서 전송된 데이터 암호화를 구성하는 데 Microsoft 365.

   - SSH 공개 키: 이 키는 커넥터가 Bloomberg SFTP 사이트에 연결할 때 보안 원격 로그인을 사용하도록 보안 셸을 구성하는 데 사용됩니다.

   - IP 주소: Bloomberg SFTP 사이트는 이 IP 주소의 연결 요청을 수락하도록 구성됩니다. Instant Bloomberg 커넥터가 SFTP 사이트에 연결하고 Instant Bloomberg 데이터를 전송하는 데 동일한 IP 주소가 Microsoft 365.

7. 취소를 **클릭하여** 마법사를 닫습니다. 3단계에서 이 마법사로 돌아와서 커넥터를 만들 수 있습니다.

### <a name="step-2-configure-the-bloomberg-sftp-site"></a>2단계: Bloomberg SFTP 사이트 구성

다음 단계는 1단계에서 획득한 PGP 및 SSH 공개 키와 IP 주소를 사용하여 Bloomberg SFTP 사이트에 대해 PGP 암호화 및 SSH 인증을 구성하는 것입니다. 이렇게 하면 3단계에서 만든 Instant Bloomberg 커넥터가 Bloomberg SFTP 사이트에 연결하고 Instant Bloomberg 데이터를 해당 사이트에 Microsoft 365. Bloomberg SFTP 사이트를 설정하려면 Bloomberg 고객 지원과 함께 작업해야 합니다. Bloomberg [고객 지원에 도움을](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) 요청하세요. 

> [!IMPORTANT]
> Bloomberg는 1단계에서 다운로드한 세 개의 파일을 전자 메일 메시지에 첨부하고 고객 지원 팀에 보내 Bloomberg SFTP 사이트를 설정하는 것이 좋습니다.

### <a name="step-3-create-an-instant-bloomberg-connector"></a>3단계: Instant Bloomberg 커넥터 만들기

마지막 단계는 2단계에서 Instant Bloomberg 커넥터를 Microsoft 365 규정 준수 센터. 커넥터는 사용자가 제공한 정보를 사용하여 Bloomberg SFTP 사이트에 연결하고 채팅 메시지를 웹 사이트의 해당 사용자 사서함 상자로 Microsoft 365.

1. 으로 <https://compliance.microsoft.com> 이동한 다음 **데이터** 커넥터  >  **Instant Bloomberg를 클릭합니다.**

2. Instant **Bloomberg** 제품 설명 페이지에서 커넥터 **추가를 클릭합니다.**

3. 서비스 **약관 페이지에서** 동의를 **클릭합니다.**

4. **Bloomberg SFTP** 사이트 자격 증명 추가 페이지의 3단계에서 다음 상자에 필요한 정보를 입력하고 다음을 **클릭합니다.**

    - **회사 코드:** Bloomberg SFTP 사이트의 사용자 이름으로 사용되는 조직의 ID입니다.

    - **암호:** Bloomberg SFTP 사이트의 암호입니다.

    - **SFTP URL:** Bloomberg SFTP 사이트의 URL(예: `sftp.bloomberg.com` ). 이 값에 IP 주소를 사용할 수도 있습니다.

    - **SFTP 포트:** Bloomberg SFTP 사이트의 포트 번호입니다. 커넥터는 이 포트를 사용하여 SFTP 사이트에 연결합니다.

5. 가져올 **데이터 형식 선택** 페이지에서 메시지와 별도로 가져올 필수 데이터 **형식을 선택합니다.**

6. Instant **Bloomberg** 사용자를 사용자 Microsoft 365 매핑 페이지에서 자동 사용자 매핑을 사용하도록 설정하고 필요한 경우 사용자 지정 사용자 매핑을 제공합니다.

   > [!NOTE]
   > 커넥터는 채팅 메시지 항목을 특정 사용자의 사서함으로 가져올 수 있습니다. **InstantBloomberg라는** 새 폴더가 특정 사용자의 사서함에 만들어지며 항목이 해당 폴더로 가져오기됩니다. 이 커넥터는 *CorporateEmailAddress* 속성 값을 사용하여 실행합니다. 모든 채팅 메시지에는 이 속성이 포함되어 있으며 이 속성은 채팅 메시지의 모든 참가자의 전자 메일 주소로 채워됩니다. *CorporateEmailAddress* 속성 값을 사용하는 자동 사용자 매핑 외에도 CSV 매핑 파일을 업로드하여 사용자 지정 매핑을 정의할 수도 있습니다. 매핑 파일에는 Bloomberg UUID 및 각 사용자에 대한 Microsoft 365 사서함 주소가 포함되어야 합니다. 자동 사용자 매핑을 사용하도록 설정하고 사용자 지정 매핑을 제공하는 경우 커넥터가 모든 채팅 항목에 대해 먼저 사용자 지정 매핑 파일을 봐야 합니다. 사용자의 Bloomberg UUID에 해당하는 유효한 Microsoft 365 사용자가 없는 경우 커넥터는 채팅 항목의 *CorporateEmailAddress* 속성을 사용됩니다. 커넥터가 채팅 항목의 *corporateEmailAddress* 속성 또는 사용자 지정 매핑 파일에서 Microsoft 365 사용자를 찾지 못하면 항목을 가져오지 않습니다.

7. **다음을** 클릭하고 설정을 검토한 다음 마친을 클릭하여 커넥터를 생성합니다. 

8. 데이터 커넥터 **페이지로 이동하여** 새 커넥터의 가져오기 프로세스 진행률을 확인하십시오. 커넥터에 대한 정보가 포함된 플라이아웃 페이지를 표시하려면 커넥터를 클릭합니다.

## <a name="set-up-a-connector-using-private-keys"></a>개인 키를 사용하여 커넥터 설정

이 섹션의 단계에서는 PGP 및 SSH 개인 키를 사용하여 Instant Bloomberg 커넥터를 설정하는 방법을 설명합니다. 이 커넥터 설정 옵션은 개인 키를 사용하여 Bloomberg SFTP 사이트를 이미 구성한 조직을 위한 것입니다.

### <a name="step-1-obtain-an-ip-address-to-configure-the-bloomberg-sftp-site"></a>1단계: Bloomberg SFTP 사이트를 구성하기 위해 IP 주소 얻기

> [!NOTE]
> 조직에서 이전에 PGP 및 SSH 개인 키를 사용하여 Bloomberg Message 데이터를 보관하도록 Bloomberg SFTP 사이트를 구성한 경우 다른 메시지를 구성할 수 없습니다. 2단계에서 커넥터를 만들 때 동일한 SFTP 사이트를 지정할 수 있습니다.

조직에서 PGP 및 SSH 개인 키를 사용하여 Bloomberg SFTP 사이트를 설정한 경우 IP 주소를 얻어 Bloomberg 고객 지원에 제공해야 합니다. Bloomberg SFTP 사이트는 이 IP 주소의 연결 요청을 수락하도록 구성해야 합니다. Instant Bloomberg 커넥터가 SFTP 사이트에 연결하고 Instant Bloomberg 데이터를 전송하는 데 동일한 IP 주소가 Microsoft 365.

IP 주소를 구하는 방법:

1. 으로 <https://compliance.microsoft.com> 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.

2. Instant  **Bloomberg의** 데이터 커넥터 페이지에서 보기를 **클릭합니다.**

3. Instant **Bloomberg** 제품 설명 페이지에서 커넥터 **추가를 클릭합니다.**

4. 서비스 **약관 페이지에서** 동의를 **클릭합니다.**

5. 콘텐츠 **원본에 대한** 자격 증명 추가 페이지에서 PGP 및 SSH 개인 키를 사용하려는 **을 클릭합니다.**

6. 1단계에서 IP 주소 다운로드를 클릭하여 **IP** 주소 파일의 복사본을 로컬 컴퓨터에 저장합니다.

   ![IP 주소를 다운로드합니다.](../media/InstantBloombergConnectorIPAddress.png)

7. 취소를 **클릭하여** 마법사를 닫습니다. 2단계에서 이 마법사로 돌아와 커넥터를 만들면 됩니다.

Bloomberg 고객 지원과 함께 이 IP 주소의 연결 요청을 수락하도록 Bloomberg SFTP 사이트를 구성해야 합니다. Bloomberg [고객 지원에 도움을](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) 요청하세요.

### <a name="step-2-create-an-instant-bloomberg-connector"></a>2단계: Instant Bloomberg 커넥터 만들기

Bloomberg SFTP 사이트를 구성한 후 다음 단계는 웹 사이트에서 Instant Bloomberg 커넥터를 Microsoft 365 규정 준수 센터. 커넥터는 사용자가 제공한 정보를 사용하여 Bloomberg SFTP 사이트에 연결하고 전자 메일 메시지를 사용자의 해당 사용자 사서함 상자로 Microsoft 365. 이 단계를 완료하기 위해 Bloomberg SFTP 사이트를 설정하는 데 사용한 동일한 개인 키 및 키 암호의 복사본이 있는지 확인해야 합니다.

1. 으로 <https://compliance.microsoft.com> 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.

2. Instant  **Bloomberg의** 데이터 커넥터 페이지에서 보기를 **클릭합니다.**

3. Instant **Bloomberg** 제품 설명 페이지에서 커넥터 **추가를 클릭합니다.**

4. 서비스 **약관 페이지에서** 동의를 **클릭합니다.**

5. 콘텐츠 **원본에 대한** 자격 증명 추가 페이지에서 PGP 및 SSH 개인 키를 사용하려는 **을 클릭합니다.**

   ![개인 키를 사용하는 옵션을 선택합니다.](../media/InstantBloombergPrivateKeysOption.png)

6. 3단계 아래에서 다음 상자에 필요한 정보를 입력한 다음 연결 유효성 **검사를 클릭합니다.**

      - **이름:** 커넥터의 이름입니다. 조직에서 고유해야 합니다.

      - **회사 코드:** Bloomberg SFTP 사이트의 사용자 이름으로 사용되는 조직의 ID입니다.

      - **암호:** 조직의 Bloomberg SFTP 사이트의 암호입니다.

      - **SFTP URL:** Bloomberg SFTP 사이트의 URL(예: `sftp.bloomberg.com` ). 이 값에 IP 주소를 사용할 수도 있습니다.

      - **SFTP 포트:** Bloomberg SFTP 사이트의 포트 번호입니다. 커넥터는 이 포트를 사용하여 SFTP 사이트에 연결합니다.

      - **PGP 개인 키:** Bloomberg SFTP 사이트의 PGP 개인 키입니다. 키 블록의 시작 및 끝 줄을 포함하여 전체 개인 키 값을 포함해야 합니다.

      - **PGP 키 암호:** PGP 개인 키의 암호입니다.

      - **SSH 개인 키:** Bloomberg SFTP 사이트의 SSH 개인 키입니다. 키 블록의 시작 및 끝 줄을 포함하여 전체 개인 키 값을 포함해야 합니다.

      - **SSH 키 암호:** SSH 개인 키의 암호입니다.

7. 연결의 유효성이 검사된 후 다음 을 **클릭합니다.**

8. Instant **Bloomberg** 사용자를 사용자 Microsoft 365 매핑 페이지에서 자동 사용자 매핑을 사용하도록 설정하고 필요한 경우 사용자 지정 사용자 매핑을 제공합니다.

   > [!NOTE]
   > 커넥터는 채팅 메시지 항목을 특정 사용자의 사서함으로 가져올 수 있습니다. **InstantBloomberg라는** 새 폴더가 특정 사용자의 사서함에 만들어지며 항목이 해당 폴더로 가져오기됩니다. 이 커넥터는 *CorporateEmailAddress* 속성 값을 사용하여 실행합니다. 모든 채팅 메시지에는 이 속성이 포함되어 있으며 이 속성은 채팅 메시지의 모든 참가자의 전자 메일 주소로 채워됩니다. *CorporateEmailAddress* 속성 값을 사용하는 자동 사용자 매핑 외에도 CSV 매핑 파일을 업로드하여 사용자 지정 매핑을 정의할 수도 있습니다. 매핑 파일에는 Bloomberg UUID 및 각 사용자에 대한 Microsoft 365 사서함 주소가 포함되어야 합니다. 자동 사용자 매핑을 사용하도록 설정하고 사용자 지정 매핑을 제공하는 경우 커넥터가 모든 채팅 항목에 대해 먼저 사용자 지정 매핑 파일을 봐야 합니다. 사용자의 Bloomberg UUID에 해당하는 유효한 Microsoft 365 사용자가 없는 경우 커넥터는 채팅 항목의 *CorporateEmailAddress* 속성을 사용됩니다. 커넥터가 채팅 항목의 *corporateEmailAddress* 속성 또는 사용자 지정 매핑 파일에서 Microsoft 365 사용자를 찾지 못하면 항목을 가져오지 않습니다.

9. **다음을** 클릭하고 설정을 검토한 다음 마친을 클릭하여 커넥터를 생성합니다. 

10. 데이터 커넥터 **페이지로 이동하여** 새 커넥터의 가져오기 프로세스 진행률을 확인하십시오. 커넥터에 대한 정보가 포함된 플라이아웃 페이지를 표시하려면 커넥터를 클릭합니다.
