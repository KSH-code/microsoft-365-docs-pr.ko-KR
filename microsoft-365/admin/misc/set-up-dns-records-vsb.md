---
title: Microsoft 365에 도메인 연결
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365로 도메인을 확인하고 DNS 레코드 만드는 방법을 배웁니다.
ms.custom:
- AdminSurgePortfolio
ms.openlocfilehash: c4282ef4b140fa9e58168ba39c37b4af22b46193
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193844"
---
# <a name="connect-your-domain-to-microsoft-365"></a>Microsoft 365에 도메인 연결

> [!NOTE]
> 도메인을 추가하지 않으면 추가할 때까지 조직의 사용자가 전자 메일 주소로 onmicrosoft.com 도메인을 사용하게 됩니다. 사용자를 두 번 설정하지 않아도 되도록 사용자를 추가하기 전에 도메인을 추가하는 것이 중요합니다.

원하는 정보를 찾지 못한 경우 [도메인 FAQ를 확인](../setup/domains-faq.yml)하세요.

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기

관리 센터 도메인 설정 마법사에서 MX 레코드에 대한 정보를 얻을 수 있습니다.

호스팅 공급자의 웹 사이트에서 새 MX 레코드를 추가합니다.
필드가 다음 값으로 설정되어 있는지 확인합니다.

- 레코드 종류: `MX`
- 우선순위: 사용 가능한 가장 높은 값(일반적으로 `0`)으로 설정됩니다.
- 호스트 이름: `@`
- 대상 주소: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.
- TTL: `3600`(또는 공급자 기본값)

레코드를 저장한 다음 다른 모든 MX 레코드를 제거합니다.

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a>CNAME 레코드를 추가하여 사용자를 사서함에 연결

관리 센터 도메인 설정 마법사에서 CNAME 레코드에 대한 정보를 얻을 수 있습니다.

호스팅 공급자의 웹 사이트에서 다음 CNAME 레코드를 추가합니다. 필드가 각각 다음 값으로 설정되어 있는지 확인합니다.

- 레코드 종류: `CNAME (Alias)`
- 호스트: 여기에 관리 센터에서 복사한 값을 붙여 넣습니다.
- 대상 주소: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.
- TTL: `3600`(또는 공급자 기본값)

## <a name="add-a-txt-record-to-help-prevent-spam"></a>스팸 방지에 유용한 TXT 레코드 추가

**시작하기 전에:** 도메인에 이미 SPF 레코드가 있는 경우 Microsoft 365의 새 SPF 레코드를 만들지 마세요. 대신, 필수 Microsoft 365 값을 호스팅 공급자 웹 사이트의 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 *단일* SPF 레코드가 있도록 합니다.

호스팅 공급자의 웹 사이트에서 기존 SPF 레코드를 편집하거나 SPF 레코드를 만듭니다.
필드가 다음 값으로 설정되어 있는지 확인합니다.

- 레코드 종류: `TXT (Text)`
- 호스트: `@`
- TXT 값: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600`(또는 공급자 기본값)

레코드를 저장합니다.

이러한 [SPF 유효성 검사 도구](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) 중 하나를 사용하여 SPF 레코드의 유효성을 검사합니다.

SPF는 스푸핑 차단을 돕지만 SPF가 방어할 수 없는 스푸핑 기술이 있습니다. 이 같은 기술로부터 보호하려면 SPF를 설정한 후에 Microsoft 365의 DKIM 및 DMARC도 설정해야 합니다.

시작하려면 [DKIM을 사용하여 Microsoft 365의 도메인에서 보낸 발신 전자 메일의 유효성 검사하기](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) 및 [DMARC를 사용하여 Microsoft 365에서 전자 메일의 유효성 검사하기](../../security/office-365-security/use-dmarc-to-validate-email.md)를 참조하세요.

마지막으로 관리 센터 도메인 설정 마법사로 돌아가 설정을 완료합니다.
