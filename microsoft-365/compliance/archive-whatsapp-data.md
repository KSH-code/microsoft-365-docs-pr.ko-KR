---
title: WhatsApp 데이터를 보관할 커넥터를 Microsoft 365
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
description: 관리자는 TeleMessage 커넥터를 설정하여 WhatsApp 데이터를 가져오고 보관할 수 Microsoft 365. 이를 통해 타사 데이터 원본의 데이터를 보관할 수 Microsoft 365 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 조직의 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 0f4759eeb26190d7fdfc92cbf986efecd017eda5
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054788"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a>WhatsApp 데이터를 보관할 커넥터 설정

메시지의 TeleMessage 커넥터를 사용하여 Microsoft 365 규정 준수 센터, 채팅, 첨부 파일, 파일 및 삭제된 메시지를 가져오고 보관할 수 있습니다. 커넥터를 설정하고 구성한 후 커넥터는 매일 조직의 TeleMessage 계정에 연결하고 TeleMessage WhatsApp 전화 Archiver 또는 TeleMessage WhatsApp Cloud Archiver를 사용하여 직원의 모바일 통신을 Microsoft 365.

WhatsApp 데이터를 사용자 사서함에 저장한 후 소송 보존, Microsoft 365 검색 및 보존 정책과 같은 Microsoft 365 준수 기능을 WhatsApp 데이터에 적용할 수 있습니다. 예를 들어 콘텐츠 검색을 사용하여 WhatsApp 메시지를 검색하거나 WhatsApp 메시지가 포함된 사서함을 특정 사례의 Advanced eDiscovery 있습니다. WhatsApp 커넥터를 사용하여 조직에서 데이터를 가져오고 Microsoft 365 정책을 준수하는 데 도움이 될 수 있습니다.

## <a name="overview-of-archiving-whatsapp-data"></a>WhatsApp 데이터 보관 개요

다음 개요에서는 커넥터를 사용하여 WhatsApp 데이터를 커넥터에 보관하는 Microsoft 365.

![WhatsApp 보관 워크플로](../media/WhatsAppConnectorWorkflow.png)

