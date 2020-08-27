---
title: Android 모바일 데이터를 보관 하는 커넥터 설정
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
ROBOTS: NOINDEX, NOFOLLOW
description: 관리자는 Android 휴대폰에서 SMS, MMS 및 음성 통화를 가져오고 보관 하도록 TeleMessage 커넥터를 설정할 수 있습니다. 이를 통해 Microsoft 365의 타사 데이터 원본에서 데이터를 보관할 수 있으므로 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용 하 여 조직의 타사 데이터를 관리할 수도 있습니다.
ms.openlocfilehash: 0eb8d77abb0c18abead03cb744102e795b7a57b5
ms.sourcegitcommit: b144e8ba1ab0c40fa7e0e8e893b5cb44aa2d8243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47282626"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data-preview"></a>Android 모바일 데이터를 보관 하는 커넥터 설정 (미리 보기)

Microsoft 365 준수 센터의 TeleMessage 커넥터를 사용 하 여 Android 휴대폰에서 SMS, MMS, 음성 통화 및 통화 기록을 가져오고 보관 합니다. 커넥터를 설정 하 고 구성한 후에는 매일 한 번씩 조직의 TeleMessage 계정에 연결 하 고 TeleMessage Android Winrar를 사용 하 여 직원의 모바일 통신을 Microsoft 365의 사서함으로 가져옵니다.

Android 휴대폰의 데이터가 사용자 사서함에 저장 되 면 소송 보존, 콘텐츠 검색 및 Microsoft 365 고정 정책과 같은 Microsoft 365 준수 기능을 Android Winrar 데이터에 적용할 수 있습니다. 예를 들어 콘텐츠 검색을 사용 하 여 Android Winrar 모바일 통신을 검색 하거나, 고급 eDiscovery 사례의 custodian에 Android Winrar connector 데이터를 포함 하는 사서함을 연결할 수 있습니다. Android Winrar 커넥터를 사용 하 여 Microsoft 365에서 데이터를 가져오고 보관 하면 조직이 정부 및 규정 정책을 준수 하는 데 도움이 될 수 있습니다.

## <a name="overview-of-archiving-android-mobile-data"></a>보관 Android 모바일 데이터의 개요

다음 개요에서는 커넥터를 사용 하 여 Microsoft 365에서 Android 모바일 데이터를 보관 하는 프로세스에 대해 설명 합니다.

![Android Winrar 커넥터 워크플로](../media/AndroidArchiverConnectorWorkflow.png)

