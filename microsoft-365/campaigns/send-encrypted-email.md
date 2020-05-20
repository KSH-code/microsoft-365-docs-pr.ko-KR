---
title: 암호화된 전자 메일 보내기
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Outlook을 사용 하 여 암호화 된 전자 메일을 보내는 방법에 대해 알아봅니다.
ms.openlocfilehash: 5318fbe045c909e3b7f81d195a8e6b4d5eb96dc1
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322150"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>중요 한 전자 메일 암호화 또는 레이블 지정

데이터 및 캠페인 정보가 중요 하 고 기밀을 유지 하는 경우가 많습니다. 사용자와 전자 메일 받는 사람이 해당 정보를 필요한 민감도로 취급할 수 있도록 암호화 및 민감도 레이블을 사용 하 여 이러한 중요 한 정보를 보호 합니다.


## <a name="best-practices"></a>모범 사례

기밀 또는 중요 한 정보가 포함 된 전자 메일을 보내기 전에 다음을 수행 하는 것이 좋습니다.

- **암호화:** 전자 메일을 암호화 하 여 전자 메일의 정보에 대 한 개인 정보를 보호할 수 있습니다. 전자 메일 메시지를 암호화 하면 읽을 수 있는 일반 텍스트에서 스크램블 된 cypher 텍스트로 변환 됩니다. 메시지를 암호화 하는 데 사용 되는 공개 키와 일치 하는 개인 키가 있는 받는 사람만 메시지를 읽을 수 있습니다. 그러나 해당 하는 개인 키가 없는 받는 사람은 해독이 되지 않은 텍스트를 보게 됩니다. 관리자는 특정 조건을 충족 하는 메시지를 자동으로 암호화 하는 규칙을 정의할 수 있습니다. 예를 들어 관리자는 조직 외부에서 전송 된 모든 메시지를 암호화 하는 규칙 또는 특정 단어나 구를 언급 하는 모든 메시지를 만들 수 있습니다. 모든 암호화 규칙이 자동으로 적용 됩니다.
- **민감도 레이블:** 또한 캠페인은 사용자가 캠페인의 정보 보호 정책을 준수 하도록 파일 및 전자 메일에 적용할 수 있는 민감도 레이블을 설정할 수도 있습니다. 레이블을 설정 하면 전자 메일 (예: 메시지에 머리글 표시)을 사용 하 여 우편물 레이블을 계속 사용할 수 있습니다.

![레이블 및 암호화에 대 한 설명선이 포함 된 전자 메일 다이어그램](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a>설정하기

미리 정의 된 규칙을 충족 하지 않는 메시지를 암호화 하거나 관리자가 규칙을 설정 하지 않은 경우 메시지를 보내기 전에 다양 한 암호화 규칙을 적용할 수 있습니다. Outlook 2013 또는 2016 또는 Mac 용 Outlook 2016에서 암호화 된 메시지를 보내려면 **> 사용 권한 옵션**을 선택 하 고 필요한 보호 옵션을 선택 합니다. 웹용 Outlook에서 **보호** 단추를 선택 하 여 암호화 된 메시지를 보낼 수도 있습니다. 자세한 내용은 [Outlook FOR PC에서 암호화 된 메시지 보내기, 보기 및 회신을](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)참조 하세요.

## <a name="admin-settings"></a>관리 설정

전자 메일 암호화 설정에 대 한 자세한 내용은 [Office 365의 전자 메일 암호화](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)를 통해 확인할 수 있습니다.

### <a name="automatically-encrypt-email-messages"></a>자동으로 전자 메일 메시지 암호화

관리자는 캠페인에서 보내고 받는 전자 메일 메시지를 자동으로 보호 하는 메일 흐름 규칙을 만들 수 있습니다. 규칙을 설정 하 여 보내는 전자 메일 메시지를 암호화 하 고 조직 내부에서 들어오는 암호화 된 메시지에서 암호화를 제거 하 고 조직에서 보낸 암호화 된 메시지에 대 한 회신을 제거할 수 있습니다. 

메일 흐름 규칙을 만들어 새 Office 365 메시지 암호화 (OME) 기능을 사용 하 여 전자 메일 메시지를 암호화 합니다. EAC (Exchange 관리 센터)를 사용 하 여 새 OME 기능으로 메시지 암호화를 트리거하는 메일 흐름 규칙을 정의 합니다. 

1. 웹 브라우저에서 전역 관리자 권한이 부여 된 회사 또는 학교 계정을 사용 하 여 Office 365에 로그인 합니다. 
2. 관리 타일을 선택 합니다. 
3. 관리 센터에서 **관리 센터 > Exchange**를 선택 합니다. 

자세한 내용은 [Office 365에서 전자 메일 메시지를 암호화 하는 메일 흐름 규칙 정의](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)를 참조 하세요.

### <a name="brand-your-encryption-messages"></a>암호화 메시지 브랜드

캠페인 브랜딩을 적용 하 여 전자 메일 메시지의 모양과 텍스트를 사용자 지정할 수도 있습니다. 자세한 내용은 [암호화 된 메시지에 조직의 브랜드 추가](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)를 참조 하세요.