1. 조직은 TeleMessage와 함께 WhatsApp Archiver 커넥터를 설치합니다. 자세한 내용은 [WhatsApp Archiver를 참조하세요.](https://www.telemessage.com/office365-activation-for-whatsapp-archiver)

2. 실시간으로 조직의 WhatsApp 데이터가 TeleMessage 사이트에 복사됩니다.

3. Microsoft 365 규정 준수 센터 만든 WhatsApp 커넥터는 매일 TeleMessage 사이트에 연결하고 이전 24시간의 WhatsApp 데이터를 Microsoft 클라우드의 보안 Azure Storage 전송합니다. 또한 커넥터는 WhatsApp 데이터를 전자 메일 메시지 형식으로 변환합니다.

4. 커넥터는 WhatsApp 데이터를 특정 사용자의 사서함으로 가져올 수 있습니다. **WhatsApp Archiver라는** 새 폴더가 특정 사용자의 사서함에 만들어지며 해당 폴더로 항목이 가져오기됩니다. 커넥터는 사용자의 전자 메일 주소 속성 값을 사용하여 이 *매핑을* 실행합니다. 모든 WhatsApp 메시지에는 메시지의 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.

   사용자의 전자 메일 주소 속성 값을  사용하는 자동 사용자 매핑 외에도 CSV 매핑 파일을 업로드하여 사용자 지정 매핑을 구현할 수도 있습니다. 이 매핑 파일에는 조직의 사용자에 대한 휴대폰 번호와 Microsoft 365 전자 메일 주소가 포함되어 있습니다. 자동 사용자 매핑과 사용자 지정 매핑을 모두 사용하도록 설정하면 모든 WhatsApp 항목에 대해 커넥터가 먼저 사용자 지정 매핑 파일을 룩합니다. 사용자의 휴대폰 번호에 해당하는 유효한 Microsoft 365 사용자가 없는 경우 커넥터는 가져오려고 하는 항목의 전자 메일 주소 속성에 있는 값을 사용합니다. 커넥터가 WhatsApp 항목의 전자 메일 주소 속성 또는 사용자 지정 매핑 파일에서 Microsoft 365 사용자를 찾지 못하면 항목을 가져오지 않습니다.

## <a name="before-you-set-up-a-connector"></a>커넥터를 설정하기 전에

WhatsApp 통신 데이터를 보관하는 데 필요한 일부 구현 단계는 Microsoft 365 외부에 있으며 준수 센터에서 커넥터를 만들기 전에 완료해야 합니다.

- [TeleMessage에서 WhatsApp Archiver](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) 서비스를 주문하고 조직에 대한 유효한 관리 계정을 얻습니다. 준수 센터에서 커넥터를 만들 때 이 계정에 로그인해야 합니다.

- TeleMessage 계정에 WhatsApp 보관이 필요한 모든 사용자를 등록합니다. 사용자를 등록할 때 사용자 계정과 동일한 전자 메일 주소를 Microsoft 365 합니다.

- TeleMessage [WhatsApp 전화 휴대폰에 보관기](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) 앱을 설치하고 활성화합니다. 또는 직원의 휴대폰에 일반 WhatsApp 또는 WhatsApp Business 앱을 설치하고 TeleMessage 웹 사이트에서 QR 코드를 검사하여 WhatsApp 클라우드 보관 서비스를 활성화할 수 있습니다. 자세한 내용은 [WhatsApp Cloud Archiver를 참조하세요.](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/)

- Verizon 네트워크 커넥터를 만드는 사용자에게 사서함 가져오기 내보내기 역할이 할당되어야 Exchange Online. 이 연결은 서버의 데이터  커넥터 페이지에서 커넥터를 추가하는 Microsoft 365 규정 준수 센터. 기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. 사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.

- 이 데이터 커넥터는 미국 GCC 클라우드의 Microsoft 365 사용할 수 있습니다. 타사 응용 프로그램 및 서비스는 Microsoft 365 인프라 외부에 있는 타사 시스템에서 조직의 고객 데이터를 저장, 전송 및 처리해야 할 수 있으므로 Microsoft 365 및 데이터 보호 약정의 적용을 Microsoft 365 수 있습니다. Microsoft는 타사 응용 프로그램에 연결하는 데 이 제품을 사용하는 것은 해당 타사 응용 프로그램이 FEDRAMP 규격임을 암시하는 표현을 사용하지 않습니다.

## <a name="create-a-whatsapp-archiver-connector"></a>WhatsApp Archiver 커넥터 만들기

이전 섹션에 설명된 선행 작업을 완료한 후 해당 섹션에서 WhatsApp 커넥터를 Microsoft 365 규정 준수 센터. 커넥터는 사용자가 제공한 정보를 사용하여 TeleMessage 사이트에 연결하고 WhatsApp 데이터를 사용자가 입력한 사서함의 해당 사용자 Microsoft 365.

1. 으로 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 이동한 다음 **데이터** 커넥터  >  **WhatsApp Archiver 를 클릭합니다.**

2. **WhatsApp Archiver** 제품 설명 페이지에서 커넥터 **추가를 클릭합니다.**

3. 서비스 **약관 페이지에서** 동의를 **클릭합니다.**

4. **TeleMessage에** 로그인 페이지의 3단계에서 다음 상자에 필요한 정보를 입력하고 다음을 **클릭합니다.**

   - **사용자 이름:** TeleMessage 사용자 이름입니다.

   - **암호:** TeleMessage 암호입니다.

5. 커넥터를 만든 후 팝업 창을 닫고 다음 페이지로 이동하면 됩니다.

6. 사용자 **매핑 페이지에서** 자동 사용자 매핑을 사용하도록 설정하고 다음 을 **클릭합니다.** CSV 파일을 업로드하는 사용자 지정 매핑이 필요한 경우 다음 을 **클릭합니다.**

7. 설정을 검토한 다음 **마친을 클릭하여** 커넥터를 생성합니다.

8. 데이터 커넥터 페이지의 커넥터  탭으로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 볼 수 있습니다.

## <a name="known-issues"></a>알려진 문제

- 현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다. 더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.