1. 조직에서 TeleMessage를 사용 하 여 Android Winrar 커넥터를 설정 합니다. 자세한 내용은 [Android winrar](https://www.telemessage.com/office365-activation-for-android-archiver/)를 참조 하세요.

2. 조직의 Android 휴대폰의 24 시간, SMS, MMS, 음성 통화 및 통화 로그가 모두 TeleMessage 사이트에 복사 됩니다.

3. Microsoft 365 준수 센터에서 만드는 Android Winrar 커넥터는 매일 TeleMessage 사이트에 연결 하 고, 이전 24 시간에서 Microsoft 클라우드의 안전한 Azure Storage 위치로 Android 데이터를 전송 합니다. 또한이 커넥터는 Android 데이터를 전자 메일 메시지 형식으로 변환 합니다.

4. 커넥터는 모바일 통신 항목을 특정 사용자의 사서함으로 가져옵니다. Android Winrar 라는 새 폴더가 특정 사용자의 사서함에 만들어지고이 폴더에 항목을 가져오게 됩니다. 커넥터는 *사용자의 전자 메일 주소* 속성 값을 사용 하 여 매핑합니다. 모든 전자 메일 메시지에는 전자 메일 메시지의 모든 참석자의 전자 메일 주소로 채워지는이 속성이 포함 되어 있습니다. *사용자의 전자 메일 주소* 속성 값을 사용 하는 자동 사용자 매핑 외에도 CSV 매핑 파일을 업로드 하 여 사용자 지정 매핑을 정의할 수 있습니다. 이 매핑 파일에는 사용자의 휴대폰 번호와 각 사용자의 해당 Microsoft 365 사서함 주소가 포함 되어 있어야 합니다. 자동 사용자 매핑을 사용 하도록 설정 하 고 사용자 지정 매핑을 제공 하는 경우 커넥터는 모든 전자 메일 항목에 대해 사용자 지정 매핑 파일을 먼저 확인 합니다. 사용자 휴대폰 번호에 해당 하는 유효한 Microsoft 365 사용자가 없으면 커넥터는 전자 메일 항목의 사용자 전자 메일 주소 속성을 사용 합니다. 커넥터가 사용자 지정 매핑 파일 또는 전자 메일 항목의 *사용자 전자 메일 주소* 속성에서 유효한 Microsoft 365 사용자를 찾지 못하면 항목을 가져오지 않습니다.

## <a name="before-you-begin"></a>시작하기 전에

Android 통신 데이터를 보관 하는 데 필요한 여러 구현 단계는 Microsoft 365 외부에 있으므로, 준수 센터에서 커넥터를 만들기 전에 완료 해야 합니다.

- [TeleMessage에서 Android winrar 서비스](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) 를 주문 하 고 조직의 유효한 관리 계정을 가져옵니다. 커넥터를 만들 때이 계정에 로그인 해야 합니다.

- TeleMessage 계정에 Android Winrar 서비스가 필요한 모든 사용자를 등록 합니다. 사용자를 등록할 때 Microsoft 365 계정에 사용 되는 것과 동일한 전자 메일 주소를 사용 해야 합니다.

- 직원의 휴대폰에 TeleMessage Android Winrar 앱을 설치 하 고 정품 인증 합니다.

- 조직에서는 Office 365 가져오기 서비스가 조직의 사서함 데이터에 액세스할 수 있도록 허용 해야 합니다. 커넥터를 만들 때이 동의를 제공 해야 합니다. 이 요청에 동의 하려면 [이 페이지로](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)이동 하 여 Office 365 전역 관리자의 자격 증명으로 로그인 한 다음 요청을 수락 합니다. &T 네트워크 커넥터에 성공적으로 만들기 전에이 단계를 완료 해야 합니다.

- Android Winrar 커넥터를 만드는 사용자에 게 Exchange Online의 사서함 가져오기 내보내기 역할이 할당 되어야 합니다. 이는 Microsoft 365 준수 센터의 **데이터 커넥터** 페이지에서 커넥터를 추가 하는 데 필요 합니다. 기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당 한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "Exchange Online에서 역할 그룹 관리" 문서의 [역할 그룹 만들기](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 또는 [역할 그룹 수정](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 섹션을 참조 하세요.

## <a name="create-an-android-archiver-connector"></a>Android Winrar 커넥터 만들기

마지막 단계는 Microsoft 365 준수 센터에 Android Winrar 커넥터를 만드는 것입니다. 커넥터는 제공 하는 정보를 사용 하 여 TeleMessage 사이트에 연결 하 고 Android 통신을 Microsoft 365의 해당 사용자 사서함 상자로 전송 합니다.

1. 으로 이동 하 여 [https://compliance.microsoft.com](https://compliance.microsoft.com) **데이터 커넥터**  >  **Android winrar**를 클릭 합니다.

2. **Android winrar** 제품 설명 페이지에서 **커넥터 추가**를 클릭 합니다.

3. **서비스 약관** 페이지에서 **수락**을 클릭 합니다.

4. **TeleMessage 로그인** 페이지의 3 단계에서 다음 상자에 필요한 정보를 입력 하 고 **다음**을 클릭 합니다.

   - **사용자 이름:** 사용자의 TeleMessage 사용자 이름입니다.

   - **암호:** TeleMessage 암호

5. 커넥터를 만든 후 팝업 창을 닫고 **다음**을 클릭 합니다.

6. **사용자 매핑** 페이지에서 자동 사용자 매핑을 사용 하도록 설정 하 고 **다음**을 클릭 합니다. 사용자 지정 매핑이 필요한 경우 CSV 파일을 업로드 하 고 **다음**을 클릭 합니다.

7. 관리자 동의를 제공 하 고 **Next (다음**)를 클릭 합니다.

   관리자의 동의를 제공 하려면 Office 365 전역 관리자의 자격 증명을 사용 하 여 로그인 한 다음 승인 요청을 수락 해야 합니다. 전역 관리자로 로그인 하지 않은 경우 [이 페이지로](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) 이동한 후 전역 관리자 자격 증명을 사용 하 여 요청을 수락할 수 있습니다.

8. 설정을 검토 하 고 **마침을** 클릭 하 여 커넥터를 만듭니다.

9. **데이터 커넥터** 페이지의 커넥터 탭으로 이동 하 여 새 커넥터에 대 한 가져오기 프로세스 진행 상황을 확인 합니다.

## <a name="known-issues"></a>알려진 문제

- 커넥터가 10mb 보다 큰 항목은 가져오지 않습니다.
